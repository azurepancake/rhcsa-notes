### Understanding Basic Permissions

| Attribute | Files | Directories |
|-|-|-|
| Read(4) | Read | List |
| Write(2) | Modify | Delete/Create |
| Execute (1) | Run | Change into |

* Read and Execute are required to fully use a directory

### Understanding umask

* `umask` is a value which subtracts a specfied number from the default permissions
  * The `umask` (by itself) command will print the current `umask`
  * If you pass `umask` a permission value, that value becomes the new `umask`
* Default permissions for files are 666
* Defailt permissions for directories are 777
* The default `umask` is set in:
 * `/etc/profile` system-wide
 * `~/.bash_profile` for a specific user

### Understanding Special Permissions

| Attribute | Files | Directory |
|-|-|-|
| SUID(4) | Run as owner | N/A |
| SGID(2) | Run as group owner | All files created in directory inheret the directory group owner |
| Sticky Bit(1) | N/A | Delete only if you are the owner of file or directory containing them |
