===========================================================================
Marvellous CVFS (Custom Virtual File System)
===========================================================================

Author       : Shreya Siddhart Sasane
Date         : 15/08/2025
Description  : 
    This project implements a simple custom virtual file system (CVFS) that 
    supports basic file operations via a command-line interface (CLI). It 
    simulates file creation, deletion, reading, writing, and metadata retrieval 
    using in-memory structures.

===========================================================================

Features:
---------
1. Create and manage files with permissions (read, write).
2. Write data into files and read data from files using file descriptors.
3. Display information about files (size, permission, link count).
4. Delete files and free associated memory.
5. List all existing files in the directory.
6. Command-line interface with commands similar to Unix shell (creat, read, write, ls, stat, unlink, man, help, exit, clear).

===========================================================================

Supported Commands:
-------------------
- exit
  Terminates the CVFS shell and deallocates all resources.

- help
  Displays help information about available commands.

- clear
  Clears the terminal screen (Windows-specific command).

- ls
  Lists all files in the directory.

- man <command>
  Displays the manual page for the specified command.

- creat <filename> <permission>
  Creates a new file with the given filename and permission (1 for read, 2 for write, 3 for read+write).
  Returns a file descriptor on success.

- write <fd>
  Writes data into the file identified by the file descriptor. Prompts for input.

- read <fd> <size>
  Reads a specified number of bytes from the file descriptor and displays the content.

- stat <filename>
  Displays metadata/statistics of the specified file.

- unlink <filename>
  Deletes the specified file from the CVFS.

===========================================================================

Error Handling:
---------------
The system returns error codes and prints error messages for:
- Invalid parameters
- File not existing
- Permission denied (read/write)
- Insufficient space or data
- Invalid file descriptors
- File already exists during creation
- No free inodes for creating new files

===========================================================================

Internal Data Structures (brief):
---------------------------------
- UFDT (User File Descriptor Table): Array holding file table entries.
- Inode: Structure representing a file with metadata like FileName, FileSize, LinkCount, Permission, etc.
- File table: Contains buffer, read/write offsets, pointer to inode.
- Linked list of inodes: Represents files in the directory.

===========================================================================

Compilation and Execution:
--------------------------
- Compile using a C/C++ compiler:
  Example: gcc -o cvfs cvfs.c
- Run executable:
  ./cvfs  (Linux/macOS)
  cvfs.exe (Windows)

===========================================================================

Notes:
------
- Currently, 'clear' command uses Windows-specific 'cls'. Change to 'clear' for Linux/macOS.
- The program uses dynamic memory allocation. Ensure proper memory management.
- The system simulates a file system in memory; no persistent storage is used.

===========================================================================

Contact:
--------
For any queries or contributions, please contact Shreya Siddhart Sasane.

===========================================================================

