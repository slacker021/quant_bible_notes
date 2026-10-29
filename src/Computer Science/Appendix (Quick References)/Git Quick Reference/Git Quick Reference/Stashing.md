---
dg-publish: true
---
There are instances when the user may not want to commit whatever unstaged changes they've done, but also do not want to delete theses changes. `git stash` allows users to do just that by stashing whatever transient or uncommitted changes have been done. The stash serves as a temporary storage for uncommitted working changes, taking all unstaged and uncommitted changes into an easily retrievable stack. Its primary utility is enabling context switching, which allows users to focus on other task or checkout to other branches. 

---
# Mechanics and Workflow
The process involves three conceptual steps:
1. **Saving (Pushing):** The user execute `git stash push`. Git takes everything in the user's working directory, cleans up the branch to a known good state (the HEAD), and places all the modified files into the private stash stack.
2. **Context Switch:** Now that the user has a clean slate, they can safely switch branches or pull new upstream updates without worrying about committing incomplete work.
3. **Restoring (Popping/Applying):** When the user returns to their original context, they can retrieve the shelved changes using `git stash pop` (which retrieves and removes the stash from the stack) or `git stash apply` (which retrieves but leaves the stash intact for potential double use).

### Methods of Stashing

##### `git stash push`
Saves all uncommitted changes onto the stash stack. This is done before switching branches or pulling remote updates the user's current work is complete. 

##### `git stash list`
Shows a list of all saved stashes (`stash@{0}`, `stash@{1}`, etc.). This is used to see what partial works-in-progress are available to retrieve. The user can then decide to check what is in their selected stashed change via `git stash show -u <diff-options> <stash_code>`. If the user knows what they want to take out of the stash, the user can then use either of the following to retrieve the stored uncommitted changes: 
```powershell
git stash pop # unstash last uncommitted change
git stash pop stash@{n} unstash nth stash
```