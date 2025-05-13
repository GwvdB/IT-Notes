#linux #permissions #commands #system-administration

The `chown` command in Linux is used to change file owner and group. See also [[Linux-Commands#Permissions]].

## Basic Syntax
```bash
chown [OPTIONS] OWNER[:GROUP] FILE(s)
```

## Common Usage Patterns

### Change Owner Only
```bash
chown user file.txt
```

### Change Owner and Group
```bash
chown user:group file.txt
```

### Change Group Only
```bash
chown :group file.txt
```
Note: Equivalent to using `chgrp group file.txt`

## Options

### Recursive Changes
```bash
chown -R user:group directory/
```
- Changes ownership of directory and all contents
- Essential for directory trees

### Symbolic Links
- `-h`: Affect symbolic links instead of referenced files
- `-L`: Traverse symbolic links to affect referenced files
```bash
chown -h user:group symlink.txt
```

### Reference File
```bash
chown --reference=ref_file target_file
```
Copies ownership from ref_file to target_file

### Verbose Output
```bash
chown -v user:group file.txt
```
Shows detailed changes being made

## Special Owners/Groups

### Numeric IDs
```bash
chown 1000:1000 file.txt
```
- Can use UID/GID instead of names
- Useful in scripts for consistency

### Special Characters
- `:` - Separator between user and group
- `.` - Group remains unchanged
```bash
chown user. file.txt  # Equivalent to: user:user's_primary_group
```

## Common Scenarios

### Web Server Files
```bash
# Make files owned by web server user
chown -R www-data:www-data /var/www/html/
```

### User Home Directory
```bash
# Fix home directory ownership
chown -R user:user /home/user/
```

### Shared Directory Setup
```bash
# Create shared directory for group
mkdir /shared
chown :developers /shared
chmod g+rwx /shared
```

## Permission Combinations
Often used with [[Linux-Commands#Permissions|chmod]]:
```bash
# Set up new application directory
mkdir /app
chown developer:developer /app
chmod 755 /app
```

## Error Handling

### Common Errors
1. Permission Denied
   ```bash
   # Solution: Use sudo
   sudo chown user:group file.txt
   ```

2. Invalid User/Group
   ```bash
   # Check if user exists
   id username
   # Check if group exists
   getent group groupname
   ```

3. No Such File
   ```bash
   # Use -h to affect symlink itself
   chown -h user:group broken_link
   ```

## Best Practices

### Security Considerations
1. Minimize use of recursive changes
2. Double-check before using sudo
3. Verify user/group existence before changing
4. Backup before bulk changes

### Maintenance Tips
1. Regular permission audits
2. Document ownership changes
3. Use groups for shared access
4. Keep consistent ownership patterns

## Scripting Examples

### Basic Script
```bash
#!/bin/bash
# Change ownership of uploaded files
upload_dir="/uploads"
web_user="www-data"
web_group="www-data"

chown -R $web_user:$web_group "$upload_dir"
```

### With Error Checking
```bash
#!/bin/bash
user="webadmin"
group="www-data"
directory="/var/www/site"

if id "$user" >/dev/null 2>&1; then
    if getent group "$group" >/dev/null 2>&1; then
        chown -R "$user":"$group" "$directory"
    else
        echo "Group $group does not exist"
        exit 1
    fi
else
    echo "User $user does not exist"
    exit 1
fi
```

## System Monitoring

### Audit Commands
```bash
# View file ownership
ls -l file.txt

# Find files owned by user
find /path -user username

# Find files owned by group
find /path -group groupname
```

## Related Commands
- [[Linux-Commands#Permissions|chmod]] - Change file permissions
- [[Linux-Commands#User Management|useradd]] - Create new users
- [[Linux-Commands#User Management|groupadd]] - Create new groups
- [[Linux-Commands#User Management|usermod]] - Modify user properties
- [[Linux-Commands#File System Navigation|ls]] - List directory contents with ownership info

## Quick Reference

### Common Commands
```bash
# Basic ownership change
chown user file.txt

# Change owner and group
chown user:group file.txt

# Recursive change
chown -R user:group directory/

# Change symbolic link
chown -h user:group link

# Copy ownership
chown --reference=source target
```

### Verification Commands
```bash
# Verify changes
ls -l file.txt

# Show user info
id username

# Show group info
getent group groupname
```

## Tips and Tricks
1. Use `chown .` to reset group to user's primary group
2. Combine with `find` for complex operations
3. Use `-v` for verification in scripts
4. Remember to check permissions after ownership changes