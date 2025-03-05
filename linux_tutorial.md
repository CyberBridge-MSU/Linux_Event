# CyberBridge Linux Tutorial for Beginners

## Introduction
Welcome to this beginner-friendly Linux tutorial, brought to you by **CyberBridge**! This guide is designed for users who have little to no experience with Linux and want to get started with the basics. We will be working with **Ubuntu** and **macOS**.

## Table of Contents
1. Basic Commands
2. Directory Traversal
3. Echo and File Manipulation
4. Text Editing with vi and nano
5. Additional Resources

---

## 1. Basic Commands
Before doing anything in Linux, let’s go over a few fundamental commands:
```bash
lsb_release -a   # Check which Linux distribution you're using
pwd              # Print current working directory
ls               # List files and directories
```

### Understanding the Linux File System
Linux follows a hierarchical directory structure. Here are some important directories under the root (`/`):

- **/root** – The home directory for the root (admin) user.
- **/home** – Contains personal files for all regular users (`/home/username`).
- **/etc** – System configuration files.
- **/bin** – Essential binary executables (like `ls`, `pwd`).
- **/sbin** – System binaries, usually requiring root privileges.
- **/var** – Variable data such as logs and temporary files.
- **/usr** – Installed user applications and libraries.
- **/tmp** – Temporary files, cleared after reboot.

Each user has their own **home directory** under `/home/username`, where personal files and configurations are stored.

---

## 2. Directory Traversal
To move around in the Linux file system, use the `cd` (change directory) command:
```bash
cd [directory_name]  # Move into a specific directory
cd ..                # Move up one level
cd ../..             # Move up two levels
cd ~                 # Go to your home directory
cd /                 # Move to the root directory
```

### Special Symbols in Linux
- `.` (dot) refers to the current directory.
- `..` (double dot) refers to the parent directory.

#### Example Walkthrough:
```bash
pwd       # Shows your current location
ls        # Lists files in the directory
cd /etc   # Move to the /etc directory
pwd       # Check the new location
cd ..     # Move back one directory
cd ~      # Return to your home directory
```

---

## 3. Echo and File Manipulation
### Using `echo`
The `echo` command prints text to the terminal and can be used to create files:
```bash
echo "Hello, Linux!"  # Prints text to the terminal
echo "This is a file" > myfile.txt  # Creates a file with text
cat myfile.txt  # View the file contents
```

### File and Directory Manipulation
```bash
touch newfile.txt   # Create an empty file
mkdir myfolder      # Create a new directory
cp file.txt backup/  # Copy a file to a directory
mv file.txt newname.txt  # Rename/move a file
rm file.txt         # Delete a file
rm -r myfolder      # Delete a directory and its contents
```

### Using `man` (Manual Pages)
To learn more about any command, use `man`:
```bash
man ls  # Opens the manual page for ls
```
Press `q` to exit the manual page.

---

## 4. Text Editing with vi and nano

### vi (obviously the best editor ever, no debate needed)
To open a file in `vi`:
```bash
vi myfile.txt
```
#### vi Controls:
- Press `i` to enter **insert mode** and start typing.
- Press `ESC` to exit insert mode.
- Type `:wq` and press `Enter` to save and exit.
- Type `:q!` to quit without saving (because, obviously, you meant to do that).

### nano (the easy way out)
To open a file in `nano`:
```bash
nano myfile.txt
```
#### nano Controls:
- Type freely to edit.
- `CTRL + X` to exit.
- `Y` to confirm saving changes.
- Press `Enter` to save.

---

## 5. Additional Resources
- [Linux Journey](https://linuxjourney.com/)
- [The Linux Command Line](https://linuxcommand.org/)
- [Official Ubuntu Documentation](https://help.ubuntu.com/)

---
Congratulations! You now have a solid foundation for working with Linux. Keep practicing and exploring!
