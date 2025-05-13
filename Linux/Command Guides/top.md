#linux #commands #process-management #system-administration

The `top` command in Linux is a dynamic real-time process viewer that provides an overview of running processes and system resource utilization. See also [[Linux-Commands#System Status]].

## Basic Syntax
```
top [OPTIONS]
```

## Common Usage Patterns

### Start top
```bash
top
```

### Display top 10 CPU-intensive processes
```bash
top -n 10
```

### Display top 10 memory-intensive processes
```bash
top -o %MEM -n 10
```

### Display real-time updates every 2 seconds
```bash
top -d 2
```

### Display process tree
```bash
top -H
```

## Options

### Update Delay (-d)
```bash
top -d 2
```
- Sets the delay between screen updates (in seconds)

### Maximum Iterations (-n)
```bash
top -n 10
```
- Limits the number of iterations before exiting

### Sort by Field (-o)
```bash
top -o %CPU
top -o %MEM
```
- Sorts the process list by the specified field

### Show Threads (-H)
```bash
top -H
```
- Displays individual threads instead of just processes

### User Filter (-u)
```bash
top -u username
```
- Displays only processes owned by the specified user

### Interactive Commands
- `k`: Kill a process
- `r`: Renice (change priority) a process
- `f`: Add/remove fields to display
- `1`: Toggle per-CPU stats
- `h`: Display help

## Common Scenarios

### Identify Resource Hogs
```bash
# Find top CPU-intensive processes
top -o %CPU -n 10

# Find top memory-intensive processes 
top -o %MEM -n 10
```

### Monitor System Performance
```bash
# Real-time system overview
top

# Monitor specific user's processes
top -u username
```

### Troubleshoot Performance Issues
```bash
# Identify hung/unresponsive processes
top -H

# Monitor process changes over time
top -d 2
```

## Error Handling

### Common Errors
1. Permission Denied
   ```bash
   # Solution: Use sudo
   sudo top
   ```

2. No Such Process
   ```bash
   # Verify process ID
   top -p 12345
   ```

3. Operation Not Permitted
   ```bash
   # Check user permissions
   top -u username
   ```

## Best Practices

### Security Considerations
1. Avoid running as root when not necessary
2. Be cautious when killing or restarting processes
3. Limit access to sensitive process information

### Maintenance Tips
1. Regularly monitor system performance
2. Create automated performance reports
3. Integrate with other monitoring tools
4. Document performance troubleshooting

## Scripting Examples

### Get Top CPU and Memory Usage
```bash
#!/bin/bash
echo "Top CPU Usage:"
top -o %CPU -n 1 | head -n 11

echo "Top Memory Usage:"
top -o %MEM -n 1 | head -n 11
```

### Monitor System Performance
```bash
#!/bin/bash
while true; do
    top -d 2 -n 1
    sleep 2
done
```

## Related Commands
- [[Linux-Commands#Process Management|kill]] - Terminate or signal a process
- [[Linux-Commands#Process Management|pkill]] - Kill processes by name
- [[Linux-Commands#Process Management|pgrep]] - Find processes by name
- [[Linux-Commands#System Administration|htop]] - Interactive process viewer

## Quick Reference

### Common Commands
```bash
# Start top
top

# Display top 10 CPU-intensive processes
top -n 10

# Display top 10 memory-intensive processes
top -o %MEM -n 10

# Display real-time updates every 2 seconds
top -d 2

# Display process tree
top -H
```

### Verification Commands
```bash
# Check running processes
ps
ps aux
```

## Tips and Tricks
1. Sort by CPU or memory usage
2. Monitor specific users or processes
3. Use interactive commands to manage processes
4. Integrate with other monitoring tools

### Common top Scenarios
```bash
# Find top CPU-intensive processes
top -o %CPU -n 10

# Find top memory-intensive processes
top -o %MEM -n 10

# Monitor system performance in real-time
top -d 2
```