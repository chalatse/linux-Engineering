This is a linux commands.

// Read and Use System Documentation

Journalctl --help - Query the Journal

// man shows the command manual

// Example
man journalctl

// The apropos command in Linux is used to search the man pages (manual pages) for a given keyword — it shows commands and descriptions related to that keyword.

// Example 
apropos copy

cp (1)               - copy files and directories
scp (1)              - secure copy (remote file copy program)
strncpy (3)          - copy a string with specified length


// Create and Manage hard Links
The stat command in Linux is used to display detailed information about a file or directory — such as size, permissions, owner, timestamps, and more.
  File: myfile.txt
  Size: 1024       Blocks: 8          IO Block: 4096   regular file
Device: 802h/2050d Inode: 131073      Links: 1
Access: 2025-04-30 08:45:12.000000000 +0200
Modify: 2025-04-29 19:14:07.000000000 +0200
Change: 2025-04-29 19:14:07.000000000 +0200
 Birth: -

//Create and Manage Soft Link

Use ln command


 Round 1: OS Concepts
1. What is an OS?
An Operating System (OS) is system software that manages computer hardware, software resources, and provides services for application programs. It acts as an interface between the user and hardware.

2. What is an OS used for?
Resource management (CPU, memory, I/O).

File and process management.

User interface (CLI or GUI).

Running applications.

3. What is a Kernel?
The kernel is the core part of an OS. It:

Manages CPU, memory, and devices.

Provides process and system call handling.

Runs in privileged mode (ring 0).

4. Difference between Kernel and Shell
Kernel	Shell
Core OS component	Interface between user and kernel
Manages hardware	Accepts commands from users
Executes low-level tasks	Executes user-level commands

5. What is a process and how does it affect CPU usage?
A process is a running instance of a program. Each process uses CPU cycles. If the process has multiple cores or threads, it can consume more CPU depending on how it's scheduled.

6. Zombie vs Orphan Process
Zombie: Process that has finished execution but still has an entry in the process table (waiting for parent to read its exit status).

Orphan: A process whose parent has terminated. It is adopted by init or systemd.

7. What is Demand Paging?
A memory management scheme where pages are loaded only when needed, not in advance. It reduces memory usage.

8. Process vs Thread
Process	Thread
Independent	Share memory with other threads
Own memory space	Light-weight, faster
Context switching is heavy	Switching is faster

🔹 Round 2: Linux Boot and Troubleshooting
1. Explain Linux Booting Process
BIOS/UEFI: Hardware initialization

MBR/GPT: Bootloader (like GRUB) is loaded

GRUB: Loads the kernel

Kernel: Initializes hardware, mounts initramfs

Init/Systemd: Starts user-space services

Login prompt: GUI or CLI login

2. What steps to take if the system doesn't boot properly?
Boot into rescue mode or live CD

Check dmesg, /var/log/boot.log

Use fsck to check disk errors

Reinstall GRUB if corrupted

Check for missing init/systemd or broken kernel

3. Will Linux boot if the file system is missing?
No — if root (/) filesystem is missing, the kernel can't mount it. You’ll get a kernel panic or emergency shell.

4. Can’t log in to server — Troubleshooting:
Check network (ping, ssh, netstat)

Check disk full (df -h)

Check authentication service (systemctl status sshd)

Look at logs: /var/log/auth.log, /var/log/messages

Boot into recovery mode if locked out

5. Types of Scheduling Algorithms:
FCFS – First Come First Serve

SJF – Shortest Job First

Round Robin

Priority Scheduling

Multilevel Queue

6. Can't access/open file — Linux permissions
Check permissions with:

bash
Copy
Edit
ls -l file.txt
Use:

chmod to change permission

chown to change ownership

sudo to gain elevated access if needed

7. Process States:
New: Being created

Ready: Waiting for CPU

Running: Currently executing

Waiting/Blocked: Waiting for I/O

Terminated: Finished execution

Zombie: Completed but not cleaned

Orphan: Parent terminated

8. Types of Operating Systems:
Batch OS: Jobs in batches (no interaction)

Time-sharing OS: Multitasking

Distributed OS: Multiple machines act as one

Real-time OS: Guaranteed response times

Mobile OS: Android, iOS

Network OS: Linux, Unix for network management

9. Multiprocessing vs Multitasking
Multiprocessing	Multitasking
Uses multiple CPUs	Multiple tasks on one CPU
True parallelism	Context switching
More powerful	Less resource-heavy

🔹 Networking Questions
10. What happens when you type www.google.com
Browser checks cache

DNS resolution to get IP

TCP handshake with Google server (3-way)

HTTPS Request sent (TLS handshake)

Google responds with HTML

Browser renders page

DNS Explained
DNS = Domain Name System

Translates domain names to IP addresses

Tools: dig, nslookup, /etc/resolv.conf

11. Check system utilization in Linux
top, htop: CPU and memory

vmstat: virtual memory stats

iostat: disk I/O

netstat, ss: network sockets

sar: system activity report
