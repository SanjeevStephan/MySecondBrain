

# Checking Permissions
#os/linux/basics/permissions/checking-permissions

use the ls command with the –l (long) switch to display the contents of a directory in long format

—this list will contain the permissions

```bash
┌──(sanju㉿Watchdog)-[~]  
└─$ ls -ln /usr/share/hashcat  
total 332  
drwxr-xr-x 6 0 0   4096 Jun 26 00:29 charsets  
-rw-r--r-- 1 0 0 240526 Oct  6  2022 hashcat.hcstat2  
drwxr-xr-x 2 0 0   4096 Jun 26 00:29 layouts  
drwxr-xr-x 2 0 0   4096 Jun 26 00:29 masks  
lrwxrwxrwx 1 0 0     25 Mar 23 14:35 modules -> ../../lib/hashcat/modules  
drwxr-xr-x 2 0 0  69632 Jun 26 00:29 OpenCL  
drwxr-xr-x 3 0 0   4096 Jun 26 00:29 rules  
drwxr-xr-x 2 0 0   4096 Jun 26 00:29 tools  
drwxr-xr-x 2 0 0   4096 Jun 26 00:29 tunings  
```
  

!![[listing-indepth-properties-of-files-in-pwd.png]]

On each line, we get information about:
1. The file type (this is the first character listed)
2. The permissions on the file for owner, groups, and users, respectively
3. The number of links
4. The owner of the file
5. The size of the file in bytes
6. When the file was created or last modified
7. The name of the file

Explainations
1.The first character tells you the file type, where d stands for a directory
and a dash (–) indicates a file. These are the two most common file types.
2.  defines the permissions on the file.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
There are three sets of three characters, 
made of some combination of 
	read (r), 
	write (w), and
	execute (x), in that order.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

| Sets           | Descriptions                                  |
| -------------- | --------------------------------------------- |
| The first set  | represents the permissions of the owner       |
| The second set | represents the permissions  of the group      |
| the last set   | represents the permissions of all other users |

| Permission  | Description                                                                       |
| ----------- | --------------------------------------------------------------------------------- |
| read (r)    | that user or group of users has permission to open andread that file or directory |
| write (w)   | A w as the middle letter means they can write to (modify) the file,               |
| execute (x) | an x at the end means they can execute (or run) the file or access the directory. |

If any r, w, or x is replaced with a dash (-), then the respective permission hasn’t been given


```bash
-rw-r--r-- 1 0 0 240526 Oct  6  2022 hashcat.hcstat2
```

| The file is called, as we know from the right end of the line, hashcat.hcstat.<br>After the initial – (which indicates it’s a file)                        |     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------- | --- |
| the permissions rw- tell us that the owner has read and write permissions but not execute permission.                                                      |     |
| The next set of permissions (r--) represents those of the group and<br>shows that the group has read permission but not write or execute permis-<br>sions. |     |
| And, finally, we see that the rest of the other users also have only read per-<br>mission (r--).                                                           |     |
 
# Changing Permissions
#os/linux/basics/permissions/changing-permission-numerically

Using the Linux command chmod (or change mode) we can change the permissions.

we'll use chmod to change permissions on hashcat.hcstat using two different methods

| methods   | descriptions                                           |
| --------- | ------------------------------------------------------ |
| numerical | First we use a numerical representation of permissions |
| symbolic  | then we use a symbolic representation.                 |

### Changing Permissions with Decimal Notation

Representations of Permissions

|Binary|Octal|rwx|Description|
|---|---|---|---|
|000|0|---|No Permission|
|001|1|--x|Only Executable Permission|
|010|2|-w-|Only Writable Permission|
|011|3|-wx|Write & Execute Permissions|
|100|4|r--|Only Read Permission|
|101|5|r-x|Read & Execute Permissions|
|110|6|rw-|Read & Write Permissions|
|111|7|rwx|Read ( r ) \| Write ( w ) \| Execute ( x )|

