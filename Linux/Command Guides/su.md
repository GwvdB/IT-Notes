#linux #commands #user-management #system-administration

The `su` (switch user) command in Linux is used to switch to another user account, typically the superuser (root) account.

## Basic Syntax
```
su [OPTIONS] [-] [USERNAME]
```

## Common Usage Patterns

### Switch to Root User
```bash
su
```

### Switch to Specific User
```bash
su - username
```

### Run a Command as Another User
```bash
su - username -c "command"
```

### Switch User and Preserve Environment
```bash
su -
```

### Switch User and Change Working Directory
```bash
su - username
```

## Options

### Login Shell (-) 
```bash
su -
su - username
```
- Starts a login shell for the target user

### Command (-c)
```bash
su - username -c "command"
```
- Executes the specified command as the target user

### Preserve Environment (-m, -p)
```bash
su -m
su -p
```
- Preserves the current environment when switching users

## Common Scenarios

### Gain Root Privileges
```bash
# Switch to the root user
su
```

### Impersonate Another User
```bash
# Switch to the "username" user
su - username
```

### Run a Command as Another User
```bash
# Run "command" as the "username" user
su - username -c "command"
```

### Maintain Environment When Switching
```bash
# Switch to root while preserving environment
su -
```

## Error Handling

### Common Errors
1. Authentication Failure
   ```bash
   # Verify username and password
   su - username
   ```

2. Permission Denied
   ```bash
   # Check user permissions
   su - username
   ```

3. No Such User
   ```bash
   # Verify the user exists
   su - non-existent-user
   ```

## Best Practices

### Security Considerations
1. Avoid running as root when not necessary
2. Use the least privilege principle
3. Carefully review user permissions
4. Implement multi-factor authentication

### Maintenance Tips
1. Document user management procedures
2. Implement user access controls
3. Audit user accounts and login activity

## Scripting Examples

### Switch to Root User
```bash
#!/bin/bash
su -c "command"
```

### Switch to Specific User
```bash
#!/bin/bash
target_user="username"
su - "$target_user" -c "command"
```

### Maintain Environment When Switching
```bash
#!/bin/bash
su -
```

## Related Commands
- [[Linux-Commands#User Management|whoami]] - Display the current username
- [[Linux-Commands#User Management|id]] - Display user and group information
- [[Linux-Commands#User Management|sudo]] - Execute a command as another user
- [[Linux-Commands#User Management|useradd]] - Create a new user account

## Quick Reference

### Common Commands
```bash
# Switch to root user
su

# Switch to specific user
su - username

# Run a command as another user
su - username -c "command"

# Switch user and preserve environment
su -
```

### Verification Commands
```bash
# Check user and group information
id
```

## Tips and Tricks
1. Use `su` to gain root privileges when necessary
2. Impersonate other users for specific tasks
3. Preserve environment when switching users
4. Avoid running as root when not required

### Common su Scenarios
```bash
# Switch to the root user
su

# Switch to the "username" user
su - username 

# Run "command" as the "username" user
su - username -c "command"

# Switch to root while preserving environment
su -
```