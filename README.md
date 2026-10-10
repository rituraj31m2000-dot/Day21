Linux File Permission Analysis

Internship Task – Day 21

Domain: Cyber Security
Task: File Permission Analysis

1. Introduction

Linux file permissions control who can read, write, and execute files and directories. Proper permission management helps protect sensitive information and prevents unauthorized access.

2. Objective

- Understand Linux file permissions.
- Analyze file and directory permissions.
- Identify overly permissive configurations.
- Learn how to improve Linux system security.

3. Tools Used

- Linux Operating System
- Linux Terminal
- "ls", "chmod", and "stat" commands

4. Understanding Linux Permissions

Linux permissions are divided into three categories:

- Owner (u): The user who owns the file.
- Group (g): Users belonging to the file's group.
- Others (o): All other users.

There are three basic permission types:

Permission| Symbol| Numeric Value
Read| r| 4
Write| w| 2
Execute| x| 1

5. Common Linux File Permissions

Permission 755

- Owner: Read, write, execute
- Group: Read, execute
- Others: Read, execute

Meaning: "rwxr-xr-x"

Use: Commonly used for executable files and directories when others need access but should not modify the owner's files.

Permission 644

- Owner: Read, write
- Group: Read
- Others: Read

Meaning: "rw-r--r--"

Use: Commonly used for non-sensitive text files and configuration files that do not require executable permission.

Permission 777

- Owner: Read, write, execute
- Group: Read, write, execute
- Others: Read, write, execute

Meaning: "rwxrwxrwx"

Security risk: Anyone with access can potentially read, modify, or execute the file. Avoid this permission unless there is a specific, justified need.

6. Commands Used for Permission Analysis

Check file permissions

ls -l

Check permissions of a specific file

ls -l filename.txt

View detailed file information

stat filename.txt

Set permissions to 644

chmod 644 filename.txt

Set permissions to 755

chmod 755 script.sh

Remove write permission from others

chmod o-w filename.txt

Find world-writable files in a directory

find . -type f -perm -0002 -print

Note: Run these commands in a test directory or on files you own. Review permissions before changing them.

7. Practical Analysis

Permission| Security Assessment
644| Usually suitable for ordinary, non-sensitive files
755| Often suitable for executable scripts and directories
777| High risk because all users can modify and execute the file
600| Suitable for private files that only the owner should read and write

The appropriate permission depends on the file's purpose, ownership, and required access.

8. Why Are Excessive Permissions Dangerous?

- Unauthorized users may modify important files.
- Sensitive information may be exposed.
- Malicious scripts may be modified or executed.
- Incorrect permissions may increase the risk of privilege escalation.
- System integrity and confidentiality may be affected.

9. Recommended Security Practices

- Follow the principle of least privilege.
- Avoid using "chmod 777" unnecessarily.
- Restrict access to sensitive files.
- Review file ownership and permissions regularly.
- Use appropriate permissions for scripts, directories, and configuration files.
- Test permission changes before applying them to important system files.

10. Conclusion

This task helped me understand Linux file permissions and their importance in cybersecurity. I learned how to inspect permissions, use "chmod" and "stat", identify world-writable files, and recommend safer permission settings.