``` java
Examples

> First, if we want to set only the read permission, locate the value for read
r w x  
4 - -

> Next, if we want to set the permission to wx, look for what sets the w and what sets the x:
r w x  
- 2 1

> Finally, when all three permissions are on, it looks like this:
r w x  
4 2 1

> And 4 + 2 + 1 = 7. when all the permission switches are on, they are represented by the octal equivalent of 7. So, if we wanted to represent all permissions for the owner, group, and all users, we could write it as follows:

7 7 7  


### Here’s where the shortcut comes in.

### By passing chmod three octal digits (one for each rwx set), followed by a filename,

### we can change permissions on that file for each type of user.
```

### Enter the following into your command line

```bash
chmod 774 hashcat.hcstat  
```

we can see that this statement gives the owner all permissions, the group all permissions, and everyone else (other) only the read permission.

Now we can see whether those permissions have changed by running ls -l on the directory and looking at the hashcat.hcstat line.

You should see -rwxrwxr-- on the left side of the hashcat.hcstat line u.

This confirms that the chmod call successfully changed permissions on the file to give both the owner and the group the ability to execute the file.

```bash
┌──(sanju㉿Watchdog)-[/usr/share/hashcat]  
└─$ sudo chmod 776 hashcat.hcstat2   
[sudo] password for sanju:   

┌──(sanju㉿Watchdog)-[/usr/share/hashcat]  
└─$ ls -ln  
total 332  
drwxr-xr-x 6 0 0   4096 Jun 26 00:29 charsets  
-rwxrwxrw- 1 0 0 240526 Oct  6  2022 hashcat.hcstat2  
drwxr-xr-x 2 0 0   4096 Jun 26 00:29 layouts  
drwxr-xr-x 2 0 0   4096 Jun 26 00:29 masks  
lrwxrwxrwx 1 0 0     25 Mar 23 14:35 modules -> ../../lib/hashcat/modules  
drwxr-xr-x 2 0 0  69632 Jun 26 00:29 OpenCL  
drwxr-xr-x 3 0 0   4096 Jun 26 00:29 rules  
drwxr-xr-x 2 0 0   4096 Jun 26 00:29 tools  
drwxr-xr-x 2 0 0   4096 Jun 26 00:29 tunings  
```

## Changing Permissions with UGO

The symbolic method is often referred to as the UGO syntax, which stands for user (or owner), group, and others.
UGO syntax is very simple. Enter the chmod command and then the users you want to change permissions for, providing u for user, g for group, or o for

others, followed by one of three operators:


| Operator | Description           |
| -------- | --------------------- |
| `-`      | Removs the Permission |
| `+`      | Adds the Permission   |
| `=`      | Sets the Permission   |


After the operator, include the permission you want to add or remove

(rwx) and, finally, the name of the file to apply it to.

Example

1. So, if you want to remove the write permission from the user that the file hashcat.hcstat belongs to, you could enter the following:
    

  
```bash
chmod u-w hashcat.hcstat  
```
# This command says to remove (-) the write (w) permission from hashcat.hcstat for the user (u).  

1. You can also change multiple permissions with just one command.

If you want to give both the user and other users (not including the group) execute permission, you could enter the following:

  
```bash
chmod u+x, o+x hashcat.hcstat  
```
```
# This command tells Linux to add the execute permission for the user  
# as well as the execute permission for others for the hashcat.hcstat file.
```

# Giving Root Execute Permission to User
#os/linux/basics/permissions/changing-executable-permission


```go
As a hacker, you’ll often need to download new hacking tools, but Linux

automatically assigns all files and directories default permissions of 666 and

777, respectively. This means that, by default, you won’t be able to execute a

file immediately after downloading it. If you try, you’ll usually get a message

that says something like “Permission denied.” For these cases, you’ll need to

give yourself root and execute permissions using chmod in order to execute

the file.

For example, say we download a new hacker tool called newhackertool
```

