#linux #commands #command-line-outputs

The `pwd` command in Linux is used to show which directory is currently being worked in. See also [[Linux-Commands#Basic Navigation]].
## Basic Usage
`pwd` - Print Working Directory

## Syntax
```bash
pwd [options]
```

## Options
- `-L`: Use PWD from environment (logical)
- `-P`: Avoid symlinks (physical)
- `--help`: Display help message
- `--version`: Display version information

## Examples

### Basic Usage
```bash
pwd
```
Shows current directory path

### Physical Path
```bash
pwd -P
```
Shows actual path, resolving symbolic links

### Logical Path
```bash
pwd -L
```
Shows path with symbolic links preserved

## How It Works
1. Reads current directory location
2. Resolves path components
3. Handles symbolic links based on options
4. Outputs absolute path

## Common Use Cases
1. Verify current location
2. Use in scripts for path operations
3. Debug path-related issues
4. Generate absolute paths

## Output Format
- Absolute path from root (/)
- One line of output
- No trailing slash

## Tips
1. Use in scripts to verify location
2. Combine with other commands
3. Store output in variables

## Environment Variables
- `PWD`: Current working directory
- `OLDPWD`: Previous working directory

## Common Issues
1. Permission denied
   - Solution: Check directory permissions

2. Symlink resolution
   - Solution: Use appropriate option (-L or -P)

## Related Commands
- `cd`: Change directory
- `dirname`: Strip last component
- `basename`: Strip directory path