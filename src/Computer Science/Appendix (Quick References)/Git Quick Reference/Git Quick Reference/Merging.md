---
dg-publish: true
---
`git merge` reconciles two separate lines of development—represented by distinct branches—by computing the minimal changeset required to integrate their independent histories into a single unified branch. Git models repository history as a *Directed Acyclic Graph* (DAG). When a branch diverges from an existing line of development, Git captures commit snapshots along that alternate path. `git merge` provides the topological mechanism to rejoin that divergent history into the parent lineage, ensuring that changes are preserved without regression.

---
# The Main Use of Merging
The primary function of a merge commit is threefold: 
1. **Historical Record:** It explicitly documents where and when two branches converged. The parent pointers of a merge commit reference the tips of both converging branches rather than a single predecessor. This preserves a non-linear graph structure that records which independent streams of work produced the integrated repository state.
2. **Non-Destructive Integration:** It establishes a traceable audit trail. If regressions emerge following an integration, the merge commit allows developers to inspect the discrete inputs from both parent histories, isolating root causes in complex multi-developer systems.
3. **Clarity of Intent:** It demarcates a stable integration milestone in the development lifecycle, formalizing that two sets of independent changes have satisfied testing and review contracts.

---
# Three Common Ways to Integrate Changes
Branch changes can be reconciled into a target line of development through three primary integration strategies:

>[!warning]+ Warning: Active Working Branch (`HEAD`)
>Before invoking `git merge`, verify the active working branch. The current branch (`HEAD`) must be the receiving branch (the merge destination). Upon execution, Git applies all incoming changes from the source branch into the active branch.

### Standard Integration Merge
- **Use Case:** Merging a completed feature or release branch into an integration line (e.g., merging `feature/order-routing` into `develop`).
- **Mechanism:** Git identifies the merge base (the common ancestor commit of both branches) and executes either a fast-forward (advancing the pointer if no divergence occurred) or a three-way merge commit that incorporates all intermediate commits from the source branch.
- **When to Use:** When the entire unedited development history, commit granularities, and author metadata must be preserved intact.
```Powershell
git merge <branch_name>
```

### Squashed Merge
- **Use Case:** Integrating feature branches that contain numerous local, work-in-progress, or checkpoint commits that would introduce noise into the core repository history.
- **Mechanism:** Instead of creating a merge commit with multiple parent pointers, Git aggregates the cumulative diff of the source branch, stages the result in the working tree as a single combined changeset, and prompts the user for a single semantic commit message.
- **When to Use:** When the project demands that the mainline history record only cohesive, discrete units of work without intermediate trial-and-error commits.

```Powershell
git merge --squash <branch_name>
```


### Cherry-Picking
- **Use Case:** Transplanting an isolated fix, security patch, or utility function from one branch directly onto another without integrating the remainder of the source branch.
- **Mechanism:** Git extracts the patch introduced by a specific commit hash and applies it cleanly onto the current `HEAD`, creating a brand-new commit with identical diff semantics but an independent commit identifier and timestamp.
- **When to Use:** When backporting hotfixes from development into production release branches, or extracting specific bug fixes from experimental branches without merging unverified features.

```Powershell
git cherry-pick <commit_hash>
```
