# CyberBridge Linux Command Guide

## Introduction
Welcome to the **CyberBridge** guide to essential Linux commands! This guide will cover fundamental commands for file management, system administration, networking, and scripting. Mastering these will help you navigate Linux effectively and prepare for job interviews.

## Table of Contents
1. File & Directory Management  
2. User & Permission Management  
3. Process Management  
4. Package Management  
5. Networking Commands  
6. System Monitoring & Logs  
7. Bash Scripting Basics  
8. Additional Resources  

---

## 1. File & Directory Management
```bash
# List files and directories
ls -l        # Long format
ls -a        # Show hidden files
ls -lh       # Human-readable sizes

# Change directory
cd /path/to/directory

# Create and remove directories
mkdir new_directory
rmdir empty_directory
rm -r directory  # Remove non-empty directory

# Create and manipulate files
touch newfile.txt  # Create a new empty file
cat file.txt       # View contents
less file.txt      # View with scrolling
head -n 10 file.txt  # Show first 10 lines
tail -n 10 file.txt  # Show last 10 lines

# Copy, move, and delete files
cp file1.txt file2.txt   # Copy file
mv oldname.txt newname.txt  # Rename/move file
rm file.txt  # Delete file
```

---

## 2. User & Permission Management
```bash
# Check current user
whoami

# Add and manage users
adduser newuser
passwd newuser  # Set password for user
usermod -aG sudo newuser  # Grant sudo privileges

groups username  # Check user groups

groupadd devteam  # Create a new group
usermod -aG devteam username  # Add user to group

deluser username  # Delete user
groupdel devteam  # Delete group

# File permissions
ls -l file.txt  # Show file permissions
chmod 755 file.txt  # Change permissions
chown user:group file.txt  # Change ownership
```

---

## 3. Process Management
```bash
# View running processes
ps aux     # List all running processes
top        # Interactive process viewer
htop       # More user-friendly process viewer

# Kill processes
kill PID  # Terminate process by ID
killall process_name  # Kill all instances of a process
pkill -9 process_name  # Forcefully kill process

# Manage jobs
bg        # Resume a job in the background
fg        # Resume a job in the foreground
jobs      # Show background jobs
```

---

## 4. Package Management

### Debian/Ubuntu-based systems
```bash
# Update package list
apt update

# Install and remove packages
apt install package_name
apt remove package_name

# Upgrade all packages
apt upgrade
```

### Red Hat-based systems
```bash
# Install package
dnf install package_name

# Remove package
dnf remove package_name

# Update system
dnf update
```

### Arch Linux
```bash
# Install package
pacman -S package_name

# Remove package
pacman -R package_name

# Update system
pacman -Syu
```

---

## 5. Networking Commands
```bash
# Check network interfaces
ip a   # Show all interfaces
ifconfig  # Alternative command

# Ping a server
ping google.com

# Check open ports
netstat -tulnp  # Show listening ports
ss -tulnp       # Alternative to netstat

# Check network connections
netstat -rn  # Show routing table
traceroute google.com  # Trace route to a host

# Test connectivity
curl -I https://example.com  # Get HTTP headers
wget https://example.com  # Download a file
```

---

## 6. System Monitoring & Logs
```bash
# System resource usage
uptime  # Show system uptime and load average
free -h  # Check memory usage
df -h  # Disk space usage
du -sh directory_name  # Show disk usage of a directory

# View logs
journalctl -xe  # View system logs
journalctl -u service_name  # Logs for a specific service
dmesg | tail -n 20  # View kernel logs

tail -f /var/log/syslog  # Monitor system logs in real-time
```

---

## 7. Bash Scripting Basics
```bash
#!/bin/bash
# Basic Bash script example

echo "Hello, Linux!"

# Variables
name="CyberBridge"
echo "Welcome to $name!"

# Conditional statements
if [ "$name" == "CyberBridge" ]; then
    echo "Correct name!"
else
    echo "Wrong name!"
fi

# Loops
for i in {1..5}; do
    echo "Loop $i"
done

# Functions
greet() {
    echo "Hello, $1!"
}
greet Linux
```

---

## 8. Additional Resources
- **Linux Command Manual**: [man pages](https://linux.die.net/man/)
- **Bash Scripting Guide**: [GNU Bash Guide](https://www.gnu.org/software/bash/manual/)
- **Commands Cheat Sheet**: [Linux Networking](https://www.tecmint.com/linux-commands-cheat-sheet/)

---

This guide provides a foundation in Linux commands that are essential for system administration, development, and troubleshooting. Mastering these will help solidify your Linux skills for real-world applications and job interviews.
