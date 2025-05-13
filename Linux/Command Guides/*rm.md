## Basic Usage
`rm` - Remove files or directories

## Syntax
```bash
rm [options] file(s)
```

## Options
- `-f`: Force remove without confirmation
- `-i`: Interactive mode (prompt before removal)
- `-I`: Prompt once before removing more than three files
- `-r, -R`: Recursive removal (for directories)
- `-d`: Remove empty directories
- `-v`: Verbose mode
- `--preserve-root`: Prevent recursion on root directory
- `--one-file-system`: Stay on one filesystem

## Examples

### Basic File Removal
```bash
# Remove single file
rm file.txt

# Remove multiple files
rm file1.txt file2.txt file3.txt

# Remove using wildcards
rm *.txt
```

### Directory Removal
```bash
# Remove empty directory
rm -d empty_directory

# Remove directory and contents
rm -r directory

# Force remove directory
rm -rf directory
```

### Interactive Removal
```bash
# Prompt for each file
rm -i file*

# Prompt once for multiple files
rm -I file*
```

## Safety Features

### Interactive Prompts
```bash
# Always prompt
rm -i file

# Prompt for dangerous operations
rm -I files*
```

### Preserve Root
```bash
# Prevent recursive deletion from root
rm --preserve-root -rf /
```

## Common Use Cases
1. Clean up temporary files
2. Remove unused files
3. Delete log files
4. Uninstall programs

## Warning Signs
1. `rm -rf /`: NEVER use this
2. `rm -rf *`: Use with extreme caution
3. `rm -rf ./`: Check current directory
4. Wildcards without specific patterns

## Protection Measures
1. Use aliases for safety
```bash
alias rm='rm -i'
```

2. Create trash script
```bash
alias rm='mv -t ~/.trash'
```

3. Use `safe-rm` wrapper

## Common Issues

### Permission Denied
```bash
# Solution: Check permissions
ls -l file
sudo rm file
```

### Device or Resource Busy
```bash
# Solution: Check what's using the file
lsof file
```

### No Such File
```bash
# Solution: Verify file existence
ls -l file
```

## Best Practices
1. Double-check before using -rf
2. Use interactive mode for important operations
3. Verify current directory
4. Make backups of important files
5. Use version control for code

## Recovery Options
1. Backup systems
2. File system snapshots
3. Professional recovery tools
4. Prevention better than recovery

## Related Commands
- `rmdir`: Remove empty directories
- `shred`: Secure file deletion
- `trash-cli`: Move to trash instead
- `find`: Find and remove files