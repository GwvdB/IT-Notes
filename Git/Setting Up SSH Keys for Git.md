## Generating SSH Key

1. Open terminal and run:
```bash
ssh-keygen -t ed25519 -C "your.email@example.com"
```
Or for legacy systems:
```bash
ssh-keygen -t rsa -b 4096 -C "your.email@example.com"
```

2. When prompted for file location, press Enter for default
3. Enter secure passphrase (recommended)

## Adding SSH Key to SSH Agent

1. Start SSH agent:
```bash
eval "$(ssh-agent -s)"
```

2. Add key to agent:
```bash
ssh-add ~/.ssh/id_ed25519  # Or id_rsa for RSA keys
```

## Adding SSH Key to GitHub

1. Copy public key:
```bash
# For macOS
pbcopy < ~/.ssh/id_ed25519.pub

# For Linux
xclip -sel clip < ~/.ssh/id_ed25519.pub

# For Windows (PowerShell)
Get-Content ~/.ssh/id_ed25519.pub | Set-Clipboard
```

2. Go to GitHub Settings → SSH and GPG keys
3. Click "New SSH key"
4. Give key a descriptive title
5. Paste public key
6. Click "Add SSH key"

## Testing Connection

```bash
ssh -T git@github.com
```

## Troubleshooting

### Common Issues
1. **Permission denied**
   - Verify key is added to ssh-agent
   - Check key is added to GitHub
   - Ensure correct permissions on SSH files

2. **Authentication failed**
   - Verify you're using correct key
   - Check if key is properly generated
   - Ensure GitHub account email matches key email

### File Permissions
```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_ed25519
chmod 600 ~/.ssh/id_ed25519.pub
```