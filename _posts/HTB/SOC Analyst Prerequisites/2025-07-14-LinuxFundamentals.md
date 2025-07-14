---
layout: post
title: Linux Fundamentals Module
date: 2025-07-14 11:57
category: [HTB, SOC Analyst Prerequisites]
tags: [HTB, SOC Analyst Prerequisites, Linux, Course, Module]
summary: Notes from the Linux Fundamentals module of the HTB SOC Analyst Prerequisites course.
---

# Linux Fundamentals
#### HTB SOC Analyst Prerequisites


---

# 1. Introduction
## 1.1. Linux Structure

Linux is an operating system renowned for its robustness, flexibility, and open-source nature. Linux comes in many distributions (distros), each tailored for specific use cases, from servers to desktops. Understanding the structure of Linux is crucial for effective system administration and security analysis.
Linux was originally developed by Linus Torvalds in 1991 as a free operating system kernel. It is under GNU General Public License (GPL), which allows users to run, study, modify, and distribute the software freely.

### Philosophy
Linux follows the Unix philosophy, which emphasizes simplicity, modularity, and openness. This philosophy encourages the development of small, single-purpose tools that can be combined to perform complex tasks. It follows 5 core principles:
1. **Everything is a file**: In Linux, almost everything is treated as a file, including hardware devices, processes, and system information. This abstraction simplifies interactions with the system.
2. **Small, single-purpose tools**: Linux encourages the use of small, specialized programs that can be combined to perform complex tasks. This modular approach allows for greater flexibility and efficiency.
3. **Ability to chain programs together to perform complex tasks**: Linux supports piping and redirection, enabling users to connect the output of one program to the input of another.
4. **Avoid captive user interfaces**: Linux provides a command-line interface (CLI) that allows users to interact with the system using text commands, promoting efficiency and automation.
5. **Configuration files are plain text**: Linux uses plain text files for configuration, making it easy to read, edit, and version control system settings.

### Components
Linux consists of several key components that work together to provide a complete operating system:
1. **Bootloader**: The bootloader is responsible for loading the Linux kernel into memory during system startup. Common bootloaders include GRUB (GRand Unified Bootloader) and LILO (Linux Loader).
2. **OS Kernel**: The kernel is the core component of the operating system, managing hardware resources, system calls, and process scheduling. It acts as an intermediary between applications and hardware.
3. **Daemons**: Daemons are background processes that run continuously to perform specific tasks, such as managing network connections, handling print jobs, or monitoring system performance. They are typically started during system boot and run until the system is shut down.
4. **OS Shell**: The shell is a command-line interface that allows users to interact with the operating system by executing commands, running scripts, and managing files. Common shells include Bash (Bourne Again SHell), Zsh (Z Shell), and Fish (Friendly Interactive SHell).
5. **Graphics Server**: The graphics server manages the display and input devices, allowing users to interact with graphical applications. X11 (X Window System) and Wayland are common graphics servers used in Linux.
6. **Window Manager**: The window manager controls the appearance and behavior of windows in a graphical environment. It manages window placement, resizing, and focus. Examples include GNOME, KDE, and XFCE.
7. **Utilities**: Utilities are command-line tools and applications that provide various functionalities, such as file management, text processing, and system monitoring. Common utilities include `ls`, `cp`, `mv`, `grep`, and `top`.

### Linux Architecture
Linux architecture is typically divided into four layers:
1. **Hardware Layer**: This layer includes the physical components of the computer, such as the CPU, memory, storage devices, and peripherals. The kernel interacts directly with the hardware to manage resources and perform operations.
2. **Kernel Layer**: The kernel is the core of the operating system, responsible for managing hardware resources, system calls, and process scheduling. It provides a bridge between the hardware and user applications.
3. **Shell**: The shell is the command-line interface that allows users to interact with the operating system. It interprets user commands, executes programs, and manages input/output operations.
4. **System Utility**: Makes available to the user all of the OS's functionality.

### Filesystem Hierarchy
Linux uses a hierarchical filesystem structure, where files and directories are organized in a tree-like structure.
The root directory (`/`) is the top-level directory, and all other files and directories are organized beneath it. Key directories in the Linux filesystem hierarchy include:
- `/bin`: Contains essential command-line utilities and binaries required for system operation.
- `/boot`: Contains files necessary for booting the system, including the kernel and bootloader configuration.
- `/dev`: Contains device files that represent hardware devices, such as disks, terminals, and network interfaces.
- `/etc`: Contains system configuration files, including network settings, user accounts, and service configurations.
- `/lib`: Contains shared libraries and kernel modules required by applications and the kernel.
- `/media`: Contains mount points for removable media, such as USB drives and CD-ROMs.
- `/mnt`: A temporary mount point for mounting filesystems.
- `/opt`: Contains optional software packages and applications that are not part of the core system.
- `/home`: Contains user home directories, where personal files and configurations are stored.
- `/var`: Contains variable data files, such as logs, databases, and temporary files.
- `/usr`: Contains user-related programs and data, including applications, libraries, and documentation.
- `/tmp`: Contains temporary files that are created by applications and can be deleted upon system reboot.
- `/sys`: Contains virtual files that provide information about the system and hardware, such as device status and kernel parameters.
- `/proc`: Contains virtual files that provide information about running processes and system resources, such as CPU usage and memory statistics.
- `/root`: The home directory for the root user, which has administrative privileges and can access all files on the system.
- `/run`: Contains runtime data and files that are used by the system during operation, such as PID files and lock files.


## 1.2. Linux Distributions

Linux distributions (distros) are variations of the Linux operating system that package the Linux kernel with additional software, libraries, and tools to create a complete operating system. Each distribution is tailored for specific use cases, user preferences, and target audiences. Here are some of the most popular Linux distributions:
1. **Ubuntu**: A user-friendly distribution based on Debian, Ubuntu is known for its ease of use and extensive community support. It is suitable for both desktop and server environments and comes with a wide range of pre-installed software.
2. **Debian**: A stable and versatile distribution that serves as the foundation for many other distros, including Ubuntu. Debian is known for its commitment to free software and its extensive package repository.
3. **Fedora**: A cutting-edge distribution sponsored by Red Hat, Fedora focuses on innovation and includes the latest software and technologies. It is often used by developers and enthusiasts who want to stay on the bleeding edge of Linux.
4. **CentOS**: A community-driven distribution based on Red Hat Enterprise Linux (RHEL), CentOS is known for its stability and long-term support. It is commonly used in server environments and is a popular choice for enterprise applications.
5. **Red Hat Enterprise Linux (RHEL)**: A commercial distribution that provides enterprise-level support and services. RHEL is widely used in corporate environments and is known for its stability, security, and extensive documentation.

For cybersecurity professionals, the following distributions are particularly relevant:
1. **Kali Linux**: A Debian-based distribution specifically designed for penetration testing and security auditing. Kali comes pre-installed with a wide range of security tools and is widely used by ethical hackers and security analysts.
2. **Parrot Security OS**: Another Debian-based distribution focused on security and privacy. Parrot includes a variety of security tools, development environments, and privacy-focused applications, making it suitable for both security professionals and developers.
3. **BackBox**: An Ubuntu-based distribution designed for security assessment and penetration testing. BackBox provides a user-friendly interface and a comprehensive set of security tools, making it suitable for both beginners and experienced security professionals.
4. **BlackArch**: An Arch Linux-based distribution that focuses on security research and penetration testing. BlackArch includes a vast collection of security tools and is suitable for advanced users who prefer the Arch Linux ecosystem.
5. **Tails**: A privacy-focused distribution that runs from a USB stick or DVD, Tails is designed to leave no trace on the host system. It routes internet traffic through the Tor network, providing anonymity and security for users who need to protect their identity.
6. **Pentoo**: A Gentoo-based distribution that focuses on penetration testing and security research. Pentoo provides a customizable environment with a wide range of security tools, making it suitable for advanced users who prefer the Gentoo ecosystem.

### Debian
Debian is a versatile and widely used Linux distribution known for its stability, security, and extensive package repository. It uses an Advanced Package Tool (`apt`) for package management, which simplifies the installation, removal, and updating of software packages. Debian is the foundation for many other distributions, including Ubuntu and Kali Linux.


## 1.3. Introduction to Shell
The shell is a command-line interface that allows users to interact with the operating system by executing commands, running scripts, and managing files. It interprets user input and provides a way to control the system through text-based commands. It is crucial to learn how to use the shell effectively, especially for server administration, automation, and security analysis.

The most commonly used shell in Linux is the Bourne Again SHell (Bash), which provides a powerful and flexible environment for executing commands and scripts. Other popular shells include Zsh (Z Shell) and Fish (Friendly Interactive SHell).

---

# 2. The Shell
## 2.1. Prompt Description
The bash prompt, by default, displays information about the current user, hostname, and working directory. The prompt can be customized to include additional information, such as the current time or the exit status of the last command. It typically looks like this:
```
user@hostname:~/current_directory$
```
When logging in, by default we are set to the home directory of the user, marked by a tilde (`~`). The prompt can be customized by modifying the `PS1` environment variable, which defines the appearance of the primary prompt.

```
user@hostname[~]$
```

If the user is the root user, the prompt changes to a `#` symbol instead of `$`, indicating that the user has administrative privileges:
```
root@hostname[~]#
```

By customizing the `PS1` variable, users can change the appearance of the prompt to include additional information, such as the current time, exit status, or custom text. Also IP address and the result of the last command. This is useful during penetration testing, allowing you to keep track of your actions effectively. Using tools like `script` or reviewing the `.bash_history` file can help you keep track of your commands and their results.
The prompt can be customized in the shell configuration file (e.g., `~/.bashrc` for Bash) with the following syntax:

| Special Character                   | Description                                   |
| ----------------------------------- | --------------------------------------------- |
| `\u`                                | Username of the current user                  |
| `\h`                                | Hostname up to the first dot                  |
| `\w`                                | Current working directory, with the full path |
| `\d`                                | Current date in "Weekday Month Date" format   |
| `\D{% raw %}{%Y-%m-%d}{% endraw %}` | Current date in "YYYY-MM-DD" format           |
| `\H`                                | Full hostname                                 |
| `\j`                                | Number of jobs currently managed by the shell |
| `\n`                                | Newline character                             |
| `\r`                                | Carriage return character                     |
| `\s`                                | Name of the shell                             |
| `\t`                                | Current time in 24hr "HH:MM:SS" format        |
| `\T`                                | Current time in 12hr "HH:MM:SS" format        |
| `\@`                                | Current time                                  |

