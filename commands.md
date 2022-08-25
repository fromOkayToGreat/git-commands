# The Commands

## `git config`

## `git init`
Use to initialize a Git repository.

## `git status`
Use to ask Git about the status of the files in working directory and the Git repostory.

## `git add <filename>`
Use to add files to the index (staging area).

## `git commit`
Use to commit files added to the index to the object database (snapshot of the changes).
> See how to write commit comments here

## `git branch`

Use to list branches in current repository.

### `<branch name>` arg

Use to create a branch with the supplied name (prefix initials, ticket#, brief description).
`fg/1618/add-css-flow-utility-class`

### `<branch name> commit-ID`
Use to create a branch with supplied name based on the commit ID provided.


### `-d <branch name>`
Use to delete a merged branch.

### `-D <branch name>`
Use to delete a unmerged branch.


## `git switch <branch name>`
Use to start using the specified branch.

## `git log`

Use to list all the commits, along with the commit metadata for the current branch.

### `--oneline` flag
Use to simplify commit history.

### `--all --graph` flag
Use to visualize commit history of every branch.

## `git diff`
Use to compare index and working directory.  Outputs file's differences.

### `--cached` `--staged` flag
Allows comparing the Index and last commit.

### `<branch name1> <branch name2>` arg
Use to compare the "tips" of two branches.

### `<commit ID1> <commit ID2>` arg
Use to compare the two disparate commits.

