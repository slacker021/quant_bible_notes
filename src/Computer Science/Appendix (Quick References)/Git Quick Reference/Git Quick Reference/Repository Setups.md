---
dg-publish: true
---
After creating a repository using `git init`, developers establish baseline configurations to standardize commit metadata, editor integration, and line-ending handling across environments. While Git provides hundreds of configuration options, a small subset of core settings ensures operational stability and cross-platform compatibility.

---
# Local Git Configuration

### Minimum Required Settings
Specifying the default text editor for authoring commit messages and resolving interactive rebases:
```powershell
git config --system core.editor "<editor_name>" # Applied system-wide to all users
git config --global core.editor "<editor_name>" # Applied to the active user account
git config --local core.editor "<editor_name>"  # Applied exclusively to the active repository
```

For external GUI editors (such as VS Code or Sublime Text), the `--wait` flag must be passed to prevent Git from completing the commit before the editor window closes:
```powershell
git config --global core.editor "<editor_name> --wait"
```

Configuring author identity metadata attached to every generated commit:
```powershell
# Global configuration (user-level)
git config --global user.name "Developer Name"
git config --global user.email "developer.email@example.com"

# Local repository overrides
git config --local user.name "Developer Name"
git config --local user.email "developer.email@example.com"
```

### Recommended Workflow Settings
Configuring the initial branch name for newly initialized repositories (`git init`):
```powershell
git config --global init.defaultBranch main
```

Standardizing line-ending normalization (`core.autocrlf`) to prevent cross-platform CRLF/LF churn:
```powershell
# Windows (converts LF to CRLF on checkout, CRLF to LF on commit)
git config --global core.autocrlf true

# Linux and macOS (converts CRLF to LF on commit; retains LF on checkout)
git config --global core.autocrlf input
```

Inspecting active configuration values:
```powershell
git config --list              # List all resolved configuration entries
git config --list --show-origin # List entries along with their origin file paths
```

Querying specific configuration keys:
```powershell
git config user.name
git config user.email
git config core.editor
```

### Advanced Configurations and Aliases
Enabling terminal color formatting:
```powershell
git config --global color.ui auto
```

Defining command aliases to streamline frequent command sequences:
```powershell
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.unstage "reset HEAD --"
git config --global alias.last "log -1 HEAD"
```

Enforcing rebase workflows as the default integration behavior for `git pull`:
```powershell
git config --global pull.rebase true
```

---
# Remote Repositories
To synchronize local development with a remote hosting platform (such as GitHub, GitLab, or Bitbucket), create an empty repository on the remote platform and establish the upstream link:
```powershell
git remote add origin https://github.com/<owner>/<repository>.git
git remote -v # Verify configured remote URLs
```

Publishing the active local branch and setting up tracking against the upstream remote:
```powershell
git push -u origin main
```

Subsequent pushes on the tracked branch require only:
```powershell
git push
```

---
# Cloning Existing Repositories
When participating in an existing line of development, copy the repository URL (HTTPS or SSH) and invoke:
```powershell
git clone https://github.com/<owner>/<repository>.git
```

By default, this clones the complete history and creates tracking branches for all remote branches. Inspecting all local and remote branches:
```powershell
git branch -a
```

To optimize storage and transfer times when only a single branch history is required:
```powershell
git clone -b <target_branch> --single-branch https://github.com/<owner>/<repository>.git
```