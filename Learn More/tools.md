# CyberBridge Essential Linux Tools Guide

## Introduction
Linux provides a powerful ecosystem of tools that enhance system administration, development, and productivity. This guide covers essential tools for package management, text editing, version control, system monitoring, and more.

## Table of Contents
1. Package Managers  
2. Text Editors  
3. Version Control (Git)  
4. System Monitoring Tools  
5. File Search & Management  
6. Containerization & Virtualization  
7. Networking & Security Tools  
8. Additional Resources  

---

## 1. Package Managers
### Debian/Ubuntu-based Systems
```bash
# Update package list
apt update

# Install a package
apt install package_name

# Remove a package
apt remove package_name
```

### Red Hat-based Systems
```bash
# Install a package
dnf install package_name

# Remove a package
dnf remove package_name
```

### Arch Linux
```bash
# Install a package
pacman -S package_name

# Remove a package
pacman -R package_name
```

---

## 2. Text Editors
### Nano
```bash
nano filename.txt  # Open file for editing
```

### Vim
```bash
vim filename.txt  # Open file in Vim
```
Common Vim commands:
- `i` – Enter insert mode
- `Esc` – Exit insert mode
- `:wq` – Save and exit
- `:q!` – Quit without saving

### Emacs
```bash
emacs filename.txt  # Open file in Emacs
```

---

## 3. Version Control (Git)
```bash
# Initialize a Git repository
git init

# Clone a repository
git clone https://github.com/user/repo.git

# Add an origin
git remote add origin https://github.com/user/repo.git

# Add files to staging
git add filename

# Commit changes
git commit -m "Commit message"

# Push changes to remote
git push origin main
```

---

## 4. System Monitoring Tools
### Checking System Resource Usage
```bash
htop  # Interactive process monitor
top   # Default Linux process viewer
free -h  # Check RAM usage
df -h  # Show disk usage
```

### Checking Logs
```bash
tail -f /var/log/syslog  # Live view of system logs
journalctl -xe  # View system logs
```

---

## 5. File Search & Management
### Searching for Files
```bash
find /path -name "filename"  # Search for a file by name
```

### Searching Inside Files
```bash
grep -R "search_term" /path  # Recursively search inside files
```

---

## 6. Containerization & Virtualization
### Docker
```bash
# Install Docker
sudo apt install docker.io

# Start a container
sudo docker run -d ubuntu
```

### VirtualBox
```bash
# Install VirtualBox
sudo apt install virtualbox
```

---

## 7. Networking & Security Tools
### Checking Open Ports
```bash
netstat -tulnp
ss -tulnp  # Alternative command
```

### Network Diagnostics
```bash
ping google.com  # Test connectivity
traceroute google.com  # Trace route to destination
```

### Firewall Management (UFW)
```bash
ufw allow 22/tcp  # Allow SSH
ufw enable  # Enable firewall
```

---

## 8. Additional Resources
- [Linux Command Cheat Sheet](https://www.linuxtrainingacademy.com/linux-commands-cheat-sheet/)
- [Git Documentation](https://git-scm.com/doc)
- [Docker Docs](https://docs.docker.com/)

---

This guide introduces essential Linux tools for daily use. Mastering these tools will enhance productivity and system efficiency!
