#linux #commands #filesystem #system-administration

The `mkdir` command in Linux is used to create directories (folders). See also [[Linux-Commands#File System]].

## Basic Syntax
```bash
mkdir [OPTIONS] DIRECTORY...
```

## Common Usage Patterns

### Create Single Directory
```bash
mkdir directory_name
```

### Create Multiple Directories
```bash
mkdir dir1 dir2 dir3
```

### Create Parent Directories
```bash
mkdir -p path/to/new/directory
```

## Options

### Create Parent Directories (-p)
```bash
mkdir -p /path/to/deep/directory
```
- Creates all parent directories if they don't exist
- No error if directory exists
- Essential for scripts and automation

### Set Permissions (-m)
```bash
mkdir -m 755 directory_name
```
- Sets specific permissions on creation
- Uses chmod-style numeric modes

### Verbose Output (-v)
```bash
mkdir -v directory_name
```
Shows what is being created

### Parents with Mode (-pm)
```bash
mkdir -pm 755 path/to/new/directory
```
Combines parent creation with permission setting

## Common Scenarios

### Project Setup
```bash
# Create standard project structure
mkdir -p project/{src,docs,tests,build}
```

### Web Server Directory Structure
```bash
# Create web application directories
mkdir -p /var/www/mysite/{public_html,logs,backup}
```

### User Home Directory Setup
```bash
# Create user directories
mkdir -p ~/Documents ~/Downloads ~/Pictures
```

## Error Handling

### Common Errors
1. Permission Denied
   ```bash
   # Solution: Use sudo
   sudo mkdir /opt/newdir
   ```

2. Directory Exists
   ```bash
   # Use -p to ignore
   mkdir -p existing_directory
   ```

3. Parent Directory Missing
   ```bash
   # Use -p to create parents
   mkdir -p /path/to/new/directory
   ```

## Best Practices

### Security Considerations
1. Set appropriate permissions on creation
2. Consider using umask for default permissions
3. Be cautious with sudo usage
4. Verify directory locations before creation

### Directory Structure Tips
1. Use meaningful names
2. Follow system directory conventions
3. Document directory purposes
4. Maintain consistent naming patterns

## Scripting Examples

### Basic Directory Creation
```bash
#!/bin/bash
# Create project structure
project_name="myproject"

mkdir -p "$project_name"/{src,docs,tests} || {
    echo "Failed to create project structure"
    exit 1
}
```

### With Error Checking
```bash
#!/bin/bash
directory="/path/to/new/dir"

if [ ! -d "$directory" ]; then
    mkdir -p "$directory" || {
        echo "Failed to create $directory"
        exit 1
    }
    echo "Directory created successfully"
else
    echo "Directory already exists"
fi
```

## System Integration

### Temporary Directories
```bash
# Create temp directory with specific permissions
mkdir -m 700 /tmp/secure_temp
```

### Application Setup
```bash
# Create application directories with proper ownership
sudo mkdir -p /opt/myapp/{bin,conf,logs}
sudo chown -R myapp:myapp /opt/myapp
```

## Related Commands
- [[Linux-Commands#File System|rmdir]] - Remove directories
- [[Linux-Commands#Permissions|chmod]] - Change directory permissions
- [[Linux-Commands#Permissions|chown]] - Change directory ownership
- [[Linux-Commands#File System Navigation|ls]] - List directory contents

## Quick Reference

### Common Commands
```bash
# Basic directory creation
mkdir directory_name

# Create with parents
mkdir -p /path/to/directory

# Create with permissions
mkdir -m 755 directory_name

# Create multiple directories
mkdir dir1 dir2 dir3

# Create nested structure
mkdir -p project/{src,lib,doc}
```

### Verification Commands
```bash
# Verify creation
ls -ld directory_name

# Check permissions
stat directory_name
```

## Tips and Tricks
1. Use brace expansion for complex structures
2. Combine with chmod/chown for complete setup
3. Use -v for verification in scripts
4. Remember to set appropriate permissions