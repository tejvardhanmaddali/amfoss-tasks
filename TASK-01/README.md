# Git Notes

## Basic Git Commands

### `git log`

* Commit history

### `git add fileName`

* Adds a file to the staging area.

### `git push`

* Pushes commits to the remote repository.

### `git commit -m "commit_message"`

* Commits all the files in staging area.
* We can't control what file to commit, so we remove files from staging area if we want to commit specific files.

### `git restore --staged fileNames`

* Remove files from staging area.

---

## `.gitignore`

Create a file named **`.gitignore`** and keep the files, directories that you want to be ignored while commiting or staging.

---

# Git Branches

### `git branch branchName`

* Creates a branch.

### `git branch -d branchName`

* Deletes a branch.

### `git checkout branchName`

or

### `git switch branchName`

* Switches branch.

---

## Merging Branches

```bash
git switch main
git merge login
```

* Used to merge **BRANCHES**.

### Resolving Merge Conflicts

To resolve merge conflict:

1. MANUALLY CHANGE THE FILE WHERE THERE IS CONFLICT.
2. ADD IT INTO STAGING AREA.
3. THEN COMMIT IT.

---

# Git Stash

### `git stash`

### `git pop stash`

* Maintenance of working area.
* Uses FIFO.

---

# Git Rebase

In order to rebase:

1. First go to the branch you want to move.
2. Then use the rebase command.

```bash
git switch change-branch-history
git rebase hot-bugfix
```

---

# Removing a File from Git Tracking

### `git rm --cached ignored.txt`

* Used to remove a file from being Tracked by GIT.

---

# Renaming Files

### `git mv File.txt file.txt`

* Used to rename committed file.
* Need to be committed again after re-naming.

---

# Amend Commit

### `git commit --amend`

* Used to change errors in file and then committing them by editing the old commit message instead of a new commit so that number of commits will be less.

### Changing an Older Commit Message

`git commit --amend` only amends the last commit message.

So in order to change any commit message, we must use **rebase interactive mode**:

```bash
git rebase -i HEAD~2
```

Then change the mode to **edit** (for the commit that you want to edit from).

After editing and committing, use:

```bash
git rebase --continue
```

* Look out for merge conflicts.

---

# Changing Commit Date

```bash
GIT_AUTHOR_DATE="1987-01-01 12:00:00" GIT_COMMITTER_DATE="1987-01-01 12:00:00" git commit --amend --no-edit
```

---

# Git Reflog

### `git reflog`

* Contains data relating to where HEAD is pointed.
* i.e. contains all the commit histories (not exactly but somewhat related).

---

# Git Reset

### Task - 15

```bash
git reset HEAD~1
```

* Undo last commit.

### Task - 16

```bash
git reset --soft HEAD~2
```

* Undo last 2 commits but keeps their stages.

---

# Making a Script Executable

```bash
chmod +x script.sh
git add script.sh
git commit -m "Make script executable"
```

---

# Git Add Patch

### `git add -p`

* Commit specific parts of the file.

---

# Git Cherry-Pick

### `git cherry-pick`

* Used for feature selection.

---

# Git Rebase Onto

### `git rebase --onto`

---

# Interactive Rebase

Go into interactive rebase to change the commit history order.

Command used:

```bash
git rebase -i HEAD~2
```

