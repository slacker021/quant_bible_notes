---
dg-publish: true
---
Circumstances frequently arise in development workflows where in-progress modifications in the working tree must be set aside without generating an incomplete commit or discarding the modified state. The `git stash` command records the current state of the working directory and index, reverting the local tree to match the `HEAD` commit. Stashed changes are stored in a Last-In, First-Out (LIFO) stack of serialized patches, enabling developers to switch branch contexts, integrate upstream updates, or resolve urgent defects without carrying uncommitted changes across branches.

---
# Mechanics and Workflow
The stash lifecycle operates through three primary phases:
1. **Shelving (Pushing):** Invoking `git stash push` serializes uncommitted modifications, reverts the working tree to the state of the current `HEAD` commit, and pushes the changes onto the stash reference stack.
2. **Context Switching:** With the working tree restored to a clean state, the developer can checkout alternative branches, apply hotfixes, or pull remote updates without conflict.
3. **Reconstitution (Applying or Popping):** Upon returning to the original development branch, the shelved modifications are restored to the working tree. Executing `git stash apply` reapplies the state while retaining the entry in the stash stack, whereas `git stash pop` reapplies the changeset and removes it from the stack upon successful reinstatement.

---
# Methods of Stashing

### Shelving Working State

Recording tracked modifications onto the stash stack:
```powershell
git stash push
```

Annotating a stash with an explicit descriptive message:
```powershell
git stash push -m "wip: prototype 1"
```

Including untracked files along with tracked modifications:
```powershell
git stash push -u
```

By default, Git does not track newly created files that have not been registered with `git add`. The `-u` (or `--include-untracked`) flag forces Git to include these files in the serialized stash object.
Stashing all files, including untracked and ignored files (`.gitignore`):
```powershell
git stash push -a
```

Staging-only stash (preserving unstaged modifications in the working tree):
```powershell
git stash push --staged
```

### Inspecting Stashed Changes
Displaying the chronological list of shelved stashes:
```powershell
git stash list
```

Each entry in the list is indexed by a reference pointer (`stash@{0}`, `stash@{1}`, etc.), where `stash@{0}` denotes the most recently pushed modification set. Inspecting a diff summary of the latest stash:
```powershell
git stash show
```

Inspecting the full patch diff of a specific stash entry:
```powershell
git stash show -p stash@{0} # Note: the most recent stash has index 0, followed by 1,2,3...
```

### Restoring and Clearing Stashes
Restoring the latest stash and immediately dropping it from the stack:
```powershell
git stash pop
```

Restoring an arbitrary stash by index without dropping it from the stack:
```powershell
git stash apply stash@{1}
```

Removing an explicit stash entry from the stack without applying it:
```powershell
git stash drop stash@{0}
```

Purging all stored stashes from the repository stack:
```
git stash clear
```
