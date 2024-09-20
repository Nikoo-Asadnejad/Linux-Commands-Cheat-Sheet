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

### Network Interface Management

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ip addr`                                    | Show all network interfaces and their IP addresses                          |
| `ip addr show <interface>`                   | Display information about a specific network interface                      |
| `ip link set <interface> up`                 | Bring a network interface up                                                |
| `ip link set <interface> down`               | Bring a network interface down                                              |
| `ifconfig`                                   | Display or configure network interface (older command, use `ip` for new systems) |
| `ifconfig <interface>`                       | Show details about a specific network interface                             |
| `ifdown <interface>`                         | Take a network interface down (Debian-based systems)                        |
| `ifup <interface>`                           | Bring a network interface up (Debian-based systems)                         |
| `ethtool <interface>`                        | Display or change Ethernet device settings                                  |
| `ip route`                                   | Display or manipulate the routing table                                     |
| `ip route add <destination> via <gateway>`   | Add a new route to the routing table                                        |
| `ip route del <destination>`                 | Remove a route from the routing table                                       |
| `hostname`                                   | Show or set the system’s hostname                                           |
| `hostname -I`                                | Display all IP addresses of the host                                        |
| `nmcli dev show <interface>`                 | Display the connection status of a specific network interface (NetworkManager) |
| `nmcli device status`                        | Show status of all network interfaces (NetworkManager)                      |
| `nmcli connection show`                      | Display saved network connections (NetworkManager)                          |
| `nmcli connection up <connection-name>`      | Bring up a specific network connection (NetworkManager)                     |
| `nmcli connection down <connection-name>`    | Bring down a specific network connection (NetworkManager)                   |
| `nmtui`                                      | Text-based user interface for managing network connections                  |

---

### DNS Management

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `dig <domain>`                               | Query DNS information for a domain                                          |
| `dig +short <domain>`                        | Get the short output (e.g., only the IP address)                            |
| `dig @<nameserver> <domain>`                 | Query a specific DNS server for domain resolution                           |
| `nslookup <domain>`                          | Query DNS information for a domain                                          |
| `host <domain>`                              | Perform DNS lookup and reverse lookup                                       |
| `systemd-resolve --status`                   | Show DNS resolution status (systemd-resolved)                               |
| `resolvectl query <domain>`                  | Query DNS using systemd-resolved                                            |
| `cat /etc/resolv.conf`                       | Display DNS server configuration                                            |

---

### Network Troubleshooting

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ping <host>`                                | Check connectivity to a host                                                |
| `ping -c <count> <host>`                     | Send a specific number of ICMP echo requests to a host                      |
| `ping6 <host>`                               | Send an ICMP echo request to a host using IPv6                              |
| `traceroute <host>`                          | Trace the path packets take to reach a host                                 |
| `tracepath <host>`                           | Similar to traceroute, but does not require superuser privileges            |
| `mtr <host>`                                 | Combines `ping` and `traceroute` to provide continuous network analysis     |
| `netstat -tuln`                              | Show listening ports and services                                           |
| `ss -tuln`                                   | Show listening sockets (more modern than `netstat`)                         |
| `nc -zv <host> <port>`                       | Check if a specific port is open on a host (TCP/UDP connection test)        |
| `nc -l <port>`                               | Open a port and listen for incoming connections                             |
| `telnet <host> <port>`                       | Check TCP connectivity to a host and port                                   |
| `curl <url>`                                 | Perform a basic HTTP request and display the response                       |
| `curl -I <url>`                              | Display HTTP headers for a URL                                              |
| `curl -O <url>`                              | Download a file from a URL                                                  |
| `wget <url>`                                 | Download files from the web using HTTP, HTTPS, or FTP                       |
| `arp -a`                                     | Display the system's ARP table (shows MAC to IP mappings)                   |
| `tcpdump`                                    | Capture and analyze network traffic                                         |
| `tcpdump -i <interface>`                     | Capture packets on a specific network interface                             |
| `tcpdump -nn -X port <port>`                 | Capture packets on a port and display the packet contents in hexadecimal    |

---

### Firewall Management (iptables and firewalld)

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `iptables -L`                                | List all firewall rules                                                     |
| `iptables -A <chain> -p <protocol> --dport <port> -j <target>` | Add a rule to a chain (e.g., ACCEPT, DROP)                                 |
| `iptables -D <chain> <rule-number>`          | Delete a specific rule from a chain                                         |
| `iptables -F`                                | Flush (delete) all firewall rules                                           |
| `firewall-cmd --list-all`                    | List all active firewalld rules (CentOS, Fedora)                            |
| `firewall-cmd --add-service=<service>`       | Temporarily allow a service through the firewall                            |
| `firewall-cmd --permanent --add-service=<service>` | Permanently allow a service through the firewall                         |
| `firewall-cmd --remove-service=<service>`    | Remove a service from the firewall                                          |
| `ufw status`                                 | Display the status of UFW (Uncomplicated Firewall) (Ubuntu)                 |
| `ufw enable`                                 | Enable UFW                                                                  |
| `ufw disable`                                | Disable UFW                                                                 |
| `ufw allow <port>/<protocol>`                | Allow traffic on a port (e.g., `ufw allow 22/tcp`)                          |
| `ufw deny <port>/<protocol>`                 | Deny traffic on a port                                                      |

---

### Network File Transfer

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `scp <source> <user>@<host>:<destination>`   | Securely copy files to a remote host                                        |
| `scp <user>@<host>:<source> <destination>`   | Securely copy files from a remote host                                      |
| `rsync -avz <source> <user>@<host>:<destination>` | Synchronize files between local and remote hosts                         |
| `rsync -avz <user>@<host>:<source> <destination>` | Synchronize files from remote to local                                    |
| `sftp <user>@<host>`                         | Start a secure file transfer session                                       |
| `ftp <host>`                                 | Start an FTP session (unencrypted)                                         |

---

### SSH and Remote Connections

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ssh <user>@<host>`                          | Connect to a remote host via SSH                                            |
| `ssh -i <keyfile> <user>@<host>`             | Connect to a remote host using a specific private key                       |
| `ssh -L <local-port>:<remote-host>:<remote-port> <user>@<host>` | Create an SSH tunnel with port forwarding                                |
| `ssh-copy-id <user>@<host>`                  | Copy local SSH key to a remote host to enable passwordless login            |
| `scp <user>@<host>:<source> <destination>`   | Securely copy files between local and remote hosts                          |
| `sftp <user>@<host>`                         | Securely transfer files to/from a remote host using SFTP                    |
| `tmux`                                       | Start a terminal multiplexer session (maintain SSH sessions)                |
| `screen`                                     | Start a screen session (maintain SSH sessions)                              |

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

