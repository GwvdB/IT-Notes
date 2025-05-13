#linux #commands #file-operations #navigation

The `cd` command in Linux is used to change the current working directory. See also [[Linux-Commands#Navigation]].

## Basic Syntax
```bash
cd [OPTIONS] [DIRECTORY]
```

## Common Usage Patterns

### Change to Directory
```bash
cd directory_name
```

### Return to Home Directory
```bash
cd
# or
cd ~
```

### Move Up One Directory
```bash
cd ..
```

### Move to Previous Directory
```bash
cd -
```

## Options

### Physical Path (-P)
```bash
cd -P directory
```
- Follows physical directory structure
- Does not follow symbolic links

### Logical Path (-L)
```bash
cd -L directory
```
- Follows symbolic links (default behavior)

## Common Scenarios

### Directory Navigation
```bash
# Go to root directory
cd /

# Go to home directory
cd ~

# Go to specific user's home
cd ~username
```

### Relative Navigation
```bash
# Go up two levels
cd ../..

# Go to sibling directory
cd ../other_directory
```

## Error Handling

### Common Errors
1. Directory Not Found
   ```bash
   # Check directory existence first
   [ -d directory ] && cd directory || echo "Directory not found"
   ```

2. Permission Denied
   ```bash
   # Solution: Check permissions
   ls -ld directory
   ```

## Best Practices

### Usage Guidelines
1. Use tab completion for accuracy
2. Verify destination before changing
3. Use relative paths when appropriate
4. Keep track of directory structure

### Directory Handling
1. Check permissions before access
2. Use absolute paths in scripts
3. Handle spaces in directory names
4. Consider using `pushd`/`popd` for temporary changes

## Scripting Examples

### Safe Directory Change
```bash
#!/bin/bash
target_dir="$1"

if [ -d "$target_dir" ]; then
    if [ -x "$target_dir" ]; then
        cd "$target_dir"
    else
        echo "Cannot access $target_dir"
        exit 1
    fi
else
    echo "Directory $target_dir not found"
    exit 1
fi
```

## Related Commands
- [[Linux-Commands#Navigation|pwd]] - Print working directory
- [[Linux-Commands#Navigation|pushd]] - Push directory to stack
- [[Linux-Commands#Navigation|popd]] - Pop directory from stack
- [[Linux-Commands#File Operations|ls]] - List directory contents

## Quick Reference

### Common Commands
```bash
# Go to home
cd ~

# Go up one level
cd ..

# Go to previous directory
cd -

# Go to absolute path
cd /path/to/directory

# Go to relative path
cd ./subdirectory
```

### Verification Commands
```bash
# Check current directory
pwd

# Check directory permissions
ls -ld directory_name
```

## Tips and Tricks
1. Use `cd -` to toggle between directories
2. Remember `~` shortcut for home
3. Use tab completion to prevent errors
4. Quote paths with spaces

### Common Use Cases
```bash
# Navigate to system directories
cd /etc

# Navigate to user configuration
cd ~/.config

# Change to parent directory
cd ..
```