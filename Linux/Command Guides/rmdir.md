#linux #commands #filesystem #system-administration

The `rmdir` command in Linux is used to remove empty directories. See also [[Linux-Commands#File System]].

## Basic Syntax
```bash
rmdir [OPTIONS] DIRECTORY...
```

## Common Usage Patterns

### Remove Single Empty Directory
```bash
rmdir directory_name
```

### Remove Multiple Empty Directories
```bash
rmdir dir1 dir2 dir3
```

### Remove Parent Directories
```bash
rmdir -p path/to/empty/directory
```

## Options

### Remove Parent Directories (-p)
```bash
rmdir -p a/b/c
```
- Removes each empty parent directory
- Stops at first non-empty directory
- Useful for cleaning up directory trees

### Verbose Output (-v)
```bash
rmdir -v directory_name
```
Shows directories as they are removed

### Ignore Failures (-ignore-fail-on-non-empty)
```bash
rmdir --ignore-fail-on-non-empty directory
```
Suppresses errors for non-empty directories

## Common Scenarios

### Cleanup After Project
```bash
# Remove empty project directories
rmdir -p project/{src,docs,tests}
```

### Temporary Directory Cleanup
```bash
# Remove temporary directory structure
rmdir -p /tmp/work/backup
```

### Build Directory Cleanup
```bash
# Clean build directories
rmdir build/temp
```

## Error Handling

### Common Errors
1. Directory Not Empty
   ```bash
   # Check contents first
   ls -la directory
   # Use rm -r instead if needed
   ```

2. Permission Denied
   ```bash
   # Solution: Use sudo
   sudo rmdir directory
   ```

3. No Such Directory
   ```bash
   # Check if directory exists
   ls -d directory 2>/dev/null || echo "Directory doesn't exist"
   ```

## Best Practices

### Safety Considerations
1. Always verify directory is empty
2. Use ls before rmdir
3. Consider using rm -ri for non-empty directories
4. Be extremely careful with sudo

### Directory Management
1. Check parent directories
2. Document directory removal
3. Use version control for project directories
4. Maintain removal logs in scripts

## Scripting Examples

### Basic Directory Removal
```bash
#!/bin/bash
# Remove project build directories
build_dir="build"

if [ -d "$build_dir" ]; then
    rmdir "$build_dir" || echo "Directory not empty"
fi
```

### With Error Checking
```bash
#!/bin/bash
directory="/path/to/dir"

if [ -d "$directory" ]; then
    if [ -z "$(ls -A "$directory")" ]; then
        rmdir "$directory" || {
            echo "Failed to remove $directory"
            exit 1
        }
        echo "Directory removed successfully"
    else
        echo "Directory not empty"
        exit 1
    fi
else
    echo "Directory doesn't exist"
fi
```

## System Maintenance

### Cleanup Scripts
```bash
# Remove empty directories in temp
find /tmp -type d -empty -exec rmdir {} \;
```

### Build System Cleanup
```bash
# Clean empty build directories
rmdir -p build/{debug,release}/temp 2>/dev/null
```

## Related Commands
- [[Linux-Commands#File System|mkdir]] - Create directories
- [[Linux-Commands#File System|rm]] - Remove files and directories
- [[Linux-Commands#File System Navigation|ls]] - List directory contents
- [[Linux-Commands#File System|find]] - Search for files and directories

## Quick Reference

### Common Commands
```bash
# Remove empty directory
rmdir directory_name

# Remove with parents
rmdir -p path/to/directory

# Remove multiple directories
rmdir dir1 dir2 dir3

# Verbose removal
rmdir -v directory_name
```

### Verification Commands
```bash
# Check if directory exists
ls -d directory_name

# Check if directory is empty
ls -A directory_name
```

## Tips and Tricks
1. Use `ls -A` to check if directory is empty
2. Combine with find for bulk operations
3. Use -v for verification in scripts
4. Remember rm -r for non-empty directories

### Alternative Commands
When rmdir isn't suitable:
```bash
# Remove non-empty directory
rm -r directory

# Remove with confirmation
rm -ri directory

# Force remove
rm -rf directory  # Use with extreme caution
```