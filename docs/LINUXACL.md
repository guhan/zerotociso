# Linux ACL
Access Control Lists (ACLs) in Linux are a mechanism that extends the traditional Unix file permissions (read, write, execute) to provide more fine-grained control over file and directory access. ACLs allow you to specify access rights for multiple users and groups beyond what can be achieved with the standard file permission system.


- getfacl: This command is used to display the ACL of a file or directory.

```getfacl /path/to/file```
- setfacl: This command allows you to modify the ACL of a file or directory. You can add or remove ACL entries and specify permissions.

```setfacl -m u:username:permissions /path/to/file```
- chacl: This command is a simplified interface for changing ACLs on files and directories.

```chacl -u username:permissions /path/to/file```
- ACL Entries: ACL entries are structured like "user:username:permissions" or "group:groupname:permissions," where "permissions" represent the desired access rights.
Example of adding an ACL entry:


```setfacl -m u:jane:rw /path/to/file```
In this example, an ACL entry is added for the user "jane" with read and write (rw) permissions.




## Enhanced Permission Control
ACLs provide a way to set permissions for additional users and groups beyond the owner and group assigned to a file or directory.
## Multiple Entries
ACLs consist of multiple entries, each specifying a user or group and the permissions assigned to them.
## Permission Inheritance
ACLs can be inherited from parent directories to child directories and files, allowing you to set default permissions for newly created objects.
## Access Levels
ACLs can grant various levels of access, such as read, write, execute, delete, and more.
## Modification and Viewing
ACLs can be modified and viewed using commands like getfacl and setfacl. For example, getfacl displays the ACL of a file or directory, while setfacl is used to modify it.

