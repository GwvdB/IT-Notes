#linux #commands #process-management #system-administration

The `kill` command in Linux is used to terminate or signal a running process. It allows you to send specific signals to processes, such as SIGTERM (terminate) or SIGKILL (kill). See also [[Linux-Commands#Process Control]]

## Basic Syntax
```
kill [OPTIONS] PID(s)
```

## Common Usage Patterns

### Terminate a Process
```bash
kill 12345
```

### Send a Specific Signal
```bash
kill -s SIGTERM 12345
kill -TERM 12345
```

### Terminate All Processes Matching a Name
```bash
killall firefox
killall -s SIGKILL firefox
```

### Terminate All Processes Owned by a User
```bash
kill -u username
```

### Terminate a Process Tree
```bash
pkill -9 -P 12345
```

## Options

### Signal (-s, -l)
```bash
kill -s SIGTERM 12345
kill -15 12345
```
- Specifies the signal to send to the process

### Process ID (-p)
```bash
kill -p 12345 67890
```
- Displays the process ID instead of terminating

### User (-u)
```bash
kill -u username
```
- Terminates all processes owned by the specified user

### Process Group (-g)
```bash
kill -g 12345
```
- Sends the signal to the entire process group

### Verbose Output (-v)
```bash
kill -v 12345
```
- Shows information about the signal sent

## Common Scenarios

### Terminate a Hung Process
```bash
# Try SIGTERM first
kill 12345

# Use SIGKILL if SIGTERM fails
kill -9 12345
```

### Kill All Instances of a Program
```bash
# Terminate all Firefox processes
killall firefox

# Use SIGKILL to force termination
killall -s SIGKILL firefox
```

### Terminate Processes Owned by a User
```bash
# Kill all processes owned by "username"
kill -u username
```

### Terminate a Process Tree
```bash
# Terminate all child processes of 12345
pkill -9 -P 12345
```

## Error Handling

### Common Errors
1. No Such Process
   ```bash
   # Verify process ID
   kill 12345
   ```

2. Operation Not Permitted
   ```bash
   # Check user permissions
   sudo kill 12345
   ```

3. Invalid Signal
   ```bash
   # Check signal name/number
   kill -s SIGFOO 12345
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

### Terminate Hung Process
```bash
#!/bin/bash
pid=12345

# Try SIGTERM first
kill "$pid"
if [ $? -ne 0 ]; then
    # Use SIGKILL if SIGTERM fails
    kill -9 "$pid"
fi
```

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

## Related Commands
- [[Linux-Commands#Process Management|ps]] - List running processes
- [[Linux-Commands#Process Management|pkill]] - Kill processes by name
- [[Linux-Commands#Process Management|top]] - Interactive process viewer
- [[Linux-Commands#Process Management|pgrep]] - Find processes by name

## Quick Reference

### Common Commands
```bash
# Terminate a process
kill 12345

# Send a specific signal
kill -s SIGTERM 12345
kill -TERM 12345

# Terminate all processes matching a name
killall firefox
killall -s SIGKILL firefox

# Terminate all processes owned by a user
kill -u username
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

### Common kill Scenarios
```bash
# Terminate a hung process
kill 12345
kill -9 12345

# Kill all Firefox processes
killall firefox
killall -s SIGKILL firefox

# Kill all processes owned by "username"
kill -u username
```