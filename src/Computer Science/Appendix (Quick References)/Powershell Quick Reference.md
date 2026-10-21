---
dg-publish: true
---
PowerShell is a CLI offered by Windows that enables users to navigate their computer without the need for a GUI. This can help save time and resources, especially on machines that lack the necessary power to help run many Windows Explorer tabs at once. Furthermore, certain functionality may be easier via PowerShell. This is a quick reference that contains the essentials of PowerShell. 

# Key Components of PowerShell Commands 

### PowerShell Cmdlets: Verb-Noun Structure
PowerShell commands use a verb-noun syntax. The verb part specifies the action to be performed, and the noun part of the command defines the object on which the action will be performed. Common verbs include:
- `Get`: Retrieves data
- `Set`: Modifies the properties of an object
- `Add`: Adds an item to a collection
- `Stop`: Stops a process or service
- `Start`: Starts a process or service
- `Clear`: Removes all the items from a collection

### PowerShell Aliases: Shortcuts and Legacy Support
Aliases are short names for cmdlets, functions and scripts. Aliases are used for typing efficiency and to support legacy versions. All aliases defined in the current PowerShell session can be shown by entering `Get-Alias`. Below are commonly used aliases: 
- `Ls`: Alias for `Get-ChildItem`. This is commonly used for showing all files and directories within the current folder. 
- `Gci`: Another alias for `Get-ChildItem`
- `Gc`: Alias for `Get-Content`
- `Rm`:  Alias for `Remove-Item`
- `Cd`: Alias for `Set-Location`
- `Cls`: Alias for `Clear-Host`
- `Dir`: Alias for `Get-ChildItem`
---
# Essential PowerShell Commands
One of the basic PowerShell commands to become familiar with is `Get-Help`, which will display information about a cmdlet that the user inquires about. Another useful cmdlet is `Get-Command`, which lists all available built-in commands installed in the user's system. This includes native cmdlets, aliases, functions, scripts, filters, and standard executable applications. 

### `Get-Command Filtering`
The user can target their command searches using specific parameters to filer through PowerShell's vast library. 

Searching for commands containing specific keywords, such as filtering by name or by Wildcard: 
```powershell
Get-Command -Name *process*
```

Filtering by PowerShell Verbs can be done by isolating commands that perform a specific type of actions (like `Get`, `Set`, or `New`). 
```powershell
Get-Command -Verb Get
```

Specific system resources or object categories can be done by filtering by PowerShell Noun: 
```powershell
Get-Command -Noun Service
```

If too much information is shown with more top-level commands, then only the commands included within a specific module package can be requested:
```powershell
Get-Command -Module Microsoft.PowerShell.Management
```

An alternative to displaying specific commands is to filter them by command type, such as aliases or applications: 
```powershell
Get-Command -CommandType Alias
```

>[!info] Remark: Useful Pro-Tips
>**View Command Syntax**: To quickly view a command's parameter sets and structure without looking up full documentation, use the `-Syntax` parameter: 
>```powershell
>Get-Command Get-Process -Syntax
>```
>**Count System Commands:** The total amount of commands currently available in the environment can be be determined by piping output to `Measure-Object`:
>```powershell
>Get-Command | Measure-Object
>```

---
# Directory Navigation
Navigating to a specific documentary on the local machine can be done using `Set-Location`: 
```powershell
Set-Location -Path "C:\Path\to\directory\project"
```
Once the specific directory has been entered into, the contents of the documentary can be shown:
```powershell
Get-ChildItem, dir, ls
```
Alternatively, files and folders in the project directory can be shown:
```powershell
Get-ChildItem "C:\Path\to\directory\project"dir  "C:\Path\to\directory\project"
```
And files as well as folders can be listed in the `project` directory:
```powershell
Get-ChildItem "D:\Office\Project" -file
dir  "D:\Office\Project" -directory
```

### Creating, Copying, and Deleting Files

This command will create the text file `myfile.txt` in the `Project` folder:
```powershell
New-Item -Path "D:\Office \Project\myfile.txt" -ItemType File
```

This command will copy `myfile.txt` from the `Project` folder to the `startup` folder:
```powershell
Copy-Item -Path "D:\Office \Project\myfile.txt" -Destination "D:\Office \Project\startup\myfile.txt"
```

This command will delete `myfile.txt` from the `Project` folder:
```powershell
Remove-Item -Path "D:\Office \Project\myfile.txt"
```

The command below will delete the `Project` folder, including all its contents:
```powershell
Remove-Item -Path "D:\Office \Project" -Recurse
```

### Checking Folder Contents and Searching: `Get-ChildItem`, `Select-String`

This command will list all files with type `.txt`:
```powershell
Get-ChildItem -Path "D:\Office\Project" -Filter "*.txt"
```

The following command will list all hidden files:
```powershell
Get-ChildItem -Path "D:\Office\Project" -Hidden
```

This command will search for string error in the file `Projectlogs.txt`:
```powershell
Select-String -Path "D:\Office\Project\projectlogs.txt" -Pattern "error"
```

