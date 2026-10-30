---
dg-publish: true
---
*PowerShell* is a CLI offered by *Windows* that enables users to navigate their computer without the need for a GUI. This can help save time and resources, especially on machines that lack the necessary power to help run many Windows Explorer tabs at once. Furthermore, certain functionality may be easier via PowerShell. This is a quick reference that contains the essentials of PowerShell. 

---
# Key Components of PowerShell Commands 

### PowerShell Cmdlets: Verb-Noun Structure
PowerShell commands use a verb-noun syntax. The verb part specifies the action to be performed, and the noun part of the command defines the object on which the action will be performed. Common verbs include:
- `Get`: Retrieves data
- `Set`: Modifies the properties of an object
- `Add`: Adds an item to a collection
- `Stop`: Stops a process or service
- `Start`: Starts a process or service
- `Clear`: Removes all the items from a collection

### PowerShell Aliases: Shortcuts and Legacy Support
Aliases are short names for cmdlets, functions, and scripts. Aliases are used for typing efficiency and to support legacy environments. All aliases defined in the current PowerShell session can be displayed by entering `Get-Alias`. Below are commonly used aliases: 
- `ls`: Alias for `Get-ChildItem`. Commonly used for listing files and directories within the current folder. 
- `gci`: Another alias for `Get-ChildItem`
- `gc`: Alias for `Get-Content`
- `rm`: Alias for `Remove-Item`
- `cd`: Alias for `Set-Location`
- `cls`: Alias for `Clear-Host`
- `dir`: Alias for `Get-ChildItem`

---
# Essential PowerShell Commands
One of the basic PowerShell commands to become familiar with is `Get-Help`, which displays documentation about a specified cmdlet. Another essential cmdlet is `Get-Command`, which lists all available commands installed in the system. This includes native cmdlets, aliases, functions, scripts, filters, and standard executable applications. 

### `Get-Command` Filtering
Command discovery can be targeted using specific parameters to filter through PowerShell's library. 

Searching for commands containing specific keywords or wildcard patterns: 
```powershell
Get-Command -Name *process*
```

Filtering by PowerShell verbs isolates commands performing a specific category of action (such as `Get`, `Set`, or `New`):
```powershell
Get-Command -Verb Get
```

Targeting specific system resources or object categories can be performed by filtering by noun:
```powershell
Get-Command -Noun Service
```

Limiting output to commands provided by a specific module package:
```powershell
Get-Command -Module Microsoft.PowerShell.Management
```

Filtering discovered commands by command type, such as aliases or applications:
```powershell
Get-Command -CommandType Alias
```

>[!info]+ Remark: Useful Pro-tips
>**View Command Syntax:** To quickly inspect parameter sets and syntax structure without opening the full help manual, use the `-Syntax` parameter:
>```powershell
>Get-Command Get-Process -Syntax
>```
>**Count System Commands:** The total number of commands currently available in the active session can be determined by piping output to `Measure-Object`:
>```powershell
>Get-Command | Measure-Object
>```

---
# Directory Navigation
Navigating to a specific directory on the local machine is performed using `Set-Location`:
```powershell
Set-Location -Path "C:\Path\to\directory\project"
```

Once the target directory has been entered, the contents of the directory can be listed using `Get-ChildItem` or its standard aliases:
```powershell
Get-ChildItem
dir
ls
```

Alternatively, files and folders in an explicit path can be inspected directly:
```powershell
Get-ChildItem -Path "C:\Path\to\directory\project"
dir "C:\Path\to\directory\project"
```

Filtering for files or directories exclusively:
```powershell
Get-ChildItem -Path "D:\Office\Project" -File
Get-ChildItem -Path "D:\Office\Project" -Directory
```

### Creating, Copying, and Deleting Files

Creating a text file `myfile.txt` in the target folder:
```powershell
New-Item -Path "D:\Office\Project\myfile.txt" -ItemType File
```

Copying `myfile.txt` from the `Project` folder to the `startup` folder:
```powershell
Copy-Item -Path "D:\Office\Project\myfile.txt" -Destination "D:\Office\Project\startup\myfile.txt"
```

Deleting `myfile.txt` from the `Project` folder:
```powershell
Remove-Item -Path "D:\Office\Project\myfile.txt"
```

Deleting the `Project` folder along with all nested contents:
```powershell
Remove-Item -Path "D:\Office\Project" -Recurse
```

# Checking Folder Contents and Searching

Listing all files matching the `.txt` extension:
```powershell
Get-ChildItem -Path "D:\Office\Project" -Filter "*.txt"
```

Listing hidden files within a directory:
```powershell
Get-ChildItem -Path "D:\Office\Project" -Hidden
```

