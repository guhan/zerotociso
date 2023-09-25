# Index Node (INODE)
An inode, short for "index node," is a data structure used in Unix-like file systems to represent and store information about a file or directory. Each file or directory in a file system is associated with an inode, which contains metadata about the file or directory, such as its permissions, ownership, timestamps, and the location of data blocks on the storage device.

## File Type
The inode specifies whether it represents a regular file, directory, symbolic link, device file, socket, or other types of files.
## File Size
The size of the file or directory in bytes.
## Ownership
The user and group owners of the file or directory.
## Permissions
The access permissions, including read, write, and execute permissions for the owner, group, and others.
## Timestamps
Inodes record several timestamps
- Access Time (atime)
The last time the file was accessed.
- Modification Time (mtime)
The last time the file's data was modified.
- Change Time (ctime)
The last time the file's metadata (e.g., permissions) was changed.
- Birth Time (btime)
The creation time of the file (not supported on all file systems).
## Pointers to Data Blocks
Inodes store references or pointers to the data blocks on the storage device where the file's actual content is stored. In the case of small files, some data may be stored directly in the inode itself (this is known as direct pointers).
## File System-specific Information
Some file systems store additional information in inodes, such as extended attributes, ACLs (Access Control Lists), and file versioning information.
