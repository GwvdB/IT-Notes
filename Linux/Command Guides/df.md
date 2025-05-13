#linux #commands #file-management #system-administration

The `df` (disk free) command in Linux is used to display information about the file system, including the amount of available and used space. See also [[Linux-Commands#System Status]].

## Basic Syntax
```
df [OPTIONS] [FILE(s)]
```

## Common Usage Patterns

### Get Disk Usage Summary
```bash
df
df -h
```

### Get Usage for a Specific Filesystem
```bash
df /
df /opt
df /home
```

### Get Usage for All Filesystems
```bash
df -a
```

### Get Inodes Usage
```bash
df -i
df -hi
```

### Get Usage for a Remote Filesystem
```bash
df hostname:/remote/path
```

## Options

### Human-Readable Output (-h)
```bash
df -h
```
- Displays sizes in human-readable format (e.g., KB, MB, GB)

### All Filesystems (-a)
```bash
df -a
```
- Shows information for all mounted filesystems

### Inodes Usage (-i)
```bash
df -i
```
- Displays information about inode usage instead of block usage

### Specific Filesystem Type (-t)
```bash
df -t ext4
```
- Displays information only for the specified filesystem type

### Exclude Filesystem Type (-x)
```bash
df -x tmpfs
```
- Excludes the specified filesystem type from the output

### Summarize Output (-s)
```bash
df -s
```
- Displays a summary line for each filesystem

### Filesystem Typename (-T)
```bash
df -T
```
- Includes the filesystem type in the output

## Common Scenarios

### Disk Space Monitoring
```bash
# Check disk usage
df -h

# Monitor disk usage over time
watch -n 60 "df -h"
```

### Filesystem Analysis
```bash
# Check inode usage
df -i

# Find filesystems over 80% full
df -h | awk '$5 > 80 {print $5, $1}'
```

### Storage Capacity Planning
```bash
# Get usage for all partitions
df -a

# Check remote filesystem usage
df hostname:/remote/path
```

## Error Handling

### Common Errors
1. Device or Resource Busy
   ```bash
   # Try again later or use alternative options
   df -x tmpfs
   ```

2. No Such File or Directory
   ```bash
   # Verify path
   df /non-existent-directory
   ```

3. Permission Denied
   ```bash
   # Solution: Use sudo
   sudo df /opt
   ```

## Best Practices

### Security Considerations
1. Avoid running as root when not necessary
2. Carefully review output for sensitive data
3. Use appropriate options to limit exposures

### Maintenance Tips
1. Regularly monitor disk usage
2. Implement disk quota policies
3. Automate disk usage reporting
4. Backup critical data before making changes

## Scripting Examples

### Get Filesystem Usage Over 80%
```bash
#!/bin/bash
df -h | awk '$5 > 80 {print $5, $1}'
```

### Monitor Disk Usage
```bash
#!/bin/bash
while true; do
    df -h
    sleep 60
done
```

### Get Usage for Remote Filesystem
```bash
#!/bin/bash
remote_host="example.com"
remote_path="/data"
df "$remote_host:$remote_path"
```

## Related Commands
- [[Linux-Commands#File Management|du]] - Estimate file space usage
- [[Linux-Commands#System Administration|mount]] - Mount a filesystem
- [[Linux-Commands#System Administration|umount]] - Unmount a filesystem
- [[Linux-Commands#File Management|find]] - Search for files

## Quick Reference

### Common Commands
```bash
# Get disk usage summary
df
df -h

# Get usage for a specific filesystem  
df /
df /opt
df /home

# Get usage for all filesystems
df -a

# Get inode usage
df -i
df -hi
```

### Verification Commands
```bash
# Check disk space usage
du -h /
```

## Tips and Tricks
1. Use human-readable output (-h)
2. Check inode usage (-i)
3. Filter by filesystem type (-t, -x)
4. Monitor disk usage over time
5. Automate disk usage reporting

### Common df Scenarios
```bash
# Find filesystems over 80% full
df -h | awk '$5 > 80 {print $5, $1}'

# Monitor disk usage
watch -n 60 "df -h"

# Get usage for remote filesystem
df example.com:/data
```