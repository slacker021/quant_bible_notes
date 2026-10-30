---
dg-publish: true
---
Remote changes are integrated into a local repository using `git pull`. Conceptually, this operation executes a `git fetch` to download upstream objects, followed immediately by an integration step (typically `git merge` or `git rebase`) into the active branch.

---
# Fetching
Fetching is executed via `git fetch`. This is strictly a read-only transport operation that queries the remote repository and downloads new commits, trees, and refs without modifying the active working tree or altering local branch pointers. 

Incoming references are written to remote-tracking branches (such as `origin/main`), updating the local repository's knowledge of the upstream state. Because local branches remain untouched, no merge conflicts can occur during a fetch.

>[!warning]+ Warning: Inspection Prior to Integration
>Fetching prior to merging enables inspection of upstream divergence. By evaluating diffs between `HEAD` and the updated remote-tracking branch (e.g., `git log HEAD..origin/main`), developers can identify structural conflicts before altering local working files.

---
# Pulling
`git pull` combines `git fetch` with an automated history reconciliation step. Depending on project workflow conventions and repository configuration, integration is executed through three standard strategies:

### Fast-Forward Only
Executing `git pull --ff-only` integrates upstream commits only if the active branch has not diverged from the remote tracking branch. If local commits exist that do not exist upstream, Git immediately aborts the operation without generating a merge commit:
```powershell
git pull --ff-only
```
This strategy prevents accidental merge commits and preserves repository topology, prompting manual inspection if histories have diverged.

### Standard Integration (Three-Way Merge)
A standard `git pull` fetches remote references and initiates a merge. If a linear fast-forward is possible, Git advances the branch pointer directly. If histories have diverged, Git creates a dedicated three-way merge commit combining both lines of development:
```powershell
git pull
```

To mandate the creation of an integration merge commit even when a fast-forward is possible, the `--no-ff` flag is specified:
```powershell
git pull --no-ff
```

### Rebasing
Invoking `git pull --rebase` fetches remote commits and temporarily shelves local unpushed commits. Git resets the local branch pointer to match the upstream tip, then replays each local commit sequentially on top of the remote changes:
```powershell
git pull --rebase
```
This eliminates redundant merge commits and maintains a linear project history. If conflicts arise, Git pauses at the problematic commit to allow manual resolution before continuing the rebase.

>[!info]+ Remark: Configuring Default Pull Behavior 
>Modern versions of Git require an explicit integration reconciliation strategy. The default behavior for the local or global environment is configured via the CLI:
>```powershell
>git config pull.rebase false # Standard merge (fast-forward if possible)
>git config pull.rebase true  # Rebase local commits onto upstream
>git config pull.ff only      # Fast-forward only; abort if divergent
>```
