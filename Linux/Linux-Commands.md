#linux #terminal #commands #reference

A comprehensive reference for Linux commands organised by category. For detailed examples of network-related commands, see also [[CURL]] and other networking notes.

## File System Navigation

### Basic Navigation
- `pwd` - Print working directory ([[pwd|Detailed Guide]])
- `ls` - List directory contents ([[ls|Detailed Guide]])
	  - `-l`: Long format
	  - `-a`: Show hidden files
	  - `-h`: Human-readable sizes
	  - `-R`: Recursive listing
- `cd` - Change directory ([[cd|Detailed Guide]])
	  - `cd ~`: Home directory
	  - `cd -`: Previous directory
	  - `cd ..`: Parent directory

### File Operations
- `cp` - Copy files/directories ([[cp|Detailed Guide]])
	  - `-r`: Recursive copy
	  - `-p`: Preserve attributes
- `mv` - Move/rename files ([[mv|Detailed Guide]])
- `rm` - Remove files ([[rm|Detailed Guide]])
	  - `-r`: Recursive delete
	  - `-f`: Force delete
- `mkdir` - Create directory ([[mkdir|Detailed Guide]])
	  - `-p`: Create parent directories
- `rmdir` - Remove empty directory ([[rmdir|Detailed Guide]])
- `touch` - Create empty file/update timestamp ([[touch|Detailed Guide]])
- `ln` - Create links ([[ln|Detailed Guide]])
	  - `-s`: Symbolic link

## File Viewing and Editing

### Viewing Files
- `cat` - Display file contents ([[cat|Detailed Guide]])
- `less` - Page through file ([[less|Detailed Guide]])
- `head` - Show first lines ([[head|Detailed Guide]])
	  - `-n`: Specify number of lines
- `tail` - Show last lines ([[tail|Detailed Guide]])
	  - `-f`: Follow file changes
- `nano` - Simple text editor
- `vim` - Advanced text editor
- `nvim` - Advanced version of vim ([[NeoVim Commands]])

### File Analysis
- `file` - Determine file type
- `stat` - Display file status
- `wc` - Count lines/words/characters
- `diff` - Compare files
- `md5sum` - Calculate MD5 checksum
- `sha256sum` - Calculate SHA256 checksum

## System Information

### System Status
- `top` - System monitoring ([[top|Detailed Guide]])
- `htop` - Interactive process viewer
- `ps` - Process status ([[ps|Detailed Guide]])
	  - `aux`: All processes
- `free` - Memory usage
- `df` - Disk space usage ([[df|Detailed Guide]])
	  - `-h`: Human-readable
- `du` - Directory space usage ([[du|Detailed Guide]])
- `uname` - System information ([[uname|Detailed Guide]])
	  - `-a`: All information

### System Control
- `shutdown` - Shutdown system in 10 seconds
	- `shutdown now` - Immediate shutdown
- `reboot` - Reboot system
- `systemctl` - Control systemd services
- `journalctl` - View systemd logs

## User Management

### User Commands
- `whoami` - Show current user ([[whoami|Detailed Guide]])
- `id` - User/group information
- `useradd` - Create user
- `usermod` - Modify user
- `userdel` - Delete user
- `passwd` - Change password ([[passwd|Detailed Guide]])

### Permissions
- `chmod` - Change file permissions ([[chmod|Detailed Guide]])
	  - Numeric: `chmod 755 file`
	  - Symbolic: `chmod u+x file`
- `chown` - Change file owner ([[chown|Detailed Guide]])
	  - Basic: `chown user file`
	  - With group: `chown user:group file`
	  - Recursive: `chown -R user:group dir/`
- `chgrp` - Change group owner ([[chgrp|Detailed Guide]])
- `umask` - Set default permissions
## Network Operations

### Network Information
- `ip` - Show/manipulate routing, devices, tunnels
- `ifconfig` - Configure network interface
- `netstat` - Network statistics
- `ss` - Socket statistics
- `ping` - Test network connectivity ([[ping|Detailed Guide]])
- `traceroute` - Trace packet route ([[traceroute|Detailed Guide]])
- `dig` - DNS lookup utility
- `nslookup` - Query DNS servers ([[nslookup|Detailed Guide]])
- `curl` - Transfer data from/to server ([[CURL|Detailed Guide]])
- `wget` - Download files

