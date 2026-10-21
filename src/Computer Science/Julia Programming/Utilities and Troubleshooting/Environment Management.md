---
dg-publish: true
---
# Creating Environments
While Julia has a default environment, it's possible to create separate environments. This is done by first activating the REPL, whether it be through a dedicated terminal window or the user's text editor's CLI. Once the REPL is activated, the user can activate the package manager `Pkg` by pressing the `]` key on the keyboard. The user can then create a new environment, by entering `activate <new_environment_name>` while using the Pkg mode. 

### Environment Modification
Once the environment has been activated, the user can now manipulate the environment with various commands offered by Julia's built-in package manager. Users can inspect the state of their environment by entering `st` while in `Pkg` mode.

##### Adding and Importing 
The user can install a package onto their environment with the `add` command followed by whatever packages they desire:
```Julia
(@1.1x) pkg> add <package_name> # this is for one package
(@1.1x) pkg> add <package_1> <package_2> ... # this is for multiple packages
```
After a package is added, it can loaded into the live REPL session:
```Julia
julia> import Example
```

##### Removing and Updating Packages
Removing packages can be done using the `rm` command:
```Julia
rm <package_name> # remove one package
rm <package_1> <package_2> ...
```

It's likely that the packages installed are at the latest version so `up` usually doesn't do anything. However, if one or more packages within the environment remain out-of-date with the latest version, this simple command updates them all.

---

# Environment Isolation
Creating an environment sends it to a default directory. However, it's also possible to create an environment outside of the default directory. The former is a global environment that affects multiple environments, which can cause environment conflicts within different projects. 

>[!warning]+ Warning: Dedicated Directory
> Before creating the environment, the user must know what directory they're in. 

The user begins this process of environmental isolation by first creating or going a dedicated directory. Once they're in the dedicated directory, they can initialize it in the Julia REPL:
```Julia
julia> using Pkg
julia> Pkg.activate(".")
```
The `"."` tells Julia to activate the environment currently defined in the working directory. Any commands used in `Pkg` will be scoped specifically to this activated project.

>[!note]+ Convention: Global Environment
> Maintaining a clean environment is a good practice for software development. This is especially true within the default global environment > that presides over every single project the user is working on. The global environment must be free of any dependencies that could lead to > version conflicts in primary projects. This is done by first inspecting the status of the global environment, which is usually what first  > appears when the user begins a new REPL session. Alternatively, the user can find the default environment via a GUI directory explorer. The > global environment is located in `C:\Users\...\.julia\environments\v1.1x`, which can be opened in the REPL using the aforementioned        > instructions. Once the global environment has been opened, the user can scan what's in it using `st`. If there's a package, then the user  > can use `rm` to remove the packages. 
>
> This prevents *configuration drift*, which occurs when the environment of a production server slowly diverges from the development         > environment due to small temporary packages that were added and never removed. This creates a "silent failure" where code works on the     > user's machine but breaks in production because a specific dependency was pulled in implicitly rather than explicitly.

>[!warning]+ Warning: Compiled Binaries
> When running `rm Packagename` in the REPL, Julia does two things: 
>   1. It removes the entry from the current directory's `project.toml` file, which serves as a record of the package. 
>   2. It removes the specific version of that package from the environment's metadata. 
> It's important to note that it doesn't necessarily delete the compiled binaries from the computer's central cache, which is managed by Julia to save the user time from having to re-download them every time.

>[!warning]+ Accessing the Correct Environment
>Whenever the user opens the REPL and switches to Pkg mode, the session always begins with the default environment. To switch to an already-existing environment, the user can switch to the environment of the current directory (if it's already been initialized as an environment) with the same commands used to initialize the current directory as an environment: 
>```Julia
>julia> using Pkg
>julia> Pkg.activate(".")
>```
