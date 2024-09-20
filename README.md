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

## Systemd Management

**systemd** is the system and service manager for Linux operating systems. It is responsible for managing services, processes, and various units.

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `systemctl`                                  | Main command for managing systemd services and units                        |
| `systemctl status <service>`                 | Check the status of a service                                               |
| `systemctl start <service>`                  | Start a service                                                             |
| `systemctl stop <service>`                   | Stop a running service                                                      |
| `systemctl restart <service>`                | Restart a service                                                           |
| `systemctl reload <service>`                 | Reload the configuration of a service without restarting it                 |
| `systemctl enable <service>`                 | Enable a service to start on boot                                           |
| `systemctl disable <service>`                | Disable a service from starting on boot                                     |
| `systemctl is-enabled <service>`             | Check if a service is enabled to start at boot                              |
| `systemctl daemon-reload`                    | Reload systemd manager configuration files after changes                    |
| `systemctl list-units --type=service`        | List all systemd services                                                   |
| `systemctl list-units --failed`              | List failed services                                                        |
| `journalctl -u <service>`                    | View logs for a specific service                                            |
| `journalctl -xe`                             | View systemd logs with more details on errors                               |
| `systemctl mask <service>`                   | Completely disable a service, even if another service tries to start it     |
| `systemctl unmask <service>`                 | Re-enable a masked service                                                  |
| `systemctl show <service>`                   | Show detailed properties of a service                                       |
| `systemctl cat <service>`                    | View the unit file for a service                                            |
| `systemctl isolate <target>`                 | Switch to a specific system target (e.g., `multi-user.target`, `rescue.target`) |

### Systemd Unit Types

Systemd manages various types of units, not just services.

| Unit Type            | Description                                              |
|----------------------|----------------------------------------------------------|
| `.service`           | A system service (e.g., web servers, databases)           |
| `.socket`            | A socket for inter-process communication                  |
| `.device`            | A device unit exposed by the Linux kernel                 |
| `.mount`             | A file system mount point                                |
| `.automount`         | A mount point that is automatically mounted on access     |
| `.swap`              | A swap device or file                                     |
| `.target`            | A group of systemd units (e.g., `multi-user.target`)      |
| `.timer`             | A scheduling unit similar to cron jobs                    |

### Common Targets

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `systemctl get-default`                      | Show the current default target (e.g., multi-user, graphical)               |
| `systemctl set-default <target>`             | Set the default target (e.g., `multi-user.target`, `graphical.target`)      |
| `systemctl isolate <target>`                 | Switch the system to the specified target (e.g., `rescue.target`)           |

---

## Process Management:

### Viewing Processes

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ps aux`                                     | List all running processes in detail                                        |
| `ps -ef`                                     | List processes with full-format output                                      |
| `top`                                        | Show real-time system resource usage (CPU, memory, processes)               |
| `htop`                                       | Enhanced interactive process viewer (`htop` needs to be installed separately)|
| `pgrep <name>`                               | Find the PID(s) of a process by name                                        |
| `pidof <process>`                            | Find the PID of a running process                                           |
| `pstree`                                     | Display processes in a tree-like format                                     |

### Managing Processes

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `kill <PID>`                                 | Terminate a process by PID                                                  |
| `kill -9 <PID>`                              | Forcefully kill a process                                                   |
| `killall <name>`                             | Kill all processes by name                                                  |
| `pkill <name>`                               | Kill processes by name (supports regular expressions)                       |
| `bg`                                         | Resume a suspended job in the background                                    |
| `fg`                                         | Bring a background job to the foreground                                    |
| `jobs`                                       | List all background jobs in the current shell                               |
| `nice -n <priority> <command>`               | Start a process with a specified priority (lower value = higher priority)   |
| `renice <priority> <PID>`                    | Change the priority of a running process                                    |

### Monitoring Processes

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `top`                                        | Display real-time information about running processes and resource usage    |
| `htop`                                       | Interactive version of `top` (install separately with `sudo apt-get install htop`) |
| `uptime`                                     | Show how long the system has been running                                   |
| `free -m`                                    | Display system memory usage in megabytes                                    |
| `vmstat`                                     | Report virtual memory statistics                                            |
| `lsof`                                       | List open files by processes                                                |
| `strace -p <PID>`                            | Trace system calls made by a process                                        |
| `watch <command>`                            | Execute a command repeatedly and monitor its output in real-time            |

### Signals

Linux processes can be sent various signals to control their behavior.

| Signal    | Number  | Description                           |
|-----------|---------|---------------------------------------|
| `SIGHUP`  | 1       | Hangup, reload configuration          |
| `SIGINT`  | 2       | Interrupt from keyboard (Ctrl + C)    |
| `SIGKILL` | 9       | Kill signal, cannot be ignored        |
| `SIGTERM` | 15      | Termination signal                    |
| `SIGSTOP` | 19      | Stop process (cannot be ignored)      |
| `SIGCONT` | 18      | Continue a stopped process            |

---

### Background & Foreground Process Management

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `command &`                                  | Run a command in the background                                             |
| `bg`                                         | Resume a suspended job in the background                                    |
| `fg`                                         | Bring a background job to the foreground                                    |
| `jobs`                                       | List current jobs and their statuses                                        |
| `nohup <command> &`                          | Run a command immune to hangups, in the background                          |
| `disown <job>`                               | Remove a job from the job table, leaving it running                         |

---

### Process Ownership and Security

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ps -u <username>`                           | List all processes belonging to a user                                      |
| `sudo -u <username> <command>`               | Run a command as a different user                                           |
| `chown <owner>:<group> <file>`               | Change ownership of files or directories                                    |
| `chmod <permissions> <file>`                 | Modify permissions for a file or directory                                  |
| `setfacl -m u:<user>:rwx <file>`             | Set file access control lists (ACLs) for a user on a file                   |
| `getfacl <file>`                             | View ACL permissions of a file                                              |

---

### Monitoring CPU and Memory Usage by Process

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `top`                                        | Display processes sorted by CPU usage                                       |
| `htop`                                       | Interactive real-time process viewer                                        |
| `ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu` | List processes sorted by CPU usage                                          |
| `ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%mem` | List processes sorted by memory usage                                       |

