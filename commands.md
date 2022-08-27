# The Commands

## `git config`

### `--list`
Lists all the configuration settings.

### `--global`
Sets the configuration setting for the current user.

### `--system`
Sets the configuration setting for the current system.

### `--local`
Sets the configuration setting for the current repository.

### `--edit`
Opens the configuration file in the default editor.

### `--unset`
Removes the configuration setting.

### `--show-origin`
Shows the origin of the configuration setting.

### `alias.<name>`
Sets an alias for a command. For example, `git config --global alias.co checkout` sets the alias `co` for the command `checkout`.

---

## `git help <command>`
Shows the help for a command.

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

### `--grep <search term>` flag
Use to search for commits with the supplied search term in the commit message. *Can take a regex.*

### `-S` flag
Use to search for commits with the supplied search term in the commit message. *Can take a regex.*

### `-p` flag
Use to show the diff of each commit.

### `-G` flag
Use to search for commits with the supplied search term in the diff of the commit.

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

## `git blame <file path>` args
Use to show what revision and author last modified each line of a file.

## `git grep <search term>` args
Use to search the working directory for a string. **Can take a regular expression.**

### `-n` flag
Use to show the line number of the search term.

### `-i` flag
Use to ignore case.

### `-w` flag
Use to match the whole word.

### `-l` flag
Use to show only the file names.

### `-c` flag
Use to show the number of matches in each file.

---

## `git checkout <commit ID> | HEAD` args
Use to "time travel" to a previous commit.  This is different from `git reset` in that it does not move the branch pointer. It is used to inspect a previous commit.

---

## `git bisect`
Use to find the commit that introduced a bug.  It does this by using a binary search algorithm to find the commit that introduced the bug.

### `start` arg
Use to start a bisect session.

### `good <commit ID>` arg
Use to mark a commit as good.

### `bad  <commit ID>` arg
Use to mark a commit as bad.

### `skip` arg
Use to skip a commit.

### `reset` arg
Use to reset the bisect session.

---

## `git tag <tag name>` args
Use to create a tag.  Tags are used to mark a specific point in the repository's history as being important.  They are usually used to mark releases.

### `-a` flag
Use to create an annotated tag.  Annotated tags are stored as full objects in the Git database.  They contain the tagger name, email, date, and tagging message, and have a checksum; it's possible to verify the contents of an annotated tag.  It's generally recommended that you create annotated tags so you can have all this information; but if you want a temporary tag or for some reason don't want to keep the other information, you can create a lightweight tag with `-a`.

### `-m` flag
Use to add a message to the tag.

---

## `git cherry-pick <commit ID>` args
Use to apply a commit to the current branch.  This is useful when you want to apply a commit from another branch to the current branch.

---

## `git stash`
Use to temporarily store changes in the working directory.  This is useful when you want to switch branches but don't want to commit your changes.

### `save` arg
Use to save the current state of the working directory.

### `list` arg
Use to list the stashes.

### `apply` arg
Use to apply the most recent stash.

### `pop` arg
Use to apply the most recent stash and remove it from the stash list.

### `drop` arg
Use to remove the most recent stash from the stash list.

---

## `git rebase`
Use to reapply commits on top of another base tip.  This is useful when you want to move a branch to a new base commit. It is also useful when you want to clean up your commit history by squashing commits together. It is also useful when you want to rebase commits from one branch to another.

### `--onto <base commit ID> <start commit ID> <end commit ID>` args
Use to rebase commits from the start commit ID to the end commit ID onto the base commit ID.

---

## `git reflog`
Use to show a log of all the references that have been updated in the local repository.  This is useful when you want to find a commit that has been garbage collected.
