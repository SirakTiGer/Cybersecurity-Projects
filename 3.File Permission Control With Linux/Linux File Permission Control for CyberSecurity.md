# File Permissions in Linux

## Project Description
As a Cybersecurity analyst, one of my responsibilities is to ensure the **Least Privilege Principle**. This means I must ensure only the right person has access to the files and directories in the organization. In this project, I will use Linux commands to review permissions, set permissions, and remove permissions from files and directories.


---

## Check File and Directory Details
To check the details of files and directories, including owner permissions, I use the `ls -la` command:
- The `-l` option shows permissions set for files and directories.
- The `-a` option shows hidden files and directories.  

When combined, `ls -la` displays the full permissions for users and groups for all files and directories, including hidden ones.


![Permission 1](https://github.com/user-attachments/assets/ffd41a7c-e869-4bf5-9d11-5c7a8876ccc3)


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

![owner-priviledge](https://github.com/user-attachments/assets/4fbab883-4479-4a68-8fb7-106042453d9e)

To remove this permission, I used chmod command as follows: 

![owner 2](https://github.com/user-attachments/assets/73303dbd-f6b8-48fe-bf26-bc71753c639d)

As the result of the command issued the write permission is removed from the Groups owner successfully. In the chmod g=r command the g represents the Groups owner and the r represents the read only permission. I used the operator =, which overrides the current permission to the permission set on  the right side of the operator, in this case read permission.

## Change Directory Permissions

The files and directories inside the `drafts` directory belong exclusively to the `researchers2` user. As a result, all access permissions should only be granted to the `researchers2` user. However, the **Group owner** had an **Execute** privilege.

To rectify the issue, I used the following command:

![image](https://github.com/user-attachments/assets/7c3b57d3-6429-4d1f-bfe7-90b1ec71efa7)

The command successfully provided the appropriate privilege as seen below

![image](https://github.com/user-attachments/assets/e31b8734-88fd-46af-8427-b75797162f63)

The `g` in the `chmod` command represents the **Group owner**, and the `x` represents the **Execute privilege**. 

I used the arithmetic operator `-` to remove the **Execute privilege** from the **Group owner**. This adjustment ensures that only the intended permissions are maintained for the directory.

## Summary

As demonstrated above, the `chown` command, along with the `ls -la` command, was a key tool used to review access privileges. I was able to grant appropriate access to the files and directories to the correct owners. 

By doing so, I contributed to the organization's overall security and privacy, ensuring that access permissions align with established policies and the **Least Privilege Principle**.