Searching for the string "error" within the file `projectlogs.txt`:
```powershell
Select-String -Path "D:\Office\Project\projectlogs.txt" -Pattern "error"
```

---
# Data Handling

### Displaying Content
The contents of a file can be read and printed directly to standard output:
```powershell
Get-Content -Path "D:\Office\Project\myfile.txt"
Get-Content -Path "D:\Office\Project\myfile.txt" -TotalCount 5 # Display the first five lines only
```

Writing string data or pipeline output into a target file:
```powershell
"Hello, World!" | Out-File -FilePath "D:\Office\Project\myfile.txt"
```

### File Exports
Retrieving process metrics for **notepad** and exporting selected properties to a CSV file:
```powershell
Get-Process -Name notepad | Select-Object Name, Id, CPU | Export-Csv -Path "D:\Office\Project\Processes.csv" -NoTypeInformation
```

Importing and iterating over records from a CSV file:
```powershell
Import-Csv -Path "D:\Office\Project\Processes.csv" | ForEach-Object { Get-Process -Id $_.Id }
```

### Data Conversions
Converting process data to an HTML report and persisting to disk:
```powershell
Get-Process -Name "notepad", "chrome" | Select-Object Name, Id, CPU | ConvertTo-Html -Property Name, Id, CPU -Title "Process Report" | Out-File "D:\Office\Project\ProcessReport.html"
```

Exporting structured process data to JSON format:
```powershell
Get-Process -Name "notepad", "chrome" | Select-Object Name, Id, CPU, StartTime | ConvertTo-Json -Depth 2 | Out-File "D:\Office\Project\Processes.json"
```

---
# Custom Aliases and Functions
Custom shortcuts can be defined during a session using `New-Alias`:
```powershell
New-Alias -Name p -Value Get-Process
```

Multiple operations can be encapsulated into reusable commands via functions:
```powershell
function Get-DirectorySummary {
    param (
        [string]$Directory
    )
    Get-ChildItem -Path $Directory
    $fileCount = (Get-ChildItem -Path $Directory).Count
    Write-Host "Total items in ${Directory}: $fileCount"
}
```

Invoking the custom function: 
```powershell
Get-DirectorySummary -Directory "C:\Temp"
```

---
# Rename Files and Folders

### Standard Renaming
The primary cmdlet for renaming items is `Rename-Item`:
```powershell
Rename-Item -Path "C:\path\to\file.ext" -NewName "new_name.ext"
Rename-Item -Path "report.txt" -NewName "archive.txt" -Force # Overwrite if item is read-only or hidden
```

>[!warning]+ Warning: `-NewName` Parameter Syntax 
>The `-NewName` parameter must contain only the target name, not a fully qualified file path.

Renaming directories follows the identical syntax:
```powershell
Rename-Item -Path "C:\Projects\OldFolder" -NewName "NewFolder"
```

### Bulk Renaming
Multiple items can be renamed dynamically across the pipeline using script blocks:
```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.Name -replace "Draft", "Final" }
```

Replacing file extensions in bulk across a directory:
```powershell
Get-ChildItem *.log | Rename-Item -NewName { $_.Name -replace '\.log$', '.txt' }
```

---
# Move Items
The `Move-Item` cmdlet transfers files, directories, and registry containers between locations, removing them from the source path upon completion.

### Standard Moving
Moving a file into a destination directory:
```powershell
Move-Item -Path "C:\source\file.txt" -Destination "C:\destination\"
```

Moving an entire directory tree to a new location:
```powershell
Move-Item -Path "C:\SourceFolder" -Destination "D:\TargetFolder"
```

Moving all files matching a specific extension using wildcards:
```powershell
Move-Item -Path "C:\SourceFolder\*.pdf" -Destination "C:\TargetFolder\"
```

Moving and renaming an item in a single operation:
```powershell
Move-Item -Path "C:\Source\oldname.txt" -Destination "C:\Destination\newname.txt"
```

---
# Removals

### Removing Directories
Recursively removing a folder along with all child files and subdirectories:
```powershell
Remove-Item -Path "C:\path\to\target\folder" -Recurse -Force
```

Emptying folder contents while leaving the root container intact:
```powershell
Remove-Item -Path "C:\path\to\target\folder\*" -Recurse -Force
```

>[!warning]+ Warning: "Folder Not Empty" Workaround 
>Deeply nested file trees on Windows can occasionally encounter issues with `Remove-Item -Recurse`. Piping child objects directly into the deletion cmdlet provides a reliable bypass:
>```powershell
>Get-ChildItem -Path "C:\path\to\target\folder" -Recurse | Remove-Item -Force
>```
