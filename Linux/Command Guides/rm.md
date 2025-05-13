#linux #commands #file-operations

The `rm` command in Linux is used to remove files and directories. See also [[Linux-Commands#File Operations]].

## Basic Syntax
```bash
rm [OPTIONS] FILE(s)
```

## Common Usage Patterns

### Remove Single File
```bash
rm filename.txt
```

### Remove Multiple Files
```bash
rm file1.txt file2.txt
```

### Remove Directory
```bash
rm -r directory/
```

## Options

### Recursive (-r, -R)
```bash
rm -r directory/
```
- Removes directories and their contents

### Force (-f)
```bash
rm -f file.txt
```
- Ignore nonexistent files
- Never prompt for confirmation

### Interactive (-i)
```bash
rm -i file.txt
```
- Prompt before every removal

### Verbose (-v)
```bash
rm -v file.txt
```
- Explain what is being done

### Directory (-d)
```bash
rm -d empty_directory/
```
- Remove empty directories

## Common Scenarios

### File Deletion
```bash
# Remove all files of type
rm *.tmp

# Remove with confirmation
rm -i important.txt

# Force remove write-protected
rm -f readonly.txt
```

### Directory Operations
```bash
# Remove directory and contents
rm -rf directory/

# Remove empty directories
rm -d empty1/ empty2/

# Remove with pattern
rm -r test*/
```

## Error Handling

### Common Errors
1. Permission Denied
   ```bash
   # Solution: Use sudo for protected files
   sudo rm protected_file
   ```

2. Directory Not Empty
   ```bash
   # Use recursive option
   rm -r non_empty_directory/
   ```

3. File Not Found
   ```bash
   # Use force option to suppress errors
   rm -f nonexistent_file
   ```

## Best Practices

### Safety Guidelines
1. Always verify before using `-rf`
2. Use `-i` for important operations
3. Double-check wildcards
4. Consider using trash instead

### File Handling
1. Quote filenames with spaces
2. Be careful with recursive deletion
3. Check permissions first
4. Backup important data

## Scripting Examples

### Safe File Removal
```bash
#!/bin/bash
target="$1"

if [ -e "$target" ]; then
    read -p "Remove $target? (y/n) " confirm
    if [ "$confirm" = "y" ]; then
        rm -v "$target"
    fi
else
    echo "File not found"
    exit 1
fi
```

### Pattern Deletion
```bash
#!/bin/bash
# Remove old backup files
find . -name "*.bak" -type f -mtime +30 -exec rm -v {} \;
```

## System Integration

### Cleanup Operations
```bash
# Clean temporary files
rm -f /tmp/temp*

# Remove old logs
rm -f /var/log/*.old

# Clean build artifacts
rm -rf build/*
```

### Secure Deletion
```bash
# Overwrite before delete (more secure)
shred -u file.txt

# Clean temporary files
rm -rf /tmp/session*
```

## Related Commands
- [[Linux-Commands#File Operations|srm]] - Secure remove
- [[Linux-Commands#File Operations|shred]] - Secure delete with overwrite
- [[Linux-Commands#File Operations|trash]] - Move to trash instead of delete
- [[Linux-Commands#File Operations|find]] - Find and remove

## Quick Reference

### Common Commands
```bash
# Remove file
rm file.txt

# Remove directory
rm -r directory/

# Force remove
rm -f file.txt

# Interactive remove
rm -i file.txt

# Remove empty directory
rm -d empty_dir/
```

### Verification Commands
```bash
# List before removal
ls -l target_file

# Check permissions
ls -ld target_directory
```

## Tips and Tricks
1. Use `rm -i` when learning
2. Create aliases for safety
3. Consider using trash
4. Verify wildcards first

### Common Use Cases
```bash
# Clean temporary files
rm *.tmp

# Remove old backups
rm *_backup.tar.gz

# Clean build directory
rm -rf build/*
```

## Safety Reminders
1. Never run `rm -rf /`
2. Avoid `rm -rf *` in root directory
3. Double-check wildcards
4. Use safeguards in scripts

### Safe Alternatives
```bash
# Create safer alias
alias rm='rm -i'

# Use trash command
# (if installed)
trash file.txt

# Use find with confirmation
find . -name "*.tmp" -exec rm -i {} \;
```