# Linux File Permissions

## Overview

This exercise explores how Linux manages file and directory permissions. Understanding permissions is important for system administration and cybersecurity because they control who can access, read, modify, and execute files.

## 1. Understanding Linux Permissions

Linux uses three permission categories:

- **Owner:** The user who owns the file or directory.
- **Group:** Users who belong to the file's assigned group.
- **Others:** All other users.

There are three basic permissions:

| Permission | Symbol | Meaning |
|---|---|---|
| Read | r | View file contents or list directory contents |
| Write | w | Modify files or directory entries |
| Execute | x | Run a file or access/traverse a directory |

## 2. Numeric Permissions

Linux also represents permissions using numbers:

- Read = 4
- Write = 2
- Execute = 1

Examples:

| Mode | Permissions | Purpose |
|---|---|---|
| 600 | rw------- | Owner can read and write |
| 644 | rw-r--r-- | Owner can read/write; others can read |
| 700 | rwx------ | Owner has full access |

## 3. Commands Practiced

### Creating a directory

`mkdir permissions-lab`

Creates a directory for permission testing.

### Creating a file

`touch report.txt`

Creates an empty file.

### Viewing permissions

`ls -l report.txt`

Displays the file's permissions, ownership, and size.

### Restricting permissions

`chmod 600 report.txt`

Restricts access to the owner.

### Allowing read access

`chmod 644 report.txt`

Allows the owner to read and write while allowing the group and others to read.

### Restricting directory access

`mkdir private`

`chmod 700 private`

Creates a directory that only its owner can access under normal permission checks.

## 4. Troubleshooting Scenario

**Problem:** A coworker reports that they cannot read a shared report file.

The file permissions are:

`-rw-------`

**Analysis:** The owner has read and write permissions, but the group and others have no permissions. A coworker who is not the owner cannot read the file through normal permission checks.

**Resolution:** If the file is intended to be readable by everyone, changing its permissions to `644` allows read access for the group and others.

## 5. Security Relevance

File permissions help administrators protect sensitive information and prevent unauthorized access.

Examples include:

- Restricting access to confidential employee records.
- Protecting configuration files.
- Limiting which users can modify system files.
- Troubleshooting permission-denied errors.

## 6. What I Learned

Through this exercise, I practiced creating files and directories, inspecting Linux permissions, modifying access with `chmod`, and analyzing a basic access-denied scenario.

I also learned that directory permissions differ from file permissions, particularly how execute permission controls directory traversal.
