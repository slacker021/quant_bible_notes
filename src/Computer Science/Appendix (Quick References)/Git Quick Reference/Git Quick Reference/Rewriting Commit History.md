---
dg-publish: true
---
>[!warning]+ Warning: History Mutation on Shared Remotes
>Rewriting published commit history on shared remote branches disrupts upstream synchronization for other collaborators, causing diverging reference graphs and duplicate commits upon synchronization. History alteration should be restricted strictly to local, unpublished feature branches prior to integration.

---
# Rebasing
The `git rebase` command integrates changes from one line of development onto another by recalculating the commit base. Unlike `git merge`, which preserves historical divergence via a dedicated merge commit, rebasing extracts the unique commits of an active branch and replays them sequentially onto the tip of the upstream branch. This produces a linear commit progression without structural divergence.

The mechanical execution proceeds in four phases:
1. Git identifies the common ancestor commit between the active feature branch (`HEAD`) and the designated upstream branch.
2. The commits unique to the active feature branch are temporarily serialized into patch files and held in memory.
3. The pointer of the active feature branch is reset to the tip of the designated upstream branch.
4. Each serialized commit patch is sequentially re-applied onto the updated baseline, generating new commit hashes with updated parent pointers.

The resulting topological graph is strictly linear, indicating that feature development proceeded directly after the latest state of the upstream branch.

---
# Common Rebase Workflows
Branch rebasing is predominantly deployed for upstream baseline synchronization or granular history sanitation.

>[!warning]+ Warning: Active Working Branch Verification
>Prior to invoking `git rebase`, verify that `HEAD` references the divergent branch whose commits are to be replayed. Executing `git rebase <upstream>` while pointing to the incorrect branch alters branch lineage and re-parents unrelated commits.

### Standard Upstream Rebase
A standard rebase pulls an active local branch forward onto the latest commit of an upstream integration branch (such as `main`):
```powershell
git checkout feature-routing
git rebase main
```
- **Operational Purpose:** Updates the feature branch with upstream modifications without introducing extraneous merge commits into the local development view.
- **Topological Outcome:** Preserves a clean linear lineage relative to the current upstream reference point.

### Interactive Rebasing
Interactive rebasing allows granular history auditing, allowing developers to reorder, combine, edit, or eliminate commits before submitting code for review:
```powershell
git rebase -i <base-commit-hash>
# Alternatively, inspect the last N commits from HEAD:
git rebase -i HEAD~N
```
The interactive editor displays commits in chronological order from oldest (top) to newest (bottom), which is the reverse order of `git log`.

### Core Interactive Actions
- **`pick` (`p`):** Retains the commit unmodified (the default instruction).
- **`reword` (`r`):** Retains the commit contents while pausing execution to edit the commit message.
- **`edit` (`e`):** Halts the rebase process at the specified commit, allowing file modifications, staging adjustments, or commit splitting before resuming via `git rebase --continue`.
- **`squash` (`s`):** Melds the commit into its immediate predecessor, prompting the developer to combine both commit messages into a single summary.
- **`fixup` (`f`):** Melds the commit into its immediate predecessor while completely discarding the child commit message, ideal for minor linting or syntax fixes.
- **`drop` (`d`):** Completely excises the commit and its corresponding patch from the project history.

---
# Minor Commit Alterations
When alterations involve only the most recent commit on the branch (`HEAD`), invoking an interactive rebase is superfluous. Single-commit adjustments are executed directly using `git commit --amend`.

### Modifying the Commit Message
Reopening the text editor to rewrite the most recent commit message:
```powershell
git commit --amend
```

Overriding the commit message directly via the CLI:
```powershell
git commit --amend -m "refactor(core): update order matching algorithm"
```

### Amending Content Without Message Alteration
To incorporate new modifications or staged files into the tip commit without altering the original commit log entry:
```powershell
git add <modified-file>
git commit --amend --no-edit
```
This amends the staged diff directly into the previous commit snapshot and generates a new SHA-1/SHA-256 identifier, maintaining atomic commit integrity.





