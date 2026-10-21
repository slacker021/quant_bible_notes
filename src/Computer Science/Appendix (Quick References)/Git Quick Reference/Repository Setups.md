---
dg-publish: true
---
After creating the *repository* using `git init`, users must set up several global configurations for smoother workflows. While Git allows users to setup their workflows with hundreds of combinations, majority of them are irrelevant and exist merely for niche purposes. Below are the most important setups users must take note of when setting up their git repositories: 

---
# Local Git 

### Minimum
The user may first specify their preferred text editor: 
```powershell
git config --system core.editor editor_name
git config --global core.editor editor_name
git config --local core.editor editor_name
```
Next thing to ensure is that the user's chosen text editor is allowed to wait while a commit message is being written:
```powershell
git config --system core.editor "editor_name --wait" # applied to all users on system
git config --global core.editor "editor_name --wait" # applied to all repositories for the current user
git config --local core.editor "editor_name --wait" # applied to current repo only
```
There's sometimes an error that causes git to abort commits prematurely. Once that's been settled, the step is to set up the identity of the user: 
```powershell
git config --system user.name "name of dev" # applied to all users on system
git config --global user.name "name of dev" # applied to all repositories for the current user
git config --local user.name "name of dev" # applied to current repo only

git config --system user.email "user.email@example.com" # applied to all users on system
git config --global user.email "user.email@example.com" # applied to all repositories for the current user
git config --local user.email "user.email@example.com" # applied to current repo only
```


### Recommended
While the code above is what the user must do to get the setup running, the code below is recommended so as to greatly improve workflow: 
```powershell
git config --global init.defaultBranch master_branch_name # state main branch
```
The user may also dictate the behavior of *line endings*, which vary depending on the user's operating system: 
```powershell
git config --global core.autocrlf true # for Linux or Mac
git config --global core.autocrlf true # for Windows
```

Git configuration settings can be viewed using
```julia
git config --list # list all settings
git config --list --show-origin # show locations of where changes are stored
```
Specific settings may be viewed using lines like
```powershell
git config user.name
git config user.email
git config core.editor
```

### Advanced Configurations
More advanced configurations can be set up using the following: 
```powershell
git config --global color.ui # enable colorful output

# below are some examples of ways to set aliases (abreviations) for common commands:
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st

# configure pull behavior
git config --global pull.rebase true
```

---

# Remote Git
Setting up a remote git repository can be done by first doing to a remote repository hoster, such as *Github*, *Bitbucket*, or *GitLab*. Once there, the user can navigate the GUI to create the empty repository on the server. After the remote repository has been set up, the user can link their local repository to the git repository. This is done by first establishing the remote connection: 
```powershell
git remote add origin https://github.com/OWNER/REPOSITORY.git # for connecting to repository
git remote -v # verify connection
```

Once the connection has been made, the user can then push whatever changes they made in their local repository to the remote: 
```powershell
git push
```

---
# Cloning
An alternative to starting one's own repository is to clone an already-existing repository off the internet. This is first done by first going to the server site hosting the repository and copying the URL or SSH key. Once the URL or SSH key has been copied, the user can then open their CLI and enter the following: 
```powershell
git clone https://github.com/USERNAME/REPOSITORY
```
Note that this option clones all branches from the repository. This can be verified by using `git branch -a` to list all downloaded remote-tracking branches. Should the user decide that they only need one branch, they can specify it:
```powershell
git clone -b <target_branhc> --single-branch <repository_url>
```


