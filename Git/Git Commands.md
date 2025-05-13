# Git Commands Cheatsheet

## Repository Setup
- `git init` - Initialize a new repository
- `git clone [url]` - Clone an existing repository

## Basic Workflow
- `git status` - Check repository status
- `git add [file]` - Stage a specific file
- `git add .` - Stage all changed files
- `git commit -m "message"` - Commit staged changes
- `git commit -am "message"` - Commit all modified tracked files

## Branching
- `git branch` - List branches
- `git branch [name]` - Create a new branch
- `git checkout [branch]` - Switch to a branch
- `git checkout -b [branch]` - Create and switch to a new branch
- `git merge [branch]` - Merge branches

## Remote Repositories
- `git remote add origin [url]` - Add remote repository
- `git push origin [branch]` - Push to remote branch
- `git pull origin [branch]` - Pull from remote branch

## Viewing Changes
- `git log` - View commit history
- `git diff` - View uncommitted changes
- `git show [commit]` - View specific commit details

## Undoing Changes
- `git reset [file]` - Unstage a file
- `git checkout -- [file]` - Discard local changes
- `git revert [commit]` - Revert a commit

## Stashing
- `git stash` - Stash current changes
- `git stash list` - List stashed changes
- `git stash apply` - Apply most recent stash
- `git stash pop` - Apply and remove most recent stash

## Advanced
- `git rebase [branch]` - Rebase current branch
- `git tag [name]` - Create a tag