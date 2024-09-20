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

| Command                                      | Description                                                       |
|----------------------------------------------|-------------------------------------------------------------------|
| `adduser <username>`                         | Create a new user with home directory and default shell            |
| `useradd <username>`                         | Create a new user (minimal setup, no home directory by default)    |
| `userdel <username>`                         | Delete a user account                                              |
| `userdel -r <username>`                      | Delete a user account and their home directory                     |
| `passwd <username>`                          | Change the password for a user                                     |
| `chage -l <username>`                        | Display password aging information for a user                      |
| `usermod -aG <groupname> <username>`         | Add a user to a group                                              |
| `groups <username>`                          | List groups a user is part of                                      |
| `id <username>`                              | Show user ID (UID), group ID (GID), and other group memberships    |
| `deluser <username>`                         | Remove a user from the system                                      |
| `deluser <username> <groupname>`             | Remove a user from a specific group                                |
| `sudo <command>`                             | Execute a command as the superuser                                 |
| `su <username>`                              | Switch to another user account (requires that user's password)     |
| `who`                                        | Show who is logged in                                              |
| `whoami`                                     | Display the current logged-in user                                 |
| `last`                                       | Show last logins of users                                          |
| `w`                                          | Display who is logged in and what they are doing                   |
| `finger <username>`                          | Display detailed information about a user                          |
| `getent passwd`                              | Display all users in the system                                    |
| `vipw`                                       | Safely edit the `/etc/passwd` file (user accounts)                 |
| `visudo`                                     | Safely edit the `/etc/sudoers` file                                |
| `chown <owner>:<group> <file>`               | Change ownership of a file                                         |
| `chmod <permissions> <file>`                 | Change file permissions                                            |

---

### Group Management

| Command                                      | Description                                                       |
|----------------------------------------------|-------------------------------------------------------------------|
| `groupadd <groupname>`                       | Create a new group                                                 |
| `groupdel <groupname>`                       | Delete a group                                                     |
| `gpasswd -a <username> <groupname>`          | Add a user to a group (alternative to `usermod -aG`)               |
| `gpasswd -d <username> <groupname>`          | Remove a user from a group                                         |
| `newgrp <groupname>`                         | Switch to a new group for the current session                      |
| `groups <username>`                          | Display the groups a user belongs to                               |
| `getent group <groupname>`                   | Show group entry in `/etc/group`                                   |

---

### Account and Session Management

| Command                                      | Description                                                       |
|----------------------------------------------|-------------------------------------------------------------------|
| `chage -E <date> <username>`                 | Set an account expiration date for a user                          |
| `chage -M <days> <username>`                 | Set maximum number of days a password remains valid                |
| `chage -m <days> <username>`                 | Set minimum number of days before a password can be changed        |
| `chage -I <days> <username>`                 | Set the number of days after a password expires before an account is disabled |
| `faillog -u <username>`                      | Show login failure statistics for a user                           |
| `faillog -r <username>`                      | Reset failed login count for a user                                |
| `lastlog`                                    | Show the last login of all users                                   |
| `pkill -u <username>`                        | Terminate all processes owned by a user                            |
| `passwd -l <username>`                       | Lock a user account (disallow login)                               |
| `passwd -u <username>`                       | Unlock a user account                                              |
| `nologin`                                    | Prevent a user from logging in by setting their shell to `/sbin/nologin` |

---

### SSH Key Management for Users

| Command                                      | Description                                                       |
|----------------------------------------------|-------------------------------------------------------------------|
| `ssh-keygen`                                 | Generate a new SSH key pair                                        |
| `ssh-copy-id <username>@<host>`              | Copy SSH key to a remote host for passwordless login               |
| `cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys` | Manually add SSH public key for user authentication            |
| `chmod 600 ~/.ssh/authorized_keys`           | Set correct permissions for SSH authorized keys                    |

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

