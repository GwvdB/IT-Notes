#linux #commands #permissions #system-administration 

The `chmod` command in Linux is used to change the access permissions of files and directories. See also [[Linux-Commands#Permissions]].

## Basic Syntax
```
chmod [OPTIONS] MODE FILE(s)
```

## Common Usage Patterns

### Change File Permissions
```bash
chmod 644 file.txt
chmod u+r,g+w,o-x file.txt
```

### Change Directory Permissions
```bash
chmod 755 directory/
chmod u+rwx,g+rx,o+r directory/
```

### Recursive Changes
```bash
chmod -R 644 directory/
chmod -R u+rw,g+r,o-wx directory/
```

## Permissions Notation

### Numeric Mode
- 4 = read
- 2 = write 
- 1 = execute
- Example: `chmod 644 file.txt`

### Symbolic Mode
- `u` = user
- `g` = group  
- `o` = others
- `+` = add permissions
- `-` = remove permissions
- `=` = set permissions
- Example: `chmod u+rw,go-wx file.txt`

## Options

### Recursive Changes (-R)
```bash
chmod -R 755 directory/
```
- Changes files and directories
- Follows subdirectories

### Change Symlinks (-h)
```bash
chmod -h 644 symlink
```
- Changes permissions of the symlink, not the target

### Reference File (--reference)
```bash
chmod --reference=source_file target_file
```
- Sets permissions to match the reference file

### Verbose Output (-v)
```bash
chmod -v 644 file.txt
```
- Shows all changes being made

## Common Scenarios

### Web Server Setup
```bash
# Set permissions for web files
chmod 644 /var/www/html/*
chmod 755 /var/www/html/
```

### Development Environment  
```bash
# Set project permissions
chmod -R 644 /opt/project/
chmod -R u+rw,g+rx,o+r /opt/project/
```

### System Administration
```bash
# Change log file permissions
chmod 644 /var/log/syslog
chmod u+rw,go+r /var/log/syslog
```

## Error Handling

### Common Errors
1. Permission Denied
   ```bash
   # Solution: Use sudo
   sudo chmod 755 directory/
   ```

2. Invalid Mode
   ```bash
   # Check mode format
   chmod u+x,g+w,o+r file.txt
   ```

3. Operation Not Permitted
   ```bash
   # Check filesystem permissions
   ls -ld directory/
   ```

## Best Practices

### Security Considerations
1. Use least privilege principle
2. Avoid overly permissive modes
3. Review permissions regularly
4. Document permission changes

### Maintenance Tips
1. Use symbolic mode for clarity
2. Perform periodic permission audits
3. Backup before making bulk changes
4. Create custom permission profiles

## Scripting Examples

### Basic Permission Change
```bash
#!/bin/bash
# Change project file permissions
project_dir="/opt/project"
mode="644"

find "$project_dir" -type f -exec chmod "$mode" {} +
chmod "$mode" "$project_dir"
```

### Recursive Directory Changes
```bash
#!/bin/bash
change_permissions() {
    local target="$1"
    local mode="$2"
    
    if [ ! -e "$target" ]; then
        echo "Target doesn't exist: $target"
        return 1
    fi
    
    if ! chmod -R "$mode" "$target"; then
        echo "Failed to change permissions of $target"
        return 1
    fi
    
    echo "Successfully changed permissions of $target to $mode"
}

change_permissions "/opt/project" "u+rw,g+rx,o+r"
```

## Related Commands
- [[Linux-Commands#Permissions|chown]] - Change owner and group
- [[Linux-Commands#Permissions|chgrp]] - Change group
- [[Linux-Commands#User Management|umask]] - Set default permissions
- [[Linux-Commands#File Management|touch]] - Create new files

## Quick Reference

### Common Commands
```bash
# Change file mode
chmod 644 file.txt
chmod u+rw,go+r file.txt

# Change directory mode
chmod 755 directory/
chmod u+rwx,go+rx directory/

# Recursive changes
chmod -R 644 directory/
chmod -R u+rw,go+r directory/
```

### Verification Commands
```bash
# Check permissions
ls -l file.txt
ls -ld directory/

# List user/group info
id
groups
```

## Tips and Tricks
1. Use symbolic mode for clarity
2. Audit permissions regularly
3. Backup before bulk changes
4. Create custom permission profiles

### Common Permission Scenarios
```bash
# Set web server permissions
chmod 644 /var/www/html/*
chmod 755 /var/www/html/

# Set project directory permissions 
chmod -R 644 /opt/project/
chmod -R u+rw,g+rx,o+r /opt/project/

# Match existing permissions
chmod --reference=source_file target_file
```
