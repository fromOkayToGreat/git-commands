# The Commands

## `git config`

---
## `git init`
Use to initialize a Git repository.

---
## `git status`
Use to ask Git about the status of the files in working directory and the Git repostory.

---
## `git add <filename>`
Use to add files to the index (staging area).

---
## `git commit`
Use to commit files added to the index to the object database (snapshot of the changes).
> See how to write commit comments here

### `--amend`
Use to edit last commit message.  *Only ammend the tips of branches!*

---
## `git branch`

Use to list branches in current repository.

### `<branch name>` arg

Use to create a branch with the supplied name (prefix initials, ticket#, brief description).
`fg/1618/add-css-flow-utility-class`

### `<branch name> commit-ID` arg
Use to create a branch with supplied name based on the commit ID provided.


### `-d <branch name>` flag
Use to delete a merged branch.

### `-D <branch name>` flag
Use to delete a unmerged branch.

### `-m <new name>` flag
Use to rename current branch.

### `-a` flag
Use to list all branches in current repository, including remote tracking branches.

### `-vv` flag
Use to list all branches in current repository, including remote tracking branches and last commit message.  *Any remote branch that has been deleted will be marked as `gone`.*




---
## `git switch <branch name>`
Use to start using the specified branch, creating it if it doesn't exist.

---
## `git log`

Use to list all the commits, along with the commit metadata for the current branch.

### `--oneline` flag
Use to simplify commit history.

### `--all --graph` flag
Use to visualize commit history of every branch.

---
## `git diff`
Use to compare index and working directory.  Outputs file's differences.

### `--cached` `--staged` flag
Allows comparing the Index and last commit.

### `<branch name1> <branch name2>` args
Use to compare the "tips" of two branches.

### `<commit ID1> <commit ID2>` args
Use to compare the two disparate commits.

---
## `git restore`
Use to undo changes in the working directory by replacing them with the version of the file(s) last added to the index.

### `<file path>` args
Undoes changes to specified file(s) path by replacing working directory version with last added to the index.

### `--staged`
Use to replace contents of the file(s) in the index with the version that was last commited.

---
## `git rm <file path>`
Use to remove *tracked* files from working directory and index.
>It requires a commit to record the deletion

### `-r` flag
Use this flag to remove directories

---

## `HEAD`
Use as the reference which commit you are on.

### `~` operator
Use to reference ancestor cmomits relative to the `HEAD`.
>`HEAD~2`, for example takes you back two generations: it represent the grandparent of the commit.

### `^` operator
Use to reference the parents of a merge commit.
> `HEAD^1` points to the first parent, `HEAD^2` points to the second.

---

## `git reset <commit ID> | HEAD` arg
Allows you to "time travel", as it moves the `HEAD` and branch to a previous commit.  Specified by the argument  or `HEAD` operator.
### `--mixed` (default) flag
Both Index and Object Database will have the files of the specified commit ID or `HEAD`.

### `--soft` flag

Only the Object Database will have the files of the specified commit ID or `HEAD`.
### `--hard` flag
Working Directory, Index, and Object Database all have files of the specified commit ID or `HEAD`.

---

## `git revert  <commit ID> | HEAD` arg
Use to undo a commit by creating an "anti-commit"- a commit that introduced a set of changes that exact the specified commit while leaving the current commit intact.

## `git clone <url> <directory name>` args
Use to clone a repository from a remote location to a local directory.


## `git push`
Use to push local commits to a remote repository. Any commits that are pushed to a remote repository are considered "shared" commits.

### `-u` flag
Use to set the upstream branch for the current branch.  This lets you specify the name of the remote and the name of the branch you want to create in the remote repository.

### `--force` flag
Use to force push to a remote repository.  This is not recommended as it can cause issues with other developers.

## `git pull`
Use to fetch and merge changes from a remote repository.

## `git fetch`
Use to retrieve al new branches and commits from a remote repository, the nuipdates the remote tracking branches in the clone.  *The local branches are not updated.*

### `-p` flag
Use to delete remote tracking branches that no longer exist on the remote repository.

