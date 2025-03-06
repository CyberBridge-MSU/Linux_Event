# CyberBridge Linux System Administration Guide

## Introduction
System administration is a core skill for managing Linux environments. This guide covers user management, process handling, service management, system monitoring, and security best practices for maintaining Linux servers and workstations.

## Table of Contents
1. User & Group Management  
2. Process Management  
3. Service Management  
4. Disk & File System Management  
5. System Logs & Troubleshooting  
6. System Security & Hardening  
7. Automation with Cron Jobs  
8. Additional Resources  

---

## 1. User & Group Management
Linux is a multi-user system, meaning user and group management is crucial for access control.

### Creating and Managing Users
```bash
# Create a new user
adduser newuser

# Set password for user
passwd newuser

# Add user to sudo group
usermod -aG sudo newuser
```

### Managing Groups
```bash
# Create a new group
groupadd devteam

# Add user to group
usermod -aG devteam newuser

# Delete user
deluser newuser

# Delete group
groupdel devteam
```

### Check Current User and Groups
```bash
whoami
id
```

---

## 2. Process Management
Processes are programs running in the system. Understanding how to monitor and control them is essential.

### Viewing Processes
```bash
# List all running processes
ps aux

# View active processes in real-time
top
htop  # More user-friendly process viewer
```

### Managing Processes
```bash
# Kill a process by PID
kill PID

# Kill a process by name
killall process_name

# Send a specific signal to a process
pkill -9 process_name
```

---

## 3. Service Management
System services (daemons) run in the background and perform essential functions.

### Managing Services with systemd
```bash
# Start a service
systemctl start nginx

# Stop a service
systemctl stop apache2

# Restart a service
systemctl restart ssh

# Enable a service to start at boot
systemctl enable docker

# Disable a service from starting at boot
systemctl disable mysql

# Check the status of a service
systemctl status ssh
```

---

## 4. Disk & File System Management
Monitoring and managing disk space and file systems is critical for system stability.

### Checking Disk Space
```bash
# Show disk usage summary
df -h

# Show directory size
du -sh /home
```

### Mounting and Unmounting Drives
```bash
# Mount a device
mount /dev/sdb1 /mnt

# Unmount a device
umount /mnt
```

---

## 5. System Logs & Troubleshooting
Logs help diagnose system issues.

### Viewing Logs with journalctl
```bash
# Show the system log
journalctl -xe

# Show logs for a specific service
journalctl -u ssh
```

### Monitoring Log Files
```bash
tail -f /var/log/syslog
dmesg | tail -n 20  # View recent kernel logs
```

---

## 6. System Security & Hardening
Security is a fundamental aspect of system administration.

### Firewall Management (UFW - Uncomplicated Firewall)
```bash
# Enable the firewall
ufw enable

# Allow SSH connections
ufw allow 22

# Deny all incoming traffic by default
ufw default deny incoming

# Check firewall status
ufw status verbose
```

### File Permissions and Ownership
```bash
# Change file permissions
chmod 755 file.txt

# Change file owner
chown user:group file.txt
```

### Finding and Killing Unauthorized Processes
```bash
# Find all processes running as root
ps aux | grep root
```

---

## 7. Automation with Cron Jobs
Cron jobs allow scheduled execution of commands and scripts.

### Editing Crontab
```bash
crontab -e
```

### Example Cron Job (Runs every day at midnight)
```bash
0 0 * * * /path/to/script.sh
```

### List Existing Cron Jobs
```bash
crontab -l
```

---

## 8. Additional Resources
- [Cron Translator](https://www.uptimia.com/cron-expression-meaning/every-day)
- [Linux Command Manual](https://linux.die.net/man/)

---

This guide provides essential knowledge for Linux system administration. Mastering these concepts will help you efficiently manage Linux environments!
