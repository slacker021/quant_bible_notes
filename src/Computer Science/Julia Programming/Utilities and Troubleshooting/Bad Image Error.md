---
dg-publish: true
---
# Precompilation Cache 
If the *precompilation cache*, which is where compiled Julia code is stored as machine code, an interrupted cache or system glitch can corrupt the precompiled code. This usually results in a *Bad Image* Error, which happens when the *system loader* (`ntdll.dll`) attempts to map a *Dynamic Link Library* (`.dll`) into the *memory space* of `julia.exe`, but the file's binary structure violated the *Expected Portable Executable* (PE) specification. 

Julia utilizes a *low-level virtual machine* (LLVM) compiler infrastructure. The system utilizes a dual-layered compilation strategy: 
1. **Caching the Abstract Syntax Tree (AST) & Type Inference:** When a package like  is installed, Julia parses the source code, lowers it into an intermediate representation (IR), runs type inference, and caches this metadata.
2. **Native Code Generation (The `.dll`):** To optimize startup times, Julia serializes this inferred code directly into machine instructions, packaging it into a standard native shared library. 
During the execution of a program that contains [[Chapter 1 - Modules, Packages, and Data Types|packages]] or dependencies, Julia doesn't compile the source code from scratch. Instead, it issues a standard API call to load the precompiled `.dll` file directly into memory. 

A bad image error is usually caused by an invalid or corrupted binary format. The file to be executed exists on the storage unit that Julia is operating in but its internal binary structures (such as headers, export tables, or section alignments) are malformed or incomplete. These tend to stem from three common faults:
1. During the precompilation phase, Julia writes machine code to a temporary file before finalizing it as a `.dll`. If the process is abruptly terminated or the device its operating on loses power while `pkg` is serializing data to disk, the file is left in a truncated state. 
2. Antiviruses on computers may target `.dll` files while Julia's compiler is writing to it. The antivirus can halt Julia, leading to the stream to fail during the compilation. 
3. If the file has many dependencies, an underlying package update or change to its internal state while another package is expecting a strictly structured binary signature can lead to a mismatch. While Julia's caching mechanism is highly sophisticated, unexpected environmental changes can occasionally cause the cached artifact to fall out of structural alignment.

A bad image error can be fixed using two methods: 

### Via the Terminal
Because the corrupted `.dll` is throwing a system-level error, the cleanest approach is to delete the cached directory directly from the file system before opening Julia again. 

###### Method 1: Using the Default Shell
1. Close any running Julia sessions. 
2. Open the shell and execute the following command to completely remove the cached precompilation files for the affected package. 

> [!example]+ Windows-Specific Example
> The following is a way to execute this on Windows 11 via powershell: 
> ```Powershell
> Remove-Item -Recurse -Force "C:\Users\...\.julia\compiled\v1.1x\PrecompiledPackage"
> ```
> The file has to be removed recursively, and by force, due to it being nested deep within the compilation folder.

###### Method 2: Using GUI-Based File Management
1. Navigate to the directory in the file explorer. 
2. Locate the compiled folder of the package. 
3. Delete this folder entirely. This won't delete the original package's source code. 

Either through method 1 or 2, Julia must be launched again. Julia must be forced to launch a clean precompilation pass to ensure everything matches up structurally: 
```Julia
pkg> precompile()
```

Julia will detect that the precompiled `.dll` for `DataStructures` is missing, re-evaluate its abstract syntax trees, and emit a fresh, uncorrupted dynamic link library tailored to the device its running on. 

>[!warning]+ Administrator Privileges
>Deleting the precompiled file may require administrator privileges. If so, it can only be deleted using a privileged CLI session via method 1. 

# Causes and Prevention
While there are many causes for bad image errors, the most common culprits for Julia are the following: 
- **Stale Precompilation Artifacts:** If the current version of Julia was updated, the package dependencies were updated, or system-level libraries were changed, existing `.jl` files can fail validation. 
- **Interrupted Writes:** Terminating a Julia session while packages are actively precompiling can write partial or corrupted binaries to disk. 
- **Target Architecture Mismatches:** If the environment variable `JULIA_CPU_TARGET` is modified between sessions, object caches generated for one microarchitecture target may be rejected or trigger bad image errors when loaded. 

Once way to temporarily alleviate such issues, which is especially useful when developing packages, is by launching Julia with precompilation toggled off temporarily: 
```Julia
julia --compiled-modules=no
```




