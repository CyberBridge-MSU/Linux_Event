# CyberBridge Linux Tutorial for Beginners

## Introduction
Welcome to this beginner-friendly Linux tutorial, brought to you by **CyberBridge**! This guide is designed for users who have little to no experience with Linux and want to get started with the basics. We will be working with **Ubuntu** and **macOS**.

## Table of Contents
1. What is Linux?
2. Basic Linux Commands
3. File System Navigation
4. User and Permissions Management
5. Creating and Editing Files
6. Installing and Managing Software
7. Networking Basics
8. Shell Scripting Introduction
9. Additional Resources

---

## 1. What is Linux?
Linux is an open-source operating system based on Unix. It is widely used for servers, development, and personal computing due to its flexibility and security. Unlike Windows and macOS, Linux comes in different distributions (distros), each with unique features.

## 2. Basic Linux Commands
Use the terminal to interact with Linux. Here are some essential commands:
```bash
ls        # List files and directories
pwd       # Print current working directory
cd        # Change directory
mkdir     # Create a new directory
touch     # Create a new file
cp        # Copy files or directories
mv        # Move or rename files
rm        # Remove files or directories
```

### Walkthrough: Listing Files and Navigating Directories
```bash
pwd       # Check where you are
ls -l     # See detailed info about files and permissions
cd /tmp   # Move to the temporary directory
mkdir test_dir  # Create a new directory
cd test_dir   # Move into the new directory
``` 

## 3. File System Navigation
Navigating directories is crucial in Linux. Here are some examples:
```bash
pwd              # Show current directory
ls               # List files in the current directory
ls -l            # List with details (permissions, owner, size, etc.)
ls -a            # Show hidden files (those starting with a dot)
cd /home/user    # Change to a specific directory
cd ..            # Move up one directory level
cd ~             # Go to the home directory
```

### Walkthrough: Creating and Moving Between Directories
```bash
mkdir my_project   # Create a new directory
cd my_project      # Move into it
mkdir src logs     # Create multiple directories
cd logs            # Move into the logs directory
cd ..              # Move back to my_project
rmdir logs         # Remove an empty directory
```

## 4. User and Permissions Management
Every file and directory in Linux has a set of permissions that determine who can read, write, and execute them. To view permissions, use:
```bash
ls -l
```
Example output:
```
drwxr-xr-x  2 user group 4096 Mar 5 10:00 Documents
-rw-r--r--  1 user group  123 Mar 5 10:01 file.txt
```

### Understanding Permissions
Each file has three permission groups:
1. **User (Owner)** – The user who owns the file.
2. **Group** – Other users in the same group.
3. **Others** – Everyone else.

Each group has three permission types:
- `r` (read) – Can view the file contents.
- `w` (write) – Can modify the file.
- `x` (execute) – Can run the file (if it is a script or program).

For example:
- `drwxr-xr-x` → A directory (`d`), where the owner can read, write, and execute (`rwx`), while the group and others can only read and execute (`r-x`).
- `-rw-r--r--` → A file (`-`), where the owner can read and write (`rw-`), while the group and others can only read (`r--`).

### Changing Permissions Using Numbers
```bash
chmod 755 filename  # Owner can read/write/execute, others can only read/execute
chmod 644 filename  # Owner can read/write, others can only read
```

### Changing Permissions Using Letters
You can also use symbolic notation:
```bash
chmod u+x filename  # Give the owner (u) execute permission
chmod g-w filename  # Remove write permission from the group (g)
chmod o+r filename  # Give others (o) read permission
chmod a+x filename  # Give execute permission to everyone (a)
```

### Walkthrough: Modifying File Permissions
```bash
touch my_script.sh   # Create a new script
ls -l my_script.sh   # Check permissions
chmod u+x my_script.sh  # Make it executable for the owner
ls -l my_script.sh   # Verify changes
```

## 5. Creating and Editing Files
### Creating a File
```bash
touch newfile.txt  # Create an empty file
echo "Hello, world!" > file.txt  # Create a file with content
cat file.txt  # Display the file contents
```

### Editing a File
Linux provides several text editors. You can use **nano**, which is simple, or **vi**, which is sarcastically the best editor ever.

#### Using nano (the easy way):
```bash
nano file.txt
```
- Edit your text.
- Press `CTRL + X`, then `Y` to save and exit.

#### Using vi (obviously the best editor ever, no debate needed):
```bash
vi file.txt
```
- Press `i` to enter insert mode and start typing.
- Press `ESC` to exit insert mode.
- Type `:wq` and press `Enter` to save and exit (because why make it easy?).
- If you made a mistake and want to quit without saving, type `:q!` (because obviously that’s intuitive).

### Walkthrough: Editing a File in Nano
```bash
nano my_note.txt   # Open nano
# Type some text
# Press CTRL+X, then Y, then Enter to save
cat my_note.txt    # View the file
```

## 6. Installing and Managing Software
Ubuntu uses the `apt` package manager:
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install package_name
```

macOS uses `brew` (Homebrew):
```bash
brew install package_name
```

## 7. Networking Basics
Check network connection:
```bash
ping google.com
```
View IP address:
```bash
ip a  # Newer command
ifconfig  # Older command (may need `net-tools` package)
```

## 8. Shell Scripting Introduction
A simple script:
```bash
#!/bin/bash
echo "Hello, Linux!"
```
Save it as `script.sh`, then make it executable:
```bash
chmod +x script.sh
./script.sh
```

## 9. Additional Resources
- [Linux Journey](https://linuxjourney.com/)
- [The Linux Command Line](https://linuxcommand.org/)
- [Official Ubuntu Documentation](https://help.ubuntu.com/)

---
Congratulations! You now have a deeper understanding of Linux. Keep exploring and practicing to improve your skills.

