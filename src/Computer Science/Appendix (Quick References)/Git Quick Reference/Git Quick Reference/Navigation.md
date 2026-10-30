---
dg-publish: true
---
# Checking File Differences
Uncommitted modifications within the working tree are inspected using `git diff`. This command calculates the difference between the current working tree (files as they physically exist on disk) and the staging area (index). It reflects uncommitted, work-in-progress modifications.

Modifications that have been staged into the index can be inspected prior to commit creation using `git diff --staged` (or its equivalent alias, `git diff --cached`). This comparison contrasts the contents of the staging area—representing the exact state of the pending snapshot—against the commit currently referenced by `HEAD`.

---
# Navigation Using Logs

### Basic Logs
Standard invocation of `git log` displays a continuous linear history of repository commits. The output can be formatted concisely to optimize terminal display:
```powershell
git log --oneline --graph --all
```

- `--oneline`: Condenses each commit object to its abbreviated 7-character SHA-1/SHA-256 hash and commit subject line.
- `--graph`: Draws an ASCII-based topological representation of branch histories and merge points.
- `--all`: Traverses references from all local branches, remote tracking branches, and tags.

### Logs with a Range
The commit log can be restricted to specific revision intervals or temporal windows:
```powershell
git log <commit_a>..<commit_b>
git log --since="2 weeks ago"
```
The double-dot notation `<commit_a>..<commit_b>` selects all commits reachable from `<commit_b>` that are not reachable from `<commit_a>`. Filtering can also be constrained by absolute dates or relative human-readable timestamps.

### Checking for Divergence
When evaluating two divergent development branches, the changes introduced by a feature branch relative to the common ancestor are evaluated using triple-dot notation:
```powershell
git diff <branch_a>...<branch_b>
```
The triple-dot syntax (`...`) computes the merge base (most recent common ancestor) of `<branch_a>` and `<branch_b>`, displaying the diff between that merge base and the tip of `<branch_b>`. This isolates the precise modifications introduced by `<branch_b>` without including subsequent mainline changes.

---
# Pager Navigation
Commands such as `git diff` and `git log` output dense textual streams designed for terminal pagination. Git routes stdout through a terminal pager—configured by default to `less`—to allow interactive buffer traversal without flooding the terminal scrollback.

### Movement (Traversal)
The following keybindings control navigation through the paginated output stream:
- **Spacebar** or **`f`**: Advance forward by one full terminal window page.
- **`b`**: Scroll backward by one full terminal window page.
- **`j` / `k`** (or **`↓` / `↑`**): Scroll downward or upward line-by-line for granular inspection.
- **`g`**: Jump directly to the first line of the output stream.
- **`G`**: Jump directly to the final line of the output stream.

### Search and Focus
Pattern matching allows rapid location of specific commit hashes, functions, or diff headers:
- **`/`**: Opens forward regular expression search prompt. Entering a pattern jumps to the first matching token down-buffer.
- **`?`**: Opens backward regular expression search prompt, scanning upward toward the start.
- **`n`**: Advances to the next occurrence matching the active search pattern.
- **`N`**: Navigates to the previous occurrence matching the active search pattern in reverse direction.

### Control and Exit
Buffer lifecycle and external process management:
- **`q`**: Terminates the pager session and returns control to the interactive shell prompt.
- **`h`**: Displays the built-in `less` command reference table.
- **`v`**: Launches the default text editor (`$VISUAL` or `$EDITOR`) on the active file or stream buffer at the current cursor position.
