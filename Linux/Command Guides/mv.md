#linux #commands #file-operations

The `mv` command in Linux is used to move or rename files and directories. See also [[Linux-Commands#File Operations]].

## Basic Syntax
```bash
mv [OPTIONS] SOURCE DESTINATION
```

## Common Usage Patterns

### Rename File
```bash
mv oldname.txt newname.txt
```

### Move File to Directory
```bash
mv file.txt /path/to/directory/
```

### Move Multiple Files
```bash
mv file1.txt file2.txt directory/
```

## Options

### Interactive (-i)
```bash
mv -i source destination
```
- Prompts before overwrite

### No Clobber (-n)
```bash
mv -n source destination
```
- Prevents overwriting existing files

### Verbose (-v)
```bash
mv -v source destination
```
- Explains what is being done

### Backup (-b)
```bash
mv -b source destination
```
- Creates backup of existing destination files

### Force (-f)
```bash
mv -f source destination
```
- Forces move without prompting

## Common Scenarios

### File Management
```bash
# Move with backup
mv -b important.txt /backup/

# Move multiple files
mv *.txt /path/to/directory/

# Rename with timestamp
mv file.txt file-$(date +%Y%m%d).txt
```

### Directory Operations
```bash
# Move directory
mv directory1 directory2

# Move directory contents
mv directory1/* directory2/
```

## Error Handling

### Common Errors
1. Permission Denied
   ```bash
   # Solution: Use sudo for protected locations
   sudo mv file /protected/location/
   ```

2. Destination Exists
   ```bash
   # Use -i for safety
   mv -i source destination
   ```

3. Source Not Found
   ```bash
   # Check source existence
   [ -e source ] && mv source destination || echo "Source not found"
   ```

## Best Practices

### Usage Guidelines
1. Use `-i` for interactive mode
2. Create backups of important files
3. Verify source and destination
4. Check permissions before moving

### File Handling
1. Quote filenames with spaces
2. Use absolute paths in scripts
3. Check available space
4. Preserve file attributes

## Scripting Examples

### Safe File Moving
```bash
#!/bin/bash
source="$1"
dest="$2"

if [ -e "$source" ]; then
    if [ -w "$(dirname "$dest")" ]; then
        mv -i "$source" "$dest"
    else
        echo "Cannot write to destination"
        exit 1
    fi
else
    echo "Source does not exist"
    exit 1
fi
```

### Batch Processing
```bash
#!/bin/bash
# Move files by extension
for file in *.txt; do
    mv -v "$file" "processed/$file"
done
```

## System Integration

### File Organization
```bash
# Organize by extension
mv *.pdf documents/
mv *.jpg images/

# Archive old files
mv *-2023.* archive/2023/
```

### Backup Operations
```bash
# Create dated backup
mv file.conf file.conf.$(date +%Y%m%d)

# Move with numbered backup
mv --backup=numbered file.txt destination/
```

## Related Commands
- [[Linux-Commands#File Operations|cp]] - Copy files and directories
- [[Linux-Commands#File Operations|rm]] - Remove files
- [[Linux-Commands#File Operations|ln]] - Create links
- [[Linux-Commands#File Operations|rsync]] - Remote file copying

## Quick Reference

### Common Commands
```bash
# Rename file
mv old.txt new.txt

# Move file to directory
mv file.txt directory/

# Interactive move
mv -i source dest

# Move with backup
mv -b source dest

# Verbose move
mv -v source dest
```

### Verification Commands
```bash
# Check permissions
ls -l filename

# Check destination space
df -h destination
```

## Tips and Tricks
1. Use `-i` for safety
2. Remember tab completion
3. Check destination space
4. Use wildcards carefully

### Common Use Cases
```bash
# Organize files
mv *.mp3 music/

# Create backup
mv -b config.conf config.conf.bak

# Batch rename
mv file.{old,new}
```