#linux #commands #shell #system

The `history` command in Linux displays or manipulates the command history list. See also [[Linux-Commands#Shell]].

## Basic Syntax
```bash
history [OPTIONS] [NUMBER]
```

## Common Usage Patterns

### Show History
```bash
history
```

### Show Last N Commands
```bash
history 10
```

### Clear History
```bash
history -c
```

## Options

### Clear (-c)
```bash
history -c
```
- Clear the history list

### Delete Entry (-d)
```bash
history -d offset
```
- Delete entry at offset

### Append (-a)
```bash
history -a
```
- Append new entries

### Read (-r)
```bash
history -r
```
- Read history file

## History Expansion

### Event Designators
- `!!` - Previous command
- `!n` - Command number n
- `!-n` - n commands ago
- `!string` - Most recent command starting with string
- `!?string` - Most recent command containing string

### Word Designators
- `:0` - Command word
- `:n` - nth word
- `:^` - First argument
- `:$` - Last argument
- `:*` - All arguments

## Common Scenarios

### Command Reuse
```bash
# Repeat last command
!!

# Reuse with sudo
sudo !!

# Use specific command
!1234
```

### History Management
```bash
# Save current history
history -a

# Clear and reload
history -c
history -r
```

## Environment Variables

### HISTFILE
```bash
echo $HISTFILE
```
- Location of history file

### HISTSIZE
```bash
echo $HISTSIZE
```
- Maximum number of commands

### HISTCONTROL
```bash
export HISTCONTROL=ignoredups
```
- Control what's recorded

## Best Practices

### Usage Guidelines
1. Use meaningful command names
2. Clear sensitive information
3. Set appropriate size limits
4. Regular backup of history

### Security Considerations
1. Remove sensitive commands
2. Control history file permissions
3. Set HISTCONTROL appropriately
4. Clear when needed

## Quick Reference

### Common Commands
```bash
# Show all history
history

# Show last 10 commands
history 10

# Clear history
history -c

# Delete entry
history -d 1234
```

## Related Commands
- [[Linux-Commands#Shell|fc]] - Fix command
- [[Linux-Commands#Shell|bash]] - Shell options
- [[Linux-Commands#Shell|alias]] - Command aliases