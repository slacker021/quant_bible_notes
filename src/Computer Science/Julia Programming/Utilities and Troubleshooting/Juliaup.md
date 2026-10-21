---
dg-publish: true
---
# Julia Version Management and Runtime Orchestration with `Juliaup`
The rapid cadence of minor and patch releases across modern programming ecosystems requires robust tooling for runtime orchestration. *Juliaup* serves as the official cross-platform multiplexer and version manager for the Julia programming language, streamlining the installation, channel tracking, and execution of concurrent toolchains. Unlike traditional manual binary extraction workflows, Juliaup isolates runtime channels, manages system path bindings automatically, and prevents environment drift across projects. This utility enables local environments to maintain exact version reproducibility across stable, release, and long-term support (LTS) builds.

### Installing Juliaup
Juliaup provides platform-native installers across all primary operating system architectures. Modern Windows environments leverage the Windows Package Manager (`winget`) via the Microsoft Store endpoint: 
```powershell
winget install --name Julia --id 9NJNWW8PVKMN -e -s msstore
```

>[!warning]+ Warning: Legacy Path Collisions 
>When migrating to Juliaup from standalone manual binary installations, all historical Julia binary directories must be completely purged from the system `PATH`. Failure to remove existing path bindings causes executable shadowing, preventing the shell from routing `julia` invocations through the Juliaup dispatcher.

---
### Channel Management and Command Reference
Juliaup operates using a channel abstraction model. Channels map either to static semver releases (e.g., `1.10.4`) or rolling release streams (`release`, `lts`, `beta`, `nightly`).

Below are a list of the commands which are used in Juliaup's operations: 

| **Command Syntax**          | **Operation Scope**  | **Lowered System Action**                                                                                    |
| --------------------------- | -------------------- | ------------------------------------------------------------------------------------------------------------ |
| `juliaup status`            | System Diagnostics   | Displays all installed Julia toolchains, active channel subscriptions, and the current global default.       |
| `juliaup list`              | Registry Inspection  | Queries the central Julia version registry for all available rolling channels and historical point releases. |
| `juliaup add <channel>`     | Version Provisioning | Downloads and unpacks the target Julia binary into the local `~/.juliaup` depot.                             |
| `juliaup update [channel]`  | Binary Maintenance   | Updates designated rolling channels (or all channels if omitted) to their latest upstream releases.          |
| `juliaup default <channel>` | Multiplexer Routing  | Rebinds the generic `julia` executable call to route into the specified channel.                             |
| `juliaup remove <channel>`  | Storage Cleanup      | Purges the specified Julia runtime binaries and associated metadata from disk.                               |
| `juliaup self update`       | Host Self-Update     | Updates the Juliaup multiplexer executable and background service daemon.                                    |

---
# Execution and Channel Switching
Juliaup wraps the system loader, allowing explicit invocation of specific runtime versions alongside the standard global default. This is mainly executed via the plus-syntax, which follows a format of `julia +<version>`:
```powershell
# Launch the globally configured default channel
julia

# Explicitly invoke a specific installed channel via the plus-syntax
julia +1.10
julia +lts
julia +nightly
```

>[!example]+ Example: Managing Multiple Environments Across Releases 
>When working across distinct projects requiring varying compiler features, toolchains can be invoked dynamically:
>```Powershell
># Inspect installed runtimes
>juliaup status
>
># add long-term support (LTS) release channel
>juliaup add lts
>
># launch an isolated session under LTS to verify compatibility
>julia +lts -e `println("Active Version: ", VERSION)`
>```

---
# Directory and Project Overrides
To enforce exact computational reproducibility across independent repositories, Juliaup provides directory-level channel overrides. This functions similarly to a per-directory toolchain pin, eliminating the need to pass manual version flags during command-line execution:
```powershell
# Set a sticky directory override for the active working directory to the LTS channel
juliaup override set lts

# Inspect active overrides across the local file system
juliaup override status

# Unlink the directory override, reverting the folder to the global default channel
juliaup override unset
```

>[!info]+ Remark: Environment and Configuration Depot Structure 
>Juliaup maintains runtime binaries within `~/.juliaup/` (or `%LOCALAPPDATA%\Juliaup` on Windows), whereas package registries, project environments, compiled `.ji` artifacts, and system images are stored separately within the primary `~/.julia/` depot. Overriding a Julia version changes the executed binary but preserves access to the global package depot.