---
# Data Handling

### Displaying Content
The information a file holds can be displayed onto the CLI:
```powershell
Get-Content -Path "D:\Office\Project\myfile.txt" # standard way of doing it
Get-Content -Path "D:\Office\Project\myfile.txt" -TotalCount 5 # show first five lines only
```
To avoid cluttering the CLI, the following can be used, which outputs the file information to another file:
```powershell
"Hello, World!" | Out-File -FilePath "D:\Office\Project\myfile.txt "
```

### File Exports
This command will get information on the process **notepad** for the specified parameters and export it to the file **processes.csv**:
```powershell
Get-Process -Name notepad | Select-Object Name, Id, CPU | Export-Csv -Path "D:\Office\Project\Processes.csv" -NoTypeInformation
```

To import a `csv` file, use **Import-Csv.** This command imports the CVS file that was just created into another cmdlet, which iterates through the objects and gets the process by the Id column:
```powershell
Import-Csv -Path "D:\Office\Project\Processes.csv" | ForEach-Object { Get-Process -Id $_.Id }
```

### Data Conversions
The following command will get information about two running processes and convert it into `HTML` format:
```powershell
Get-Process -Name "notepad" , "chrome" | Select-Object Name, Id, CPU | ConvertTo-Html -Property Name, Id, CPU -Title "Process Report" | Out-File "D:\Office\Project\ProcessReport.html"
```
Similarly, the following commands will export the information into JSON format:
```powershell
Get-Process -Name "notepad" , "chrome"  | Select-Object Name, Id, CPU, StartTime| ConvertTo-Json -Depth 2 | Out-File "D:\Office\Project\Processes.json"
```

---
# Custom Aliases
The user can specify their own custom commands that make using PowerShell easier to use. This is done via the `Alias` keyword:
```powershell
New-Alias -Name p -Value Get-Process
```
Multiple commands can be bundled into a single command with the use of `function`: 
```powershell
function ListAndCountFiles {    param (        [string]$directory    )    Get-ChildItem -Path $directory    $fileCount = (Get-ChildItem -Path $directory).Count    Write-Host "Total files in $($directory): $fileCount"}
```
where this sample function can later be used:
```powershell
ListAndCountFiles -directory "C:\Temp"
```



# Rename Files and Folders

### Standard Renaming
Files can be renamed in multiple ways. The main method of doing so is
```powershell
Rename-item -Path "C:\path\to\file.ext" -NewName "new_name.ext" # primary syntax
# use this if the item is read-only or hidden
Rename-Item -Path "report.txt" -NewName "archive.txt" -Force
```
>[!warning]+ Warning: `-NewName` Parameter Syntax
>The `-NewName` parameter must only contain the new name, not the full file path. 

This can also be applied to folders/directories: 
```powershell
Rename-Item -Path "C:\Projects\OldFolder" -NewName "NewFolder"
```

### Bulk Renaming
Multiple Items can be renamed at once using `Get-ChildItem`: 
```powershell
Get-ChildItem *.txt | Rename-Item -NewName { $_.Name -replace "Draft", "Final" }
```
This example replaces the word "Draft" with "Final" in all text files. 

File extensions can also be swapped in bulk: 
```powershell
Get-ChildItem *.log | Rename-Item -NewName { $_.Name -replace '\.log$', '.txt' }
```
This example changes all `.log` items in a folder to `.txt` files. 

---
# Move Items
The **`Move-Item`** cmdlet is the primary tool used to move files, folders, and registry keys from one location to another in PowerShell. It transfers the items completely, deleting them from the source once the relocation is finished.

### Standard Moving
The primary way of moving a file from one directory to another is
```powershell
Move-Item -Path "C:\source\file.txt" -Destination "C:\destination\"
```
This moves the target file from the root directory to a sub-directory `destination`.  This can also be used on a folder and its contents: 
```powershell
Move-Item -Path "C:\SourceFolder" -Destination "D:\TargetFolder"
```
All files of a specific type can be moved using wildcards `*`: 
```Julia
Move-Item -Path "C:\SourceFolder\*.pdf" -Destination "C:\TargetFolder\"
```
Lastly, a file can be moved and renamed simultaneously: 
```powershell
Move-Item -Path "C:\Source\oldname.txt" -Destination "C:\Destination\newname.txt"
```

---

# Removals

### Removing Directories
To delete a folder, along with all its subfolders and files:
```powershell
Remove-Item -Path "C:\path\to\your\folder" -Recurse -Force
```
Additionally, the folder's contents can be wiped without deleting the folder itself: 
```powershell
Remove-Item -Path "C:\path\to\your\folder\*" -Recurse -Force
```

>[!warning]+ Warning: "Folder Not Empty" Bug
>A known issue in PowerShell can sometimes cause `Remove-Item -Recurse` to fail or skip files when deleting deeply nested directories. The most reliable workaround is to pipe the contents directly into the delete command:
>```powershell
>Get-ChildItem -Path "C:\path\to\your\folder" -Recurse | Remove-Item -Force
>```
