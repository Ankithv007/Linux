# Essential Linux Commands Cheat Sheet

This guide provides a list of crucial Linux commands for system navigation, file operations, process management, networking, and more. These commands are essential for Linux users and system administrators.

## Table of Contents

- [System Information](#system-information)
- [File Operations](#file-operations)
- [Directory Operations](#directory-operations)
- [Text Manipulation](#text-manipulation)
- [User Management](#user-management)
- [Process Management](#process-management)
- [Networking](#networking)
- [Disk Usage](#disk-usage)
- [Package Management](#package-management)
- [Permissions Management](#permissions-management)

---

## System Information

- **`uname -a`**: Display all system information.
- **`hostname`**: Show the system’s hostname.
- **`uptime`**: Display system uptime.
- **`whoami`**: Show the current logged-in user.
- **`top`**: Display all running processes.
- **`ps aux`**: Show active processes with detailed info.
- **`df -h`**: Show disk space usage in human-readable format.
- **`free -h`**: Display free and used memory in the system.

## File Operations

- **`ls`**: List files and directories.
  - `ls -l`: Long listing with file permissions, owner, size, etc.
  - `ls -a`: Include hidden files in the list.
- **`cat`**: Display contents of a file.
- **`cp source destination`**: Copy files or directories.
- **`mv source destination`**: Move or rename files and directories.
- **`rm filename`**: Delete a file.
  - `rm -r dirname`: Delete a directory and its contents recursively.
  - `rm -f filename`: Force deletion without prompting.
- **`touch filename`**: Create an empty file or update an existing file’s timestamp.
- **`find /path -name filename`**: Search for files in a specific directory.
- **`locate filename`**: Find files by name.

## Directory Operations

- **`pwd`**: Show current working directory.
- **`cd directory`**: Change to a specified directory.
- **`mkdir dirname`**: Create a new directory.
- **`rmdir dirname`**: Remove an empty directory.
- **`tree`**: Display directory structure in a tree format.

## Text Manipulation

- **`echo "text"`**: Print text to the console.
- **`grep 'pattern' filename`**: Search for a specific pattern in a file.
  - `grep -i 'pattern' filename`: Case-insensitive search.
- **`sort filename`**: Sort lines in a file.
- **`uniq filename`**: Remove duplicate lines from sorted data.
- **`head filename`**: Display the first 10 lines of a file.
- **`tail filename`**: Display the last 10 lines of a file.
- **`wc filename`**: Count lines, words, and characters in a file.
- **`cut -d':' -f1 filename`**: Cut fields from each line of a file.
- **`sed 's/old/new/g' filename`**: Find and replace text in a file.

## User Management

- **`adduser username`**: Create a new user.
- **`passwd username`**: Change the password for a user.
- **`userdel username`**: Delete a user account.
- **`usermod -aG groupname username`**: Add a user to a group.
- **`who`**: Show who is logged in.

## Process Management

- **`ps`**: Show currently running processes.
- **`top`**: Display real-time process monitoring.
- **`kill PID`**: Terminate a process by its PID.
- **`killall processname`**: Kill all instances of a process by name.
- **`bg`**: Resume a stopped job in the background.
- **`fg`**: Bring a background job to the foreground.
- **`jobs`**: List all jobs running in the background.

## Networking

- **`ping hostname`**: Send packets to a host and check connectivity.
- **`ifconfig`**: Show network interface configuration.
- **`ip addr`**: Display IP addresses assigned to network interfaces.
- **`curl url`**: Transfer data from or to a server.
- **`wget url`**: Download files from a URL.
- **`netstat`**: Show network connections, routing tables, etc.
- **`ss`**: Display socket statistics (alternative to `netstat`).
- **`traceroute hostname`**: Trace the path packets take to a network host.

## Disk Usage

- **`df -h`**: Display disk usage in human-readable format.
- **`du -h filename`**: Show the disk space used by files or directories.
- **`fdisk -l`**: List all disk partitions.
- **`mount /dev/sdX /mnt`**: Mount a filesystem.
- **`umount /mnt`**: Unmount a filesystem.

## Package Management

- **For Debian/Ubuntu-based systems:**
  - **`apt update`**: Update package lists.
  - **`apt upgrade`**: Upgrade installed packages.
  - **`apt install packagename`**: Install a new package.
  - **`apt remove packagename`**: Remove a package.
- **For RHEL/CentOS-based systems:**
  - **`yum update`**: Update all packages.
  - **`yum install packagename`**: Install a new package.
  - **`yum remove packagename`**: Remove a package.

## Permissions Management

- **`chmod permissions filename`**: Change file permissions.
  - Example: `chmod 755 filename` sets read, write, and execute for the owner and read and execute for others.
- **`chown user:group filename`**: Change the file owner and group.
- **`chgrp group filename`**: Change the group ownership of a file.

---

These are some of the most essential commands in Linux. This guide can be used as a quick reference for system administration, file management, and more in the Linux environment.
