#linux #commands #text-editing #system-administration

The `vi` (Visual Editor) command in Linux is a powerful and widely-used text editor. It provides a modal interface with different modes for editing, navigating, and executing commands.

## Basic Syntax
```
vi [OPTIONS] [FILE(s)]
```

## Common Usage Patterns

### Open a File
```bash
vi file.txt
```

### Create a New File
```bash
vi new_file.txt
```

### Open Multiple Files
```bash
vi file1.txt file2.txt file3.txt
```

### Open a File at a Specific Line
```bash
vi +42 file.txt
```

### Open a File in Read-Only Mode
```bash
vi -R file.txt
```

## Common Vi Modes

### Normal Mode
- Default mode for navigation and commands
- Used for moving the cursor, deleting/copying text, etc.

### Insert Mode
- Entered by pressing `i`, `a`, `o`, etc.
- Used for inserting and editing text

### Command Mode
- Entered by pressing `:` 
- Used for executing commands, such as saving, quitting, or searching

### Visual Mode
- Entered by pressing `v`
- Used for selecting and manipulating text

## Common Vi Commands

### Navigate
- `h`, `j`, `k`, `l`: Move left, down, up, right
- `w`, `b`: Move to next/previous word
- `0`, `$`: Move to start/end of line
- `G`, `gg`: Move to last/first line

### Edit
- `i`, `a`: Enter insert mode before/after cursor
- `x`: Delete character under cursor
- `dd`: Delete current line
- `yy`: Yank (copy) current line
- `p`: Paste text

### Save and Quit
- `:w`: Save file
- `:q`: Quit
- `:wq`: Save and quit
- `:q!`: Quit without saving

### Search and Replace
- `/pattern`: Search forward for pattern
- `?pattern`: Search backward for pattern
- `:%s/old/new/g`: Replace all occurrences of "old" with "new"

### Vi Modes
- `i`: Enter insert mode
- `v`: Enter visual mode
- `:`: Enter command mode

## Common Scenarios

### Edit Configuration Files
```bash
# Edit the nginx configuration file