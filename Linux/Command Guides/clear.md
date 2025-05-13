#linux #commands #command-line-outputs 

The `clear` command in Linux is used to remove all previous commands and outputs in the command line interface. See also [[Linux-Commands#System Cleanup]].
## Basic Usage
`clear` - Clears the terminal screen

## Syntax
```bash
clear [options]
```

## Options
- `-x`: Don't set cursor position
- `-T TERM`: Use this terminal type instead of $TERM
- `-V`: Display version information
- `-h`: Display help message

## Examples

### Basic Clear
```bash
clear
```
Clears screen and moves cursor to top

### Clear Without Repositioning Cursor
```bash
clear -x
```

## How It Works
1. Sends special control sequences to terminal
2. Different terminals may behave differently
3. Usually moves cursor to top-left position

## Alternative Methods
1. Keyboard shortcut: Ctrl + L
2. Reset command: `reset`
3. Clear scrollback: `clear && printf '\e[3J'`

## Common Use Cases
1. Clean up cluttered terminal
2. Prepare for new output
3. Improve screenshot readability
4. Remove sensitive information from view

## Tips
1. Add alias for custom clear behavior
2. Use in scripts for clean output
3. Combine with other commands

## Environment Variables
- `TERM`: Terminal type
- `TERMINFO`: Terminal information database

## Related Commands
- `reset`: More thorough terminal reset
- `tput`: Terminal manipulation