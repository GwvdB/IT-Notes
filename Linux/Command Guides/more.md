#linux #commands #text-processing #file-viewing

The `more` command in Linux is a simple file pager for viewing text files. See also [[Linux-Commands#File Viewing]].

## Basic Syntax
```bash
more [OPTIONS] FILE
```

## Common Usage Patterns

### View File
```bash
more filename.txt
```

### View Multiple Files
```bash
more file1.txt file2.txt
```

### View Command Output
```bash
command | more
```

## Options

### Skip Lines (+n)
```bash
more +10 filename.txt
```
- Start display at line n

### Lines Per Screen (-n)
```bash
more -10 filename.txt
```
- Set screen size to n lines

### No Scroll (-d)
```bash
more -d filename.txt
```
- Display help prompt

### Clear Screen (-c)
```bash
more -c filename.txt
```
- Clear screen before display

## Navigation Commands

### Basic Movement
- `Space` - Next page
- `Enter` - Next line
- `b` - Back one page (if supported)
- `=` - Show current line number
- `q` - Quit
- `/pattern` - Search pattern

## Common Scenarios

### File Viewing
```bash
# View text file
more textfile.txt

# View with line numbers
more -d filename.txt

# Start at specific line
more +100 filename.txt
```

### Command Output
```bash
# Pipe directory listing
ls -l | more

# View system files
more /etc/passwd
```

## Best Practices

### Usage Guidelines
1. Use for simple viewing
2. Consider `less` for large files
3. Remember quit command
4. Use clear screen when needed

### When to Use More
1. Quick file viewing
2. Simple forward scrolling
3. Basic text navigation
4. System compatibility

## Quick Reference

### Common Commands
```bash
# Basic viewing
more file.txt

# Multiple files
more file1.txt file2.txt

# Start at line 10
more +10 file.txt

# Clear screen mode
more -c file.txt
```

## Related Commands
- [[Linux-Commands#File Viewing|less]] - Advanced pager
- [[Linux-Commands#File Viewing|cat]] - Concatenate files
- [[Linux-Commands#File Viewing|view]] - Read-only vim

## Comparison with Less
1. More limited functionality
2. Forward-only scrolling (typically)
3. Simpler interface
4. Available on most systems
5. Memory efficient

## Usage Tips
1. Use `q` to quit
2. Space for next page
3. Enter for next line
4. `/` for basic search