#linux #commands #process-management #system-administration

The `killall` command in Linux is used to terminate processes by name. It sends a specified signal to all processes running under the invoking user's real user ID with the given name. See also [[Linux-Commands#Process Control]]

## Basic Syntax
```
killall [OPTIONS] PROCESS_NAME
```

## Common Usage Patterns

### Terminate All Instances of a Process
```bash
killall firefox
```

### Send a Specific Signal
```bash
killall -s SIGTERM firefox
killall -TERM firefox
```

### Terminate Processes Owned by a User
```bash
killall -u username
```

### Terminate a Process Tree
```bash
pkill -9 -P 12345
```

## Options

### Signal (-s, -l)
```bash
killall -s SIGTERM firefox
killall -15 firefox
```
- Specifies the signal to send to the processes

### User (-u)
```bash
killall -u username
```
- Terminates all processes owned by the specified user

### Ignore Case (-I)
```bash
killall -I firefox
```
- Matches process names case-insensitively

### Verbose Output (-v)
```bash
killall -v firefox
```
- Shows information about the signals sent

### Interactively Select (-i)
```bash
killall -i firefox
```
- Prompts before killing each process

## Common Scenarios

### Terminate All Instances of a Program
```bash
# Terminate all Firefox processes
killall firefox

# Use SIGKILL to force termination
killall -s SIGKILL firefox
```

### Terminate Processes Owned by a User
```bash
# Kill all processes owned by "username"
killall -u username
```

### Terminate a Process Tree
```bash
# Terminate all child processes of 12345
pkill -9 -P 12345
```

## Error Handling

### Common Errors
1. No Matching Processes Found
   ```bash
   # Verify process name
   killall non-existent-process
   ```

2. Operation Not Permitted
   ```bash
   # Check user permissions
   sudo killall firefox
   ```

3. Invalid Signal
   ```bash
   # Check signal name/number
   killall -s SIGFOO firefox
   ```

## Best Practices

### Security Considerations
1. Use the least privilege principle
2. Carefully review processes before termination
3. Avoid terminating critical system processes

### Maintenance Tips
1. Document process termination procedures
2. Implement process monitoring and alerting
3. Automate process cleanup tasks

## Scripting Examples

### Kill All Instances of a Program
```bash
#!/bin/bash
program="firefox"

# Terminate all instances
killall "$program"
if [ $? -ne 0 ]; then
    # Use SIGKILL to force termination
    killall -s SIGKILL "$program"
fi
```

### Kill All Processes Owned by a User
```bash
#!/bin/bash
username="myuser"

# Terminate all processes owned by "username"
killall -u "$username"
```

## Related Commands
- [[Linux-Commands#Process Management|ps]] - List running processes
- [[Linux-Commands#Process Management|kill]] - Terminate or signal a process
- [[Linux-Commands#Process Management|pkill]] - Kill processes by name
- [[Linux-Commands#Process Management|top]] - Interactive process viewer

## Quick Reference

### Common Commands
```bash
# Terminate all instances of a process
killall firefox

# Send a specific signal
killall -s SIGTERM firefox
killall -TERM firefox

# Terminate processes owned by a user
killall -u username
```

### Verification Commands
```bash
# Check running processes
ps
top
```

## Tips and Tricks
1. Use SIGTERM first, then SIGKILL if needed
2. Terminate all instances of a program
3. Terminate processes owned by a specific user
4. Terminate a process tree

### Common killall Scenarios
```bash
# Kill all Firefox processes
killall firefox
killall -s SIGKILL firefox

# Kill all processes owned by "username"
killall -u username
```