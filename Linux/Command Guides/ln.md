#linux #commands #file-operations

The `ln` command in Linux is used to create links between files. See also [[Linux-Commands#File Operations]].

## Basic Syntax
```bash
ln [OPTIONS] TARGET LINK_NAME
```

## Common Usage Patterns

### Create Hard Link
```bash
ln target link_name
```

### Create Symbolic Link
```bash
ln -s target link_name
```

### Create Multiple Links
```bash
ln target1 target2 directory/
```

## Options

### Symbolic (-s)
```bash
ln -s target link_name
```
- Creates symbolic (soft) link

### Force (-f)
```bash
ln -f target link_name
```
- Remove existing destination files

### Interactive (-i)
```bash
ln -i target link_name
```
- Prompt before overwrite

### Verbose (-v)
```bash
ln -v target link_name
```
- Print name of each linked file

### No Dereference (-n)
```bash
ln -n target link_name
```
- Treat destination as normal file if it is a symlink

## Common Scenarios

### File Linking
```bash
# Create symbolic link to file
ln -s /path/to/file.txt link.txt

# Create hard link to file
ln original.txt hard_link.txt

# Link to executable
ln -s /usr/bin/python3 python
```

### Directory Operations
```bash
# Link to directory
ln -s /path/to/directory dir_link

# Link multiple files to directory
ln -s file1.txt file2.txt target_dir/
```

## Error Handling

### Common Errors
1. Target Does Not Exist
   ```bash
   # Check target existence
   [ -e target ] && ln -s target link || echo "Target not found"
   ```

2. Permission Denied
   ```bash
   # Solution: Check permissions
   ls -l target
   sudo ln -s target link
   ```

3. Link Already Exists
   ```bash
   # Use force option
   ln -sf target link
   ```

## Best Practices

### Usage Guidelines
1. Use absolute paths for symlinks
2. Check target existence
3. Verify link creation
4. Handle circular links carefully

### Link Management
1. Keep track of link relationships
2. Use relative paths when appropriate
3. Clean up broken links
4. Document link purposes

## Scripting Examples

### Safe Link Creation
```bash
#!/bin/bash
target="$1"
link_name="$2"

if [ -e "$target" ]; then
    if [ -L "$link_name" ]; then
        echo "Link already exists"
        exit 1
    else
        ln -s "$target" "$link_name"
    fi
else
    echo "Target does not exist"
    exit 1
fi
```

### Link Verification
```bash
#!/bin/bash
# Check if symlink is valid
if [ -L "$1" ] && [ -e "$1" ]; then
    echo "Valid symlink"
else
    echo "Broken link"
fi
```

## System Integration

### Configuration Management
```bash
# Link configuration files
ln -s ~/.config/app/config.conf ~/.app/config

# Link system binaries
sudo ln -s /opt/app/bin/app /usr/local/bin/
```

### Application Setup
```bash
# Set default version
ln -sf python3.9 python3

# Link shared libraries
ln -s libexample.so.1.0.0 libexample.so.1
```

## Related Commands
- [[Linux-Commands#File Operations|cp]] - Copy files and directories
- [[Linux-Commands#File Operations|mv]] - Move files and directories
- [[Linux-Commands#File Operations|rm]] - Remove files
- [[Linux-Commands#File Operations|readlink]] - Print resolved symbolic links

## Quick Reference

### Common Commands
```bash
# Create symbolic link
ln -s target link

# Create hard link
ln target link

# Force create link
ln -sf target link

# Create verbose
ln -sv target link
```

### Verification Commands
```bash
# Check if symbolic link
ls -l link_name

# Print resolved path
readlink -f link_name
```

## Tips and Tricks
1. Use absolute paths for system links
2. Verify link targets
3. Clean up broken links
4. Document link relationships

### Common Use Cases
```bash
# Link configuration
ln -s ~/.config/app/config ~/.app/config

# Create version alternatives
ln -s python3.9 python3

# Link to shorter name
ln -s long_filename.txt short.txt
```

## Link Types Comparison

### Hard Links
- Same inode as target
- Cannot cross filesystems
- Cannot link directories
- Target must exist
```bash
# Create hard link
ln file.txt hardlink.txt
```

### Symbolic Links
- Points to file path
- Can cross filesystems
- Can link directories
- Target can be nonexistent
```bash
# Create symbolic link
ln -s file.txt symlink.txt
```

### Management Tools
```bash
# Find broken links
find . -type l -! -exec test -e {} \; -print

# Update multiple links
ln -sf target link1 link2 link3

# Check link status
file link_name
```