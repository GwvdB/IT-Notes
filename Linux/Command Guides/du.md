#linux #commands #file-management #system-administration

The `du` (disk usage) command in Linux is used to estimate file space usage. It provides information about the disk space occupied by files and directories. See also [[Linux-Commands#System Status]].

## Basic Syntax
```
du [OPTIONS] [FILE(s)]
```

## Common Usage Patterns

### Get Directory Size
```bash
du /opt/project
du -h /opt/project
```

### Get All Files in Directory
```bash
du -a /opt/project
du -a -h /opt/project
```

### Get Total Directory Size Recursively
```bash
du -s /opt/project
du -sh /opt/project
```

### Get Size of Single File
```bash
du file.txt
du -h file.txt
```

## Options

### Human-Readable Output (-h)
```bash
du -h /opt/project
```
- Displays sizes in human-readable format (e.g., KB, MB, GB)

### Summarize Output (-s)
```bash
du -s /opt/project
```
- Displays the total size of the directory/file

### All Files (-a)
```bash
du -a /opt/project
```
- Displays the size of every file and directory

### Maximum Depth (-d N)
```bash
du -d 1 /opt/project
```
- Limits the depth of the directory tree to N levels

### Exclude Files (-x)
```bash
du --exclude='*.log' /opt/project
```
- Excludes files matching the given pattern

### Apparent Size (-A)
```bash
du -A /opt/project
```
- Shows the apparent size, which includes sparse files

### Total Size (-c)
```bash
du -c /opt/project
```
- Displays the grand total at the end of the output

## Common Scenarios

### Disk Space Analysis
```bash
# Get top 10 largest directories
du -h / | sort -hr | head -10

# Find directories over 1GB
du -h / | grep -E '^[0-9\.]+G'
```

### System Cleanup
```bash
# Find large files to delete
du -a /var/log | sort -nr | head -n 20

# Remove old log files
find /var/log -type f -mtime +30 -exec rm {} \;
```

### Backup Planning
```bash
# Estimate backup size
du -sh /home/user /opt/project
```

## Error Handling

### Common Errors
1. Permission Denied
   ```bash
   # Solution: Use sudo
   sudo du /opt/project
   ```

2. No Such File or Directory
   ```bash
   # Verify path
   du /non-existent-directory
   ```

3. Device or Resource Busy
   ```bash
   # Try again later or use alternative options
   du -x /mnt/busy-filesystem
   ```

## Best Practices

### Security Considerations
1. Avoid running as root when not necessary
2. Carefully review output for sensitive data
3. Use appropriate options to limit exposures

### Maintenance Tips
1. Regularly monitor disk usage
2. Automate cleanup scripts
3. Implement disk quota policies
4. Backup critical data before deleting

## Scripting Examples

### Get Top 10 Largest Directories
```bash
#!/bin/bash
du -h / | sort -hr | head -10
```

### Find Directories Over 1GB
```bash
#!/bin/bash
du -h / | grep -E '^[0-9\.]+G'
```

### Clean Up Old Log Files
```bash
#!/bin/bash
find /var/log -type f -mtime +30 -exec rm {} \;
```

## Related Commands
- [[Linux-Commands#File Management|ls]] - List directory contents
- [[Linux-Commands#File Management|find]] - Search for files
- [[Linux-Commands#File Management|rm]] - Remove files
- [[Linux-Commands#System Administration|df]] - Report file system disk space usage

## Quick Reference

### Common Commands
```bash
# Get directory size
du /opt/project
du -h /opt/project

# Get all files in directory
du -a /opt/project
du -a -h /opt/project  

# Get total directory size recursively
du -s /opt/project
du -sh /opt/project

# Get size of single file
du file.txt
du -h file.txt
```

### Verification Commands
```bash
# Check disk space
df -h
```

## Tips and Tricks
1. Use human-readable output (-h)
2. Summarize output with (-s)
3. Exclude files/directories as needed
4. Automate cleanup tasks
5. Monitor disk space regularly

### Common du Scenarios
```bash
# Find top 10 largest directories
du -h / | sort -hr | head -10

# Find directories over 1GB
du -h / | grep -E '^[0-9\.]+G'

# Clean up old log files
find /var/log -type f -mtime +30 -exec rm {} \;
```