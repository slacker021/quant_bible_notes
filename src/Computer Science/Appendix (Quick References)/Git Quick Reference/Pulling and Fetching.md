---
dg-publish: true
---
Users can pull the latest changes from the remote git repository using `git pull`. This is simply a `git fetch` followed by a `git merge`. 

---
# Fetching
One option the user has is *fetching*, which is done via `git fetch`.  This is purely a download operation that reaches out to the remote repository and downloads only the latest information about what exists on that server. This doesn't modify any of the local branches that the information is downloaded to, nor does it perform a merge commit or attempt to solve any conflicts within the working directory. It simply  updates the user's local repository’s knowledge of the remote state, typically storing these incoming references under names like `origin/main` (the version of main as seen by the remote).

>[!warning]+ Warning: Inspect before Doing
>This is critical for allowing the user to decide what to do before pulling changes. By fetching first, the user can determine what changes may conflict with local files. This is recommended as being the first thing the user does before *pulling*. 

---
# Pulling
 `pull` is a convenient, two-step shortcut that combines two distinct operations: `git fetch` followed by `git merge`. This is often convenient as it automatically attempts to perform the merge. While there are many ways of pulling, the three most common ways are as follows: 

### Rebasing
`git pull --rebase` pulls all the latest commits from the remote repository and layers them on top of the latest commit of the local repository. This is a clean and convenient option that eliminates the need to merge manually. 

### Standard Pull
`git pull` or `git pull --ff-only` is the standard means of pulling information from the remote repository. This results in an automatic merge commit, which prompts the user to enter a commit message before finalizing the merge. 

### Fast-Forward Only
`git pull -ff-only` is similar to standing pulling but will immediately stop the merge attempt, simply updating the branch pointer. Instead of generating an unexpected merge commit, which can result in merge conflicts, it immediately aborts the process. This gives the user the change to inspect the changes and manually decide if they want to merge it as normal, or rebase it. 

>[!info]+ Remark: Self-Pacing
>This is ideal for beginners or those who want to inspect the code at their own pace. Note that its possible to alter the default pulling behavior via the CLI: 
>```powershell
>git config pull.rebase false # merge
>git config pull.rebase # rebase
>git config pull.ff only # fast-forward only
>```
>Newer versions of git even require users to set the default behavior. 