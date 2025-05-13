# System Administration

System administration encompasses the management and maintenance of computer systems, servers, and networks, ensuring optimal performance, security, and reliability.

## Table of Contents

- [[#Introduction to System Administration]]
- [[#User Management]]
- [[#Filesystem Management]]
- [[#Service Management]]
- [[#Networking and Security]]
- [[#Monitoring and Performance Tuning]]
- [[#Automation and Scripting]]

---

# Introduction to System Administration

System administration is crucial for maintaining the efficiency and reliability of IT infrastructure, encompassing a wide range of tasks from managing users to monitoring system performance.

### Key Responsibilities of a System Administrator
- Managing user access and permissions
- Configuring and maintaining system software and hardware
- Ensuring data security and system integrity
- Monitoring and tuning system performance
- Automating routine tasks

---

# User Management

Managing users is a fundamental part of system administration. Key tasks include creating and deleting user accounts, setting permissions, and managing groups.

### Key Commands
- `useradd` / `adduser`: Add a new user.
- `passwd`: Change a user’s password.
- `usermod`: Modify a user’s properties.
- `userdel`: Delete a user.
- `groupadd`, `groupmod`, `groupdel`: Manage groups.

### Example
```bash
# Add a new user
sudo useradd -m username

# Set password for the user
sudo passwd username
```

---

# Filesystem Management

Filesystem management involves organizing, accessing, and maintaining data storage, ensuring efficiency and reliability.

### Key Concepts
- **Partitions**: Logical divisions of a disk.
- **File permissions**: Determines access levels for files.
- **Mounting**: Making file systems available.

### Common Commands
- `df`: Display disk space usage.
- `du`: Show directory/file sizes.
- `lsblk`: List block devices.
- `mount` / `umount`: Mount or unmount file systems.
- `chmod`, `chown`: Change permissions and ownership.

### Example
```bash
# List disk usage
df -h

# Change file permissions
chmod 755 /path/to/file
```

---

# Service Management

Services are background processes that run continuously to provide various functionalities, such as web servers or database servers.

### Common Commands
- `systemctl`: Manage system services.
- `service`: An alternative command for managing services.
- `ps`: List running processes.
- `kill`: Terminate a process.

### Example
```bash
# Start a service
sudo systemctl start apache2

# Check service status
sudo systemctl status apache2
```

---

# Networking and Security

Networking and security are essential to ensure reliable communication and safeguard systems against threats.

### Key Commands and Tools
- **Networking**: `ip`, `ifconfig`, `netstat`, `ping`, `traceroute`
- **Firewall**: `iptables`, `firewalld`, `ufw`
- **SSH**: `ssh` for secure remote access.
- **Security Audits**: `fail2ban`, `clamav` (for antivirus)

### Example
```bash
# View network interfaces
ip addr show

# Enable UFW firewall
sudo ufw enable

# Allow SSH through the firewall
sudo ufw allow ssh
```

---

# Monitoring and Performance Tuning

Monitoring system performance helps ensure systems are running optimally. Performance tuning adjusts configurations to meet usage demands.

### Common Monitoring Tools
- `top`, `htop`: View active processes and resource usage.
- `vmstat`: Monitor memory, I/O, and CPU usage.
- `iostat`: Display CPU and disk I/O statistics.
- `free`: Show memory usage.

### Example
```bash
# Check memory usage
free -h

# Monitor CPU and memory usage in real-time
top
```

---

# Automation and Scripting

Automation is vital for system administration, as it reduces manual tasks and enhances efficiency. Bash scripting and tools like cron allow for scheduling and automating tasks.

### Useful Commands
- **Cron**: Schedule tasks.
- **Bash scripts**: Create reusable commands and automations.
  
### Example
```bash
# Open crontab to edit scheduled tasks
crontab -e

# A simple Bash script to back up a directory
#!/bin/bash
tar -czvf backup.tar.gz /path/to/directory
```