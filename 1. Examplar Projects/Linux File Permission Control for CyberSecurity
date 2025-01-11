# File Permissions in Linux

## Project Description
As a Cybersecurity analyst, one of my responsibilities is to ensure the **Least Privilege Principle**. This means I must ensure only the right person has access to the files and directories in the organization. In this project, I will use Linux commands to review permissions, set permissions, and remove permissions from files and directories.


---

## Check File and Directory Details
To check the details of files and directories, including owner permissions, I use the `ls -la` command:
- The `-l` option shows permissions set for files and directories.
- The `-a` option shows hidden files and directories.  

When combined, `ls -la` displays the full permissions for users and groups for all files and directories, including hidden ones.


---
## Describe the Permission String
The permission strings in Linux are a combination of **d, r, w, x,** and **-**. Each character represents a level of authorization for each user or group regarding a specific file or directory.  

### Permission String Breakdown:
- `d`: Indicates the item is a directory.
- `r`: Represents read permission, allowing the owner to see the content of a file or directory.
- `w`: Represents write permission, allowing the owner to edit the content of a file or directory.
- `x`: Represents execute permission, allowing the owner to run executable files in the directory.
- `-`: Indicates the item is a file (if at the beginning) or the absence of a permission.

### Example:
If `project_r.txt` has a permission string of `-rw-rw-r--`, the interpretation is as follows:
- The first character (`-`) shows it is a file.
- The next three characters (`rw-`) represent **User owner** permissions: read and write, but no execute.
- The second set (`rw-`) represents **Group owner** permissions: read and write, but no execute.
- The last set (`r--`) represents **Other owner** permissions: read only.

---

## Change File Permissions
In the example below, the **Other owner** has write permission on `projects_k.txt`, which is against organizational policy.  

To remove this permission, I used:
```bash
chmod o-w projects_k.txt
