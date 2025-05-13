#linux #commands #text-processing #file-viewing

The `less` command in Linux is a file pager that allows forward and backward movement in text files. See also [[Linux-Commands#File Viewing]].

## Basic Syntax
```bash
less [OPTIONS] FILE
```

## Common Usage Patterns

### View File
```bash
less filename.txt
```

### View Multiple Files
```bash
less file1.txt file2.txt
```

### View Command Output
```bash
command | less
```

## Options

### Line Numbers (-N)
```bash
less -N filename.txt
```
- Show line numbers

### Ignore Case (-I)
```bash
less -I filename.txt
```
- Case-insensitive search

### Show Status (-M)
```bash
less -M filename.txt
```
- Show detailed prompt

### Quit if One Screen (-F)
```bash
less -F filename.txt
```
- Exit if content fits on one screen

### Raw Control Chars (-r)
```bash
less -r filename.txt
```
- Display control characters

## Navigation Commands

### Basic Movement
- `Space/f` - Forward one window
- `b` - Backward one window
- `d` - Forward half window
- `u` - Backward half window
- `j/↓` - Forward one line
- `k/↑` - Backward one line
- `G` - End of file
- `g` - Start of file

### Search
- `/pattern` - Search forward
- `?pattern` - Search backward
- `n` - Next match
- `N` - Previous match

### Multiple Files
- `:n` - Next file
- `:p` - Previous file
- `:x` - First file
- `:d` - Remove current file

## Common Scenarios

### File Viewing
```bash
# View log file
less /var/log/syslog

# View compressed file
zless compressed.gz

# View with line numbers
less -N large_file.txt
```

### Command Output
```bash
# Pipe long output
ls -R / | less

# View command help
man command | less
```

## Best Practices

### Usage Guidelines
1. Use search efficiently
2. Mark important positions
3. Use line numbers for reference
4. Take advantage of screen size

### Navigation Tips
1. Learn key bindings
2. Use marks for navigation
3. Use pattern search
4. Remember quit command 'q'

## Quick Reference

### Common Commands
```bash
# Basic viewing
less file.txt

# With line numbers
less -N file.txt

# Multiple files
less file1.txt file2.txt

# With status line
less -M file.txt
```

## Related Commands
- [[Linux-Commands#File Viewing|more]] - Simple pager
- [[Linux-Commands#File Viewing|cat]] - Concatenate files
- [[Linux-Commands#File Viewing|view]] - Read-only vim