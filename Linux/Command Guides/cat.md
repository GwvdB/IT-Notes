#linux #commands #file-operations #text-processing

The `cat` command in Linux is used to concatenate and display file contents. See also [[Linux-Commands#Viewing Files]].

## Basic Syntax
```bash
cat [OPTIONS] [FILE(s)]
```

## Common Usage Patterns

### Display File Contents
```bash
cat filename.txt
```

### Concatenate Multiple Files
```bash
cat file1.txt file2.txt
```

### Create New File with Input
```bash
cat > newfile.txt
# Type content, press Ctrl+D when done
```

### Append to Existing File
```bash
cat >> existing.txt
# Type content, press Ctrl+D when done
```

## Options

### Line Numbers (-n)
```bash
cat -n file.txt
```
- Shows all line numbers

### Numbered Non-blank (-b)
```bash
cat -b file.txt
```
- Numbers only non-blank lines

### Show Special Characters (-A)
```bash
cat -A file.txt
```
- Shows non-printing characters
- Shows line endings
- Shows tabs and spaces

### Squeeze Blank Lines (-s)
```bash
cat -s file.txt
```
- Combines multiple blank lines into one

### Show Tabs (-T)
```bash
cat -T file.txt
```
- Displays TAB characters as ^I

### Show Line Ends (-E)
```bash
cat -E file.txt
```
- Shows $ at end of each line

## Common Scenarios

### File Viewing
```bash
# View configuration file
cat /etc/hostname

# View multiple config files
cat /etc/*.conf
```

### File Creation
```bash
# Create file with content
cat > script.sh << 'EOF'
#!/bin/bash
echo "Hello World"
EOF
```

### File Concatenation
```bash
# Combine log files
cat access.log.* > combined_logs.txt
```

## Error Handling

### Common Errors
1. File Not Found
   ```bash
   # Check file existence first
   [ -f file.txt ] && cat file.txt || echo "File not found"
   ```

2. Permission Denied
   ```bash
   # Solution: Use sudo for protected files
   sudo cat /etc/shadow
   ```

3. Binary File Content
   ```bash
   # Use -v to make binary content viewable
   cat -v binary_file
   ```

## Best Practices

### Usage Guidelines
1. Avoid using cat for very large files
2. Use [[less]]/[[more]] for paginated viewing
3. Consider [[head]]/[[tail]] for partial views
4. Use text editors for large edits

### File Handling
1. Check file type before reading
2. Verify file permissions
3. Use appropriate tools for binary files
4. Handle special characters properly

## Scripting Examples

### Basic File Processing
```bash
#!/bin/bash
# Process multiple files
for file in *.txt; do
    echo "=== $file ==="
    cat "$file"
    echo
done
```

### With Error Checking
```bash
#!/bin/bash
file="input.txt"

if [ -f "$file" ]; then
    if [ -r "$file" ]; then
        cat "$file"
    else
        echo "Cannot read $file"
        exit 1
    fi
else
    echo "File $file not found"
    exit 1
fi
```

## System Integration

### Log Viewing
```bash
# View system logs
sudo cat /var/log/syslog

# View multiple logs
cat /var/log/*.log
```

### Configuration Management
```bash
# Backup before editing
cat original.conf > backup.conf

# Combine config files
cat config.d/* > combined.conf
```

## Related Commands
- [[Linux-Commands#File Operations|less]] - View files with pagination
- [[Linux-Commands#File Operations|more]] - View files with pagination
- [[Linux-Commands#File Operations|head]] - View beginning of file
- [[Linux-Commands#File Operations|tail]] - View end of file
- [[Linux-Commands#Text Processing|grep]] - Search file contents

## Quick Reference

### Common Commands
```bash
# View file
cat file.txt

# Number lines
cat -n file.txt

# Show special characters
cat -A file.txt

# Combine files
cat file1 file2 > combined

# Create new file
cat > newfile.txt

# Append to file
cat >> existing.txt
```

### Verification Commands
```bash
# Check file type
file filename

# Check permissions
ls -l filename
```

## Tips and Tricks
1. Use `-A` for debugging whitespace
2. Combine with grep for searching
3. Use redirection for file creation
4. Remember Ctrl+D to end input

### Common Use Cases
```bash
# View compressed files
zcat file.gz

# Number non-blank lines
cat -b file.txt

# Multiple file operations
cat file1 file2 | grep "pattern"
```