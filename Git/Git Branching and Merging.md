## Branching Basics

### Creating Branches
```bash
# Create new branch
git branch feature-name

# Create and switch to new branch
git checkout -b feature-name

# List branches
git branch  # Local branches
git branch -a  # All branches including remote
```

### Switching Branches
```bash
# Switch to existing branch
git checkout branch-name

# Switch to previous branch
git checkout -
```

## Merging

### Basic Merge
```bash
# Switch to target branch
git checkout main

# Merge feature branch into current branch
git merge feature-name
```

### Merge Strategies
1. **Fast-forward**
   - Default when possible
   - Linear history
   ```bash
   git merge feature-name
   ```

2. **No-fast-forward**
   - Creates merge commit
   - Preserves branch history
   ```bash
   git merge --no-ff feature-name
   ```

3. **Squash**
   - Combines all commits into one
   - Cleaner history
   ```bash
   git merge --squash feature-name
   ```

## Handling Merge Conflicts

### When Conflicts Occur
1. Git marks conflicts in files
2. Manually resolve conflicts
3. Stage resolved files
4. Complete merge with commit

### Conflict Resolution
```bash
# Check status of conflict
git status

# After resolving conflicts
git add <resolved-files>
git commit -m "Merge branch 'feature-name'"

# Abort merge if needed
git merge --abort
```

## Branch Management

### Clean Up Branches
```bash
# Delete local branch
git branch -d branch-name  # Safe delete
git branch -D branch-name  # Force delete

# Delete remote branch
git push origin --delete branch-name
```

### Update Branches
```bash
# Update remote branches list
git fetch --prune

# Update local branch with remote changes
git pull origin branch-name
```

## Branching Strategies

### Feature Branch Workflow
1. Create feature branch from main
2. Develop feature
3. Pull request
4. Code review
5. Merge to main

### Gitflow
- `main`: Production code
- `develop`: Integration branch
- `feature/*`: New features
- `release/*`: Release preparation
- `hotfix/*`: Production fixes

### Trunk-Based Development
- Short-lived feature branches
- Frequent integration to main
- Feature flags for incomplete features

## Advanced Topics

### Cherry-picking
```bash
# Apply specific commit to current branch
git cherry-pick <commit-hash>
```

### Rebasing
```bash
# Rebase current branch onto main
git rebase main

# Interactive rebase
git rebase -i HEAD~3
```

### Branch Protection
1. Require pull request reviews
2. Require status checks
3. Require linear history
4. Enforce branch naming conventions