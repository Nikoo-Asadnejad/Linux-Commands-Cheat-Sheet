# Linux-Commands-Cheat-Sheet

A collection of common Linux commands for system navigation, file management, networking, and more.

## Table of Contents
1. [Basic Commands](#basic-commands)
2. [Operators](#operators)
3. [File and Directory Management](#file-and-directory-management)
4. [File Permissions](#file-permissions)
5. [Screen](#screen)
6. [Shutdown and Sleep](#shutdown_and_sleep)
7. [User Management](#user-management)
8. [Package Management](#package-management)
9. [Cron Jobs and Scheduling](#cron-jobs-and-scheduling)
10. [Process Management](#process-management)
11. [System Monitoring](#system-monitoring)
12. [Systemd Management](systemd-management)
13. [Networking](#networking)
14. [SSH Management](#ssh-management)
15. [Mail Management](mail-management)
16. [Kernel and Modules Management](#kernel-and-modules-management)
17. [Boot, Bootloader (GRUB), and EFI Firmware](#boot-bootloader-grub-and-efi-firmware)

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

### System Information

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `uname -a`                                   | Display detailed system information (kernel, hostname, etc.)                |
| `uname -r`                                   | Show the kernel version                                                     |
| `hostname`                                   | Show or set the system hostname                                             |
| `hostnamectl`                                | Display or set the system's hostname and related settings                   |
| `uptime`                                     | Show how long the system has been running and system load                   |
| `whoami`                                     | Display the current user                                                    |
| `id`                                         | Show the current user’s ID and group information                            |
| `who`                                        | Show who is currently logged into the system                                |
| `w`                                          | Display who is logged in and what they are doing                            |
| `date`                                       | Show or set the system date and time                                        |
| `cal`                                        | Display a calendar for the current month                                    |
| `df -h`                                      | Show disk space usage in human-readable format                              |
| `du -h <directory>`                          | Display the disk usage of files and directories in human-readable format    |
| `du -sh <directory>`                         | Display the total size of a directory                                       |
| `top`                                        | Display real-time system resource usage and processes                       |
| `free -h`                                    | Show memory usage in human-readable format                                  |
| `lscpu`                                      | Display CPU architecture information                                        |
| `lsblk`                                      | List information about block devices (disks, partitions)                    |
| `dmesg`                                      | Display messages from the kernel ring buffer                                |
| `lsusb`                                      | List information about USB devices                                          |
| `lspci`                                      | List information about PCI devices                                          |
| `uptime`                                     | Display the system’s uptime and load averages                               |
| `last`                                       | Show the last logins of users                                               |
| `uname -m`                                   | Show the machine hardware name (e.g., x86_64)                               |

---

## Operators

| Operator        | Description                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| `|` (Pipe)      | Pass the output of one command as input to another command (`ls | grep txt`) |
| `>`             | Redirect output to a file, overwriting the file if it exists (`echo "Hello" > file.txt`) |
| `>>`            | Redirect output to a file, appending if the file exists (`echo "Hello" >> file.txt`) |
| `<`             | Redirect input from a file to a command (`sort < file.txt`)                 |
| `2>`            | Redirect error output to a file (`command 2> error.log`)                    |
| `2>&1`          | Redirect error output to standard output (`command > file.txt 2>&1`)        |
| `&`             | Run a command in the background (`command &`)                               |
| `&&`            | Run the next command only if the previous command succeeds (`command1 && command2`) |
| `||`            | Run the next command only if the previous command fails (`command1 || command2`) |
| `;`             | Run multiple commands in sequence (`command1; command2; command3`)          |
| `$(command)`    | Command substitution: use the output of a command as an argument (`echo $(date)`) |
| `&>`            | Redirect both standard output and error output to a file (`command &> output.log`) |

___

## File and Directory Management

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ls`                                         | List files and directories in the current directory                         |
| `ls -l`                                      | List files and directories with detailed information                        |
| `ls -a`                                      | List all files, including hidden files                                      |
| `cd <directory>`                             | Change to a specific directory                                              |
| `cd ..`                                      | Move up one directory level                                                 |
| `pwd`                                        | Display the current working directory                                       |
| `mkdir <directory>`                          | Create a new directory                                                      |
| `rmdir <directory>`                          | Remove an empty directory                                                   |
| `rm <file>`                                  | Delete a file                                                               |
| `rm -r <directory>`                          | Remove a directory and its contents recursively                             |
| `rm -rf <directory>`                         | Forcefully remove a directory and its contents                              |
| `cp <source> <destination>`                  | Copy files or directories                                                   |
| `cp -r <source-directory> <destination>`     | Copy directories recursively                                                |
| `mv <source> <destination>`                  | Move or rename files and directories                                        |
| `touch <file>`                               | Create an empty file or update the timestamp of an existing file            |
| `ln -s <target> <link>`                      | Create a symbolic link (soft link)                                          |
| `ln <target> <link>`                         | Create a hard link                                                          |
| `cat <file>`                                 | Display the contents of a file                                              |
| `less <file>`                                | View the contents of a file page by page                                    |
| `more <file>`                                | View the contents of a file page by page (older than `less`)                |
| `head <file>`                                | Display the first 10 lines of a file                                        |
| `tail <file>`                                | Display the last 10 lines of a file                                         |
| `tail -f <file>`                             | Display the contents of a file in real-time (follow the file as it grows)   |
| `find <directory> -name <filename>`          | Search for a file or directory by name                                      |
| `find <directory> -type d -name <dirname>`   | Find directories matching a specific name                                   |
| `find <directory> -type f -name <filename>`  | Find files matching a specific name                                         |
| `grep "<pattern>" <file>`                    | Search for a specific pattern in a file                                     |
| `grep -r "<pattern>" <directory>`            | Search for a pattern recursively in a directory                             |

---

## File Permissions

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ls -l`                                      | List files and show their permissions, owner, and group                     |
| `chmod <permissions> <file>`                 | Change the permissions of a file or directory                               |
| `chmod 644 <file>`                           | Set read/write for owner and read-only for group and others                 |
| `chmod 755 <directory>`                      | Set read/write/execute for owner, read/execute for group and others         |
| `chown <owner>:<group> <file>`               | Change the owner and group of a file or directory                           |
| `chown <owner> <file>`                       | Change the owner of a file                                                  |
| `chgrp <group> <file>`                       | Change the group of a file                                                  |

---

## Screen

| Command                      | Description                                         |
|------------------------------|-----------------------------------------------------|
| `screen`                     | Start a new screen session                          |
| `screen -S <session_name>`    | Start a new screen session with a custom name       |
| `screen -ls`                 | List all active screen sessions                     |
| `screen -r <session_id>`      | Reattach to a detached screen session               |
| `Ctrl + a + d`               | Detach from the current screen session               |
| `screen -X -S <session_id> quit` | Force quit a screen session                     |
| `Ctrl + a + k`               | Kill the current screen                             |
| `screen -x <session_id>`      | Attach to a running session shared by multiple users|
| `Ctrl + a + n`               | Switch to the next window in the screen session      |
| `Ctrl + a + p`               | Switch to the previous window in the screen session  |
| `Ctrl + a + c`               | Create a new window in the current screen session    |
| `Ctrl + a + "`               | List all windows in the current session              |

___

## Shutdown and Sleep

| Command                      | Description                                           |
|------------------------------|-------------------------------------------------------|
| `shutdown now`               | Shut down the system immediately                      |
| `shutdown -h now`            | Halt the system immediately                           |
| `shutdown -r now`            | Restart the system immediately                        |
| `shutdown -h +<time>`        | Schedule shutdown after a specified time (e.g., `+10` for 10 minutes) |
| `shutdown -c`                | Cancel a scheduled shutdown                           |
| `reboot`                     | Reboot the system                                     |
| `halt`                       | Halt the system without powering it off               |
| `systemctl poweroff`         | Power off the system                                  |
| `systemctl reboot`           | Reboot the system                                     |
| `systemctl suspend`          | Suspend the system (sleep mode)                       |
| `systemctl hibernate`        | Hibernate the system                                  |
| `systemctl hybrid-sleep`     | Hibernate and suspend the system                      |
| `pm-suspend`                 | Suspend the system (if `pm-utils` is installed)       |
| `pm-hibernate`               | Hibernate the system (if `pm-utils` is installed)     |
| `pm-suspend-hybrid`          | Hibernate and suspend the system (if `pm-utils` is installed) |

___

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

## Cron Jobs and Scheduling

### Managing Cron Jobs

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `crontab -e`                                | Edit the current user's crontab file                                      |
| `crontab -l`                                | List the current user's cron jobs                                          |
| `crontab -r`                                | Remove the current user's crontab file                                     |
| `sudo crontab -e -u <username>`            | Edit the crontab for a specified user                                      |
| `sudo crontab -l -u <username>`            | List the crontab for a specified user                                      |
| `sudo crontab -r -u <username>`            | Remove the crontab for a specified user                                    |

---

### Cron Job Syntax
Cron jobs are defined using the following syntax:
<p>* * * * * command_to_run</p>

#### Example Cron Job Entries

| Entry                                        | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `0 5 * * * /path/to/script.sh`             | Run a script every day at 5:00 AM                                         |
| `*/15 * * * * /path/to/backup.sh`          | Run a backup script every 15 minutes                                       |
| `0 0 1 * * /path/to/report.sh`             | Run a report script at midnight on the first day of every month           |
| `30 2 * * 1 /path/to/cleanup.sh`           | Run a cleanup script every Monday at 2:30 AM                              |

---

### System-Wide Cron Jobs

System-wide cron jobs are configured in `/etc/crontab` and can also be found in the `/etc/cron.d/` directory.

### Scheduling with `at`

The `at` command is used to schedule one-time tasks.

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `at 10:00`                                  | Schedule a command to run at 10:00 AM (prompt for the command)            |
| `echo "command_to_run" | at 10:00`         | Schedule a command to run at 10:00 AM                                     |
| `atq`                                       | List scheduled jobs for the current user                                   |
| `atrm <job_number>`                         | Remove a scheduled job by its job number                                   |

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

## Networking

### Network Interface Management

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ip addr`                                    | Show all network interfaces and their IP addresses                          |
| `ip -a`                                      | Show all network interfaces and their IP addresses                          |
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
| `sudo nmcli connection reload`               | Reload connection                                                           |
| `nmtui`                                      | Text-based user interface for managing network connections                  |
| `sudo systemctl restart NetworkManager`      | Apply configs                                                               |
| `sudo nmtui`                                 |  Ui for managing network in RHel                                            |
| `cat /etc/sysconfig/network-scripts/ifcfg-eth160` | ip configs in redhat                                                   |

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

This section provides commands for monitoring system performance, processes, CPU, memory, disk I/O, and network activity.

### General System Monitoring

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `top`                                        | Real-time view of CPU and memory usage by processes                         |
| `htop`                                       | Enhanced, interactive version of `top` with additional features (may require installation) |
| `vmstat`                                     | Report virtual memory statistics, including processes, memory, paging, block I/O, and CPU activity |
| `glances`                                    | Comprehensive system monitoring tool (requires installation)                |
| `uptime`                                     | Show how long the system has been running and system load                   |
| `watch <command>`                            | Run a command repeatedly at regular intervals and display the output live   |

---

### CPU Monitoring

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `mpstat`                                     | Display CPU usage per core (from `sysstat` package)                         |
| `sar`                                        | Collect, report, and save system activity information (including CPU, memory, I/O, etc.) |
| `lscpu`                                      | Display CPU architecture information (model, cores, speed)                  |
| `cat /proc/cpuinfo`                          | Display detailed CPU information                                            |
| `iostat`                                     | CPU and I/O statistics, part of the `sysstat` package                       |

---

### Memory Monitoring

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `free -h`                                    | Display memory usage in human-readable format (total, used, free, swap)     |
| `vmstat -s`                                  | Memory and swap statistics in a detailed format                             |
| `cat /proc/meminfo`                          | View detailed memory statistics                                             |
| `watch free -h`                              | Monitor memory usage in real-time                                           |
| `dmidecode --type memory`                    | Display detailed information about installed memory (requires root)         |

---

### Disk Usage and I/O Monitoring

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `df -h`                                      | Display disk space usage in human-readable format                           |
| `du -sh <directory>`                         | Display the total size of a directory in human-readable format              |
| `iostat`                                     | Show disk I/O and CPU usage statistics (from `sysstat` package)             |
| `iotop`                                      | Display real-time disk I/O usage by processes (requires installation)       |
| `dstat`                                      | Comprehensive resource statistics (including disk I/O)                      |
| `lsblk`                                      | List block devices, partitions, and file systems                            |
| `blkid`                                      | Display block device attributes such as UUIDs and file system types         |
| `df -i`                                      | Show inode usage for file systems                                           |
| `du -ah <directory>`                         | Show disk usage for all files and directories                               |
| `hdparm -t /dev/sda`                         | Test read speed of a disk (may require installation)                        |

---

### Process Monitoring

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ps aux`                                     | List all running processes with detailed information                        |
| `pgrep <process-name>`                       | Search for a running process by name                                        |
| `pidof <process-name>`                       | Find the process ID (PID) of a running process                              |
| `pstree`                                     | Show processes in a tree-like format                                        |
| `kill <PID>`                                 | Send a signal to terminate a process using its PID                          |
| `killall <process-name>`                     | Terminate all processes matching a specific name                            |
| `pkill <process-name>`                       | Send a signal to processes based on name and other attributes               |
| `renice <priority> <PID>`                    | Change the priority of a running process                                    |
| `strace -p <PID>`                            | Trace system calls and signals for a specific process                       |
| `lsof`                                       | List open files by processes                                                |
| `lsof -i :<port>`                            | List processes using a specific network port                                |
| `nice -n <priority> <command>`               | Start a command with a specified priority                                   |

---

### Network Monitoring

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `netstat -tuln`                              | Show listening ports and their associated services                          |
| `ss -tuln`                                   | More modern version of `netstat`, shows listening ports                     |
| `iftop`                                      | Display real-time network bandwidth usage (requires installation)           |
| `nload`                                      | Show incoming and outgoing network traffic (requires installation)          |
| `tcpdump -i <interface>`                     | Capture and display network packets on a specific interface                 |
| `iptraf-ng`                                  | Real-time network traffic monitoring (requires installation)                |
| `ping <hostname/IP>`                         | Test network connectivity by sending ICMP echo requests                     |
| `traceroute <hostname/IP>`                   | Trace the path packets take to reach a network host                         |
| `ss -s`                                      | Show detailed socket statistics                                             |
| `arp -a`                                     | Display the system's ARP table (address resolution protocol)                |
| `dig <hostname>`                             | Query DNS servers for information about a hostname                          |
| `host <hostname>`                            | Perform DNS lookup for a domain or IP address                               |
| `nslookup <hostname>`                        | Query DNS to resolve a hostname to an IP address                            |
| `mtr <hostname>`                             | Network diagnostic tool combining `ping` and `traceroute` (requires installation) |

---

### Miscellaneous System Monitoring

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `uptime`                                     | Show how long the system has been running and the current load average      |
| `last`                                       | Show the last logins of users on the system                                 |
| `sar`                                        | Collect and display system activity statistics (CPU, memory, I/O, network)  |
| `dstat`                                      | Tool for generating detailed performance and resource statistics            |
| `vmstat`                                     | Report information about processes, memory, paging, and I/O                 |
| `iostat -x`                                  | Show extended I/O statistics, including disk utilization                    |
| `tload`                                      | Show a graphical representation of system load in the terminal              |
| `uptime`                                     | Display system uptime and load averages                                     |
| `w`                                          | Show who is logged in and what they are doing                               |
| `who`                                        | Show who is logged in to the system                                         |


## SSH Management

SSH (Secure Shell) is a protocol used for securely accessing remote machines over a network. This section covers commands for managing SSH connections, keys, and configuration.

### Basic SSH Commands

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ssh <user>@<host>`                          | Connect to a remote host as a specified user                               |
| `ssh -p <port> <user>@<host>`               | Connect to a remote host on a specific port                                |
| `ssh -i <keyfile> <user>@<host>`            | Connect using a specific private key file                                   |
| `ssh -L <local_port>:<remote_host>:<remote_port> <user>@<host>` | Create an SSH tunnel for local port forwarding                              |
| `ssh -R <remote_port>:<local_host>:<local_port> <user>@<host>` | Create an SSH tunnel for remote port forwarding                             |
| `ssh -D <local_port> <user>@<host>`         | Set up a SOCKS proxy on the specified local port                           |
| `scp <file> <user>@<host>:<remote_path>`    | Copy a file to a remote host using SSH                                    |
| `scp <user>@<host>:<remote_path> <local_path>` | Copy a file from a remote host to the local machine                       |
| `rsync -avz -e "ssh -p <port>" <source> <user>@<host>:<destination>` | Sync files with a remote host over SSH                                    |

---

### SSH Key Management

SSH keys provide a secure way to authenticate without using passwords.

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` | Generate a new SSH key pair (RSA, 4096 bits)                               |
| `ssh-add <keyfile>`                         | Add a private key to the SSH authentication agent                          |
| `ssh-copy-id <user>@<host>`                  | Install your public key on a remote host for passwordless authentication    |
| `cat ~/.ssh/id_rsa.pub`                     | Display your public key for sharing                                        |
| `ssh-agent bash`                            | Start a new shell with the SSH agent running                               |
| `ssh-keygen -R <host>`                       | Remove the specified host from the known_hosts file                        |
| `ssh -Q key`                                 | List supported key types                                                  |

---

### Common SSH Configuration Options

| Option                                       | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `Host <name>`                               | Alias for a host configuration                                             |
| `HostName <hostname>`                       | Actual hostname or IP address to connect to                                |
| `User <username>`                           | Default username to log in as                                             |
| `Port <port_number>`                        | Port to connect to (default is 22)                                        |
| `IdentityFile <path>`                       | Path to the private key file for authentication                            |
| `ForwardAgent yes`                          | Enable SSH agent forwarding                                                |
| `StrictHostKeyChecking no`                  | Disable host key verification (not recommended for security)              |

---

### SSH Key Management for Users

| Command                                      | Description                                                       |
|----------------------------------------------|-------------------------------------------------------------------|
| `ssh-keygen`                                 | Generate a new SSH key pair                                        |
| `ssh-copy-id <username>@<host>`              | Copy SSH key to a remote host for passwordless login               |
| `cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys` | Manually add SSH public key for user authentication            |
| `chmod 600 ~/.ssh/authorized_keys`           | Set correct permissions for SSH authorized keys                    |

---

### SSH Security Best Practices

| Best Practice                                 | Description                                                                 |
|-----------------------------------------------|-----------------------------------------------------------------------------|
| Use SSH keys instead of passwords             | SSH keys provide better security than passwords.                           |
| Disable root login                            | Prevent direct SSH login as root by editing `/etc/ssh/sshd_config`:      |
|                                               | ```plaintext                                                               |
| PermitRootLogin no                            |
| ```                                          |
| Use strong passphrases for SSH keys          | Protect private keys with strong passphrases.                              |
| Change the default SSH port                   | Edit `/etc/ssh/sshd_config` and change `Port 22` to another port.        |
| Enable two-factor authentication               | Add an extra layer of security with 2FA using tools like `Google Authenticator`. |

---

### SSH Configuration

The SSH client can be configured using the `~/.ssh/config` file for convenience and ease of use.

#### Example SSH Configurations

```plaintext
# Default settings
Host *
    User your_username
    Port 22
    IdentityFile ~/.ssh/id_rsa

# Specific host configuration
Host myserver
    HostName myserver.example.com
    User myuser
    Port 2222
    IdentityFile ~/.ssh/myserver_id_rsa
```

## Mail Management

### Sending Mail

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `mail <recipient>`                           | Open the mail client to send an email                                      |
| `echo "Email body" | mail -s "Subject" <recipient>` | Send an email with a subject from the command line                      |
| `sendmail <recipient>`                       | Send an email using the sendmail command                                   |
| `mailx -s "Subject" <recipient> < <file>`   | Send the contents of a file as the body of the email                       |
| `mutt -s "Subject" <recipient> < <file>`    | Send an email with a subject using mutt                                    |
| `ssmtp <recipient>`                          | Send an email using ssmtp (simple SMTP client)                            |
| `mail -c <cc_recipient>`                    | Send a carbon copy (CC) of the email to another recipient                  |
| `mail -b <bcc_recipient>`                   | Send a blind carbon copy (BCC) of the email to another recipient           |

---

### Common Mail Services

| Service                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `postfix`                                   | A widely used mail transfer agent (MTA)                                   |
| `sendmail`                                  | A traditional mail transfer agent, often used for sending mail            |
| `exim`                                      | Another popular mail transfer agent                                        |
| `ssmtp`                                     | A simple utility to send emails via SMTP                                   |
| `mutt`                                      | A text-based email client for Unix                                         |
| `mailx`                                     | An enhanced version of the mail command                                    |

---

### Mail Troubleshooting

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `tail -f /var/log/mail.log`                 | Monitor mail logs for sending issues (Debian/Ubuntu)                      |
| `grep "error" /var/log/mail.log`            | Search for errors in the mail log                                          |
| `mailq`                                     | View the mail queue                                                       |
| `sendmail -bv <recipient>`                  | Verify if an email can be sent to a recipient                             |

### Mail Configuration

Configuration files for mail services can typically be found in `/etc/mail/` or `/etc/`.

#### Example `/etc/ssmtp/ssmtp.conf` Configuration

```plaintext
root=postmaster
mailhub=smtp.example.com:587
AuthUser=username
AuthPass=password
UseSTARTTLS=YES
```

## Kernel and Modules Management

This section provides commands for managing the Linux kernel and its modules, including loading, unloading, and querying kernel modules.

### Kernel Information

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `uname -r`                                   | Display the current kernel version                                          |
| `uname -a`                                   | Display all system information, including the kernel version                |
| `hostnamectl`                                | Show information about the host, including kernel version                   |
| `cat /proc/version`                          | Display kernel version information from the `/proc` filesystem              |
| `dmesg`                                      | Display boot and kernel log messages                                        |
| `dmesg | grep <keyword>`                     | Filter kernel messages for specific keywords                                |
| `ls /boot/`                                  | List the files related to the kernel, including kernel images               |

---

### Kernel Module Management

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `lsmod`                                      | List currently loaded kernel modules                                        |
| `modinfo <module_name>`                      | Display detailed information about a specific kernel module                 |
| `modprobe <module_name>`                     | Load a kernel module into the running kernel                                |
| `modprobe -r <module_name>`                  | Remove a kernel module from the running kernel                              |
| `insmod <path_to_module>`                    | Insert a module into the kernel (requires the full path to the module file) |
| `rmmod <module_name>`                        | Remove a kernel module                                                      |
| `depmod -a`                                  | Generate a list of module dependencies                                      |
| `modprobe --show-depends <module_name>`      | Show module dependencies before loading it                                  |
| `ls /lib/modules/$(uname -r)/kernel/`        | List the kernel modules available for the current kernel                    |

---

### Kernel Parameters Management

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `sysctl -a`                                  | Display all kernel parameters (sysctl settings)                             |
| `sysctl <parameter>`                         | View the current value of a specific kernel parameter                       |
| `sysctl -w <parameter>=<value>`              | Set the value of a kernel parameter at runtime                              |
| `cat /proc/sys/<parameter>`                  | View a kernel parameter's current value directly from the `/proc` filesystem|
| `echo <value> > /proc/sys/<parameter>`       | Temporarily change a kernel parameter (until reboot)                        |
| `nano /etc/sysctl.conf`                      | Edit the sysctl configuration file to apply kernel parameter changes permanently |
| `sysctl -p`                                  | Reload sysctl settings from the configuration file                          |

---

### Kernel Boot Parameters

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `cat /proc/cmdline`                          | Show the kernel parameters passed at boot time                              |
| `nano /etc/default/grub`                     | Edit GRUB configuration to permanently modify kernel boot parameters        |
| `grub-mkconfig -o /boot/grub/grub.cfg`       | Rebuild the GRUB configuration file after making changes                    |
| `update-grub`                                | Update GRUB to apply boot configuration changes                             |

---

### Rebuilding the Initramfs

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `mkinitcpio -p linux`                        | Rebuild the initramfs for Arch-based systems                                |
| `update-initramfs -u`                        | Update the initramfs for the current kernel (Debian/Ubuntu)                 |
| `dracut -f`                                  | Regenerate initramfs on systems using Dracut                                |

---

### Kernel Upgrade and Management

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `apt-cache search linux-image`               | Search for available kernel versions (Debian/Ubuntu)                        |
| `apt install linux-image-<version>`          | Install a specific kernel version (Debian/Ubuntu)                           |
| `dnf list kernel`                            | List available kernel versions (Fedora)                                     |
| `dnf install kernel-<version>`               | Install a specific kernel version (Fedora)                                  |
| `yum update kernel`                          | Update the kernel to the latest version (CentOS/Red Hat)                    |
| `grubby --default-kernel`                    | Show the default kernel used at boot time                                   |
| `grubby --set-default /boot/vmlinuz-<version>`| Set a specific kernel as the default for booting (RHEL/CentOS)              |
| `reboot`                                     | Reboot the system to load the newly installed kernel                        |

---

### Kernel Compilation (Advanced)

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `make menuconfig`                            | Configure kernel options before compiling                                   |
| `make -j$(nproc)`                            | Compile the kernel using all available CPU cores                            |
| `make modules_install`                       | Install compiled kernel modules                                             |
| `make install`                               | Install the compiled kernel                                                 |
| `make mrproper`                              | Clean up all kernel build files and configurations                          |
| `cp /boot/config-$(uname -r) .config`        | Copy the current kernel config file as a base for compiling                 |

---

## Boot, Bootloader (GRUB), and EFI Firmware

This section covers commands related to system boot, managing the GRUB bootloader, and working with EFI/UEFI firmware.

---

### GRUB Bootloader Management

GRUB (GRand Unified Bootloader) is the default bootloader for many Linux distributions, and it manages which kernel or operating system to boot.

#### Common GRUB Commands

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `grub-install /dev/sda`                      | Install GRUB bootloader on the specified disk (e.g., `/dev/sda`)            |
| `grub-mkconfig -o /boot/grub/grub.cfg`       | Generate the GRUB configuration file (run after installing or updating GRUB)|
| `update-grub`                                | Update GRUB configuration (Debian/Ubuntu)                                   |
| `grub-set-default <entry>`                   | Set the default boot entry by specifying the menu entry index or title      |
| `grub-reboot <entry>`                        | Reboot the system into a specific GRUB entry once                           |
| `grub-editenv list`                          | List the saved GRUB environment variables                                   |
| `grub2-mkconfig -o /boot/grub2/grub.cfg`     | Generate GRUB configuration (Red Hat/CentOS/Fedora)                         |
| `grub2-install /dev/sda`                     | Install GRUB on Red Hat-based systems (RHEL/CentOS/Fedora)                  |
| `nano /etc/default/grub`                     | Edit GRUB configuration file for setting timeout, default OS, etc.          |

#### GRUB Configuration Example

You can manually edit `/etc/default/grub` to modify boot options, such as default kernel, timeout, or adding kernel boot parameters.

```bash
GRUB_DEFAULT=0
GRUB_TIMEOUT=5
GRUB_CMDLINE_LINUX="quiet splash"
GRUB_GFXMODE=1920x1080
```
After making changes, update the GRUB configuration:
```bash
sudo update-grub
```

### EFI/UEFI Firmware Management

EFI (Extensible Firmware Interface) or UEFI (Unified Extensible Firmware Interface) is the modern replacement for the traditional BIOS. It manages the system boot process and offers advanced features like secure boot, boot entries management, and boot order control.

#### EFI/UEFI Commands

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `efibootmgr`                                 | Manage UEFI boot entries and settings                                       |
| `efibootmgr -v`                              | List all UEFI boot entries in verbose mode                                  |
| `efibootmgr -n <boot-number>`                | Set the next boot entry for the system to boot from once                    |
| `efibootmgr -o 0001,0002`                    | Change the boot order to prioritize boot entry 0001 followed by 0002        |
| `efibootmgr -b 0003 -B`                      | Remove the UEFI boot entry number 0003                                      |
| `efibootmgr -c -d /dev/sda -p 1 -L "Linux" -l /vmlinuz` | Create a new boot entry for Linux on the EFI partition on `/dev/sda1`     |
| `efibootmgr -t 5`                            | Set a 5-second timeout for the UEFI boot menu                               |
| `efibootmgr -a <boot-number>`                | Activate a specific boot entry                                              |

---

#### Viewing and Modifying EFI Variables

EFI variables contain information about system settings and configuration.

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `ls /sys/firmware/efi/efivars/`              | List all EFI variables on the system                                        |
| `cat /sys/firmware/efi/fw_platform_size`     | Display whether the platform is 32-bit or 64-bit UEFI                       |
| `efivar --list`                              | List all UEFI variables in a readable format                                |
| `efivar --print <variable>`                  | Display detailed information about a specific EFI variable                  |
| `modprobe efivars`                           | Load the `efivars` module to access UEFI variables                         |

---

#### Secure Boot Management

Secure Boot is a feature of UEFI that only allows signed software (such as bootloaders and operating systems) to boot. 

| Command                                      | Description                                                                 |
|----------------------------------------------|-----------------------------------------------------------------------------|
| `mokutil --sb-state`                         | Check the current state of Secure Boot                                      |
| `mokutil --enable-validation`                | Enable Secure Boot validation                                               |
| `mokutil --disable-validation`               | Disable Secure Boot validation                                              |
| `mokutil --list-enrolled`                    | List the keys enrolled in Secure Boot                                       |
| `mokutil --import <keyfile>`                 | Import a new key to be used for Secure Boot                                 |
| `mokutil --reset`                            | Reset all Secure Boot keys to their default state                           |

---

#### Booting into UEFI Firmware

To enter the UEFI firmware settings from Linux:

1. **Systemd-based distributions**:
   ```bash
   systemctl reboot --firmware-setup

