# CyberBridge Linux Scripting Guide

## Introduction
Bash scripting is an essential skill for Linux users, system administrators, and developers. It allows automation of tasks, system administration, and the creation of powerful command-line tools. This guide covers fundamental scripting concepts and best practices.

## Table of Contents
1. Introduction to Bash Scripting  
2. Variables & User Input  
3. Conditional Statements  
4. Loops & Iteration  
5. Functions in Bash  
6. Working with Files & Directories  
7. Error Handling & Debugging  
8. Automating Tasks with Cron Jobs  
9. Advanced Scripting Techniques  
10. Additional Resources  

---

## 1. Introduction to Bash Scripting
Bash scripts are text files containing a series of commands executed in sequence by the Bash shell.

### Creating and Running a Script
```bash
#!/bin/bash
# My first script
echo "Hello, CyberBridge!"
```
- `#!/bin/bash` – Shebang line specifies the script interpreter.
- `echo` – Prints text to the terminal.

To make the script executable:
```bash
chmod +x myscript.sh
./myscript.sh
```

---

## 2. Variables & User Input
### Defining Variables
```bash
name="CyberBridge"
echo "Welcome to $name!"
```
### User Input
```bash
read -p "Enter your name: " username
echo "Hello, $username!"
```

---

## 3. Conditional Statements
```bash
if [ "$username" == "admin" ]; then
    echo "Welcome, Admin!"
else
    echo "Access Denied."
fi
```

---

## 4. Loops & Iteration
### For Loop
```bash
for i in {1..5}; do
    echo "Loop iteration $i"
done
```
### While Loop
```bash
count=1
while [ $count -le 5 ]; do
    echo "Count: $count"
    ((count++))
done
```

---

## 5. Functions in Bash
```bash
function greet {
    echo "Hello, $1!"
}
greet Linux
```

---

## 6. Working with Files & Directories
### Checking If a File Exists
```bash
if [ -f "/path/to/file" ]; then
    echo "File exists!"
else
    echo "File not found."
fi
```
### Reading a File Line by Line
```bash
while IFS= read -r line; do
    echo "$line"
done < myfile.txt
```

---

## 7. Error Handling & Debugging
### Debugging Scripts
Run the script with debugging enabled:
```bash
bash -x myscript.sh
```
### Handling Errors
```bash
command || echo "Command failed!"
```

---

## 8. Automating Tasks with Cron Jobs
To schedule a script, use `crontab -e` and add:
```bash
0 12 * * * /path/to/script.sh  # Runs daily at noon
```

---

## 9. Advanced Scripting Techniques
- **Arrays**
```bash
arr=("apple" "banana" "cherry")
echo "First item: ${arr[0]}"
```
- **Regular Expressions**
```bash
echo "hello world" | grep -E "hello"
```

---

## 10. Additional Resources
- [Bash Guide](https://www.gnu.org/software/bash/manual/)
- [Linux Shell Scripting Tutorial](https://linuxconfig.org/bash-scripting-tutorial-for-beginners)

---

This guide provides a strong foundation in Bash scripting. Mastering these concepts will greatly enhance your efficiency and automation capabilities in Linux!
