## Essential Commands

### Setup Commands
```bash
# Initialize repository
git init

# Clone repository
git clone <repository-url>

# Configure user information
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### Basic Operations
```bash
# Check status
git status

# Stage files
git add <filename>
git add .  # Add all files
git add -p # Add files interactively

# Commit changes
git commit -m "Commit message"
git commit -am "Commit message"  # Add and commit tracked files

# View history
git log
git log --oneline
git log --graph --oneline --decorate
```

### Remote Operations
```bash
# Add remote
git remote add origin <repository-url>
git remote -v  # List remotes

# Push changes
git push -u origin main  # First push
git push  # Subsequent pushes

# Pull changes
git pull origin main
git fetch origin  # Fetch without merging
```

### Inspection Commands
```bash
# View changes
git diff  # Working directory vs staging
git diff --staged  # Staging vs last commit
git show <commit-hash>  # Show specific commit

# File history
git blame <filename>  # Show who changed what
git log -p <filename>  # Show file history
```

### Undo Operations
```bash
# Undo staging
git reset <filename>
git reset  # Unstage all

# Undo commits
git reset HEAD~1  # Undo last commit, keep changes
git reset --hard HEAD~1  # Undo last commit, discard changes

# Revert commits
git revert <commit-hash>  # Create new commit that undoes changes
```

## Advanced Commands

### Stashing
```bash
# Save changes temporarily
git stash
git stash save "message"
git stash list
git stash pop
git stash apply
git stash drop
```

### Tagging
```bash
# Create tags
git tag v1.0.0
git tag -a v1.0.0 -m "Version 1.0.0"
git push origin v1.0.0
git push origin --tags
```

### Submodules
```bash
# Add submodule
git submodule add <repository-url>
git submodule update --init --recursive
```

### Maintenance
```bash
# Clean repository
git clean -n  # Dry run
git clean -f  # Remove untracked files
git gc  # Garbage collection
```