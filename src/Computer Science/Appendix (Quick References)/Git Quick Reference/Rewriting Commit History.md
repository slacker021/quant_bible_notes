---
dg-publish: true
---


> [!warning]+ Warning: On Shared Repositories
> Rewriting commit history isn't recommended on repositories being worked on by many developers. Doing so can confuse others working on their project. However, doing this is fine on a solo project. 
# Rebasing
`git rebase` allows users to integrate changes from one commit to another, similar to [[Merging|merging]]. However, this involves rewriting commit history because the project the target branch's changes are added onto the origin branch such that it seems as if there was no divergence between the two branches. This makes the history look like one clean progression of development.  Simply put, it takes a series of commits and reapplies them onto a different base commit or branch tip. The mechanism works by:
1. Identifying where the user's current feature branch (`FeatureA`) diverged from its primary source (say, `main`).
2. Temporarily “saving” all the unique commits that belong only to `FeatureA`.
3. Moving the base of `FeatureA` forward to a new starting point on the target branch (e.g., the absolute latest commit of `main`).
4. Re-applying every saved commit, one by one, onto this new, advanced historical baseline.

The result is a perfectly linear history where it looks as if the work after all the commits that were previously on the target branch had already been implemented. 

### Common Ways of Rebasing
There are two primary ways of rebasing: The standard rebase for alignment, and the interactive rebase for deep structural cleanup.

>[!warning]+ Warning: Current Branch
>Before using `git rebase`, the user must know what branch they are on. Once the rebase is performed, Git takes all commits in the target branch against the current branch, which is where the user is, then places them on top of the branch whose history is going to be altered. 

##### Standard Rebase 
- **Command Form:** `git rebase <target-branch>` (e.g., `git checkout feature-x` then `git rebase main`)
- **Purpose:** This is used to take your local, private development branch and pull it forward onto the latest state of a shared mainline branch. It ensures that before the user submits their work, all the commits on the target branch have been accounted for in their history.
- **Use Case:** Whenever the user wants to update their feature branch with upstream changes without creating an extra merge commit that clutters their local development view. This keeps their feature’s history pristine and linear relative to its starting point.

##### Interactive Rebasing
- **Command Form:** `git rebase -i <commit-hash>` or `git rebase -i HEAD~N` (where `N` is the number of commits).
- **Purpose:** This is used for cleaning up local history. It presents an interactive list of all the last `N` commits and allows the user to choose how they should be treated before being reapplied.
- **Use Cases (The Core Commands):**
    - **`squash`:** Combining multiple, minor, iterative commits into a single meaningful commit. 
    - **`pick`:** The default action; keeping the commit exactly as is.
    - **`edit` (or `e`):** Stopping the rebase process temporarily so the user can manually amend a commit, modify files, or change structure before continuing. This is vital for fixing subtle errors deep in the history that only become apparent when the code runs against the new base.
    - **`drop`:** Removing an unnecessary commit entirely from the historical record.

---
# Minor Commit Alterations
Interactive rebasing may be too much if the user simply wants to perform a minor change on a single commit. The last commit's message and contents can be altered by entering `git commit --amend`, which allows the user to not only change its message but to also add in the latest uncommitted changes. Note that the user must add the latest commits into the staging area first before doing this, if they intend to include said latest uncommitted changes. 