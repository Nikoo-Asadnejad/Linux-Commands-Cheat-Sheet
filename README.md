# Linux-Commands-Cheet-Sheet

A collection of common Linux commands for system navigation, file management, networking, and more.

## Table of Contents
1. [Basic Commands](#basic-commands)
2. [File and Directory Management](#file-and-directory-management)
3. [File Permissions](#file-permissions)
4. [Networking](#networking)
5. [Process Management](#process-management)
6. [System Monitoring](#system-monitoring)
7. [Disk Usage](#disk-usage)
8. [Package Management](#package-management)
9. [User Management](#user-management)
10. [SSH and Remote Access](#ssh-and-remote-access)

---

## Basic Commands

| Command            | Description                         |
|--------------------|-------------------------------------|
| `pwd`              | Print the current working directory |
| `ls`               | List files in the directory         |
| `cd <directory>`   | Change directory                    |
| `whoami`           | Display current user                |
| `echo <text>`      | Print text to terminal              |
| `history`          | Show command history                |

---

## File and Directory Management

| Command                                  | Description                             |
|------------------------------------------|-----------------------------------------|
| `touch <file>`                           | Create a new empty file                 |
| `mkdir <directory>`                      | Create a new directory                  |
| `cp <source> <destination>`              | Copy files or directories               |
| `mv <source> <destination>`              | Move or rename files/directories        |
| `rm <file>`                              | Delete a file                           |
| `rm -r <directory>`                      | Delete a directory and its contents     |
| `find <directory> -name <filename>`      | Search for files by name                |
| `grep '<pattern>' <file>`                | Search text in files                    |

---

## File Permissions

| Command                      | Description                                 |
|------------------------------|---------------------------------------------|
| `chmod <permissions> <file>`  | Change file permissions                     |
| `chown <owner>:<group> <file>`| Change file owner and group                 |
| `ls -l`                       | List files with permissions                 |

---

## Networking

| Command                      | Description                                 |
|------------------------------|---------------------------------------------|
| `ifconfig`                   | Show network interfaces and IP addresses    |
| `ping <host>`                | Send ICMP requests to a host                |
| `netstat -tuln`              | Show active network connections             |
| `traceroute <host>`          | Trace the route packets take to a host      |
| `wget <URL>`                 | Download a file from the web                |

---

## Process Management

| Command                      | Description                                 |
|------------------------------|---------------------------------------------|
| `ps aux`                     | List all running processes                  |
| `top`                        | Display real-time system stats              |
| `kill <PID>`                 | Terminate a process by PID                  |
| `killall <process>`          | Terminate all instances of a process        |
| `bg`                         | Resume a suspended job in the background    |
| `fg`                         | Bring a job to the foreground               |

---

## System Monitoring

| Command                      | Description                                 |
|------------------------------|---------------------------------------------|
| `df -h`                      | Show disk space usage                       |
| `du -h <directory>`           | Estimate file space usage                   |
| `free -h`                    | Display memory usage                        |
| `uptime`                     | Show system uptime                          |
| `dmesg`                      | Show kernel message buffer                  |
| `vmstat`                     | Display system resource usage               |

---

## Disk Usage

| Command                      | Description                                 |
|------------------------------|---------------------------------------------|
| `df -h`                      | Display disk usage by mounted partitions    |
| `du -h <directory>`           | Show the size of files or directories       |
| `lsblk`                      | List block devices (disks)                  |

---

## Package Management

### Debian/Ubuntu

| Command                      | Description                                 |
|------------------------------|---------------------------------------------|
| `apt-get update`              | Update package list                         |
| `apt-get upgrade`             | Upgrade all installed packages              |
| `apt-get install <package>`   | Install a package                           |
| `apt-get remove <package>`    | Remove a package                            |

### Red Hat/CentOS

| Command                      | Description                                 |
|------------------------------|---------------------------------------------|
| `yum update`                  | Update package list                         |
| `yum install <package>`       | Install a package                           |
| `yum remove <package>`        | Remove a package                            |

---

## User Management

| Command                      | Description                                 |
|------------------------------|---------------------------------------------|
| `adduser <username>`          | Create a new user                           |
| `passwd <username>`           | Change user password                        |
| `usermod -aG <group> <user>`  | Add a user to a group                       |
| `deluser <username>`          | Delete a user                               |
| `who`                         | Show who is logged in                       |

---

## SSH and Remote Access

| Command                      | Description                                 |
|------------------------------|---------------------------------------------|
| `ssh <user>@<host>`           | Connect to a remote host via SSH            |
| `scp <file> <user>@<host>:<path>` | Copy file to remote host via SSH        |
| `rsync -avz <source> <destination>` | Sync files between locations          |
| `ssh-keygen`                  | Generate SSH key pair                       |
| `ssh-copy-id <user>@<host>`   | Copy SSH key to remote host                 |

---