### Remote Access
- `ssh` - Secure shell
	  - `ssh user@host`
- `scp` - Secure copy
- `rsync` - Remote file sync

## Package Management

### APT (Debian/Ubuntu)
- `apt update` - Update package list
- `apt upgrade` - Upgrade packages
- `apt install` - Install package
- `apt remove` - Remove package
- `apt search` - Search packages

### YUM/DNF (RHEL/Fedora)
- `yum update`/`dnf update` - Update packages
- `yum install`/`dnf install` - Install package
- `yum remove`/`dnf remove` - Remove package
- `yum search`/`dnf search` - Search packages

## Text Processing

### Text Manipulation
- `grep` - Search text patterns ([[grep|Detailed Guide]])
	  - `-r`: Recursive search
	  - `-i`: Case insensitive
	  - `-v`: Invert match
- `sed` - Stream editor
- `awk` - Pattern scanning/processing
- `sort` - Sort lines of text ([[sort|Detailed Guide]])
- `uniq` - Report/omit repeated lines
- `tr` - Translate characters
- `cut` - Cut out selected fields
- `paste` - Merge lines of files

## Process Management

### Process Control
- `kill` - Terminate process ([[kill|Detailed Guide]])
- `killall` - Kill processes by name ([[killall|Detailed Guide]])
- `pkill` - Kill processes by pattern
- `nice` - Run with modified priority
- `nohup` - Run immune to hangups
- `bg` - Background process
- `fg` - Foreground process
- `jobs` - List background jobs

## Archiving and Compression

### Archive Commands
- `tar` - Tape archive ([[tar|Detailed Guide]])
	  - `-c`: Create archive
	  - `-x`: Extract archive
	  - `-f`: Specify filename
	  - `-z`: Use gzip compression
- `gzip` - Compress files ([[gzip and gunzip|Detailed Guide]])
- `gunzip` - Decompress files ([[gzip and gunzip|Detailed Guide]])
- `zip` - Package and compress files
- `unzip` - Extract zip archives

## System Maintenance

### Disk Management
- `fdisk` - Partition table manipulator
- `mount` - Mount filesystem
- `umount` - Unmount filesystem
- `fsck` - Check filesystem
- `dd` - Convert and copy files

### System Cleanup
- `clear` - Clear terminal screen ([[clear|Detailed Guide]])
- `history` - Command history ([[history|Detailed Guide]])
- `updatedb` - Update file database
- `find` - Search for files
	  - `-name`: Search by name
	  - `-type`: Search by type
	  - `-size`: Search by size

## Advanced Features

### Shell Features
- `alias` - Create command alias
- `export` - Set environment variable
- `cron` - Schedule tasks ([[cron|Detailed Guide]])
- `at` - Schedule one-time task
- `screen` - Terminal multiplexer
- `tmux` - Terminal multiplexer

### Performance Monitoring
- `iostat` - I/O statistics
- `vmstat` - Virtual memory stats
- `sar` - System activity reporter
- `lsof` - List open files

## Related Notes
- [[CURL]] - Detailed curl command usage
- [[HTTP]] - HTTP protocol reference
- [[Bash-Scripting]] - Bash scripting guide (if you have this note)
- [[System-Administration]] - System administration guide 

## Tips and Tricks

### Command Help
- `man` - Manual pages
- `info` - GNU info pages
- `whatis` - Brief command description
- `apropos` - Search manual pages
- `--help` - Command help option

### Shortcuts
- `Ctrl + C` - Interrupt current process
- `Ctrl + Z` - Suspend current process
- `Ctrl + D` - End of input/logout
- `Ctrl + L` - Clear screen
- `Ctrl + R` - Search command history
- `!!` - Repeat last command
- `!$` - Last argument of previous command

### Command Chaining
- `command1 && command2` - Run if previous succeeds
- `command1 || command2` - Run if previous fails
- `command1 ; command2` - Run sequentially
- `command1 | command2` - Pipe output

### Wildcards
- `*` - Match any characters
- `?` - Match single character
- `[]` - Match character range
- `{}` - Match pattern list