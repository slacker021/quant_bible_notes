---
dg-publish: true
---
# Checking File Differences
Checking changes that've been made without committing them can be made using `git diff`. This shows all differences between the current working directory, which are files as they physically exist on the disk, and the staging index. It's a reflection of something that is **work in progress**. 

Staged changes that have been added before being committed can be inspected using `git diff --changed`. This compares the latest pre-committed changes with the last commit's state. This is a critical step before committing something. This reveals the exact state between the staging area, which is Git's memory of the next commit, and the last commit snapshot, which is the *HEAD*. 

---
# Navigation Using Logs

### Basic Logs
The basic `git log` command provides a large and undifferentiated waterfall of commit history. It's possible to view commit history more concisely so as to save terminal space: 
```poershell
git log --oneline --graph --all
```
- `--oneline`: Condenses each commit into a clean, concise subject and SHA hash.
- `--graph`: Draws an ASCII representation of branch history, making complex merges immediately visible.
- `--all`: Ensures the history from _every_ local and remote branch is seen (critical when collaborating).

### Logs with a Range
The log can also be condensed by altering the time range of the commits: 
```powershell
git log <commit_A> ... <Commit_B> # method 1
git log --since="2 weeks ago" # method 2, in this case two weeks
```
This allows for the viewing of the history based on SHA identifiers, branch names, or a time range. 

### Checking for Divergence
When two parallel lines of development (branches) exist, the divergence point of both of those branches can be inspected
```powershell
git diff <branch_A> ... <branch_B> 
```
The `...` syntax compares the common ancestor of both branches to the tip of branch B. This shows only the changes introduced on branch B since it diverged from branch A, making it a pristine comparison for merging or feature reviews. 

---
# Pager
`git diff` and `git log` display vast streams of information, so vast that it cannot be displayed all at once. Git does this to prevent the terminal from being cluttered, where the user can then decide to see what they wanna see. This is done through the *pager*, which is the git component that enables state traversal through the history or differences. The pager's standard setting is `less`, unless otherwise configured.
### Movement (Traversal)
 These commands manage the user's position within the document stream, allowing for quick traversal across large changes or logs: 

- **Spacebar** or `f` key: Move forward one full screen page. This is the standard "next page" function. 
- `b` key: Move back one full screen page. This sis the reversal of the primary action. 
- **Arrow Keys (↑↑ / ↓↓) or `j`/`k`**: Scroll up or down line-by-line. Used for fine-grained, textual examination.
- **`g` (Go To Start)**: Immediately jump to the very beginning of the file/output stream, restarting the review process. 
- **`G` (Go To End)**: Jump immediately to the final line of the output, revealing the culmination of the data series.

### Search and Focus (Pinpointing Anomalies)
This is used for finding specific details: 

- `/`: Initiates a forward search prompt. The user types their search term or a specific file path, where the pager then jumps to the first instance found. 
	- After searching) **`n`**: Jumps to the _next_ occurrence of the searched pattern. This is critical for comparing multiple instances of the same change across different files.
	- `N`: Jumps to the previous (or “non-next”) occurrence.

### Control and Exit (System State Management)
These commands manage the pager’s state—pausing, quitting, or repeating actions: 
- **`q`**: The most important control. **Quit**. This exits the `less` utility and returns the user to their command prompt. 
- **`h`**: Displays a help screen detailing all available commands. 
- **`v`**: Toggle visual mode. Useful if the user needs to use other terminal tools that rely on raw output.