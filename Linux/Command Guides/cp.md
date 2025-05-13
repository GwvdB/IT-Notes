#linux #commands #file-management

The `cp` command in Linux is used to copy files and directories. See also [[Linux-Commands#File Operations]].

## Basic Usage
```bash
cp [options] source destination
```

### Common Options
- `-r`, `-R`: Recursive copy (directories)
- `-i`: Interactive (prompt before overwrite)
- `-f`: Force copy (overwrite without prompt)
- `-v`: Verbose output
- `-p`: Preserve attributes
- `-l`: Create hard links
- `-s`: Create symbolic links
- `-u`: Update (copy only newer files)
- `-a`: Archive mode (same as -dr --preserve=all)
- `-n`: No overwrite of existing files
- `--backup`: Make backup of existing files

### Examples
```bash
# Basic file copy
cp file.txt backup.txt

# Copy directory recursively
cp -r source_dir/ destination_dir/

# Preserve attributes
cp -p original.txt copy.txt

# Copy with backup
cp --backup=numbered file.txt file.txt

# Copy multiple files to directory
cp file1.txt file2.txt destination/
```

### Advanced Usage
```bash
# Copy with progress
cp -v large_file.iso /backup/

# Update only newer files
cp -ru /source/* /destination/

# Create symbolic links
cp -s /path/to/file link_name
```