You can also customize the color and font, among other things. You can use the following site to generate your own prompt: [Bash Prompt Generator](https://bash-prompt-generator.org/)

## 2.2. Getting Help
You can use the `man` command to access the manual pages for commands and utilities in Linux. The `man` command provides detailed documentation on how to use a command, its options, and examples. For example, to view the manual page for the `ls` command, you can run `man ls`. The manual pages are organized into sections, and you can specify a section number to view a specific section of the manual. For example, `man 1 ls` will show the user commands section, while `man 5 ls` will show the file formats section.
You can navigate through the manual pages using the arrow keys, Page Up/Down, and search for specific terms using the `/` key followed by the search term. To exit the manual page, press `q`.
You can also use the `--help` option with most commands to get a brief overview of the command's usage and options. For example, `ls --help` will display a summary of the `ls` command and its available options. Some tools use `-h` instead of `--help`, so you can try both options if one doesn't work.
Another useful command is `whatis`, which provides a brief description of a command. For example, `whatis ls` will display a short description of the `ls` command.
You can also use the `apropos` command to search for commands related to a specific keyword. For example, `apropos file` will list all commands related to files, along with their descriptions.

## 2.3. System Information
Linux provides several commands to gather system information, which is essential for troubleshooting, monitoring, and security analysis. Here are some commonly used commands to retrieve system information:

| Command              | Description                                                                                                                                                                             |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `whoami`             | Displays the current user's username.                                                                                                                                                   |
| `id`                 | Displays the user ID (UID) and group ID (GID) of the current user.                                                                                                                      |
| `hostname`           | Displays the hostname of the system.                                                                                                                                                    |
| `uname`              | Displays system information, such as the kernel name, version, and architecture. Use `uname -a` for detailed information.                                                               |
| `pwd`                | Displays the current working directory.                                                                                                                                                 |
| `ifconfig` or `ip a` | Displays network interface configuration, including IP addresses and network interfaces. Use `ifconfig` for older systems and `ip a` for newer systems.                                 |
| `ip addr`            | Displays detailed information about network interfaces, including IP addresses and MAC addresses.                                                                                       |
| `netstat`            | Displays network connections, routing tables, and interface statistics. Use `netstat -tuln` to view listening ports and established connections.                                        |
| `ss`                 | Displays socket statistics, similar to `netstat`, but provides more detailed information about network connections. Use `ss -tuln` to view listening ports and established connections. |
| `ps`                 | Displays information about running processes. Use `ps aux` to view all processes with detailed information, including user, CPU usage, memory usage, and command line.                  |
| `top` or `htop`      | Like `ps`, provides a real-time view of system processes and resource usage similar to the Task Manager in Windows. You can use `htop` for an enhanced version.                         |
| `who`                | Displays information about users currently logged into the system, including their login time and idle time.                                                                            |
| `env`                | Displays the current environment variables and their values. Environment variables store system-wide settings and user-specific configurations.                                         |
| `lsblk`              | Lists block devices, such as hard drives and partitions, along with their sizes and mount points. This is useful for understanding the storage configuration of the system.             |
| `lsusb`              | Lists USB devices connected to the system, providing information about their vendor, product ID, and device class. This is useful for identifying connected peripherals.                |
| `lsof`               | Lists open files and the processes that have them open. This is useful for identifying which processes are using specific files or network sockets.                                     |
| `lscpu`              | Displays detailed information about the CPU architecture, including the number of cores, threads, and CPU model. This is useful for understanding the system's processing capabilities. |

## 2.4. Logging in via SSH
SSH (Secure Shell) is a protocol used to securely connect to remote systems over a network. It provides a secure channel for remote administration and file transfer, allowing users to log in to remote machines and execute commands securely. We can connect to a remote system using the `ssh` command followed by the username and hostname or IP address of the remote machine. For example:
```bash
spaniel@htb[/htb]$ ssh user@remote_host
```

If the remote host uses a non-standard port (not port 22), you can specify the port using the `-p` option:
```bash
spaniel@htb[/htb]$ ssh -p 2222 user@remote_host
```

When connecting to a remote host for the first time, you may see a message asking if you want to trust the host's key. Type `yes` to accept the key and continue with the connection. After that, you will be prompted to enter the user's password. Once authenticated, you will have access to the remote system's shell, and you can execute commands as if you were logged in locally.

We can use `uname -a` to check the system information of the remote host, and `whoami` to verify the current user. To exit the SSH session, simply type `exit` or press `Ctrl + D`. For example, if we log in to a remote host and use `uname -a`, we can figure out the kernel version, architecture, and other details about the remote system, which can be useful when looking for vulnerabilities or compatibility issues.

### 2.4.1. Questions
First, we log in to the remote host using SSH.
```bash
spaniel@htb[/htb]$ ssh htb-student@10.129.18.248
htb-student@10.129.18.248's password: HTB_@cademy_stdnt!
```

#### 1. Find out the machine hardware name
To find out the machine hardware name, I used the `uname -m` command. This command displays the machine hardware name, which indicates the architecture of the system (e.g., x86_64 for 64-bit systems).
```bash
htb-student@nixfund:/$ uname -m
x86_64
```

#### 2. What is the path to the user's home directory?
The path to the user's home directory can be found using the `echo $HOME` command. Or by using the `pwd` command while in the home directory. The home directory is typically located at `/home/username`, where `username` is the name of the user.
```bash
htb-student@nixfund:/$ echo $HOME
/home/htb-student
```

#### 3. What is the path to the user's email?
The path to the user's email can be found by using `echo $MAIL`. The email is typically stored in a file named after the username in the `/var/mail/` directory.
```bash
htb-student@nixfund:/$ echo $MAIL
/var/mail/htb-student
```

#### 4. Which shell is specified for the user?
The shell specified for the user can be found by using the `echo $SHELL` command.
```bash
htb-student@nixfund:/$ echo $SHELL
/bin/bash
```

#### 5. Which kernel release is installed? (Format: 1.22.3)
To find out the kernel release installed on the system, I used the `uname -r` command. This command displays the kernel version currently running on the system.
```bash
htb-student@nixfund:/$ uname -r
4.15.0-123-generic
```

#### 6. What is the name of the network interface with the MTU set to 1500?
To find the name of the network interface with the MTU set to 1500, I used the `ifconfig` command. This command displays the network interfaces and their configurations, including the MTU (Maximum Transmission Unit) size.
```bash
htb-student@nixfund:/$ ifconfig
ens192: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        [...]
```

---

# 3. Workflow
## 3.1. Navigation
`ls` is used to list files and directories in the current directory. Passing options like `-l` (long format) or `-a` (show hidden files) can provide more detailed information. For example, `ls -la` will show all files, including hidden ones, with detailed information such as permissions, ownership, size, and modification date.
`cd` is used to change the current directory. You can use `cd ..` to go up one level in the directory hierarchy, or `cd /path/to/directory` to navigate to a specific directory. With `cd -`, you can quickly switch back to the previous directory you were in.
`pwd` is used to print the current working directory, showing the full path of the directory you are currently in.

You can search through the command history using `Ctrl + R`, which allows you to type a part of the command and find previous commands that match. This is useful for quickly recalling commands you've used before without having to retype them. You can quickly clear the terminal screen using the `clear` command or by pressing `Ctrl + L`. 
### 3.1.1. Questions
#### 1. What is the name of the hidden "history" file in the htb-user's home directory?
I used the `ls -a` or `ls -la` command to list all files, including hidden ones, in the user's home directory. The hidden files in Linux start with a dot (`.`).
```bash
htb-student@nixfund:~$ ls -a
.  ..  .bash_history  .bash_logout  .bashrc  .cache  .gnupg  .profile
```

#### 2. What is the index number of the "sudoers" file in the "/etc" directory? 
To find the index number (inode number) of the "sudoers" file in the `/etc` directory, I used the `ls -i` command.
```bash
htb-student@nixfund:~$ ls -i /etc
    1 .  2 ..  3 adduser.conf  4 alternatives  5 apache2  6 apparmor.d
    [...]
    147627 sudoers
```

## 3.2. Working with Files and Directories
Linux provides a variety of commands for working with files and directories directly from the command line.
### 3.2.1. Create, Move and Copy
If we want to create a new file, we can use the `touch` command followed by the filename. For example, `touch newfile.txt` creates an empty file named `newfile.txt`. To create a new directory, we can use the `mkdir` command followed by the directory name, such as `mkdir newdir`. We can also create nested directories using the `-p` option, like `mkdir -p parent/child/grandchild`, which creates the entire directory structure in one command. We can see the structure of the current directory using the `tree` command.
To move or rename a file or directory, we can use the `mv` command. For example, `mv oldfile.txt newfile.txt` renames `oldfile.txt` to `newfile.txt`. To move a file to a different directory, we can specify the target directory, such as `mv file.txt /path/to/directory/`.
To copy a file or directory, we can use the `cp` command. For example, `cp file.txt /path/to/directory/` copies `file.txt` to the specified directory. To copy a directory and its contents, we can use the `-r` (recursive) option, such as `cp -r sourcedir /path/to/destination/`.
To delete a file, we can use the `rm` command followed by the filename, such as `rm file.txt`. To delete a directory and its contents, we can use the `-r` option with `rm`, like `rm -r directoryname`. Be cautious when using `rm`, as it permanently deletes files without confirmation. To avoid accidental deletions, you can use the `-i` option with `rm`, which prompts for confirmation before deleting each file. For example, `rm -i file.txt` will ask for confirmation before deleting `file.txt`. To delete a file or directory without confirmation, you can use the `-f` (force) option with `rm`, like `rm -f file.txt`. This will delete the file without prompting for confirmation, so use it with caution.

### 3.2.2. Questions
#### 1. What is the name of the last modified file in the "/var/backups" directory?
To find the last modified file in the `/var/backups` directory, I used the `ls -lt` command, which lists files sorted by modification time, with the most recently modified file at the top.
```bash
htb-student@nixfund:~$ ls -lt /var/backups
total 2160
-rw-r--r-- 1 root root    41872 Nov 12  2020 apt.extended_states.0
-rw-r--r-- 1 root root     4437 Nov 12  2020 apt.extended_states.1.gz
```

#### 2. What is the inode number of the "shadow.bak" file in the "/var/backups" directory?
Just like before, I used the `ls -i` command to find the inode number of the "shadow.bak" file.
```bash
htb-student@nixfund:~$ ls -i /var/backups
262248 alternatives.tar.0        262233 apt.extended_states.4.gz  262235 dpkg.diversions.6.gz    262236 dpkg.statoverride.6.gz  262230 dpkg.status.6.gz
262559 alternatives.tar.1.gz     262178 dpkg.diversions.0         262231 dpkg.statoverride.0     263999 dpkg.status.0           265226 group.bak
262261 alternatives.tar.2.gz     262203 dpkg.diversions.1.gz      262205 dpkg.statoverride.1.gz  262179 dpkg.status.1.gz        265817 gshadow.bak
266334 apt.extended_states.0     262264 dpkg.diversions.2.gz      262310 dpkg.statoverride.2.gz  262234 dpkg.status.2.gz        264599 passwd.bak
266335 apt.extended_states.1.gz  262257 dpkg.diversions.3.gz      262311 dpkg.statoverride.3.gz  262241 dpkg.status.3.gz        265293 shadow.bak
266430 apt.extended_states.2.gz  262246 dpkg.diversions.4.gz      262247 dpkg.statoverride.4.gz  262243 dpkg.status.4.gz
264827 apt.extended_states.3.gz  262249 dpkg.diversions.5.gz      262250 dpkg.statoverride.5.gz  262220 dpkg.status.5.gz
```

## 3.3. Editing Files
Some of the most common ways to edit files in Linux are text editors like `nano`, `vi`, and `vim`. Each editor has its own set of commands and features, but they all allow you to create, modify, and save text files. We will start with nano which is less commonly used but easier to grasp.
### 3.3.1. Nano
`nano` is a simple and user-friendly text editor that is often pre-installed on Linux systems and is suitable for beginners. It provides a straightforward interface for editing text files, with on-screen prompts for common commands. To create or open a file in `nano`, you can use the command:
```bash
nano filename.txt
```

Below we see two lines with short descriptions. The caret (^) stands for our [CTRL] key. For example, if we press [CTRL + W], a "Search:" line appears at the bottom of the editor, where we can enter the word or words we are looking for. If we now search for the word "we" and press [ENTER], the cursor will move to the first word that matches.

We can save the file by pressing [CTRL + O] (write out). This will prompt us to confirm the filename. Press [ENTER] to save the file with the same name. To exit `nano`, we can press [CTRL + X]. If we have unsaved changes, `nano` will prompt us to save them before exiting.

### 3.3.2. Back on the Shell

To view the contents of a file we can use the `cat` command, which displays the contents of a file in the terminal. For example, `cat filename.txt` will show the contents of `filename.txt`. If the file is too long to fit on one screen, we can use `less` or `more` to view it page by page. For example, `less filename.txt` allows us to scroll through the file using the arrow keys and exit by pressing `q`.

On Linux systems there are several files which are important to penetration testers, one of which is the `/etc/passwd` file. This file contains user account information, including usernames, user IDs (UIDs), group IDs (GIDs), home directories, and default shells. It is a plain text file that can be viewed using `cat`. Historically, this file was used to store user hashed passwords, but now it only contains user account information, while the actual hashed passwords are stored in the `/etc/shadow` file, which is more secure and accessible only by the root user.

### 3.3.3. Vim
Vim is an improved version of the Vi editor, which is a powerful and widely used text editor in the Linux world. Vim has a steeper learning curve than `nano`, but it offers advanced features and capabilities for efficient text editing. You can start it with `vim`.

Vim has six modes that allow you to perform different tasks:
1. **Normal Mode**: The default mode for navigating and manipulating text. All inputs are considered commands. You can enter Normal Mode by pressing `Esc`.
2. **Insert Mode**: Used for inserting and editing text. You can enter Insert Mode by pressing `i` (insert before the cursor) or `a` (append after the cursor). To return to Normal Mode, press `Esc`.
3. **Visual Mode**: Used for selecting text. You can enter Visual Mode by pressing `v` (character-wise selection) or `V` (line-wise selection). To return to Normal Mode, press `Esc`.
4. **Command-Line Mode**: Used for executing commands, such as saving or quitting. You can enter Command-Line Mode by pressing `:` in Normal Mode. For example, `:w` saves the file, and `:q` quits Vim.
5. **Replace Mode**: Used for replacing existing text. You can enter Replace Mode by pressing `R` in Normal Mode. To return to Normal Mode, press `Esc`.
6. **Ex Mode**: A mode for executing Ex commands, which are more advanced commands for text manipulation. You can enter Ex Mode by pressing `Q` in Normal Mode. Allows to execute multiple commands in sequence.

Vim includes a tutorial that can be accessed by running `vimtutor` in the terminal. This tutorial provides an interactive way to learn the basics of Vim and its commands.

## 3.4. Find Files and Directories
It is essential to know how to find files and directories in Linux. One of the most common tools is `which`, this tool returns the path to a file that would be executed, which lets us check whether programs are available in the system. For example, `which python` will return the path to the Python interpreter if it is installed. If the command is not found, it will return nothing.
Another useful command is `find`, which allows you to search for files and directories based on various criteria. The basic syntax is:
```bash
find <path> <options> <expression>
```
The options find provides include:
- `-name`: Search for files by name (case-sensitive).
- `-iname`: Search for files by name (case-insensitive).
- `-type`: Specify the type of file to search for (e.g., `f` for regular files, `d` for directories).
- `-size`: Search for files based on their size (e.g., `+100M` for files larger than 100 megabytes).
- `-mtime`: Search for files based on their modification time (e.g., `-mtime +7` for files modified more than 7 days ago).
- `-user`: Search for files owned by a specific user.
- `-newermt`: Search for files newer than a specific time.
- `-exec`: Execute a command on the found files (e.g., `-exec rm {} \;` to delete the found files).
For example, to find all files named `config.txt` in the `/etc` directory, you can use:
```bash
find /etc -name config.txt
```
To find all .txt files in the current directory and its subdirectories, you can use:
```bash
find . -type f -name "*.txt"
```

We can use `2>/dev/null` to suppress error messages when searching in directories where we do not have permission to read. For example:
```bash
find / -name "config.txt" 2>/dev/null
```


Finally, we have `locate`, or `mlocate`, which is a command that uses a pre-built index of files and directories to quickly find files by name. It is faster than `find` but requires the index to be updated regularly using the `updatedb` command. It might not be installed by default on all systems, so you may need to install it using your package manager. You must run `sudo updatedb` to update the index before using `locate`.

### 3.4.1. Questions
#### 1. What is the name of the config file that has been created after 2020-03-03 and is smaller than 28k but larger than 25k?
To find the config file that meets the specified criteria, I used the `find` command with the `-newermt` option to specify the date and the `-size` option to filter by size. The command looks like this:
```bash
htb-student@nixfund:/etc$ find / -type f -name "*.conf" -newermt 2020-03-03 -size +25k -size -28k 2>/dev/null
/usr/share/drirc.d/00-mesa-defaults.conf
```

#### 2. How many files exist on the system that have the ".bak" extension?
There's 4. I used the `locate` command to quickly find files with the `.bak` extension. The command looks like this:
```bash
htb-student@nixfund:/etc$ locate *.bak
/var/backups/group.bak
/var/backups/gshadow.bak
/var/backups/passwd.bak
/var/backups/shadow.bak
```

#### 3. Submit the full path of the "xxd" binary.
It's `/usr/bin/xxd`. I used the `which` command to find the path as it's a binary, however `locate` would also work.
```bash
htb-student@nixfund:/etc$ which xxd
/usr/bin/xxd
```

## 3.5. File Descriptors and Redirections
A file descriptor is a reference, maintained by the kernel, that allows the system to manage Input/Output (I/O) operations for files, sockets, and other resources. Each process has its own set of file descriptors, which are represented by non-negative integers. You can think of it as a ticket number when you check in your coat at a coatroom. The ticket (file descriptor) represents your connection to your coat (the file) and it is what you use to retrieve it, as the attendant (OS) knows exactly where it is. The three standard file descriptors are:
- **Standard Input (stdin)**: File descriptor 0, used for input from the keyboard or other input devices.
- **Standard Output (stdout)**: File descriptor 1, used for output to the terminal
- **Standard Error (stderr)**: File descriptor 2, used for error messages and diagnostics.

### 3.5.1. STDIN, STDOUT and STDERR
Let's see an example with `cat`. If we run cat, we give it input from the keyboard (FD 0) and it outputs the text to the terminal (FD 1) upon confirming with enter. In the case of stderr, it is used when an error occurs, such as trying to read a file that does not exist, or when permission is denied. The error message will be printed to the terminal, but it will be sent to file descriptor 2 (stderr) instead of file descriptor 1 (stdout). This is useful, as we saw before, to separate normal output from error messages, allowing us to handle them differently if needed. When using the find command earlier we redirected the error messages to `/dev/null` to avoid cluttering the output with permission denied errors. This is done by appending `2>/dev/null` to the command, which redirects file descriptor 2 (stderr) to `/dev/null`, effectively discarding any error messages.

### 3.5.2. Redirection
We can redirect the output of a command to a file using the `>` operator. For example, `ls -l > output.txt` will save the output of the `ls -l` command to a file named `output.txt`. If the file already exists, it will be overwritten. To append the output to an existing file instead of overwriting it, we can use the `>>` operator, like this: `ls -l >> output.txt`.

To redirect stdout and stderr to different files, we can use a number before the `>` operator. For example, `command > output.txt 2> error.txt` will redirect stdout to `output.txt` and stderr to `error.txt`. If we want to redirect both stdout and stderr to the same file, we can use `&>` or `>>` for appending. For example, `command &> output.txt` or `command >> output.txt 2>&1`.

To redirect stdin, we can use the `<` operator. For example, `command < input.txt` will read input from `input.txt` instead of the keyboard. This is useful when we want to provide input to a command from a file instead of typing it manually. For example we can use `sort < unsorted.txt` to sort the contents of `unsorted.txt` and display the sorted output in the terminal.

We can also use `<<` to add the standard input through a stream, we can use EOF (End Of File) to indicate the end of the input. For example:
```bash
cat << EOF > stream.txt
> This is
> a test
> EOF

cat stream.txt
This is
a test
```

### 3.5.3. Pipes
Another, quicker way to redirect output is to use pipes (`|`). Pipes allow us to take the output of one command and use it as the input for another command. For example, `ls -l | grep "txt"` will list all files in long format and then filter the output to show only files that contain "txt" in their names. This is useful for chaining commands together to perform complex operations on data.
Pipes can be used to connect multiple commands together, allowing us to create powerful command-line workflows by combining the functionality of different commands.
Another useful tool is `wc -l` which allows us to count the number of lines in the output of a command. For example, `ls -l | wc -l` will count the number of files and directories in the current directory.

#### 1. How many files exist on the system that have the ".log" file extension?
I used the `find` command to search for files with the `.log` extension and used a pipe with the `wc -l` command to count the number of files found. The command looks like this:
```bash
htb-student@nixfund:/etc$ find / -name *.log 2>/dev/null | wc -l
32
```
#### 2. How many total packages are installed on the target system?
To find the total number of installed packages on the system, I used the `dpkg` command with the `-l` option to list all installed packages and then piped the output to `wc -l` to count the number of lines. This wasn't enough, as the command also lists the header and footer, so I used `grep -c` to count only the lines that contain package information. The command looks like this:
```bash
htb-student@nixfund:/etc$ dpkg -l | wc -l
748
htb-student@nixfund:/etc$ dpkg -l | grep -c '^ii'
737
```
With the correct answer being 737, as the first one includes the header and footer lines, and also packages marked as `rc` which means they aren't really installed, only the configuration files are present.

## 3.6. Filter Contents
In this section we'll see how to read files directly from the command line. There are two powerful tools for this: `more` and `less`. Both commands allow you to view the contents of a file one page at a time, making it easier to read large files without overwhelming the terminal.
### 3.6.1. More
`more` is a simple pager program that allows you to view the contents of a file one screen at a time. You can navigate through the file using the spacebar to go to the next page, or the Enter key to go down one line. To exit `more`, you can press `q`. It is useful for quickly viewing the contents of a file without opening it in an editor. For example, you can use `more filename.txt` to view the contents of `filename.txt`. You can also use `more` with pipes to view the output of a command. For example, `ls -l | more` will display the long listing of files one page at a time.
### 3.6.2. Less
`less` is a more advanced pager program that provides additional features compared to `more`. It allows you to scroll both forward and backward through the file, search for text, and navigate using various commands. You can use the arrow keys to scroll up and down, or the Page Up and Page Down keys to navigate through the file. To search for text, you can press `/` followed by the search term, and then press Enter. To exit `less`, you can press `q`. For example, you can use `less filename.txt` to view the contents of `filename.txt`. You can also use `less` with pipes to view the output of a command. For example, `dmesg | less` will display the kernel messages one page at a time.
### 3.6.3. Head
`head` is a command that allows you to view the first few lines of a file. By default, it displays the first 10 lines, but you can specify a different number using the `-n` option. For example, `head -n 5 filename.txt` will display the first 5 lines of `filename.txt`. This is useful for quickly checking the contents of a file without opening it in an editor.
### 3.6.4. Tail
`tail` is a command that allows you to view the last few lines of a file. By default, it displays the last 10 lines, but you can specify a different number using the `-n` option. For example, `tail -n 5 filename.txt` will display the last 5 lines of `filename.txt`. This is useful for checking the most recent entries in log files or other files that are frequently updated. Additionally, you can use the `-f` option with `tail` to continuously monitor a file for new lines as they are added. For example, `tail -f logfile.txt` will display new lines added to `logfile.txt` in real-time.
### 3.6.5. Sort
`sort` is a command that allows you to sort the lines of a file or the output of a command in a specified order. By default, it sorts lines in ascending order based on ASCII values. You can use the `-r` option to sort in reverse order, and the `-n` option to sort numerically. For example, `sort -n numbers.txt` will sort the numbers in `numbers.txt` in ascending numerical order. You can also use the `-k` option to specify a specific column to sort by when dealing with structured data. For example, `sort -k 2 file.txt` will sort the lines in `file.txt` based on the second column.
### 3.6.6. Grep
`grep` is a powerful command-line utility used to search for specific patterns or text within files. It stands for "Global Regular Expression Print." You can use `grep` to search for a specific string or pattern in a file or the output of a command. For example, `grep "search_term" filename.txt` will search for the string "search_term" in `filename.txt` and display the matching lines. You can use the `-i` option to perform a case-insensitive search, and the `-r` option to search recursively in directories. For example, `grep -ri "search_term" /path/to/directory` will search for "search_term" in all files within the specified directory and its subdirectories. Using `grep` with the `-v` option will invert the search, displaying lines that do not match the specified pattern. For example, `grep -v "search_term" filename.txt` will display all lines in `filename.txt` that do not contain "search_term."
You can also use `grep` with pipes to filter the output of a command. For example `ps aux | grep "process_name"` will display all processes that match "process_name." This is useful for finding specific processes or filtering command output based on certain criteria.
### 3.6.7. Cut
`cut` is a command-line utility used to extract specific sections or fields from lines of text. It is particularly useful for processing structured data, such as CSV files or tab-separated values. You can specify the delimiter used to separate fields using the `-d` option, and you can specify which fields to extract using the `-f` option. For example, `cut -d ',' -f 1,3 filename.csv` will extract the first and third fields from each line in `filename.csv`, assuming the fields are separated by commas. You can also use `cut` to extract specific character positions from each line using the `-c` option. For example, `cut -c 1-5 filename.txt` will extract the first five characters from each line in `filename.txt`. This is useful for extracting fixed-width fields or specific character ranges from text files.
### 3.6.8. Tr
`tr` is a command-line utility used to translate or delete characters from input text. It is often used to perform character substitutions, such as converting uppercase letters to lowercase or removing specific characters from text. For example, `tr 'A-Z' 'a-z' < input.txt` will convert all uppercase letters in `input.txt` to lowercase. You can also use `tr` to delete specific characters by using the `-d` option. For example, `tr -d 'aeiou' < input.txt` will remove all vowels from the text in `input.txt`. This is useful for cleaning up text or removing unwanted characters from files, or when replacing delimiters such as commas with spaces. For example, `tr ',' ' ' < input.txt` will replace all commas in `input.txt` with spaces.
### 3.6.9. Column
Column can be used with pipes to display the results in tabular form, using the `-t` option to create a table with aligned columns. For example, `ps aux | column -t` will display the output of the `ps aux` command in a neatly formatted table.
### 3.6.10. Awk
`awk` is a powerful text processing tool that allows you to manipulate and analyze structured data. It is particularly useful for processing tabular data, such as CSV files or log files. `awk` operates on a line-by-line basis, allowing you to specify patterns and actions to perform on matching lines. You can use it to display, for example, only the first and last results on each line. For example, `awk '{print $1, $NF}' filename.txt` will print the first and last fields of each line in `filename.txt`.
### 3.6.11. Sed
`sed` (Stream Editor) is a powerful text processing tool that allows you to perform basic text transformations on an input stream (a file or input from a pipeline). It is often used for tasks such as search and replace, insertion, deletion, and more. You can use `sed` to modify text in a file or the output of a command without opening it in an editor. For example, `sed 's/old_text/new_text/g' filename.txt` will replace all occurrences of "old_text" with "new_text" in `filename.txt`. The `g` at the end indicates that the replacement should be done globally on each line.
### 3.6.12. Wc
`wc` (Word Count) is a command-line utility that counts the number of lines, words, and characters in a file or input stream. It is useful for quickly analyzing the size of text files or the output of commands. By default, `wc` displays the line count, word count, and character count. You can use options to display only specific counts:
- `-l`: Count lines only.
- `-w`: Count words only.
- `-c`: Count characters only.
For example, `wc -l filename.txt` will display the number of lines in `filename.txt`. You can also use `wc` with pipes to count the output of a command. For example, `ls -l | wc -l` will count the number of files and directories in the current directory.

### 3.6.13. Questions
#### 1. How many services are listening on the target system on all interfaces? (Not on localhost and IPv4 only)
This one took a while as the answer I got with netstat was way above the real answer. Instead using `ss` as follows, to exclude localhost and count only IPv4 interfaces:
```bash
htb-student@nixfund:~$ ss -l -4 | grep -v "127.0.0" | grep "LISTEN" | wc -l
7
```

#### 2. Determine what user the ProFTPd server is running under. Submit the username as the answer.
To determine the user under which the ProFTPd server is running, I used `htop` to view the running processes and found the ProFTPd process. The user running the ProFTPd server is `proftpd`.
```bash
htb-student@nixfund:~$ htop
```

Using filters in `htop`, I searched for "proftpd" and found the process running under the user `proftpd`. Alternatively, you can use `ps aux | grep proftpd` to find the user running the ProFTPd server:
```bash
htb-student@nixfund:~$ ps aux | grep proftpd
proftpd   1986  0.0  0.1 126444  3692 ?        Ss   15:03   0:00 proftpd: (accepting connections)
htb-stu+  6230  0.0  0.0  14864  1096 pts/0    S+   15:30   0:00 grep --color=auto proftpd
```

#### 3. Use cURL from your Pwnbox (not the target machine) to obtain the source code of the "https://www.inlanefreight.com" website and filter all unique paths (https://www.inlanefreight.com/directory" or "/another/directory") of that domain. Submit the number of these paths as the answer.
To obtain the source code of the "https://www.inlanefreight.com" website and filter all unique paths, I used the following command:
```bash
┌─[spaniel@parrot]─[~]
└──╼ $curl -s https://www.inlanefreight.com | grep -oP '(?<=href=")[^"]*' | wc -l
34
```

## 3.7. Regular Expressions
Regular expressions (regex) are powerful tools for pattern matching and text manipulation. They allow you to search for specific patterns in text, validate input, and perform complex text transformations. Regular expressions consist of a combination of literal characters and special symbols that define the pattern to match.
### 3.7.1. Grouping
Among other things, regex allows us to group patterns together. It is done with the following operators:
- `(a)`: Parentheses are used to group patterns together. For example, `(abc)` matches the exact sequence "abc". You can define further patterns within these.
- `[a-z]`: Square brackets are used to define a character class. For example, `[a-z]` matches any lowercase letter from 'a' to 'z'. You can also use ranges like `[0-9]` for digits or `[A-Z]` for uppercase letters.
- `{n}`: Curly braces are used to specify the exact number of occurrences of a pattern. For example, `a{3}` matches exactly three occurrences of the letter 'a'. You can also use `{n,m}` to specify a range, where `n` is the minimum and `m` is the maximum number of occurrences.
- `?`: The question mark is used to indicate that the preceding character or group is optional
- `*`: The asterisk is used to match zero or more occurrences of the preceding character or group. For example, `a*` matches zero or more occurrences of the letter 'a'.
- `+`: The plus sign is used to match one or more occurrences of the preceding character or group. For example, `a+` matches one or more occurrences of the letter 'a'.
- `|`: The pipe symbol is used to specify alternatives. For example, `a|b` matches either 'a' or 'b'. You can use parentheses to group alternatives together, like `(a|b)c`, which matches either "ac" or "bc".
- `^`: The caret symbol is used to match the start of a line. For example, `^abc` matches "abc" only if it appears at the beginning of a line. If used inside square brackets, it negates the character class, meaning `[^a-z]` matches any character that is not a lowercase letter from 'a' to 'z'.
- `$`: The dollar sign is used to match the end of a line. For example, `abc$` matches "abc" only if it appears at the end of a line.
- `.`: The dot matches any single character except a newline. For example, `a.b` matches "a" followed by any character and then "b", such as "acb", "a1b", or "a b".
- `.*`: The dot followed by an asterisk matches zero or more occurrences of any character. For example, `a.*b` matches "a" followed by any characters (including none) and then "b", such as "ab", "acb", or "a123b".
- `\`: The backslash is used to escape special characters. For example, `\.` matches a literal dot instead of any character. It is also used to escape metacharacters like `\*`, `\+`, `\?`, etc.
- `\d`: Matches any digit (equivalent to `[0-9]`).
- `\D`: Matches any non-digit character (equivalent to `[^0-9]`).

## 3.8 Permission Management
In Linux, permissions are keys used to control access to files and directories. Each file and directory has three types of permissions: read (r), write (w), and execute (x). These permissions can be assigned to three different categories of users:
- **Owner**: The user who owns the file or directory.
- **Group**: A group of users who share the same permissions for the file or directory.
- **Others**: All other users who are not the owner or part of the group.

Every file and directory has an associated permission set that determines who can read, write, or execute it. When you create a new file it becomes yours and is associated to the group you belong to. The default permissions for new files and directories are determined by the system's umask setting, which specifies the permissions that should be removed from the default set.

When a user wants to access a file or directory, it needs to have this 'key' just like opening a locked door. The 'key' is the execute permission, which allows the user to access the file or directory. If a user does not have the necessary permissions, they will receive an error message when trying to access the file or directory. To make it simple, having 'execute' permission is like having permission to walk through a hallway, it lets you see the doors inside even if you can't open them. If you have 'read' permission, you can look inside the rooms, and if you have 'write' permission, you can change the contents of the rooms.

Having execute permission on a directory doesn't mean you can execute files inside it, it just means you can access the directory and see its contents. If you want to execute a file, you need to have execute permission on that file itself. To modify the contents you'll need write permission, meaning you can't rename a file or delete it if you don't have write permission on the directory containing it.

### 3.8.1. Changing Permissions
To change permissions, we can use the `chmod` command, using `u` for user (owner), `g` for group, `o` for others and `a` for all. We can add permissions with `+`, remove them with `-`, or set them explicitly with `=`. For example, if we have the file `shell` with permissions `-rwxr-x--x`:
```bash
htb-student@nixfund:~$ ls -l shell
-rwxr-x--x 1 htb-student htb-student 0 Oct  1 00:00 shell
```
We can add read permission for all users with:
```bash
htb-student@nixfund:~$ chmod a+r shell && ls -l shell
-rwxr-xr-x 1 htb-student htb-student 0 Oct  1 00:00 shell
```
We can also set permissions by using octal notation, where each permission is represented by a number:
- `7` for read, write, and execute (rwx)
- `6` for read and write (rw-)
- `5` for read and execute (r-x)
- `4` for read (r)
- `3` for write and execute (wx)
- `2` for write (w)
- `1` for execute (x)
- `0` for no permission (-)

Think of it as a combination lock where each digit represents a different permission. For example, `chmod 754 shell` sets the permissions to `rwxr-xr-x`, meaning the owner has read, write, and execute permissions, while the group has read and execute permissions and others only have read permission. If we switch it to binary, to easily understand, it would be `chmod` 111 (owner) 101 (group) 100 (others), where each 1 represents a given permission (read, write, execute) for user, group, and others respectively.

### 3.8.2. Changing Ownership
To change the ownership of a file or directory, we can use the `chown` command with the following syntax:
```bash
chown <user>:<group> <file/directory>
```

For example, to change ownership of the file `shell` to root:
```bash
htb-student@nixfund:~$ sudo chown root:root shell && ls -l shell
-rwxr-xr-x 1 root root 0 Oct  1 00:00 shell
```

To change the ownership of a directory and its contents recursively, we can use the `-R` option:
```bash
htb-student@nixfund:~$ sudo chown -R root:root /path/to/directory
```

### 3.8.3. SUID and SGID
In addition to regular permissions, Linux has special permissions called SUID (Set User ID) and SGID (Set Group ID). These permissions allow users to execute files with the permissions of the file owner or group, respectively. They act like temporary access keys that grant elevated privileges for specific tasks. The presence of these permissions is indicated by an `s` in the execute position of the user or group permissions. When a program with SUID permission is executed, it runs with the privileges of the file owner, allowing users to perform actions that they would not normally have permission to do. For example, if a program owned by root has the SUID bit set, any user who runs that program will execute it with root privileges. This allows users to perform tasks that require elevated privileges without giving them full access to the system, but it can also pose security risks if not managed properly. For example, if a program with SUID includes a function to launch a shell within it, any user that runs that program will have a shell with root privileges, which could lead to privilege escalation.

### 3.8.4. Sticky Bit
The sticky bit is a special permission that can be set on directories to restrict file deletion. When the sticky bit is set on a directory, only the owner of a file within that directory can delete or rename it, even if other users have write permissions on the directory. This is useful for shared directories where multiple users have write access, such as `/tmp`, to prevent users from deleting each other's files. The sticky bit is indicated by a `t` in the execute position of the others' permissions. For example, if a directory has permissions `drwxrwxrwt`, it means that the sticky bit is set, and only the owner of a file can delete or rename it. It's essentially like a lock on the lockers of a shared room. If the `t` is capitalized, like `drwxrwxrwT`, it means that the sticky bit is set, but the execute permission for others is not set.

---

# 4. System Management
## 4.1. User Management
In Linux, user management is an essential aspect of system administration. It involves creating, modifying, and deleting user accounts, as well as managing user groups and permissions. User accounts are used to control access to the system and its resources, ensuring that users have the appropriate permissions to perform their tasks.
### 4.1.1. Execution as user
To perform tasks that require elevated privileges, users can use the `sudo` command. This command allows a user to execute commands with the privileges of another user, typically the root user. The user must be granted permission to use `sudo` in the `/etc/sudoers` file. For example, to run a command as root, you can use:
```bash
sudo cat /etc/shadow
```
### 4.1.2. Execution as root
The root user is the superuser in Linux, with full administrative privileges. It won't require a password to run commands as root, but it is generally recommended to use `sudo` for executing commands with elevated privileges to maintain a record of actions taken by users. To switch to the root user from your user, you can use the `sudo su` command:
```bash
sudo su
```

### 4.1.3. User Management Commands
To manage users and groups in Linux, there are several commands available:
- `useradd`: Used to create a new user account. For example, `sudo useradd -m newuser` creates a new user named `newuser` with a home directory.
- `usermod`: Used to modify an existing user account. For example, `sudo usermod -aG sudo newuser` adds `newuser` to the `sudo` group, granting them sudo privileges.
- `userdel`: Used to delete a user account. For example, `sudo userdel newuser` deletes the user `newuser`. To remove the user's home directory as well, you can use `sudo userdel -r newuser`.
- `passwd`: Used to change a user's password. For example, `sudo passwd newuser` allows you to set a new password for `newuser`.
- `groupadd`: Used to create a new group. For example, `sudo groupadd newgroup` creates a new group named `newgroup`.
- `groupmod`: Used to modify an existing group. For example, `sudo groupmod -n newgroupname oldgroupname` renames the group `oldgroupname` to `newgroupname`.
- `groupdel`: Used to delete a group. For example, `sudo groupdel newgroup` deletes the group `newgroup`.

### 4.1.4. Questions
#### 1. Which option needs to be set to create a home directory for a new user using "useradd" command?
`-m`: `sudo useradd -m newuser`

#### 2. Which option needs to be set to lock a user account using the "usermod" command? (long version of the option)
`--lock`: `sudo usermod --lock username`

#### 3. Which option needs to be set to execute a command as a different user using the "su" command? (long version of the option) 
`--command`: `sudo su --command="command_to_run" username`

## 4.2. Package Management
Package management is a crucial aspect of Linux system administration, allowing users to install, update, and remove software packages on their systems. Different Linux distributions use different package management systems, but the concepts are generally similar across distributions. The features that package management systems provide include:
- **Package downloading and installation**: The ability to download software packages from repositories or local sources.
- **Dependency resolution**: The ability to automatically resolve and install dependencies required by a package.
- **Standard binary package format**: The use of a standard binary package format for easy installation and management.
- **Common installation and configuration locations**: The use of common directories for installing and configuring software, such as `/usr/bin`, `/etc`, and `/var`.
- **Additional system-related configuration**: The ability to manage system-related configurations, such as services and startup scripts.
- **Quality control**: The ability to ensure that packages meet certain quality standards before being installed on the system.

Package management systems only require that the software to be installed is available as a corresponding package, which is often offered under Linux distributions. The package management system will handle the installation based on the files provided in the package, which typically includes the binary files, configuration files, and metadata about the package. If the package requires additional dependencies, the package management system will alert the user and attempt to resolve them automatically by downloading and installing the required packages.

### 4.2.1. Package Management Programs
- **dpkg**: The low-level package management tool for Debian-based systems, such as Ubuntu. It is used to install, remove, and manage `.deb` packages.
- **apt**: The high-level package management tool for Debian-based systems, built on top of `dpkg`. It provides a user-friendly interface for managing packages, including searching for packages, installing, updating, and removing them. It also handles dependencies automatically.
- **aptitude**: An alternative to `apt` that provides a text-based user interface for managing packages. It offers more advanced features and allows users to navigate through packages and their dependencies interactively.
- **snap**: A package management system that allows users to install and manage software packages in a sandboxed environment. It is designed to work across different Linux distributions and provides a way to install applications without worrying about dependencies or conflicts with the system libraries.
- **gem**: A package management system for Ruby applications. It allows users to install and manage Ruby libraries and applications, making it easy to work with Ruby projects.
- **pip**: A package management system for Python applications. It allows users to install and manage Python libraries and applications, making it easy to work with Python projects.
- **git**: While not a package management system in the traditional sense, Git is a version control system that allows users to manage source code repositories. It is commonly used to clone, pull, and push code changes, making it an essential tool for developers working on collaborative projects.

### 4.2.2. Advanced Packaging Tool (APT)
APT (Advanced Package Tool) is a powerful package management system used in Debian-based Linux distributions, such as Ubuntu. A package is an archive file containing multiple `.deb` files, which are the binary packages used by APT. APT is simply an interface to the underlying `dpkg` tool, which makes it easier to handle dependencies and provides a more user-friendly experience for managing packages. Each Linux distribution uses software repositories, which are often updated. When installing or updating a program, the system queries these repositories for the desired package. Repositories can be labeled as stable, testing, or unstable. Most distros use the stable (main) repository. This can be checked in the `/etc/apt/sources.list` file. In ParrotOS this file is located at `/etc/apt/sources.list.d/parrot.list`.
APT uses a database called the APT cache. We can search here for packages, using `apt-cache search <package_name>`. This will return a list of packages that match the search term. For example, `apt-cache search nmap` will return a list of packages related to Nmap. We can view information about a package using `apt-cache show <package_name>`. For example, `apt-cache show nmap` will display detailed information about the Nmap package, including its description, version, dependencies, and more. With `apt list --installed` we can see all installed packages. Keep in mind to install packages we need sudo.

### 4.2.3. Git
Git is a distributed version control system that allows users to track changes in source code and collaborate on software development projects. It is widely used in the software industry for managing code repositories and facilitating collaboration among developers. Git provides a powerful set of features for branching, merging, and managing code changes, making it an essential tool for modern software development.
We can use git to download useful tools from GitHub. Let's go ahead and download a project we'll use later (https://github.com/samratashok/nishang) with the following command:
```bash
[spaniel@parrot]─[~]
└──╼ $mkdir ~/tools/ && mkdir ~/tools/nishang/ && git clone https://github.com/samratashok/nishang.git ~/tools/nishang/
Cloning into '/home/spaniel/tools/nishang'...
remote: Enumerating objects: 1705, done.
remote: Counting objects: 100% (14/14), done.
remote: Compressing objects: 100% (12/12), done.
remote: Total 1705 (delta 5), reused 8 (delta 2), pack-reused 1691 (from 1)
Receiving objects: 100% (1705/1705), 10.89 MiB | 12.20 MiB/s, done.
Resolving deltas: 100% (1064/1064), done.
```

### 4.2.4. DPKG
With `wget` we can download packages directly from the source, and then install them using `dpkg` or `apt`. Since we already used apt let's see the syntax for dpkg: `sudo dpkg -i <package_name>.deb`.

## 4.3. Service and Process Management
Services, also known as daemons, are background processes that run continuously on a Linux system to provide various functionalities. They can generally be categorized into two types: system services and user services. System services are essential for the operation of the system, such as networking, logging, and scheduling tasks. User services are specific to individual users and can include applications like web servers, databases, and other software that runs in the background.
Daemons are often identified by the letter 'd' at the end of their names, such as `sshd` for the SSH daemon or `systemd` for the system management daemon. They are typically started during the boot process and run until the system is shut down or the service is stopped. The most common operations when dealing with a service or process are:
- Start/Restart
- Stop
- Status
- Enable/Disable
- Find

All processes in Linux are assigned a PID (Process ID), which is a unique identifier for each running process. The PID is used by the system to manage and control processes, and can be viewed under the `/proc` directory. Each process might also have a PPID (Parent Process ID), which indicates the process that spawned it.

A process can be in the following states:
- **Running**: The process is currently executing.
- **Sleeping**: The process is waiting for an event or resource.
- **Stopped**: The process has been stopped, usually by a signal.
- **Zombie**: The process has completed execution but still has an entry in the process table, waiting for its parent to read its exit status.

### 4.3.1. Systemctl
`systemctl` is the command-line tool used to manage system services and processes in modern Linux distributions that use `systemd` as their init system. It provides a unified interface for controlling services, checking their status, and managing system resources. We can start a process with `systemctl start <service_name>`, stop it with `systemctl stop <service_name>`, and check its status with `systemctl status <service_name>`. Using `systemctl enable <service_name>` will ensure that the service starts automatically at boot time, while `systemctl disable <service_name>` will prevent it from starting automatically. To view all active services, we can use `systemctl list-units --type=service`.

An easier way to see running processes is `ps`, we can also use `top` and `htop`.
Using `journalctl` we can view the system logs, which can be useful for troubleshooting issues with services or processes. For example, `journalctl -u <service_name>` will show the logs for a specific service, while `journalctl -xe` will display the most recent logs with detailed information about any errors or warnings.

### 4.3.2. Killing a Process
Processes can be terminated with `kill`, `pkill`, `pgrep` and `killall`. The `kill` command is used to send a signal to a process, typically to terminate it. The most common signal is `SIGTERM`, which gracefully stops the process, but you can also use `SIGKILL` to forcefully terminate it. The syntax is `kill <PID>`, where `<PID>` is the Process ID of the process you want to terminate. For example, `kill 1234` will send the default `SIGTERM` signal to the process with PID 1234.
To forcefully kill a process, you can use `kill -9 <PID>`, which sends the `SIGKILL` signal, immediately terminating the process without allowing it to clean up. For example, `kill -9 1234` will forcefully terminate the process with PID 1234.
The most commonly used signals are:

| Signal | Description                                                                                                       |
| ------ | ----------------------------------------------------------------------------------------------------------------- |
| 1      | `SIGHUP` - Sent when the terminal that controls a process is closed                                               |
| 2      | `SIGINT` - Sent when the user press [Ctrl] + C in the controlling terminal                                        |
| 3      | `SIGQUIT` - Sent when the user press [Ctrl] + D                                                                   |
| 9      | `SIGKILL` - Immediately kill a process with no cleanup operations                                                 |
| 15     | `SIGTERM` - Program termination                                                                                   |
| 19     | `SIGSTOP` - Stop the program. It cannot be handled anymore.                                                       |
| 20     | `SIGTSTP` - Sent when a user presses [Ctrl] + Z to request for a service to suspend. It can be handled afterward. |

### 4.3.4. Background a Process
Sometimes we may need to put a process we've started in the background so that we can continue using the terminal session for other tasks. We can do this quickly with [Ctrl + Z], which will suspend the process and put it in the background. To keep running it in the background we can use the `bg` command, which resumes the process in the background. For example, if we have a process running in the foreground and we want to put it in the background, we can press [Ctrl + Z] to suspend it, and then type `bg` to resume it in the background. The `jobs` command can be used to list all background jobs in the current shell session. We can also use `fg <id>` to bring a background process back to the foreground. Another option to do this from start is to append an `&` at the end of the command, like so:
```bash
[spaniel@parrot]─[~]
└──╼ $ ping -c 10 google.com &
[1] 12345
```
The results will be shown when the process finishes.

### 4.3.5. Execute Multiple Commands
To execute multiple commands in a single line, we can use the `;` operator to separate the commands. For example, `command1; command2; command3` will execute `command1`, then `command2`, and finally `command3`. If we want to execute the next command only if the previous one was successful, we can use the `&&` operator. For example, `command1 && command2` will execute `command2` only if `command1` was successful (returned an exit status of 0). If we want to execute the next command only if the previous one failed, we can use the `||` operator. For example, `command1 || command2` will execute `command2` only if `command1` failed (returned a non-zero exit status). Finally, as we saw earlier, we can use pipes (`|`) to pass the output of one command as input to another command. For example, `command1 | command2` will take the output of `command1` and pass it as input to `command2`. This is useful for chaining commands together to perform complex operations on the output of a command.

### 4.3.6. Questions
#### 1. Use the "systemctl" command to list all units of services and submit the unit name with the description "Load AppArmor profiles managed internally by snapd" as the answer.
```bash
htb-student@nixfund:~$ systemctl | grep "Load AppArmor"
snapd.apparmor.service                                                                           loaded active exited    Load AppArmor profiles managed internally by snapd
```

## 4.4. Task Scheduling
Task scheduling is a feature in Linux that allows users to automate the execution of commands or scripts at specified times or intervals. This is useful for performing routine tasks, such as backups, system maintenance, or running scripts without manual intervention. It's essential for cybersecurity specialists as it can serve both as a security measure but also as a vector of attack if not properly managed. For example, an attacker could schedule a malicious script to run at a specific time, allowing them to maintain persistence on the system.
### 4.4.1. Systemd
With systemd, timers can be used to schedule tasks. 
#### Create a Timer
To create a timer, we need to create a directory where the timer script will be stored:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo mkdir -p /etc/systemd/system/mytimer.timer.d
[spaniel@parrot]─[~]
└──╼ $sudo vim /etc/systemd/system/mytimer.timer

[Unit]
Description=My Timer

[Timer]
OnBootSec=3min
OnUnitActiveSec=1hour

[Install]
WantedBy=timers.target
```

If we want to run our script only once after system boot, we use OnBootSec, however, if we want to run it periodically, we use OnUnitActiveSec. In this case, the timer will run every hour after the system boots. We can also use `OnCalendar` to specify a specific time or date for the timer to run.

#### Create a Service
Next, we need to create a service that will be executed by the timer:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo vim /etc/systemd/system/mytimer.service

[Unit]
Description=My Service

[Service]
ExecStart=/path/to/your/script.sh

[Install]
WantedBy=multi-user.target
```

#### Reload Systemd
After creating the timer and service files, we need to reload systemd to recognize the new files:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo systemctl daemon-reload
```

#### Enable and Start the Timer
Finally, we can enable and start the timer:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo systemctl enable mytimer.timer
[spaniel@parrot]─[~]
└──╼ $sudo systemctl start mytimer.timer
```

### 4.4.2. Cron
Cron is a time-based job scheduler in Unix-like operating systems. It allows users to schedule tasks (known as cron jobs) to run at specific intervals, such as daily, weekly, or monthly. Cron jobs are defined in a configuration file called the crontab file, which contains a list of commands to be executed at specified times. Each user can have their own crontab file, and there is also a system-wide crontab file located at `/etc/crontab`.
#### Crontab Syntax
The crontab file has a specific syntax for defining cron jobs. Each line in the crontab file represents a single cron job and consists of six fields separated by spaces:
```
# Service name
* * * * * /path/to/command
```
Where the fields represent:

| Field   | Description                                                              |
| ------- | ------------------------------------------------------------------------ |
| Minute  | The minute of the hour when the command should run (0-59)                |
| Hour    | The hour of the day when the command should run (0-23)                   |
| Day     | The day of the month when the command should run (1-31)                  |
| Month   | The month when the command should run (1-12)                             |
| Weekday | The day of the week when the command should run (0-6, where 0 is Sunday) |

For example, to run a command every day at 2:30 AM, you would use:
```
# My Cron Job
30 2 * * * /path/to/command
```

### 4.4.3. Questions
#### 1. What is the Type of the service of the "dconf.service"?
To find the type of the service for `dconf.service`, we can find its location using the `find` command and then check its contents with `cat` and `grep`.
```bash
[spaniel@parrot]─[~]
└──╼ $find / -name dconf.service -type f 2>/dev/null
/usr/lib/systemd/user/dconf.service
[spaniel@parrot]─[~]
└──╼ $cat /usr/lib/systemd/user/dconf.service | grep -i type
Type=dbus
```

## 4.5. Network Services
Network services are designed to perform specific tasks, many of which enable remote operations. It's important to have the knowledge to identify and manage these services, establish connections, transfer files, analyze traffic and communicate with other computers over the network.

### 4.5.1. SSH
SSH (Secure Shell) is a network protocol that allows secure remote access to a computer or server over an unsecured network. It provides a secure channel for communication between two computers, allowing users to log in to remote systems, execute commands, and transfer files securely. SSH uses encryption to protect the data transmitted over the network, ensuring that sensitive information remains confidential.
SSH is commonly used for remote administration of servers, secure file transfers, and secure tunneling of network connections.
The most commonly used SSH server is the OpenSSH server, which is widely available on Linux distributions. The SSH server listens for incoming connections on port 22 by default, but this can be changed in the SSH server configuration file located at `/etc/ssh/sshd_config`. In this file we can also set up passwords, keys, host checking, limited attempts, and more.
To install: `sudo apt install openssh-server -y`
Using `systemctl`, we can manage the SSH service as we saw before.

To connect to a remote server using SSH, we can use the `ssh` command followed by the username and hostname or IP address of the remote server:
```bash
[spaniel@parrot]─[~]
└──╼ $ssh user@remote_host
```

For example, when we connect to the target for this section, we use:
```bash
[spaniel@parrot]─[~]
└──╼ $ssh htb-student@<target_ip>
```

### 4.5.2. NFS
NFS (Network File System) is a distributed file system protocol that allows users to access files and directories on remote servers as if they were local. It enables file sharing across a network, allowing multiple clients to access the same files simultaneously. NFS is commonly used in environments where multiple systems need to share files, such as in enterprise networks or clusters. We can use this service just like FTP in case there is no FTP available on the target.
To install: `sudo apt install nfs-kernel-server -y`
We can configure NFS via the `/etc/exports` file, where we specify the directories to be shared and the clients that are allowed to access them. There are some important access rights that can be configured here:

| Access Right     | Description                                                                                                              |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------ |
| `ro`             | Read-only access to the shared directory                                                                                 |
| `rw`             | Read and write access to the shared directory                                                                            |
| `no_root_squash` | Allows the root user on the client to have root access to the shared directory                                           |
| `root_squash`    | Maps the root user on the client to a non-privileged user on the server, preventing root access to the shared directory  |
| `sync`           | Ensures that changes to the shared directory are written to disk immediately                                             |
| `async`          | Allows changes to be cached before being written to disk, improving performance but risking data loss in case of a crash |

#### Create NFS Share
```bash
[spaniel@parrot]─[~]
└──╼ $sudo mkdir nfs_share
[spaniel@parrot]─[~]
└──╼ $echo '/home/spaniel/nfs_share hostname(rw,sync,no_root_squash)' >> /etc/exports
```
What we did here was create a directory called `nfs_share` and then added an entry to the `/etc/exports` file to share that directory with a specific hostname (or IP address) with read and write permissions, synchronous writes, and no root squashing.

#### Mount NFS Share
```bash
[spaniel@parrot]─[~]
└──╼ $sudo mkdir ~/target_nfs
[spaniel@parrot]─[~]
└──╼ $sudo mount <target_ip>:/home/john/docs ~/target_nfs
```
This command mounts the NFS share located at `/home/john/docs` on the target server to the local directory `~/target_nfs`. After mounting, we can access the files in the NFS share as if they were local files.

### 4.5.3. Web Servers
Web servers are software applications that serve web content over the internet or a local network. They handle HTTP requests from clients (usually web browsers) and respond with the requested content, such as HTML pages, images, or other files. Web servers can also run server-side scripts to generate dynamic content based on user input or other factors. These are primary targets for penetration testing, as they often expose vulnerabilities that can be exploited to gain unauthorized access to the server or its data. They can be employed to facilitate file transfers and leveraged to conduct phising attacks by hosting replica sites of legitimate services.
The most commonly used web servers are Apache, Nginx, and Lighttpd. We also have Python Web Server.
To install apache: `sudo apt install apache2 -y`
We can configure apache via the `/etc/apache2/apache2.conf` file, where we can set up virtual hosts, security settings, and other configurations.

With python installed, we can run `python3 -m http.server` to start a simple HTTP server in the current directory. This is useful for quickly sharing files over HTTP without needing to set up a full web server. This server will listen on port 8000 by default, but we can specify a different port by adding it at the end of the command, like so: `python3 -m http.server 8080`. Adding `--directory` will allow us to specify a different directory to serve files from, like so: `python3 -m http.server --directory /path/to/directory`. If we now type `curl http://localhost:8000`, we will see the contents of the current directory served over HTTP.

### 4.5.4. VPNs
VPNs (Virtual Private Networks) are used to create secure connections over the internet, allowing users to access resources on a remote network as if they were physically present on that network. VPNs encrypt the data transmitted between the client and the server, providing privacy and security for sensitive information. They are commonly used to access corporate networks remotely, bypass geographical restrictions, and protect user privacy while browsing the internet. It works by establishing a secure tunnel between the client and the server.
Among the most widely used VPN solutions for Linux servers are OpenVPN, L2TP/IPsec, PPTP, SSTP, SoftEther, and WireGuard. Each of these protocols has its own strengths and weaknesses, and the choice of protocol depends on the specific requirements of the network and the level of security needed. OpenVPN stands out as an open-source option compatible with various operating systems.
To install OpenVPN: `sudo apt install openvpn -y`
To configure OpenVPN we can edit the config file in `/etc/openvpn/server.conf`. This file contains settings such as the port to listen on, the protocol to use (TCP or UDP), the IP address range for clients, and security settings like encryption and authentication methods. We can also set up user authentication using certificates or username/password combinations.
To connect to an OpenVPN server we can use the `.ovpn` file provided by the server administrator with the `openvpn` command as follows:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo openvpn --config /path/to/your.ovpn
```

## 4.6. Working with Web Services
Setting up a web server on Linux can be done in several ways, most popular being Nginx, IIS and Apache. In this section, we will focus on Apache, which is a widely used open-source web server software. Apache's true strength lies in its modularity, for example `mod_ssl` allows us to enable SSL/TLS support, `mod_rewrite` allows us to rewrite URLs, and `mod_proxy` allows us to set up a reverse proxy. Apache also supports the creation of dynamic web pages through server-side scripting languages like PHP, Python, and Perl. This allows developers to create interactive and dynamic web applications that can respond to user input and generate content on the fly.

### 4.6.1. Apache Configuration
To install Apache: `sudo apt install apache2 -y`
To start the Apache service: `sudo systemctl start apache2`
Now we can navigate to `http://localhost` in our web browser to see the default Apache welcome page. The default document root for Apache is usually located at `/var/www/html`, where we can place our HTML files and other web content. By default, Apache listens on port 80 for HTTP requests and port 443 for HTTPS requests.

It's important to also learn how to use tools like `curl` and `wget` to interact with web servers. These tools allow us to send HTTP requests, download files, and test web applications from the command line. 

### 4.6.2. cURL
`curl` is a command-line tool for transferring data using various protocols, including HTTP, HTTPS and FTP. It is widely used for testing and interacting with web services, as it allows users to send requests and receive responses directly from the command line. `curl` supports a wide range of options for customizing requests, such as setting headers, specifying request methods (GET, POST, PUT, DELETE), and handling cookies.

### 4.6.3. Wget
`wget` is another command-line tool for downloading files from the web. It is particularly useful for downloading large files or entire websites, as it can resume interrupted downloads and handle recursive downloads. `wget` supports HTTP, HTTPS, and FTP protocols, and it can be used to download files in the background or with specific options to control the download process.

### 4.6.4. Python 3 (http.server)
Another option often used to quickly set up a web server is Python's built-in HTTP server. This sets up a server with the root being the current directory, allowing us to serve files over HTTP. To start the server, we can run: `python3 -m http.server 8000`. This will start a simple HTTP server on port 8000, and we can access it by navigating to `http://localhost:8000` in our web browser. We can also specify a different directory to serve files from by using the `--directory` option, like so: `python3 -m http.server --directory /path/to/directory`.

### 4.6.5. Questions
#### 1. Find a way to start a simple HTTP server inside Pwnbox or your local VM using "npm". Submit the command that starts the web server on port 8080 (use the short argument to specify the port number).
This one took a while to figure out, but we can use `npx http-server -p 8080` to start a simple HTTP server on port 8080. The `npx` command allows us to run npm packages without installing them globally, and `http-server` is a simple, zero-configuration command-line HTTP server. I didn't get this at first, so I installed the package first and ran it as a command afterwards:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo npm install -g http-server
[spaniel@parrot]─[~]
└──╼ $http-server -p 8080
```

#### 2. Find a way to start a simple HTTP server inside Pwnbox or your local VM using "php". Submit the command that starts the web server on the localhost (127.0.0.1) on port 8080.
Reading the manual page for `php` we can see that we can use the `-S` option to start a built-in web server.
```bash
PHP also contains an built-in web server for application development purpose. By using the -S option where addr:port point to a local address and port
PHP will listen to HTTP requests on that address and port and serve files from the current working directory or the docroot passed by the -t option.
```
Knowing this, we can run the following command to start a simple HTTP server on port 8080:
```bash
┌─[spaniel@parrot]─[~]
└──╼ $php -S 127.0.0.1:8080
[Fri Jul 11 13:18:58 2025] PHP 8.2.28 Development Server (http://127.0.0.1:8080) started
```

## 4.7. Backup and Restore
Linux provides several tools and methods for backing up and restoring data, which are essential for maintaining system integrity and recovering from data loss. We can use Rsynx, Deja Dup and Duplicity, among others.
### 4.7.1. Rsync
`rsync` is a powerful command-line utility for synchronizing files and directories between two locations, either on the same system or across a network. It is commonly used for backups and file transfers due to its efficiency and flexibility. `rsync` can copy files locally or remotely, and it only transfers the differences between the source and destination, making it faster than other methods.
`Duplicity` is a command-line tool that uses `rsync` to create incremental backups. It allows users to back up their data to various storage locations, including local disks, remote servers, and cloud storage. `Duplicity` supports encryption and compression, making it a secure and efficient backup solution. `Deja Dup` is easier to use and provides a graphical interface for managing backups.

To install `rsync`: `sudo apt install rsync -y`
To backup an entire directory using `rsync`, we can use the following command:
```bash
[spaniel@parrot]─[~]
└──╼ $rsync -avz /path/to/source [user@remote_host:]/path/to/destination
```
The `user@remote_host:` part is optional, and only for remote backups. The `-a` option stands for "archive mode," which preserves file permissions, timestamps, and symbolic links. The `-v` option enables verbose output, and the `-z` option compresses the data during transfer to save bandwidth. We can also use `--delete` to remove files in the destination that no longer exist in the source, and `--backup` with `--backup-dir=/path/to/backup/folder` to create incremental backups.
To restore our directory from the backup server, we can use:
```bash
[spaniel@parrot]─[~]
└──╼ $rsync -av [user@remote_host:]/path/to/destination /path/to/source
```

### 4.7.2. Encrypting Rsync
To ensure the security of our file transfer we can combine SSH and other security measures. To tell `rsync` to use SSH for the transfer, we can use the `-e` option followed by the SSH command:
```bash
[spaniel@parrot]─[~]
└──╼ $rsync -avz -e ssh /path/to/source [user@remote_host:]/path/to/destination
```
This will use SSH to encrypt the data during transfer, providing a secure connection between the source and destination. We can also use `--progress` to show the progress of the transfer, and `--bwlimit=RATE` to limit the bandwidth used by `rsync`.

### 4.7.3. Auto-Synchronization
To automate the synchronization process, we can use `cron` to schedule regular backups. We can create a cron job that runs the `rsync` command at specified intervals, such as daily or weekly. We can create a new script `RSYNC_Backup.sh`, but as we are using ssh we also need to configure key-based authentication to avoid entering the password every time the script runs. We can generate an SSH key pair using `ssh-keygen` and copy the public key to the remote server using `ssh-copy-id user@remote_host`. This will allow us to connect to the remote server without entering a password, making it easier to automate the backup process.
```bash
[spaniel@parrot]─[~]
└──╼ $ssh-keygen -t rsa -b 2048
[spaniel@parrot]─[~]
└──╼ $ssh-copy-id user@remote_host
```

Now, to create the script:
```
#!/bin/bash
# RSYNC_Backup.sh

rsync -avz -e ssh /path/to/source user@remote_host:/path/to/destination
```

Now we ensure the script is executable:
```bash
[spaniel@parrot]─[~]
└──╼ $chmod +x RSYNC_Backup.sh
```

Finally, we can create a cron job to run the script at a specific time.
```bash
[spaniel@parrot]─[~]
└──╼ $crontab -e
```

## 4.8. File System Management
Linux supports many different file systems, each with its own features and capabilities. The most commonly used file systems in Linux are:
- **ext2**: The second extended file system, which was the default file system for many Linux distributions for a long time. It supports large files and directories, but does not support journaling.
- **ext3** and **ext4**: The third and fourth extended file systems, which are improvements over ext2. They support journaling, which helps prevent data loss in case of a system crash or power failure. ext4 is the most widely used file system in modern Linux distributions.
- **Btrfs**: A copy-on-write file system that supports advanced features like snapshots, checksums, and dynamic inode allocation. It is designed for high performance and scalability, making it suitable for large storage systems.
- **XFS**: A high-performance file system that is designed for scalability and reliability.
- **NTFS**: A file system used by Windows, which can be accessed from Linux using the `ntfs-3g` driver. It is commonly used for external drives and dual-boot systems.

Linux's file system architecture is based on the Unix model. This structure consists of several components, most critical being `inodes`. Inodes are data structures that store metadata about files and directories, such as their size, permissions, ownership, and timestamps. Each file or directory is represented by an inode, which contains a unique identifier (inode number) that the file system uses to access the file's data blocks on disk. Inodes do not store the file's actual data nor its name, but rather a pointer to the data blocks where the file's content is stored. This allows for efficient access to file metadata and enables features like hard links, where multiple file names can point to the same inode and thus share the same data blocks.
The inode table is a collection of these inodes, acting as a database the kernel uses to track every file and directory on the system. In Linux, files can be stored in one of several key types: regular files, directories, symbolic links, among others. Regular files contain data, directories are special files that contain references to other files, and symbolic links are pointers to other files or directories.

### 4.8.1. Disks and Drives
In Linux, disks and drives are represented as block devices, which are files in the `/dev` directory. Each disk or drive is assigned a device file, such as `/dev/sda`, `/dev/sdb`, etc. The `sda` designation refers to the first SCSI or SATA disk, while `sdb` refers to the second disk, and so on. Partitions on these disks are represented as sub-devices, such as `/dev/sda1`, `/dev/sda2`, etc., where the number indicates the partition number.
We can use `fdisk` to view and manage disk partitions. The `fdisk -l` command lists all available disks and their partitions, showing information such as the device name, size, type, and file system. Other tools like `parted` and `gparted` provide more advanced features for managing disk partitions, including resizing, creating, and deleting partitions.

### 4.8.2. Mounting and Unmounting
Each partition or storage drive must be assigned to a specific directory in the file system hierarchy to be accessible. This process is known as mounting. When a partition is mounted, its contents become available under the specified directory, allowing users to access files and directories stored on that partition. Commonly, the `mount` command is used to mount partitions, but you can automatically mount partitions at boot time by adding entries to the `/etc/fstab` file. To mount a USB drive to a specific directory, we can use the following command:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo mount /dev/sdb1 /mnt/usb
```
Where `/dev/sdb1` is the device file for the USB drive's partition, and `/mnt/usb` is the directory where we want to mount it. After mounting, we can access the files on the USB drive by navigating to `/mnt/usb`.
To unmount a partition, we can use the `umount` command followed by the mount point or device file.

### 4.8.3. Swapping
Swap space is a portion of the hard drive that is used as virtual memory when the physical RAM is full. It allows the system to continue running by temporarily moving inactive pages from RAM to disk, freeing up memory for active processes. This is particularly useful in low-memory situations or when running memory-intensive applications.
Swap space can be created as a dedicated partition or as a swap file. A swap partition is a separate partition on the hard drive that is designated for swap space, while a swap file is a regular file that is used as swap space. The size of the swap space can be adjusted based on the system's memory requirements and workload.

To create swap space, we can use the `mkswap` command to format a partition or file as swap space, and then use the `swapon` command to enable it.

The size of the swap space is not fixed and depends on the intended usage. Modern systems might not even require swap space if they have sufficient RAM. It is sometimes also recommended to encrypt the swap space to prevent sensitive data from being stored in plain text on disk.

Swap space is also used for hibernation, where the contents of RAM are saved to disk before powering off the system. This allows the system to resume from where it left off when powered back on. For hibernation to work, the swap space must be at least as large as the amount of RAM in the system.

### 4.8.4. Questions
#### 1. How many partitions exist in our Pwnbox? (Format: 0)
Using the `fdisk -l` command, I can see there's 3.

## 4.9. Containerization
Containerization is the process of packaging and running applications in isolated e nvironments, referred to as containers. These are lightweight, consistent and portable environments that can run on any system that supports containerization, regardless of the underlying infrastructure. Containers share the host operating system's kernel but run in isolated user spaces, allowing multiple containers to run on the same host without interfering with each other. It's like a pallet that contains everything needed to run an application, including the code, runtime, libraries, and dependencies. This makes it easier to deploy and manage applications across different environments, such as development, testing, and production.
Containers isolate applications from the host system, providing a barrier that reduces the risk of malicious activities affecting the host or other containers. But it's important to note that containers do not offer the same level of isolation as virtual machines, as they share the host's kernel. If not properly configured, they leave risk of privilege escalation or container escapes.

### 4.9.1. Docker
Docker is an open-source platform that automates the deployment, scaling, and management of applications using containerization. It provides a set of tools and services for creating, running, and managing containers, making it easier to develop and deploy applications in a consistent and reproducible manner. Docker uses a client-server architecture, where the Docker client communicates with the Docker daemon to manage containers.
Imagine Docker containers as a sealed lunchbox. You can eat the food (run applications) inside, but once you close the box (stop the container), everything resets. To make a new lunchbox (new container) with updated contents (modified configurations), you create a new recipe (Dockerfile) based on the original. When serving multiple lunchboxes in a restaurant (production), you'd use a kitchen system (Kubernetes/Docker Compose) to manage all the orders smoothly.

We can use this script to install Docker on an Ubuntu host:
```bash
#!/bin/bash

# Preparation
sudo apt update -y
sudo apt install ca-certificates curl gnupg lsb-release -y
sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Install Docker Engine
sudo apt update -y
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

# Add user htb-student to the Docker group
sudo usermod -aG docker htb-student
echo '[!] You need to log out and log back in for the group changes to take effect.'

# Test Docker installation
docker run hello-world
```

We can obtain pre-made images from Docker Hub, which is a public repository of Docker images. We can search for images using the `docker search` command, and pull them using the `docker pull` command. 
To create a Docker image, we need to create a Dockerfile, which is a text file that contains instructions for building the image. The Dockerfile specifies the base image to use, the commands to run, and the files to include in the image. We can build the image using the `docker build` command, specifying the path to the Dockerfile and a tag for the image. A sample Dockerfile creation script might look like this:
```bash
# Use the latest Ubuntu 22.04 LTS as the base image
FROM ubuntu:22.04

# Update the package repository and install the required packages
RUN apt-get update && \
    apt-get install -y \
        apache2 \
        openssh-server \
        && \
    rm -rf /var/lib/apt/lists/*

# Create a new user called "docker-user"
RUN useradd -m docker-user && \
    echo "docker-user:password" | chpasswd

# Give the docker-user user full access to the Apache and SSH services
RUN chown -R docker-user:docker-user /var/www/html && \
    chown -R docker-user:docker-user /var/run/apache2 && \
    chown -R docker-user:docker-user /var/log/apache2 && \
    chown -R docker-user:docker-user /var/lock/apache2 && \
    usermod -aG sudo docker-user && \
    echo "docker-user ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

# Expose the required ports
EXPOSE 22 80

# Start the SSH and Apache services
CMD service ssh start && /usr/sbin/apache2ctl -D FOREGROUND
```

Now we can build the image using the `docker build` command:
```bash
[spaniel@parrot]─[~]
└──╼ $docker build -t my_docker_image .
```

Finally, we can run the Docker container using the `docker run` command:
```bash
[spaniel@parrot]─[~]
└──╼ $docker run -d -p 8080:80 -p 2222:22 --name my_docker_container my_docker_image
```
This command runs the container in detached mode (`-d`), maps port 8080 on the host to port 80 in the container, and port 2222 on the host to port 22 in the container. The `--name` option allows us to give the container a specific name for easier management.

There are several commands we can use to manage Docker containers:

| Command                         | Description                                          |
| ------------------------------- | ---------------------------------------------------- |
| `docker ps`                     | Lists all running containers.                        |
| `docker stop <container_id>`    | Stops a running container.                           |
| `docker start <container_id>`   | Starts a stopped container.                          |
| `docker restart <container_id>` | Restarts a running or stopped container.             |
| `docker rm <container_id>`      | Removes a stopped container.                         |
| `docker rmi <image_id>`         | Removes a Docker image.                              |
| `docker logs <container_id>`    | Displays the logs of a running or stopped container. |

Any changes made to a running container will not persist after the container is stopped or removed. We can create a new Dockerfile to build a new image with the changes using a `FROM` statement at the start, or we can commit the changes to the existing container using the `docker commit` command.

### 4.9.2. Linux Containers (LXC)
Linux Containers (LXC) is a lightweight virtualization technology that allows users to run multiple isolated Linux systems (containers) on a single host. It uses control groups and namespaces, to ensure independency. Where Docker is more focused on the ease of use and portability of applications and their deployment, LXC provides a more traditional virtualization experience, allowing users to run full Linux distributions in containers.

To install LXC: `sudo apt-get install lxc lxc-utils -y`
To create a new LXC container, we can use the `lxc-create` command:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo lxc-create -n my_lxc_container -t ubuntu
```
Commands to manage LXC containers:

| Command                                           | Description                                            |
| ------------------------------------------------- | ------------------------------------------------------ |
| `lxc-ls`                                          | Lists all LXC containers.                              |
| `lxc-start -n <container_name>`                   | Starts an LXC container.                               |
| `lxc-stop -n <container_name>`                    | Stops a running LXC container.                         |
| `lxc-restart -n <container_name>`                 | Restarts a running or stopped LXC container.           |
| `lxc-config -n <container_name> -s storage`       | Manage container storage settings.                     |
| `lxc-config -n <container_name> -s network`       | Manage container network settings.                     |
| `lxc-config -n <container_name> -s security`      | Manage container security settings.                    |
| `lxc-attach -n <container_name>`                  | Attaches to a running LXC container's console.         |
| `lxc-attach -n <container_name> -f /path/to/file` | Connects to a running LXC container and shares a file. |

LXC containers are useful when we need to quickly test a particular version of a database or a web server, for example. We can quickly set up environments that mimic target systems. We can use these to test software without affecting the host system or the target system. 

To secure LXC containers, we can configure control groups (cgroups) to limit resource usage in the `/usr/share/lxc/config/<container_name>.conf` file. We can set limits on CPU, memory, and disk usage to prevent a single container from consuming all resources on the host system. Additionally, we can use AppArmor or SELinux to enforce security policies for LXC containers, restricting their access to system resources and files.

---

# 5. Linux Networking
## 5.1. Network Configuration
It's important to know how to configure and manage network settings on Linux. This allows us to quickly set up testing environments, manipulate network traffic and identify vulnerabilities.
One of the primary tasks is managing network interfaces, this involves assigning IP addresses, configuring network devices, and setting up various protocols such as TCP/IP, DNS, DHCP and FTP.
### 5.1.1. Network Access Control
Network Access Control (NAC) is a security approach that restricts access to network resources based on the identity and security posture of devices attempting to connect. It ensures that only authorized devices can access the network, and it can enforce policies such as requiring up-to-date antivirus software, operating system patches, and compliance with security standards.

There's 3 key NAC models:
- **Discretionary Access Control (DAC)**: This model allows users to control access to their own resources, granting permissions to other users as needed. It is based on the principle of least privilege, where users have the minimum permissions necessary to perform their tasks.
- **Mandatory Access Control (MAC)**: This model enforces strict access controls based on security labels assigned to resources and users. It is commonly used in high-security environments where access to sensitive data must be tightly controlled.
- **Role-Based Access Control (RBAC)**: This model assigns permissions based on user roles within an organization. Users are granted access to resources based on their job functions, making it easier to manage permissions and enforce security policies.

Configuring network access control on Linux typically involves setting up firewall rules (SELinux) and application security (AppArmor), configuring network interfaces, and managing user permissions. Tools like `ping`, `nslookup`, `nmap`, `syslog`, `rsyslog`, `ss`, `lsof`, `tcpdump`, and the ELK stack (Elasticsearch, Logstash, Kibana) can be used to monitor network activity and enforce access control policies.

### 5.1.2. Network Interface Configuration
Network interfaces are the hardware or software components that connect a computer to a network. In Linux, network interfaces can be physical (e.g., Ethernet, Wi-Fi) or virtual (e.g., loopback, VLAN). Each interface is assigned a unique name, such as `eth0`, `wlan0`, or `lo` for the loopback interface.
To view the current network interfaces and their configurations, we can use the `ifconfig` command or the newer, better `ip` command. With these commans we can not only see the current network interfaces, but also configure them.
To activate a network interface, we can use the `ifconfig` command followed by the interface name and the `up` option, or the `ip` command with the `link set` option:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo ifconfig eth0 up
[spaniel@parrot]─[~]
└──╼ $sudo ip link set eth0 up
```
To assign an IP address to a network interface, we can use the `ifconfig` command followed by the interface name, the IP address, and the `netmask` option, or the `ip` command with the `addr add` option:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo ifconfig eth0 192.168.1.2
[spaniel@parrot]─[~]
└──╼ $sudo ifconfig eth0 netmask 255.255.255.0
[spaniel@parrot]─[~]
└──╼ $sudo ip addr add 192.168.1.2/24 dev eth0
```
Where `/24` is the CIDR notation for the subnet mask, equivalent to `255.255.255.0`

To assign the route (gateway) to an interface, we can use the `route` command or the `ip` command with the `route add` option:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo route add default gw 192.168.1.1 eth0
[spaniel@parrot]─[~]
└──╼ $sudo ip route add 192.168.1.2/24 via 192.168.1.1 dev eth0
[spaniel@parrot]─[~]
└──╼ $sudo ip route add default via 192.168.1.1 dev eth0 # Sets up a default gateway
```

To view the current routing table, we can use the `route -n` command or the `ip route show` command.

It is often necessary to configure the DNS settings for a network interface. This can be done by editing the `/etc/resolv.conf` file, where we can specify the DNS servers to use. For example:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo vim /etc/resolv.conf

nameserver 8.8.8.8 # Google's public DNS server
nameserver 8.8.4.4 # Another Google DNS server
```

Now we need to ensure that the changes persist across reboots. This can be done by configuring the network interface settings in the `/etc/network/interfaces` file or using NetworkManager.
```bash
[spaniel@parrot]─[~]
└──╼ $sudo vim /etc/network/interfaces

auto eth0
iface eth0 inet static
  address 192.168.1.2
  netmask 255.255.255.0
  gateway 192.168.1.1
  dns-nameservers 8.8.8.8 8.8.4.4
```

By setting the eth0 network interface to use a static IP address of 192.168.1.2, with a netmask of 255.255.255.0 and a default gateway of 192.168.1.1, we can ensure that our network connection remains stable and reliable. Additionally, by specifying DNS servers of 8.8.8.8 and 8.8.4.4, we can ensure that our computer can easily access the internet and resolve domain names. Once we have made these changes to the configuration file, saving the file and exiting the editor is important. After that, we must restart the networking service to apply the changes.

```bash
[spaniel@parrot]─[~]
└──╼ $sudo systemctl restart networking
```

### 5.1.3. Network Troubleshooting
Network troubleshooting is the process of diagnosing and resolving issues related to network connectivity, performance, and configuration. It involves identifying the root cause of network problems and implementing solutions to restore normal operation. Common network issues include connectivity problems, slow performance, misconfigured devices, and security vulnerabilities.
To troubleshoot network issues, we can use various tools and commands, such as `ping`, `traceroute`, `netstat`, `ifconfig`, `ip`, `ss`, `tcpdump`, `wireshark`, and `nmap`. These tools help us gather information about network devices, monitor traffic, and identify potential problems.
We can use `ping` to check the connectivity to a specific host or IP address. For example:
```bash
[spaniel@parrot]─[~]
└──╼ $ping <target_host>
```
We can use `traceroute` to trace the path packets take to reach a specific host, which helps identify where delays or packet loss occur:
```bash
[spaniel@parrot]─[~]
└──╼ $traceroute <target_host>
```
This will display the route taken by packets to reach the target host, along with the response times for each hop.
We can use `netstat` to display network connections, routing tables, and interface statistics. For example:
```bash
[spaniel@parrot]─[~]
└──╼ $netstat -a

Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State      
tcp        0      0 localhost:5901          0.0.0.0:*               LISTEN     
tcp        0      0 0.0.0.0:sunrpc          0.0.0.0:*               LISTEN     
tcp        0      0 0.0.0.0:http            0.0.0.0:*               LISTEN     
tcp        0      0 0.0.0.0:ssh             0.0.0.0:*               LISTEN
...SNIP...
```

With the `-tulpn` options, we can display TCP and UDP connections, along with the process ID (PID) and program name associated with each connection:

### 5.1.4. Network Hardening
Network hardening is the process of securing a network by implementing various measures to protect against unauthorized access, data breaches, and other security threats. It involves configuring network devices, applying security policies, and monitoring network traffic to ensure the integrity and confidentiality of data. The most common methods are SELinux, AppArmor and TCP wrappers.
#### SELinux
Security-Enhanced Linux (SELinux) is a security module that provides mandatory access control (MAC) for Linux systems. It enforces security policies that restrict the actions of processes and users, preventing unauthorized access to system resources. SELinux uses labels to define the security context of files, processes, and users, allowing fine-grained control over access permissions.
#### AppArmor
AppArmor is another security module with MAC capabilities, similar to SELinux. It allows administrators to define security profiles for applications, specifying what resources they can access and what actions they can perform. AppArmor uses path-based profiles, making it easier to configure and manage compared to SELinux. AppArmor is implemented as a Linux Security Module (LSM) and provides a way to enforce security policies on applications and processes.
#### TCP Wrappers
TCP Wrappers are a host-based access control system for network services. It allows administrators to restrict access to specific services based on the IP address or hostname of the client. TCP Wrappers use configuration files (`/etc/hosts.allow` and `/etc/hosts.deny`) to define access rules, allowing or denying connections to services based on the client's identity. This provides an additional layer of security by controlling which hosts can access specific services on the server.

## 5.2. Remote Desktop Protocols in Linux
Remote Desktop Protocols (RDP) allow users to access and control a computer or server remotely over a network. In Linux, there are several RDP implementations that enable remote desktop access, including VNC, XRDP, and SSH with X11 forwarding.
### 5.2.1. XServer
The XServer is the user-side component of the X Window System network protocol (X11), which provides a graphical user interface (GUI) for Unix-like operating systems. It allows users to run graphical applications on a remote server and display them on their local machine. The XServer handles input from the keyboard and mouse, and it communicates with the X client applications to render the graphical output.
When a desktop is started on a Linux system, the XServer is launched, and it listens for incoming connections from X client applications. The protocol mainly uses TCP/IP as a transport base but can also be used on pure Unix sockets. The ports used are typically in the TCP/6001-6009 range. To use it we need to make sure forwarding is enabled in the SSH configuration file (`/etc/ssh/sshd_config`) by setting `X11Forwarding yes`. This allows us to run graphical applications on a remote server and display them on our local machine.
Now we can start it as follows:
```bash
[spaniel@parrot]─[~]
└──╼ $ssh -X user@remote_host /usr/bin/firefox
```
As mentioned, X11 is not secure by default as communication is unencrypted. This makes it a target for attackers who can intercept and manipulate the data being transmitted, for example with `xwd` to capture the screen output or `xgrabsc`. Other famous vulnerabilities related are the CVE-2017-2624, CVE-2017-2625 and CVE-2017-2626, which allow attackers to execute arbitrary code on the remote system by exploiting vulnerabilities in the X11 protocol. 
To mitigate these risks, we can use SSH tunneling to encrypt the X11 traffic. This can be done by using the `-X` or `-Y` option when connecting to the remote host via SSH, which enables X11 forwarding and encrypts the communication between the client and server.

### 5.2.2. XDMCP
The X Display Manager Control Protocol (XDMCP) is a protocol used to manage remote X11 sessions. It allows users to start and manage X11 sessions on remote servers, providing a way to access graphical applications over a network. XDMCP is typically used in environments where multiple users need to access a shared server or when users want to run graphical applications on a remote machine. XDMCP is not a secure protocol and should not be used in any environment that requires security. It is vulnerable to various attacks, such as Man-in-the-Middle (MitM) attacks, where an attacker can intercept and manipulate the XDMCP traffic to gain unauthorized access to the remote server or execute arbitrary commands.

### 5.2.3. VNC
Virtual Network Computing (VNC) is a remote desktop sharing system based on the RFB (Remote Framebuffer) protocol. It allows users to remotely control a computer's desktop environment over a network. VNC works by transmitting the graphical output of the remote machine to the local machine, allowing users to interact with the remote desktop as if they were physically present. It is generally considered to be secure, as it encrypts the communication between the client and server. Many IT services use VNC to provide remote support and access to users, as it allows them to troubleshoot issues and perform maintenance tasks without needing physical access to the machine.
Traditionally, VNC servers listen on port 5900, and each display number corresponds to a different port (e.g., display 1 listens on port 5901, display 2 on port 5902, etc.).
The most used tools for VNC in Linux are `TigerVNC`, `TightVNC`, `RealVNC`, and `UltraVNC`.
To set up a VNC server, we can install a VNC server package, such as `tigervnc` or `tightvnc`, and configure it to start a VNC session. We'll also need the XFCE4 desktop manager since GNOME is somewhat unstable with VNC. We also need to create a password for the VNC session, which will be required to connect to the VNC server.
```bash
[spaniel@parrot]─[~]
└──╼ $sudo apt install xfce4 xfce4-goodies tigervnc-standalone-server -y
[spaniel@parrot]─[~]
└──╼ $vncpasswd
```
A hidden folder will be created in the home directory called `.vnc`, we need to create two additional files in this folder: `xstartup` and `config`. The `xstartup` file will contain the commands to start the XFCE4 desktop environment when a VNC session is initiated, while the `config` file will contain the configuration settings for the VNC server.
```bash
[spaniel@parrot]─[~]
└──╼ $touch ~/.vnc/xstartup ~.vnc/config
[spaniel@parrot]─[~]
└──╼ $cat <<EOT >> ~/.vnc/xstartup

#!/bin/bash
unset SESSION_MANAGER
unset DBUS_SESSION_BUS_ADDRESS
/usr/bin/startxfce4
[ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
[ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
x-window-manager &
EOT

[spaniel@parrot]─[~]
└──╼ $cat <<EOT >> ~/.vnc/config

geometry=1920x1080
dpi=96
EOT

[spaniel@parrot]─[~]
└──╼ $chmod +x ~/.vnc/xstartup

[spaniel@parrot]─[~]
└──╼ $vncserver
```
We can use `vncserver -list` to see the running VNC sessions and their display numbers. The display number is used to connect to the VNC server, for example, `:1` corresponds to port 5901.

To encrypt the VNC connection, we can use SSH tunneling. This can be done by creating an SSH tunnel from the local machine to the remote VNC server. We can use the following command to create the tunnel:
```bash
[spaniel@parrot]─[~]
└──╼ $ssh -L 5901:127.0.0.1:5901 -N -f -l user remote_host
```

Finally, we can connect to the server through the tunnel using `xtightvncviewer`:
```bash
[spaniel@parrot]─[~]
└──╼ $xtightvncviewer 127.0.0.1:5901
```

---

# 6. Linux Hardening
## 6.1. Linux Security
All computer systems have an inherent risk of intrusion. Linux systems are less prone to viruses that affect Windows systems and generally don't present as large an attack surface as Active Directory domain-joined hosts. Regardless, Linux systems are still vulnerable to various types of attacks, such as unauthorized access, data breaches, and denial-of-service attacks. Therefore, it is essential to implement security measures to protect Linux systems from these threats.
One of the most important things to do is to keep the system up-to-date with the latest security patches and updates.
```bash
[spaniel@parrot]─[~]
└──╼ $sudo apt update && sudo apt dist-upgrade -y
```

If firewall rules are not properly set at the network level, we can use the Linux firewall and/or `iptables` to restrict access to the system. The firewall can be configured to allow or deny incoming and outgoing traffic based on specific rules, such as source and destination IP addresses, ports, and protocols. This helps prevent unauthorized access to the system and protects against network-based attacks.
If SSH is open on the server, configuration should disallow password login and disallow root user login from SSH. Also avoid logging in as root unless necessary.
Another good mechanism is `fail2ban`, which is a log-parsing tool that scans log files for failed login attempts and blocks the IP addresses of attackers who exceed a specified number of failed attempts. This helps prevent brute-force attacks on SSH and other services.

More options to lock down Linux systems are SELinux and AppArmor, which are mandatory access control (MAC) systems that enforce security policies on processes and files. They restrict the actions that processes can perform and the files they can access, providing an additional layer of security beyond traditional discretionary access control (DAC) mechanisms.
There are different applications such as `Snort`, `Suricata`, `chkrootkit`, `rkhunt`, and `Lynis` that can be used to monitor and detect security threats on Linux systems.

Other good practices include:

- Remove or disable all unnecessary services and software
- Remove services that rely on unencrypted authentication mechanisms
- Ensure NTP is enabled and Syslog is running
- Ensure each user has their own account
- Enforce the use of strong passwords
- Set up password aging and restrict reuse of previous passwords
- Lock user accounts after repeated login failures
- Disable all unwanted SUID/SGID binaries

### 6.1.1. TCP Wrappers
TCP Wrapper is a host-based access control system for network services. It allows administrators to restrict access to specific services based on the IP address or hostname of the client. TCP Wrappers use configuration files (`/etc/hosts.allow` and `/etc/hosts.deny`) to define access rules, allowing or denying connections to services based on the client's identity. This provides an additional layer of security by controlling which hosts can access specific services on the server.
```bash
[spaniel@parrot]─[~]
└──╼ $sudo cat /etc/hosts.allow

# Allow access to SSH from the local network
sshd : 10.129.14.0/24

# Allow access to FTP from a specific host
ftpd : 10.129.14.10

# Allow access to Telnet from any host in the inlanefreight.local domain
telnetd : .inlanefreight.local

[spaniel@parrot]─[~]
└──╼ $sudo cat /etc/hosts.deny

# Deny access to all services from any host in the inlanefreight.com domain
ALL : .inlanefreight.com

# Deny access to SSH from a specific host
sshd : 10.129.22.22

# Deny access to FTP from hosts with IP addresses in the range of 10.129.22.0 to 10.129.22.255
ftpd : 10.129.22.0/24
```

## 6.2. Firewall Setup
A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. It acts as a barrier between a trusted internal network and untrusted external networks, such as the internet. Firewalls can be hardware-based, software-based, or a combination of both.
Linux provides built-in firewall capabilities through tools like `iptables`, `nftables`, and `firewalld`. These tools allow administrators to define rules for filtering network traffic, controlling access to services, and protecting the system from unauthorized access. In Linux, the firewall functionality is typically implemented using the Netfilter framework
### 6.2.1. iptables
`iptables` is a command-line utility for configuring the Linux kernel's packet filtering rules. It operates at the network layer and allows administrators to define rules for filtering, modifying, and redirecting network traffic. `iptables` uses a set of tables, chains, and rules to determine how packets should be handled. `Nftables` is the successor to `iptables`, providing a more flexible and efficient way to manage firewall rules. It uses a single framework for both IPv4 and IPv6, simplifying the configuration process. `UFW` (Uncomplicated Firewall) is a user-friendly front-end for `iptables` that simplifies the management of firewall rules, making it easier for users to configure and maintain their firewall settings.
The main components of `iptables` are:
- **Tables**: `iptables` uses different tables to organize rules based on their purpose.
  - `filter`: The default table for filtering packets.
  - `nat`: Used for Network Address Translation (NAT) rules.
  - `mangle`: Used for packet alteration and modification.
  - `raw`: Used for configuring exemptions from connection tracking.
- **Chains**: Each table contains built-in chains that define the flow of packets through the firewall.
  - `INPUT`: Handles incoming packets destined for the local system.
  - `OUTPUT`: Handles outgoing packets originating from the local system.
  - `FORWARD`: Handles packets being routed through the system.
  - `PREROUTING`: Used for altering packets before routing decisions are made.
  - `POSTROUTING`: Used for altering packets after routing decisions are made.
- **Rules**: Each chain contains rules that specify how packets should be processed. Rules can match specific criteria, such as source and destination IP addresses, ports, protocols, and more. When a packet matches a rule, the specified action is taken (e.g., accept, drop, log, or redirect).
- **Matches**: `iptables` supports various match criteria that can be used to filter packets based on specific attributes, such as source and destination IP addresses, ports, protocols, and more. Matches can be combined to create complex filtering rules.
  - `-p`: Specifies the protocol (e.g., TCP, UDP, ICMP).
  - `-s`: Specifies the source IP address or network.
  - `-d`: Specifies the destination IP address or network.
  - `-m state`: Matches packets based on their connection state (e.g., NEW, ESTABLISHED, RELATED).
  - `-m multiport`: Matches packets based on multiple ports.
  - `-m tcp`: Matches TCP packets based on specific flags (e.g., SYN, ACK, FIN).
  - `-m udp`: Matches UDP packets based on specific ports.
  - `-m string`: Matches packets based on specific string patterns in the payload.
  - `-m limit`: Limits the rate of matching packets to prevent flooding.
  - `-m conntrack`: Matches packets based on connection tracking information.
  - `-m mark`: Matches packets based on a specific mark set by previous rules.
  - `-m mac`: Matches packets based on the Media Access Control (MAC) address of the source or destination.
  - `-m iprange`: Matches packets based on a range of IP addresses.
- **Targets**: Each rule can specify a target action, which determines what happens to the packet if it matches the rule. Common targets include:
  - `ACCEPT`: Allow the packet to pass through.
  - `DROP`: Discard the packet without any response.
  - `REJECT`: Discard the packet and send an error response.
  - `LOG`: Log the packet for further analysis.
  - `DNAT`: Perform destination NAT to redirect the packet to a different IP address.
  - `SNAT`: Perform source NAT to change the source IP address of the packet.
  - `MASQUERADE`: A special form of SNAT used for dynamic IP address translation, commonly used for internet sharing.
  - `REDIRECT`: Redirect the packet to a different port on the same machine.
  - `MARK`: Mark the packet for further processing by other rules or applications.

Consider that we want to add a new entry to the `INPUT` chain to allow incoming SSH connections on port 22. We can use the following command:
```bash
[spaniel@parrot]─[~]
└──╼ $sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
```

## 6.3. System Logs
System logs are essential for monitoring and troubleshooting Linux systems. They provide valuable information about system events, errors, and security-related activities. Linux uses a centralized logging system to collect and store log messages from various sources, such as the kernel, system services, applications, and user activities. There are several different types of system logs in Linux, including:
- **Kernel logs**: These logs contain messages generated by the Linux kernel, including hardware events, driver messages, and system startup information. They are typically stored in the `/var/log/kern.log` file.
- **System logs**: These logs contain messages from system services and daemons, such as system startup, shutdown, and service status changes. They are usually stored in the `/var/log/syslog` or `/var/log/messages` file.
- **Authentication logs**: These logs record authentication-related events, such as successful and failed login attempts, user account changes, and sudo command usage. They are typically stored in the `/var/log/auth.log` or `/var/log/secure` file.
- **Application logs**: These logs contain messages generated by specific applications and services, such as web servers, databases, and mail servers. The location of application logs varies depending on the application, but they are often found in the `/var/log/` directory with names specific to the application (e.g., `/var/log/apache2/access.log` for Apache web server logs).
- **Security logs**: These logs record security-related events, such as firewall activity, intrusion detection system (IDS) alerts, and security policy violations. They may be stored in various files, depending on the security tools used (e.g., `/var/log/ufw.log` for UFW firewall logs).

---

# 7. Linux Distributions vs Solaris
## 7.1. Solaris
Solaris is a Unix-based operating system developed by Sun Microsystems (now part of Oracle Corporation). It is known for its scalability, reliability, and advanced features, making it a popular choice for enterprise environments. Solaris is built on the System V Release 4 (SVR4) kernel and incorporates various technologies, such as the ZFS file system, DTrace for dynamic tracing, and Zones for lightweight virtualization. It includes a built-in hypervisor called Oracle VM Server for SPARC. It can handle large amounts of data and provide reliable and secure services.

## 7.2. Differences between Linux and Solaris
Solaris and Linux are both Unix-like operating systems, but they have several key differences. Firstly, Solaris is proprietary and therefore its source code is not available to the public, while Linux is open-source and its source code is freely available. This means that Linux can be modified and distributed by anyone, while Solaris is controlled by Oracle Corporation. Also, Linux distributions mostly use the Zettabyte File System (ZFS), and Solaris uses a Service Management Facility (SMF) for managing system services.
For package management, Solaris uses the Image Packaging System (IPS), while Linux distributions typically use package managers like `apt`, `yum`, or `dnf`. It also provides advanced security features such as Role-Based Access Control (RBAC) and Process Rights Management, which are not commonly found in Linux distributions.

## 7.3. Command Equivalents

| Ubuntu Command      | Solaris Command                   | Description                                      |
| ------------------- | --------------------------------- | ------------------------------------------------ |
| `uname`             | `showrev`                         | Displays system information.                     |
| `apt-get install`   | `pkgadd -d`                       | Installs a package from a specified directory.   |
| `find / -perm 4000` | `find / -perm -4000`              | Finds files with the SUID bit set.               |
|                     | `share -F nfs -o rw /export/home` | Shares a directory over NFS.                     |
| `lsof`              | `pfiles`                          | Lists open files and their associated processes. |
| `strace`            | `truss`                           | Traces system calls and signals.                 |


---

# 8. Tips and Tricks
## 8.1. Shortcuts

| Shortcut               | Description                                                      |
| ---------------------- | ---------------------------------------------------------------- |
| [TAB]                  | Autocompletes commands and file names.                           |
| [Ctrl] + [A]           | Moves the cursor to the beginning of the line.                   |
| [Ctrl] + [E]           | Moves the cursor to the end of the line.                         |
| [Ctrl] + [←] / [→]     | Moves the cursor one word left/right.                            |
| [Alt] + [B] / [F]      | Moves the cursor one word left/right (alternative).              |
| [Ctrl] + [U]           | Deletes everything from the cursor to the beginning of the line. |
| [Ctrl] + [K]           | Deletes everything from the cursor to the end of the line.       |
| [Ctrl] + [W]           | Deletes the word before the cursor.                              |
| [Ctrl] + [Y]           | Pastes the last deleted text.                                    |
| [Ctrl] + [C]           | Cancels the current command.                                     |
| [Ctrl] + [Z]           | Suspends the current command.                                    |
| [Ctrl] + [D]           | Exits the current shell or logs out.                             |
| [Ctrl] + [L]           | Clears the terminal screen.                                      |
| [Ctrl] + [R]           | Searches command history interactively.                          |
| [Alt] + [Tab]          | Switch between open applications.                                |
| [Ctrl] + [Shift] + [C] | Copies selected text to the clipboard.                           |
| [Ctrl] + [Shift] + [V] | Pastes text from the clipboard.                                  |
| [Ctrl] + [Shift] + [T] | Opens a new terminal tab.                                        |
| [Ctrl] + [Shift] + [N] | Opens a new terminal window.                                     |
| [Ctrl] + [+]           | Zooms in the terminal text.                                      |
| [Ctrl] + [-]           | Zooms out the terminal text.                                     |

# 9. Conclusion
I found this module extremely useful, as it gave a good refresher on some key concepts I learned about years ago and had forgotten by now, while also providing new insights into OS security which weren't taught at university. Having knowledge on the topic made it easy to understand, but I still believe this module is a good starting point for newcomers to computer science, as it covers most of the basics needed to understand how operating systems work.

I am uploading this in accordance with the current HTB policy, which allows sharing of 'free' academy modules. Regardless, these are my own notes based on the module content and I believe none of the information here is a direct copy (other than examples and commands). If there is any issue with this post, please do not hesitate to contact me and it will be removed. Otherwise, I hope you find this information useful and that it helps you just like it helped me.
