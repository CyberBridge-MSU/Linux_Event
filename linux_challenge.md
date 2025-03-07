# Linux Quest: The Debian Adventure

## Introduction

Welcome to "Linux Quest: The Debian Adventure"! This fun, story-driven challenge will help you master Linux basics on your Debian system. Each quest combines practical skills with an engaging storyline. Complete them to earn the title of "Command Line Hero"!

## Getting Started

1. Each participant needs access to a Debian-based system
2. Create a directory called `~/quest` to store your adventure progress
3. Have fun and help your fellow adventurers along the way!

## Quest 1: Secret Agent Setup

**Storyline:** You've been recruited as a Linux secret agent! Your first mission is to set up your headquarters and gather intelligence.

**Tasks:**
- Create your secret base: `mkdir -p ~/quest/hq`
- Discover your system's codename and save it: `lsb_release -a > ~/quest/hq/system_intel.txt`
- Find out who else is logged into the system: `who > ~/quest/hq/agents.txt`

**Learning Focus:** Directory creation, command output redirection, system information commands

**Hint:** The `mkdir` command creates directories. The `-p` flag creates parent directories if needed. Use the `>` symbol to save command output to a file.

**Super Hint:** Run these commands to complete the quest:
```
mkdir -p ~/quest/hq
lsb_release -a > ~/quest/hq/system_intel.txt
who > ~/quest/hq/agents.txt
cat ~/quest/hq/system_intel.txt
cat ~/quest/hq/agents.txt
```

## Quest 2: The Hidden Message

**Storyline:** A secret message has been encrypted! Decode it to receive your next mission.

**Tasks:**
- Run this command to create the encrypted message:
  ```
  echo "VGhlIHBhc3N3b3JkIGlzICJsaW51eGZ1biIuIFlvdXIgbmV4dCBtaXNzaW9uIGlzIHRvIGZpbmQgdGhlIGhpZGRlbiB0cmVhc3VyZSE=" > ~/quest/encrypted.txt
  ```
- Decode the message using the base64 tool
- Create a new file with the password found in the message

**Learning Focus:** Basic encryption/decryption, more file manipulation

**Hint:** Base64 is a simple encoding method. The `base64` command with the `-d` flag decodes text.

**Super Hint:** Use these commands:
```
base64 -d ~/quest/encrypted.txt
echo "linuxfun" > ~/quest/password.txt
```

## Quest 3: Treasure Hunt

**Storyline:** There's a hidden treasure somewhere in your file system! Use your search skills to find it.

**Tasks:**
- Create the treasure by running:
  ```
  sudo touch /usr/share/treasure.txt
  sudo bash -c 'echo "You found the treasure! The next clue is: Use pip install cowsay and then run cowsay to show off your discovery" > /usr/share/treasure.txt'
  ```
- Find the treasure file somewhere in your system (it's in `/usr/share/`)
- Read the contents of the treasure file
- Follow the instructions in the treasure

**Learning Focus:** File searching, reading file contents, installing packages

**Hint:** The `find` command can search your entire file system. Try `find / -name "treasure.txt" 2>/dev/null` to search for the file named "treasure.txt" (the `2>/dev/null` part hides error messages).

**Super Hint:** Complete this quest with:
```
find / -name "treasure.txt" 2>/dev/null
cat /usr/share/treasure.txt
sudo apt update
sudo apt install python3-pip -y
pip install cowsay
cowsay "I found the treasure!"
```

## Quest 4: Process Patrol

**Storyline:** A mysterious process is running on your system! Identify it and learn about process management.

**Tasks:**
- Start the "mysterious" process: `yes > /dev/null &`
- Find the process using process listing tools
- Check what resources it's using
- Safely stop the process

**Learning Focus:** Process management, background processes, monitoring

**Hint:** The `ps` command shows processes. Try `ps aux` to see all processes. The `top` command shows real-time process information. The `kill` command stops processes when you provide the process ID (PID).

**Super Hint:** Here's how to complete this quest:
```
yes > /dev/null &
ps aux | grep yes
top -n 1 | grep yes
kill [PID]
```
(Replace [PID] with the actual process ID number you found)

## Quest 5: Network Explorer

**Storyline:** Your next mission requires you to explore the digital landscape. Map your network territory!

**Tasks:**
- Find your IP address
- Check if google.com is reachable
- See what route your data takes to reach google.com

**Learning Focus:** Basic networking commands and concepts

**Hint:** The `ip` command shows network information. The `ping` command checks connectivity. The `traceroute` command shows the path data takes across the internet.

**Super Hint:** Complete with these commands:
```
ip addr show
ping -c 4 google.com
traceroute google.com
```

## Final Challenge: Automation Station

**Storyline:** A true Linux hero automates repetitive tasks! Create a simple script that performs multiple actions.

**Tasks:**
- Create a bash script called `daily_report.sh` in your quest directory that:
  - Displays the current date and time
  - Shows disk space usage
  - Lists the top 3 CPU-consuming processes
- Make the script executable
- Run the script to see your report

**Learning Focus:** Basic bash scripting, file permissions, automation

**Hint:** Use a text editor like `nano` to create your script. Every bash script starts with `#!/bin/bash`. The `chmod +x` command makes files executable.

**Super Hint:** Create your script with:
```
nano ~/quest/daily_report.sh
```

Add these contents:
```bash
#!/bin/bash
echo "=== Daily Report ==="
echo "Date and time: $(date)"
echo ""
echo "=== Disk Space ==="
df -h /
echo ""
echo "=== Top 3 CPU Processes ==="
ps aux --sort=-%cpu | head -4
```

Then make it executable and run it:
```
chmod +x ~/quest/daily_report.sh
~/quest/daily_report.sh
```

## Celebration

Congratulations, Command Line Hero! You've completed the Linux Quest adventure. You now have practical experience with:

- Creating and navigating directories
- Viewing and manipulating files
- Finding things on your system
- Managing processes
- Checking network connectivity
- Creating a simple automation script

Share your accomplishments with the community and help others on their Linux journey. Remember, the true Linux spirit is about continuous learning and helping others!

## Tracking Your Solutions

To keep track of your solutions and share them with others, create a Git repository to document your journey:

```bash
# Install Git if you don't have it
sudo apt update
sudo apt install git -y

# Create a new directory for your repository
mkdir -p ~/linux_adventure_solutions

# Initialize Git repository
cd ~/linux_adventure_solutions
git init

# Create a README file
echo "# My Linux Adventure Solutions" > README.md
echo "This repository contains my solutions to the Linux Quest challenges." >> README.md

# Create a branch for your solutions
git add README.md
git commit -m "Initial commit"
git branch my-solutions
git checkout my-solutions

# After completing each quest, you can add your solutions
# For example:
echo "## Quest 1: Secret Agent Setup" > quest1_solution.md
echo "I completed this quest by running the following commands:" >> quest1_solution.md
echo '```bash' >> quest1_solution.md
echo "mkdir -p ~/quest/hq" >> quest1_solution.md
echo "lsb_release -a > ~/quest/hq/system_intel.txt" >> quest1_solution.md
echo "who > ~/quest/hq/agents.txt" >> quest1_solution.md
echo '```' >> quest1_solution.md

# Commit your solution
git add quest1_solution.md
git commit -m "Add solution for Quest 1"
```

This creates a Git repository with a branch specifically for your solutions. You can continue adding solution files for each quest as you complete them. If you want to share with others, you can push this to GitHub or another Git hosting service.

