#linux #commands #archiving #compression

The `tar` command in Linux is used for archiving files and directories. See also [[Linux-Commands#File Operations]].

## Basic Syntax
```bash
tar [OPTIONS] [ARCHIVE_NAME] [FILE(S)]
```

## Common Usage Patterns

### Create Archive
```bash
tar -cf archive.tar files
```

### Extract Archive
```bash
tar -xf archive.tar
```

### Create Compressed Archive
```bash
tar -czf archive.tar.gz files
```

## Options

### Creation Options (-c)
```bash
tar -c file.tar directory/
```
- Creates a new archive

### Extract Options (-x)
```bash
tar -x file.tar
```
- Extracts files from archive

### File Options (-f)
```bash
tar -f archive.tar
```
- Specifies archive file name

### Compression Options
```bash
# gzip compression (-z)
tar -czf archive.tar.gz files

# bzip2 compression (-j)
tar -cjf archive.tar.bz2 files

# xz compression (-J)
tar -cJf archive.tar.xz files
```

### Verbose Output (-v)
```bash
tar -cvf archive.tar files
```
- Shows processed files

### Update Archive (-u)
```bash
tar -uf archive.tar newfile
```
- Adds files newer than copy in archive

### Append Files (-r)
```bash
tar -rf archive.tar file
```
- Appends files to archive

## Common Scenarios

### Directory Archiving
```bash
# Archive entire directory
tar -czf backup.tar.gz /path/to/directory

# Archive with base directory
tar -czf backup.tar.gz -C /path/to directory
```

### Selective Archiving
```bash
# Archive specific file types
tar -czf code.tar.gz *.c *.h

# Exclude certain files
tar -czf backup.tar.gz --exclude='*.tmp' directory/
```

## Error Handling

### Common Errors
1. Permission Denied
   ```bash
   # Solution: Use sudo
   sudo tar -czf backup.tar.gz /etc
   ```

2. No Space Left
   ```bash
   # Check available space first
   df -h
   ```

3. Archive Corruption
   ```bash
   # Test archive integrity
   tar -tf archive.tar
   ```

## Best Practices

### Usage Guidelines
1. Always use -f option
2. Choose appropriate compression
3. Test archives after creation
4. Maintain proper permissions

### File Handling
1. Verify source files exist
2. Check destination space
3. Use relative paths when possible
4. Preserve file permissions

## Scripting Examples

### Basic Backup Script
```bash
#!/bin/bash
backup_dir="/path/to/backup"
date=$(date +%Y%m%d)
tar -czf "$backup_dir/backup-$date.tar.gz" /important/files
```

### With Error Checking
```bash
#!/bin/bash
archive="backup.tar.gz"
if tar -czf "$archive" files/; then
    echo "Archive created successfully"
else
    echo "Archive creation failed"
    exit 1
fi
```

## Related Commands
- [[Linux-Commands#File Operations|gzip]] - Compression utility
- [[Linux-Commands#File Operations|bzip2]] - Compression utility
- [[Linux-Commands#File Operations|xz]] - Compression utility
- [[Linux-Commands#File Operations|find]] - File searching

## Quick Reference

### Common Commands
```bash
# Create archive
tar -cf archive.tar files

# Create compressed archive
tar -czf archive.tar.gz files

# Extract archive
tar -xf archive.tar

# List contents
tar -tf archive.tar

# Extract single file
tar -xf archive.tar file
```

### Verification Commands
```bash
# Check archive integrity
tar -tf archive.tar

# Check compression type
file archive.tar.gz
```

## Tips and Tricks
1. Use -v for verbose output
2. Choose compression based on needs
3. Test archives after creation
4. Use relative paths
5. Preserve permissions with -p

### Common Use Cases
```bash
# System backup
tar -czpf system-backup.tar.gz /etc /home

# Extract to different directory
tar -xf archive.tar -C /target/directory

# Exclude version control
tar -czf project.tar.gz --exclude='.git' ./project
```