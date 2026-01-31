
# Introduction

**Linux Structure**  
Linux is an open-source operating system used on desktops, servers, embedded systems, and mobile devices. It is a core platform in cybersecurity due to stability, security, and flexibility. Exists in many distributions (distros) tailored to different needs.

**History**  
Linux originates from Unix (1970). GNU project (1983) aimed to create a free Unix-like OS. Linux kernel was created in 1991 by Linus Torvalds. Licensed under GPLv2. Today it has millions of lines of code and hundreds of distributions (Ubuntu, Debian, Fedora, Mint, etc.).

**Why Linux is Important**  
More secure and stable than many OSs, less malware-prone, frequently updated. Open-source allows modification and redistribution. Used everywhere: servers, desktops, embedded systems, Android.

**Linux Distributions**  
Different versions of Linux built on the same kernel. Examples: Ubuntu, Debian, Fedora, Arch, Linux Mint, Parrot OS. Parrot OS is security-focused and used for pentesting.

**Linux Philosophy**  
Based on simplicity, modularity, and openness. Uses small tools that do one thing well and can be combined. Configuration stored in text files and heavy use of the terminal.

**Core Principles**  
- Everything is a file.  
- Small single-purpose programs.  
- Programs can be chained together.  
- Avoid captive user interfaces (CLI preferred).  
- Configuration stored in text files (e.g. /etc/passwd).

**Main Components**  
- Bootloader: starts the OS (e.g. GRUB).  
- Kernel: manages hardware and system resources.  
- Daemons: background services.  
- Shell: command-line interface (Bash, Zsh, etc.).  
- Graphics Server: provides graphical support (X server).  
- Window Manager / GUI: graphical interface (GNOME, KDE, etc.).  
- Utilities: tools and applications.

**Linux Architecture**  
- Hardware: physical components.  
- Kernel: controls and virtualizes hardware resources.  
- Shell: interface between user and kernel.  
- System Utilities: provide OS functionality.

**File System Hierarchy**  
Linux uses a tree-like structure defined by the FHS standard.
![[Pasted image 20260128173404.png]]

**Root Directory (/)**  
Top-level directory containing everything required to boot and run the system.

**Important Directories**  
`/bin`: essential system commands.  
`/boot`: bootloader and kernel files.  
`/dev`: device files.  
`/etc`: system and application configuration.  
`/home`: user directories.  
`/lib`: essential shared libraries.  
`/media`: removable media mount points.  
`/mnt`: temporary mounts.  
`/opt`: optional and third-party software.  
`/root`: root user home directory.  
`/sbin`: system administration binaries.  
`/tmp`: temporary files.  
`/usr`: user programs, libraries, documentation.  
`/var`: variable data (logs, mail, web data).

# Shell

**Introduction to Shell**  
Learning the Linux shell is essential because many servers run Linux, especially web servers. The shell allows full control of the operating system and is more powerful than using only the GUI.

**Terminal / Shell / Console**  
A terminal (or shell, command line) is a text-based interface between the user and the kernel. It allows executing commands to control the system. The term console refers to a text-mode screen, not a window.

**Purpose of the Shell**  
Acts as a text-based interface to perform tasks like navigating directories, managing files, executing programs, and retrieving system information, with more flexibility and power than a GUI.

**Terminal Emulators**  
Software that emulates a terminal inside a graphical environment (GUI). They allow users to interact with the shell using text-based commands within a window.

**Command-Line Interfaces (CLI)**  
CLIs can run multiple terminals within one terminal session. They allow parallel command execution and multitasking.

**Terminal Multiplexers**  
Tools that extend terminal functionality by allowing multiple panes, sessions, and workspaces in a single terminal window. Example: tmux.

**Shell**  
The shell interprets user commands and communicates with the kernel. Everything done via GUI can also be done via the shell, often faster and more efficiently.

**Bash (Bourne-Again Shell)**  
The most commonly used Linux shell. Part of the GNU project. Supports scripting and automation, making repetitive tasks easier.

**Other Shells**  
Alternative shells include Tcsh/Csh, Ksh, Zsh, and Fish, each with different features and user experience.

![[Pasted image 20260128175448.png]]

## Bash (type of shell)

**Bash Prompt**  
The Bash prompt is a line of text showing system readiness. By default, it displays **username**, **hostname**, and **current directory**, with a cursor waiting for commands.

**Default Symbols**

- `$` → regular user
- `#` → root user
- `~` → home directory

**PS1 Variable**  
Controls how the prompt looks. Can be customized to show:

- Username, hostname, current directory
- Colors, special characters
- Date, time, IP address, last command status

**Example Custom Prompt**

`<username>@<hostname>[<current directory>]$ root@htb[/htb]#`

**Useful Special Characters for PS1**

