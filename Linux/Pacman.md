#linux #commands #packages #arch

The `pacman` command is the powerful package manager used in Arch Linux for installing, removing, and managing software packages. Here's a detailed guide on using pacman and its various flags.

## Basic Syntax
```bash
pacman [options] [actions] [packages]
```

## Common Usage Patterns

### Install a Package
```bash
sudo pacman -S package_name
```

### Remove a Package
```bash
sudo pacman -R package_name
```

### Upgrade All Packages
```bash
sudo pacman -Syu
```

### Search for a Package
```bash
pacman -Ss search_term
```

### List Installed Packages
```bash
pacman -Q
```

## Options

### Sync Options (-S)
- `-S package`: Install a package
- `-Ss search`: Search for a package
- `-Syu`: Upgrade all installed packages
- `-Sy`: Refresh package database without upgrading
- `-Sc`: Clean package cache
- `-Scc`: Completely clean package cache

### Remove Options (-R)
- `-R package`: Remove a package
- `-Rs package`: Remove a package and its dependencies
- `-Rns package`: Remove a package, dependencies, and configuration files

### Query Options (-Q)
- `-Q`: List all installed packages
- `-Qi package`: Show information about an installed package
- `-Ql package`: List files owned by an installed package
- `-Qn`: List native (non-foreign) installed packages
- `-Qm`: List foreign (AUR) installed packages

### File Options (-F)
- `-F package.file`: Query the package that owns a file

### Database Options (-D)
- `-D --asdeps package`: Mark a package as dependency
- `-D --asexplicit package`: Mark a package as explicitly installed

### General Options
- `-v`: Show version information
- `-h`: Show help
- `-c`: Show configuration file

## Common Scenarios

### Install a Package
```bash
sudo pacman -S firefox
```

### Remove a Package
```bash
sudo pacman -R firefox
```

### Upgrade the System
```bash
sudo pacman -Syu
```

### Search for a Package
```bash
pacman -Ss text-editor
```

### List Installed Packages
```bash
pacman -Q
pacman -Qe # Explicitly installed packages
pacman -Qd # Dependency packages
```

### Query Package Information
```bash
pacman -Qi firefox
pacman -Ql firefox
```

### Find Package that Owns a File
```bash
pacman -F /usr/bin/vim
```

### Reinstall a Package
```bash
sudo pacman -S --force package_name
```

## Error Handling

### Common Errors
1. Package Not Found
   ```bash
   # Check package name spelling
   pacman -Ss package_name

   # Search AUR if not in repos
   yay package_name
   ```

2. Unsatisfied Dependencies
   ```bash
   # Install missing dependencies
   sudo pacman -S package_name --asdeps
   ```

3. Package Conflicts
   ```bash
   # Remove conflicting packages
   sudo pacman -R conflicting_package
   ```

4. Corrupted Package Database
   ```bash
   # Rebuild the package database
   sudo pacman -Syvv
   ```

## Best Practices

### Usage Guidelines
1. Always use sudo for system-level operations
2. Update package database before installing
3. Upgrade the system regularly
4. Clean package cache periodically
5. Review package information before installing

### Package Management
1. Install packages from official repositories
2. Use AUR helpers for community packages
3. Mark dependencies as such to avoid unnecessary installs
4. Remove unused dependencies with `pacman -Qdtq`
5. Backup package list for reinstallation `pacman -Qqe > pkglist.txt`

## Scripting Examples

### Install Multiple Packages
```bash
#!/bin/bash
packages=(
    "vim"
    "git"
    "htop"
)

for pkg in "${packages[@]}"; do
    sudo pacman -S "$pkg"
done
```

### Backup and Restore Packages
```bash
#!/bin/bash
# Backup package list
pacman -Qqe > pkglist.txt

# Restore from backup
sudo pacman -S --needed - < pkglist.txt
```

### Automate Package Cleanup
```bash
#!/bin/bash
# Remove orphaned dependencies
sudo pacman -Qdtq | sudo pacman -Rs -
# Clean package cache
sudo pacman -Sc
```

## Related Commands
- [[Linux-Commands#Package Management|yay]] - AUR helper for Arch Linux
- [[Linux-Commands#Package Management|paru]] - Another AUR helper for Arch Linux
- [[Linux-Commands#Package Management|aurman]] - Deprecated AUR helper

## Quick Reference

### Common Commands
```bash
# Install package
sudo pacman -S package_name

# Remove package
sudo pacman -R package_name 

# Upgrade all packages
sudo pacman -Syu

# Search for package
pacman -Ss search_term

# List installed packages
pacman -Q
```

### Verification Commands
```bash
# Check package info
pacman -Qi package_name

# List package contents
pacman -Ql package_name

# Find package that owns a file
pacman -F /usr/bin/vim
```

## Tips and Tricks
1. Use tab completion for package names
2. Combine options for efficiency (e.g. -Syu)
3. Review package details before installing
4. Automate package backups and cleanups
5. Enable color output in pacman.conf

### Common Use Cases
```bash
# Install development tools
sudo pacman -S base-devel

# Remove orphaned dependencies
sudo pacman -Qdtq | sudo pacman -Rs -

# Downgrade a package
pacman -U /path/to/package.pkg.tar.zst
```