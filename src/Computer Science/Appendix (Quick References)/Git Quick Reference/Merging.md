---
dg-publish: true
---
`git merge` can be used to take two separate lines of development, which are represented by two distinct branches, and calculates the minimal set of changes necessary to reconcile both histories into a single unified branch history. Git's repository control system can be viewed as a *Direct Acyclic Graph*, where when a user creates a secondary branch from another branch, Git creates snapshot at a specific point in time, allowing development to proceed on an alternate path. `git merge` allows for the secondary branch to be stitched back into its origin branch, ensuring that no changes are lost during transition. 

---
# The Main Use of Merging
The primary function of the merge commit is threefold
1. **Historical Record:** It explicitly documents where and when two branches were intended to meet. The parent pointers of a merge commit point back to the tips of both converging branches, rather than just one. This creates a non-linear graph structure that tells users exactly which independent streams of work contributed to this specific integrated state.
2. **Non-Destructive Integration:** It provides an audit trail. If something breaks after the merge, users can always point back to the merge commit and examine the inputs from both parent histories. This is paramount for debugging complex systems or analyzing systemic failures in a financial as it shows users which components came from which development path.
3. **Clarity of Intent:** It signifies a conscious decision in the development lifecycle that declares that these two sets of changes are now considered stable and integrated. 

---
# Three Common Ways to Merge
There're many ways to perform commits but below are the most common and standard ways of doing so: 

>[!warning]+ Warning: Current Branch
>Before using `git merge`, the user must know what branch they are on, which should be the branch that's to be committed against. Once the merge is performed, Git takes all changes from the target branch onto the current branch. 
### Standard Integration Merge
- **Use Case:** This is the default, most robust method.  This involves merging an entire branch’s history into their current branch (e.g., merging `feature/auth` into `develop`).
- **What it does:** Git identifies a Common Ancestor Point and then fast-forwards or creates a merge commit incorporating all unique commits from the source branch that haven’t been integrated yet.
- **When to use it:** Whenever the user wants the full unedited history of the feature development preserved in their project’s timeline. This is the safest, most traceable method.
- Standard syntax is `git merge <branch_name>`

### The Squashed Merge
- **Use Case:** When a feature branch has many small, iterative “work-in-progress” commits (e.g., `fix typo`, `oops revert`, `almost there`). Bringing all these messy commits into `main`, the main branch of development, becomes noisy and unreadable.
- **What it does:** Instead of creating a merge commit that brings in all individual commits, this command gathers the net changes from the entire source branch and stages them as if they were one single, monolithic change set. This requires the user to manually create a clean and meaningful commit message for this combined work.
- **When to use it:** When the user wants the effect of merging (all code is now together) but only want to record the _semantic unit of work_ (one clean commit) on their main branch history. This keeps the core development graph elegant and focused.
- Standard syntax is `git merge --squash <branch_name>`

### Targeted Commits
- **Use Case:** When the user discovers a single, critical fix or function developed in one area that belongs in another area _right now_, but it isn’t part of any larger branch integration yet.
- **What it does:** It takes the exact changes introduced by a single commit (identified by its unique SHA hash) and applies those patch changes onto your current working state, creating a brand-new commit with those changes. The history is kept clean because only one specific unit of work was moved.
- **When to use it:** This is useful for hotfixes or cherry-picking essential fixes from development branches back into release branches without merging the entire messy feature set.
- Standard syntax is `git cherry-pick <commit_hash>` 