- `\u` → username
- `\h` → hostname
- `\w` → full path of current directory
- `\d` → date (Mon Feb 6)
- `\D{%Y-%m-%d}` → date (YYYY-MM-DD)
- `\t` → time 24-hour (HH:MM:SS)
- `\T` → time 12-hour
- `\@` → time with AM/PM
- `\j` → number of jobs in shell
- `\n` → newline
- `\r` → carriage return
- `\s` → shell name

**Customization Benefits**

- Improves workflow and efficiency
- Helps track commands in penetration testing
- Makes terminal visually appealing
- Tools like **bash-prompt-generator** or **Powerline** can help adapt the prompt



# Help Commands

**Getting Help**  
In Linux, it’s essential to know how to get help for commands and tools you don’t know. The main methods are **man pages**, **help flags**, and **search tools**.

**ls Command Example**  
`ls` lists files and directories in the current folder.

- `ls --help` → shows short help with options
- `man ls` → shows full manual with syntax, description, and options

**Symbols in Prompts**

- `$` → regular user prompt
- `#` → root prompt

**Man Pages (`man <tool>`)**

- Displays detailed documentation for a command
- Shows syntax, description, options, and examples

**Help Option (`--help` or `-h`)**

- Quick reference for command options
- Most commands support `--help` (some support `-h`)

**Apropos Tool (`apropos <keyword>`)**

- Searches man pages for a keyword
- Returns commands and a short description  
    Example: `apropos sudo` lists sudo-related commands

**Explainshell**

- Website: [explainshell.com](https://explainshell.com/)
- Breaks down complex commands and explains each part

**Tip**  
Always explore commands, check man pages, and experiment. It saves time later and helps understand new tools efficiently.

# System info

**Common System Commands**

- `whoami` → shows current username.
- `id` → shows user ID, group ID, and group memberships.
- `hostname` → prints or sets the system hostname.
- `uname` → prints system info; `uname -a` shows all details (kernel, hostname, release, version, hardware, OS).
- `pwd` → prints current working directory.
- `ifconfig` → shows/configures network interfaces.
- `ip` → show/manipulate network interfaces and routing.
- `netstat` → shows network status.
- `ss` → investigate sockets.
- `ps` → shows running processes.
- `who` → shows logged-in users.
- `env` → prints or sets environment variables.
- `lsblk` → lists block devices.
- `lsusb` → lists USB devices.
- `lsof` → lists open files.
- `lspci` → lists PCI devices.

**SSH**

- `ssh user@[IP]` → securely access a remote machine via command line.
- SSH is lightweight, GUI-free, and efficient for remote administration.

**Hostname**

- `hostname` → prints the name of the machine.

**Whoami**

- `whoami` → prints the current logged-in user.

**Id**

- `id` → shows user ID, group ID, and groups.
- Membership in groups like `sudo`, `adm` can indicate potential privileges.

**Uname**

- `uname -a` → shows kernel, hostname, release, version, hardware, and OS.
- Individual flags:
    - `-r` → kernel release (useful for checking exploits).
    - `-s` → kernel name
    - `-n` → hostname
    - `-v` → kernel version
    - `-m` → machine hardware

# Navigation

**pwd**  
Prints the current working directory.

**ls**  
Lists files and directories in the current directory.

**ls -l**  
Shows detailed information: permissions, links, owner, group, size, date.

**ls -a**  
Shows hidden files (files starting with `.`).

**ls -la**  
Combines detailed view and hidden files.

**`ls -l` columns**

- `drwxr-xr-x` → file type and permission.
- `2` → number of hard links
- `user` → file owner
- `group` → group owner
- `4096` → size
- `date` → date and time
- `name` → file or directory name

**Hidden files**  
Files starting with `.` (e.g. `.bashrc`, `.bash_history`).

**cd -**  
Returns to the previous directory.

**Ctrl + R**  
Search through command history.

# Files and Directories

**touch <name_file>**
creates a file

**mkdir <name_directory>**
creates a directory

**mkdir -p <name_directory/name/name/...>**
creates parent directories

**tree .**
look structure of direcotires

**mv <file/directory> <destination_file/directory>**
to move to another directory or to rename a file `mv info.txt information.txt`

**cp <file/directory> <destination_file/directory>**
copy a file or directory

**nano**
`^` --> Ctrl

**cat <file_name>**
show file content
One such important file is the `/etc/passwd` file. This file contains essential information about the users on the system, such as their usernames, user IDs (`UIDs`), group IDs (`GIDs`), and home directories.
`/etc/shadow` stores the password hashes

**vim**
like nano but harder XD
![[Pasted image 20260131194137.png]]

**vimtutor**
For learning vim

**which <name_file/programm/directory>**
return the path if existing

**find <location_file/directory> <options_>**
![[Pasted image 20260131194528.png]]

**locate <file/directory>**
like find but faster, searches in a local db
![[Pasted image 20260131194846.png]]

