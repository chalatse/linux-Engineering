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