```bash
┌──(sanju㉿Watchdog)-[~]  
└─$ ls -l  
total 40  
drwxr-xr-x 2 sanju sanju 4096 Jun 27 20:12 Desktop  
drwxr-xr-x 4 sanju sanju 4096 Jun 28 00:13 Documents  
drwxr-xr-x 2 sanju sanju 4096 Jun 27 22:52 Downloads  
drwxr-xr-x 2 sanju sanju 4096 Jun 26 00:44 Music  
drwxr-xr-x 3 sanju sanju 4096 Jun 27 13:22 MyScripts  
-rw-r--r-- 1 sanju sanju   48 Jun 28 00:14 newhackertool  
drwxr-xr-x 2 sanju sanju 4096 Jun 27 22:48 Pictures  
drwxr-xr-x 2 sanju sanju 4096 Jun 26 00:44 Public  
drwxr-xr-x 2 sanju sanju 4096 Jun 26 00:44 Templates  
drwxr-xr-x 2 sanju sanju 4096 Jun 26 00:44 Videos  
```
 

We can see that our newhackertool doesn’t have execute permission for anyone.

Linux won’t let you execute a file you downloaded, but overall this setting makes your system more secure.

We can give the user - the permission to execute newhackertool by enteringthe following:

# └─>

```bash
sudo chmod u+x newhackertool
```

Now, when we perform a long listing on the directory, we can see that

our newhackertool has execute permission for the owner:

```bash
┌──(sanju㉿Watchdog)-[~]  
└─$ ls -ln  
total 40  
drwxr-xr-x 2 1000 1000 4096 Jun 27 20:12 Desktop  
drwxr-xr-x 4 1000 1000 4096 Jun 28 00:14 Documents  
drwxr-xr-x 2 1000 1000 4096 Jun 27 22:52 Downloads  
drwxr-xr-x 2 1000 1000 4096 Jun 26 00:44 Music  
drwxr-xr-x 3 1000 1000 4096 Jun 27 13:22 MyScripts  
-rwxr--r-- 1 1000 1000   48 Jun 28 00:14 newhackertool  
drwxr-xr-x 2 1000 1000 4096 Jun 27 22:48 Pictures  
drwxr-xr-x 2 1000 1000 4096 Jun 26 00:44 Public  
drwxr-xr-x 2 1000 1000 4096 Jun 26 00:44 Templates  
drwxr-xr-x 2 1000 1000 4096 Jun 26 00:44 Videos
```

# Giving Root Execute Permission to ALL


We can give everyone - the permission to execute newhackertool by enteringthe following:

# └─> sudo chmod +x newhackertool

```bash
┌──(sanju㉿Watchdog)-[~]  
└─$ ls -ln  
total 40  
drwxr-xr-x 2 1000 1000 4096 Jun 27 20:12 Desktop  
drwxr-xr-x 4 1000 1000 4096 Jun 28 00:19 Documents  
drwxr-xr-x 2 1000 1000 4096 Jun 27 22:52 Downloads  
drwxr-xr-x 2 1000 1000 4096 Jun 26 00:44 Music  
drwxr-xr-x 3 1000 1000 4096 Jun 27 13:22 MyScripts  
-rwxr-xr-x 1 1000 1000   48 Jun 28 00:14 newhackertool  
drwxr-xr-x 2 1000 1000 4096 Jun 27 22:48 Pictures  
drwxr-xr-x 2 1000 1000 4096 Jun 26 00:44 Public  
drwxr-xr-x 2 1000 1000 4096 Jun 26 00:44 Templates  
drwxr-xr-x 2 1000 1000 4096 Jun 26 00:44 Videos
```

# Granting Ownership to an Individual User
#os/linux/basics/permissions/grant-ownership-to-user  


To move ownership of a file to a different user so that they have the ability to control permissions, we can use the *chown* (or change owner) command

```bash
sudo chown bob /tmp/bobsfile
```

Here, we give the command, the name of the user we are giving owner-ship to, and then the location and name of the relevant file. This command grants the user account for Bob u ownership of `bobsfile`