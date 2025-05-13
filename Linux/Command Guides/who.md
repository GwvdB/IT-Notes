#linux #commands #user-management #system-administration

The `who` command in Linux is used to display information about the users currently logged into the system.

## Basic Syntax
```
who [OPTIONS]
```

## Common Usage Patterns

### List Currently Logged-in Users
```bash
who
```

### Display User, Terminal, Login Time, and Host
```bash
who -a
```

### Show Only Usernames
```bash
who -q
```

### Show Boottime and System Uptime
```bash
who -b
who -s
```

### Show User, Terminal, Login Time, and Process ID
```bash
who -l
```

## Options

### All Information (-a)
```bash
who -a
```
- Displays user, terminal, login time, and host

### Query List (-q)
```bash
who -q
```
- Displays only a list of usernames

### Boot Time (-b)
```bash
who -b
```
- Displays the system boot time

### Process ID (-l)
```bash
who -l
```
- Displays user, terminal, login time, and process ID

### Short Format (-s)
```bash
who -s
```
- Displays a shortened output format

### Write Output (-w)
```bash
who -w
```
- Displays a "who" and "write" output

## Common Scenarios

### List Currently Logged-in Users
```bash
# See who is currently logged in
who
```

### Identify Active User Sessions
```bash
# Get detailed information about user sessions
who -a
```

### Troubleshoot Login Issues
```bash
# Check login records and process IDs
who -l
```

### Monitor System Uptime
```bash
# View system boot time and uptime
who -b
who -s
```

## Error Handling

### Common Errors
1. No Errors

The `who` command does not typically produce any errors. It simply displays information about logged-in users.

## Best Practices

### Security Considerations
1. Avoid running as root when not necessary
2. Use the least privilege principle
3. Carefully review user login information

### Maintenance Tips
1. Document user management procedures
2. Implement user access controls
3. Audit user accounts and login activity

## Scripting Examples

### Get List of Logged-in Users
```bash
#!/bin/bash
echo "Currently logged-in users:"
who
```

### Monitor System Uptime
```bash
#!/bin/bash
echo "System boot time:"
who -b

echo "System uptime:"
who -s
```

## Related Commands
- [[Linux-Commands#User Management|whoami]] - Display the current username
- [[Linux-Commands#User Management|id]] - Display user and group information
- [[Linux-Commands#User Management|last]] - Show a listing of last logged in users
- [[Linux-Commands#User Management|w]] - Show who is logged in and what they are doing

## Quick Reference

### Common Commands
```bash
# List currently logged-in users
who

# Display detailed user information
who -a

# Show only usernames
who -q

# View system boot time and uptime
who -b
who -s
```

### Verification Commands
```bash
# Check user and group information
id
```

## Tips and Tricks
1. Use `who` to identify active user sessions
2. Monitor system uptime and boot time
3. Integrate `who` output into custom scripts

### Common who Scenarios
```bash
# List currently logged-in users
who

# Get detailed information about user sessions
who -a

# Check login records and process IDs
who -l

# View system boot time and uptime
who -b
who -s
```