#os/linux/basics/permissions

![[index-of-linux-basics-for-hacker]]

As you know, in Linux, the root user is all-powerful. The root user can do basically anything on the system. Other users on the system have more limited capabilities and permissions and almost never have the access that the root user has.

|owner|group|all users|
|---|---|---|

Not every user of a single operating system should have the same level of access to files and directories.

Like any professional or enterprise-level operating system, Linux has methods for securing file and directory access. This security system allows the system administrator—the root user—or the file owner to protect their files from unwanted access or tampering by granting select users permissions to read, write, or execute files.


| w   | Permission to write   | This allows users to view and edit a file                                 |
| --- | --------------------- | ------------------------------------------------------------------------- |
| r   | Permission to read.   | This grants permission only to open and view a file                       |
| x   | Permission to execute | This allows users to execute a file (but not necessarily view or edit it) |

In this way, the root user can grant users a level of permission depending on what they need the files for. When a file is created, typically the user who created it is the owner of the file

|Title|Granting Ownership to an Individual User|
|---|---|
|Syntax|chown bob /tmp/bobsfile|
|Desciption|Here, we give the command, the name of the user we are giving ownership to, and then the location and name of the relevant file. This command grants the user account for Bob u ownership of bobsfile|
|||
|||

## Changing Permissions with Decimal Notation

We can use a shortcut to refer to permissions by using a single number to represent one rwx set of permissions.

A binary set like this is then easily represented as one digit by converting it into octal, an eight-digit number system that starts with 0 and ends with 7. An octal digit represents a set of three binary digits, meaning we

can represent an entire rwx set with one digit. Table 5-1 contains all possible permission combinations and their octal and binary representatives.

|Binary|Octal|rwx|
|---|---|---|
|000|0|---|
|001|1|--x|
|010|2|-w-|
|011|3|-wx|
|100|4|r--|
|101|5|r-x|
|110|6|rw-|
|111|7|rwx|

Using this information, let’s go through some examples.


| Permissions | (Numerals) | What does it do ?                                                                                                                                                                                                      |
| ----------- | ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| r w x       | 4--        | set only the read permission                                                                                                                                                                                           |
| r w x       | - 2 1      | set the permission to write and execute\|the octal representation for -wx is 3, which not . so coincidently happens to be the same value we get when we add the two values for setting w and x individually: 2 + 1 = 3 |
| r w x       | 4 2 1      | Finally, when all three permissions are on, it looks like this\|And 4 + 2 + 1 = 7. Here, we see that in Linux, when all the permission<br><br>switches are on, they are represented by the octal equivalent of 7.      |

So, if we wanted to represent all permissions for the owner, group, and all users, we could write it as follows:

| owner              | group              | all users          |
| ------------------ | ------------------ | ------------------ |
| r w x<br><br>4 2 1 | r w x<br><br>4 2 1 | r w x<br><br>4 2 1 |
| 7                  | 7                  | 7                  |

|Command|Explaination|
|---|---|
|chmod 774 hashcat.hcstat|By passing chmod three octal digits (one for each rwx set), followed by a filename, we can change permissions on that file for each type of user.|

# Changing Permissions with UGO

UGO syntax is very simple.

The symbolic method is often referred to as the UGO syntax, which stands for

|user (or owner)|group|others|
|---|---|---|
|u|g|o|

Enter the chmod command and then the users you want to change permissions for,

providing u for user, g for group, or o for others, followed by one of three operators:

|Operator|What does it do ?|
|---|---|
|-|Removes a permission|
|+|Adds a permission|
|=|Sets a permission|

After the operator, include the permission you want to add or remove (rwx) and, finally, the name of the file to apply it to.

|TO DO|to remove the write permission from the user that the file hashcat.hcstat belongs to, Simply Enter this Command|
|---|---|
|COMMAND|chmod u-w hashcat.hcstat|
|EXPLAINATION|This command says to remove (-) the write (w) permission from hashcat .hcstat for the user (u).|

You can also change multiple permissions with just one command.

If you want to give both the user and other users (not including the group) execute permission, you could enter the following

|TO DO|This command tells Linux to add the execute permission for the user<br><br>as well as the execute permission for others for the hashcat.hcstat file.|
|---|---|
|Command|chmod u+x, o+x hashcat.hcstat|

# Giving Root Execute Permission on a New Tool

As a hacker, you’ll often need to download new hacking tools, but Linux automatically assigns all files and directories default permissions of 666 and 777, respectively.

This means that, by default, you won’t be able to execute a file immediately after downloading it.

If you try, you’ll usually get a message that says something like “Permission denied.”

For these cases, you’ll need to give yourself root and execute permissions using chmod in order to execute the file.

```bash
kali >ls -l  
total 80  
drwxr-xr-x 7 root root 4096 Dec 5 11.17 Desktop  
drwxr-xr-x 7 root root 4096 Dec 5 11.17 Documents  
drwxr-xr-x 7 root root 4096 Dec 5 11.17 Downloads  
drwxr-xr-x 7 root root 4096 Dec 5 11.17 Music  
-rw-r--r-- 1 root root 1072 Dec 5 11.17 newhackertoolu  
drwxr-xr-x 7 root root 4096 Dec 5 11.17 Pictures
```

By default, Linux won’t let you execute a file you downloaded, but overall this setting makes your system more secure.

We can give ourselves permission to execute newhackertool by entering the following

|chmod 766 newhackertool|
|---|

Now, when we perform a long listing on the directory, we can see that our newhackertool has execute permission for the owner

```bash
--snip--  
drwxr-xr-x 7 root root 4096 Dec 5 11.17 Music  
-rwxrw-rw- 1 root root 1072 Dec 5 11.17 newhackertool  
drwxr-xr-x 7 root root 4096 Dec 5 11.17 Pictures  
--snip--
```

As you now understand, this grants us (as the owner) all permissions, including execute, and grants the group and everyone else only read and write permissions (4 + 2 = 6)