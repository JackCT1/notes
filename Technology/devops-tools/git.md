# Git

- [Overview](#overview)
- [Architecture](#architecture)
- [Commands](#commands)
  - [Setup](#setup)
  - [Repositories](#repositories)

## Overview

Git is a tool for managing changes in files. More specifically, it is a version control system used by developers for managing and controlling source code in their projects. It records changes made to code files over time in a `repository`.

A snapshot of the current state of the directory can be taken called a `commit`. Each git commit has a unique id and is linked to the previous commit. This allows developers to see a timeline of the changes made to the files and to access previous versions.

## Architecture

Git has 4 different stages; the working directory, the staging area, the local repository, and the remote repository

The `working directory` is the folder in which the files are being written.

The `staging area` is where we add files with untracked changes ready to be committed to the local repo.

The `local repo` stores the chain of commits of the files.

The `remote repo` is a repo hosted remotely on the internet that is linked to local repo.

The sequence of commits can be split into `branches` where developers can work on separate features in separate branches and merge them together once complete.

## Commands

### Setup

Set the name that will be atached to commits

```
git config --global user.name “[firstname lastname]”
```

set the email address that will be attached to commits

```
git config --global user.email “[valid-email]”
```

```
git config --global color.ui auto
```

### Repositories

Initialise working directory as a git repo

```
git init
```

Retrieve an entire repo hosted at [url]

```
git clone [url]
```

Show modified files on working directory

```
git status
```

Stage changes to a specific file ready to be committed (from working directory to staging area )

```
git add [file]
```

Unstage specific file

```
git reset [file]
```

Commit staged changes as new snapshot

```
git commit -m "descriptive message"
```

Push local branch commits to remote repo branch

```
git push
```

### Branching

List all branches in repo

```
git branch
```

Create a new branch

```
git branch [branch-name]
```

Move into a specified branch (-b creates branch if it doesn't exist)

```
git checkout [-b] [branch-name]
```

Merge specified branch into current one

```
git merge [branch]
```

### Inspection

Show commit history of current branch

```
git log
```

Show commits on Branch A not on Branch B

```
git log branchB..branchA
```

Show the diff in Branch A not in Branch B

```
git diff branchB...branchA
```

Show commit history of specific file

```
git log --follow [file]
```

### Managing History

### Temporary Commits

Saved staged changes without committing in order to change branches

```
git stash
```

List stashed files changes

```
git stash list
```

Apply stashed changes into working directory and clear stash

```
git stash pop
```

Discard stashed changes

```
git stash drop
```
