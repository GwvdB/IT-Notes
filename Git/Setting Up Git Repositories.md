## Creating New Repository

### Local Repository
1. Create directory:
```bash
mkdir project-name
cd project-name
```

2. Initialize repository:
```bash
git init
```

3. Add initial files:
```bash
touch README.md
git add README.md
git commit -m "Initial commit"
```

### Remote Repository on GitHub
1. Go to GitHub → New Repository
2. Fill in repository details:
   - Name
   - Description
   - Public/Private
   - Initialize with README (optional)
   - Add .gitignore (optional)
   - Choose license (optional)

## Connecting Local to Remote

### New Repository
```bash
# Add remote
git remote add origin git@github.com:username/repo-name.git

# Push existing repository
git branch -M main
git push -u origin main
```

### Existing Repository
```bash
# Clone existing repository
git clone git@github.com:username/repo-name.git
cd repo-name
```

## Repository Configuration

### .gitignore Setup
1. Create .gitignore:
```bash
touch .gitignore
```

2. Common entries:
```
# OS files
.DS_Store
Thumbs.db

# Dependencies
/node_modules
/vendor

# Build output
/dist
/build

# Environment files
.env
.env.local

# IDE files
.idea/
.vscode/
```

### Repository Settings
1. Protected branches
2. Branch rules
3. Deployment keys
4. Webhooks
5. GitHub Pages

## Best Practices

### Repository Structure
```
project/
├── README.md
├── LICENSE
├── .gitignore
├── docs/
├── src/
├── tests/
└── scripts/
```

### README Content
- Project name and description
- Installation instructions
- Usage examples
- Contributing guidelines
- License information
- Contact information

### Repository Maintenance
1. Regular cleanup
2. Archive old repositories
3. Update documentation
4. Review access permissions