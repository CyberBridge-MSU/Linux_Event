# CyberBridge Linux Networking & Security Guide

## Introduction
Networking and security are crucial aspects of managing Linux systems. This guide covers fundamental networking commands, security best practices, and tools to manage secure connections.

## Table of Contents
1. Basic Networking Commands  
2. Configuring Network Interfaces  
3. Firewall Management  
4. Secure Remote Access (SSH)  
5. Network Troubleshooting  
6. VPN & Secure Browsing  
7. Network Monitoring & Security Tools  
8. Additional Resources  

---

## 1. Basic Networking Commands
These commands help diagnose and inspect network configurations.

```bash
# Show all network interfaces and IP addresses
ip a

# Show active network connections
netstat -tulnp
ss -tulnp  # Alternative command

# Display current routing table
ip route show
netstat -rn

# Test network connectivity
ping google.com
traceroute google.com  # Trace the route to a destination

# Fetch an external IP address
curl ifconfig.me
```

---

## 2. Configuring Network Interfaces
### Viewing and Assigning IP Addresses
```bash
# Show network interfaces and IPs
ip a

# Assign an IP address temporarily
ip addr add 192.168.1.100/24 dev eth0

# Remove an assigned IP
ip addr del 192.168.1.100/24 dev eth0
```

### Configuring a Static IP (Ubuntu/Debian)
Edit `/etc/netplan/01-netcfg.yaml`:
```yaml
network:
  version: 2
  ethernets:
    eth0:
      addresses:
        - 192.168.1.100/24
      gateway4: 192.168.1.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 1.1.1.1
```
Apply the changes:
```bash
sudo netplan apply
```

---

## 3. Firewall Management
### UFW (Uncomplicated Firewall - Ubuntu/Debian)
```bash
# Enable firewall
ufw enable

# Allow SSH traffic
ufw allow 22/tcp

# Allow HTTP and HTTPS
ufw allow 80/tcp
ufw allow 443/tcp

# Deny all incoming connections by default
ufw default deny incoming

# View firewall rules
ufw status verbose
```

### IPTables (Advanced Firewall Rules)
```bash
# Block all incoming traffic except SSH
iptables -P INPUT DROP
iptables -A INPUT -p tcp --dport 22 -j ACCEPT

# Save firewall rules
iptables-save > /etc/iptables/rules.v4
```

---

## 4. Secure Remote Access (SSH)
### Configuring SSH Access
```bash
# Connect to a remote server
ssh user@remote_host

# Copy files using SCP
scp file.txt user@remote_host:/path/to/destination
```

### Hardening SSH Security
Edit `/etc/ssh/sshd_config` and modify:
```
PermitRootLogin no
PasswordAuthentication no
AllowUsers specificuser
```
Restart SSH service:
```bash
systemctl restart ssh
```

---

## 5. Network Troubleshooting
### Diagnosing Network Issues
```bash
# Check if the server is reachable
ping 8.8.8.8

# Display DNS resolution details
nslookup example.com
dig example.com

# View all active network connections
netstat -tulnp
```

### Restarting Network Services
```bash
systemctl restart networking
```

---

## 6. VPN & Secure Browsing
### Setting Up OpenVPN Client
```bash
sudo apt install openvpn
sudo openvpn --config client.ovpn
```

### Using WireGuard VPN
```bash
sudo apt install wireguard
wg-quick up wg0
wg-quick down wg0
```

---

## 7. Network Monitoring & Security Tools
### Monitoring Network Traffic
```bash
# Monitor live network traffic
tcpdump -i eth0

# Analyze network activity
iftop -i eth0

# Scan open ports on a remote host
nmap -p- remote_host
```

### Intrusion Detection with Fail2Ban
```bash
# Install and start Fail2Ban
sudo apt install fail2ban
sudo systemctl enable fail2ban
sudo systemctl start fail2ban

# Configure SSH protection
sudo nano /etc/fail2ban/jail.local

[sshd]
enabled = true
bantime = 600
findtime = 600
maxretry = 3
```
Restart Fail2Ban:
```bash
sudo systemctl restart fail2ban
```

---

## 8. Additional Resources
- [Linux Networking Basics](https://www.tecmint.com/linux-network-commands/)
- [Linux Security & Hardening](https://www.linux.com/tutorials/linux-security-guide/)

---

This guide provides essential Linux networking and security fundamentals. Mastering these concepts will help secure and manage network infrastructure efficiently!
