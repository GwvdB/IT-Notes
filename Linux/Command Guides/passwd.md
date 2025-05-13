#linux #commands #user-management #system-administration

The `passwd` command in Linux is used to change the password of a user account. It can be used by both regular users and the root user. See also [[Linux-Commands#User Commands]]

## Basic Syntax
```
passwd [OPTIONS] [USERNAME]
```

## Common Usage Patterns

### Change Current User's Password
```bash
passwd
```

### Change Another User's Password (as root)
```bash
passwd username
```

### Set Password to Never Expire
```bash
passwd -e 0 username
```

### Disable a User Account
```bash
passwd -l username
```

### Enable a User Account
```bash
passwd -u username
```

## Options

### Expire Password (-e)
```bash
passwd -e 0 username
```
- Sets the password to never expire

### Lock Account (-l)
```bash
passwd -l username
```
- Locks the specified user account

### Unlock Account (-u)
```bash
passwd -u username
```
- Unlocks the specified user account

### Delete Password (-d)
```bash
passwd -d username
```
- Deletes the password for the specified user

### Quiet Mode (-q)
```bash
passwd -q
```
- Runs the command in quiet mode, suppressing output

## Common Scenarios

### Change Your Own Password
```bash
# Change the password for the current user
passwd
```

### Change Another User's Password
```bash
# Change the password for the "username" user
sudo passwd username
```

### Disable a User Account
```bash
# Lock the "username" user account
sudo passwd -l username
```

### Enable a User Account
```bash
# Unlock the "username" user account
sudo passwd -u username
```

## Error Handling

### Common Errors
1. Permission Denied
   ```bash
   # Use sudo to change another user's password
   sudo passwd username
   ```

2. Authentication Token Manipulation Error
   ```bash
   # Ensure the current user has permission to change the password
   passwd
   ```

3. No Such User
   ```bash
   # Verify the username exists
   passwd non-existent-user
   ```

## Best Practices

### Security Considerations
1. Enforce strong password policies
2. Regularly audit and update passwords
3. Implement multi-factor authentication
4. Limit access to password management

### Maintenance Tips
1. Document password management procedures
2. Implement password expiration policies
3. Monitor password-related security events

## Scripting Examples

### Change Current User's Password
```bash
#!/bin/bash
passwd
```

### Change Another User's Password
```bash
#!/bin/bash
target_user="username"
sudo passwd "$target_user"
```

### Disable a User Account
```bash
#!/bin/bash
target_user="username"
sudo passwd -l "$target_user"
```

## Related Commands
- [[Linux-Commands#User Management|useradd]] - Create a new user account
- [[Linux-Commands#User Management|userdel]] - Delete a user account
- [[Linux-Commands#User Management|usermod]] - Modify a user account
- [[Linux-Commands#User Management|chage]] - Change user password expiration information

## Quick Reference

### Common Commands
```bash
# Change current user's password
passwd

# Change another user's password
sudo passwd username

# Disable a user account
sudo passwd -l username

# Enable a user account
sudo passwd -u username
```

### Verification Commands
```bash
# Check user information
id
```

## Tips and Tricks
1. Use `sudo` to change another user's password
2. Implement password expiration policies
3. Monitor password-related security events

### Common passwd Scenarios
```bash
# Change the current user's password
passwd

# Change the "username" user's password
sudo passwd username

# Lock the "username" user account
sudo passwd -l username

# Unlock the "username" user account
sudo passwd -u username
```