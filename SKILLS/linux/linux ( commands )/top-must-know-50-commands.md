#os/linux/commands/must-know-commands

All Linux commands fall into one of the following four categories:

| [Shell](https://phoenixnap.com/kb/linux-shells) **builtins** | Commands built directly into the shell with the fastest execution.                               |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| **Shell functions**                                          | Shell scripts (grouped commands).                                                                |
| **Aliases**                                                  | Custom command shortcuts.                                                                        |
| **Executable programs**                                      | Compiled and installed [programs](https://phoenixnap.com/glossary/what-is-a-program) or scripts. |
**Note:** Check any command type by running **`type <command>`**.

> Below is a list of typical Linux commands with explanations and examples of how they work. Open the terminal (**CTRL**+**ALT**+**T**) and follow along

## 0. The ( `man` ) Command
The [man command](https://phoenixnap.com/kb/linux-man) (**man**ual) is a convenient manual available in the terminal. Add **`man`** as a prefix to any command to check the manual reference:

| Syntax | man `<put-any-command-here>` |
| ------ | ---------------------------- |

![[Pasted image 20240620204013.png]]
To exit the manual, press **q**.
## 1. The ( `pwd` ) Command
The [pwd command](https://phoenixnap.com/kb/pwd-linux) (**p**rint **w**orking **d**irectory) is a shell builtin command that prints the current location. The output shows an absolute [directory](https://phoenixnap.com/glossary/what-is-a-directory) path, starting with the root directory (**`/`**).
The output prints the current location in the **`/home/<username>`** format.


## 2. The ( `ls` ) Command
The [ls command](https://phoenixnap.com/kb/linux-ls-commands) (**l**i**s**t) prints a list of the current directory's contents.

Additional options provide flexibility with the display output. Typical usage includes combining the following options:

| ls      |                                                                                            |
| ------- | ------------------------------------------------------------------------------------------ |
| ls -l   | Show as a list:                                                                            |
| ls -la  | Show as a list and include hidden [files](https://phoenixnap.com/glossary/what-is-a-file): |
| ls -lah | Show sizes in a human-readable format:                                                     |
|         |                                                                                            |
## 3. The ( `cd` ) Command
The [cd command](https://phoenixnap.com/kb/linux-cd-command) (change directory) is a shell builtin command for changing the current working directory:

| cd `<directory>`<br> |
| -------------------- |
The working directory changes in the terminal interface. In a non-default interface, use the **`pwd`** command to check the current directory.

Use **`cd`** without any parameters to return to the home directory (**`~`**).

## 4. The ( `cat` ) Command
The [cat command](https://phoenixnap.com/kb/linux-cat-command) (con**cat**enate) displays the contents of a file in the terminal (standard output or stdout). 
To use the command, provide a file name from the current directory:

| cat `<filename>`        | Display the Content of `<filename>`                                 |
| ----------------------- | ------------------------------------------------------------------- |
| cat `<path>/<filename>` | Alternatively, provide a path to the file along with the file name: |
| cat `<file1> <file1>`   | Display contents of multiple files                                  |
| cat -n `<filename>`     | Display Contents with line-numbers                                  |
## 5. The ( `touch` ) Command
The command creates an empty file (or a batch of files) quickly, if it does not exist.

| touch `<filename.txt>` |
| ---------------------- |

## 6. The ( `cp` ) Command
The main best way to [copy files and directories in Linux](https://phoenixnap.com/kb/how-to-copy-files-directories-linux) is through the [cp command](https://phoenixnap.com/kb/cp-command) (**c**o**p**y)

| Syntax              | cp `<source-file> <target-file>`                     |
| ------------------- | ---------------------------------------------------- |
| Same-Directory      | cp `file.txt file_copy.txt`                          |
| Different-Directory | cp `/source-dir/file.txt` `destination-dir/file.txt` |

## 7. The ( `mv` ) Command
Use the [mv command](https://phoenixnap.com/kb/mv-command-linux) (**m**o**v**e) to move files or directories from one location to another.

| Syntax      | mv `<filename>` `~/Destination-Dir/<filename>` |
| ----------- | ---------------------------------------------- |
| Rename-File | mv `<filename>` `<renamed-filename>`           |
| Example     | mv `anyfile.txt ~/Documents/anyfile.txt`       |
## 8. The ( `mkdir` ) Command
The [mkdir command](https://phoenixnap.com/kb/create-directory-linux-mkdir-command) (**m**a**k**e **dir**ectory) creates a new directory in the provided location.
## 9. The ( `rmdir` ) Command
Use the [rmdir command](https://phoenixnap.com/kb/remove-directory-linux) (**r**e**m**ove **dir**ectory) to delete an empty directory.
> Note : If the directory is not empty, the command fails.
## 10. The ( `rm` ) Command
The **rm** command (**r**e**m**ove) [deletes files or directories](https://phoenixnap.com/kb/how-to-remove-files-directories-linux-command-line). To use the command for non-empty directories, add the **`-r`** tag:
> Note : Unlike the **`rmdir`** command, **`rm`** also removes all the contents from the directory.

| Syntax  | rm -r `<file or directory` |
| ------- | -------------------------- |
| Example | rm -r `~/TEST`             |
> **Note:** Removing some directories in Linux is dangerous. Make sure you know what you're removing before running a [dangerous Linux terminal command](https://phoenixnap.com/kb/dangerous-linux-terminal-commands).

## 11. The ( `locate` ) Command
The [locate command](https://phoenixnap.com/kb/locate-command-in-linux) is a simple Linux tool for finding a file. The command checks a file database on a system to perform the search quickly. However, the result is sometimes inaccurate if the database is not updated.

| Syntax    | locate `<filename>` |
| --------- | ------------------- |
| Example-1 | locate .bashrc      |
| Example-2 | locate sources.list |

To use the command, install locate and then try
The output prints the file's location path. 
The matching is unclear and outputs any file that contains the file name.

## 12. The ( `find` ) Command
Use the [find command](https://phoenixnap.com/kb/guide-linux-find-command) to perform a thorough search on the system. Add the **`-name`** tag to search for a file or directory by name:

| Syntax  | find -name `<file or directory>` |
| ------- | -------------------------------- |
The output prints the file's path and performs an exact match. Use additional options to control the search further.

## 13. The ( `grep` ) Command
The [grep command](https://phoenixnap.com/kb/grep-command-linux-unix-examples) (**g**lobal **r**egular **e**xpression **p**rint) enables searching through text in a file or a standard output. 


| Syntax  | grep `<search string>` `<filename>` |
| ------- | ----------------------------------- |
| Example | grep world `~/Documents/hello.txt`  |
The output highlights all matches. Advanced commands include using [grep for multiple strings](https://phoenixnap.com/kb/grep-multiple-strings) or writing [grep regex](https://phoenixnap.com/kb/grep-regex) statements.
## 14.  The ( `sudo` ) Command
The [sudo command](https://phoenixnap.com/kb/linux-sudo-command) (**s**uper**u**ser **do**) elevates a user's permissions to administrator or [root](https://phoenixnap.com/glossary/what-is-root-access). Commands that change system configuration require elevated privilege.
> Add **`sudo`** as a prefix to any command that requires elevated privileges
> Use the command with caution to avoid making accidental changes permanent.

| Syntax | sudo `<command>` |
| ------ | ---------------- |
## 15. The ( `df` ) Command
The **`df`** command (**d**isk **f**ree) is used to [check available disk space](https://phoenixnap.com/kb/linux-check-disk-space) on the [file system](https://phoenixnap.com/kb/linux-file-system). To see how **`df`** works, run the following:


| Syntax | df -h |
| ------ | ----- |
```bash
┌──(cipher㉿watchdog)-[~]
└─$ df -h
Filesystem      Size  Used Avail Use% Mounted on
udev            3.8G     0  3.8G   0% /dev
tmpfs           785M  1.4M  783M   1% /run
/dev/sda1       210G   83G  117G  42% /
tmpfs           3.9G  5.5M  3.9G   1% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
tmpfs           785M  2.5M  782M   1% /run/user/1000
                                           
```

> The output shows the amount of space used by different drives. Add the **`-h`** tag to make the output in human-readable format (kilobytes, megabytes, and gigabytes).

## 16. The ( `du` ) Command
The **`du`** (**d**isk **u**sage) command helps show how much space a file or directory takes up. Run the command without any parameters:

| Syntax | du -h |
| ------ | ----- |
> The output shows the amount of space used by files and directories in the current directory. The size displays in blocks, and adding the **`-h`** tag changes the measure to human-readable format.


## 17. The ( `head` ) Command

Use the [head command](https://phoenixnap.com/kb/linux-head) to truncate long outputs. The command can [truncate files](https://phoenixnap.com/kb/linux-truncate-file), for example:

| Syntax                                           | head `<filename>`   |
| ------------------------------------------------ | ------------------- |
| pipe **`head`** to a command with a long output: | `<command>` \| head |
| See the first ten lines of `du` Command          | du \| head          |
> The output shows the first ten lines instead of everything.

## 18. The ( `tail` ) Command
The [Linux tail command](https://phoenixnap.com/kb/linux-tail) does the opposite of **`head`**. Use the command to show the last ten lines of a file:

| Syntax                                           | head `<filename>`   |
| ------------------------------------------------ | ------------------- |
| pipe **`tail`** to a command with a long output: | `<command>` \| tail |
| See the last ten lines of `du` Command           | du \| tail          |
> The output shows the last ten lines instead of everything.
## 19. The ( `diff` ) Command
The [diff command](https://phoenixnap.com/kb/linux-diff) (**diff**erence) compares two files and prints the difference.

| Syntax  | diff `<file-01>` `<file-02>`     |
| ------- | -------------------------------- |
| Example | diff `hello-01.txt hello-02.txt` |
> Developers often use **`diff`** to compare versions of the same code.
> Note : if there is no difference found in the file. It would return nothing.

## 20. The ( `tar` ) Command
The [tar command](https://phoenixnap.com/kb/tar-command-in-linux) (**t**ape **ar**chiver) helps archive, compress, and [extract archived files](https://phoenixnap.com/kb/extract-tar-gz-files-linux-command-line).
The command manages and creates files known as **tarballs**, which often appear during installation processes. The options provide different functionalities depending on the task.

## 21. The ( `chmod`) Command
Use the **`chmod`** (**ch**ange **mod**e) command to change file and directory permissions. The command requires setting the permission code and the file or directory to which the permissions apply.

| Syntax | chmod `<permission>` `<file or directory>` |
| ------ | ------------------------------------------ |


The permission is a number code consisting of three numbers:

- The first number is the permission of the current user (owner).
- The second number is the permission for the group.
- The third number is permissions for everyone else.

For example, to change the file permissions for a test.txt file so anyone can read, write, and execute, run:

| Example | `chmod 777 file.txt` |
| ------- | -------------------- |

> **Note:** Allowing anyone to read, write, and execute files is considered a bad security practice. Implement [privileged access management](https://phoenixnap.com/blog/privileged-access-management) to maximize security on your system

## 22. The ( `chown` ) Command
The [chown command](https://phoenixnap.com/kb/linux-chown-command-with-examples) (**ch**ange **own**ership) changes the ownership of a file or directory. To transfer ownership, use the following command as sudo:


| Syntax  | ````sudo chown <new owner name or UID> <file or directory>```` |
| ------- | -------------------------------------------------------------- |
| Example | `sudo chown bob file.txt`                                      |
> Configuring ownership is a common task during installations. The **`chown`** command allows daemons and processes to access files during setup.

## 23. The ( `ps`) Command
The **`ps`** (process status) command [lists processes](https://phoenixnap.com/kb/list-processes-linux) currently running on the system. Every task creates a single or multiple processes running in the background.
```bash
┌──(cipher㉿watchdog)-[~/TEST]
└─$ ps
    PID TTY          TIME CMD
 211414 pts/1    00:00:25 zsh
 348484 pts/1    00:00:00 ps
                                           
```

The output shows the process ID (PID), the terminal type, CPU time usage, and the command that started the process

## 24. The ( `top` ) Command
The [top command](https://phoenixnap.com/kb/top-command-in-linux) (**t**able **o**f **p**rocesses) is an extended version of the **`ps`** command. Run the command without any options to see the result:

![[Pasted image 20240620200921.png]]
> The output lists all running processes in [real-time](https://phoenixnap.com/glossary/real-time-technology). To exit the viewer, press **CTRL**+**C**.

## 25. The ( `kill`) Command
Use the **`kill`** command to [terminate an unresponsive process](https://phoenixnap.com/kb/how-to-kill-a-process-in-linux).

| Syntax | ```kill <signal option> <process ID>``` |
| ------ | --------------------------------------- |
There are sixty-four different signal numbers, but the most commonly used are:

| Signal-Number | What does it do ?                              |
| ------------- | ---------------------------------------------- |
| **`-15`**     | saves all progress before closing the process. |
| **`-9`**      | forces a stop immediately.                     |

> The process ID (PID) is unique for every program. Use the **`ps`** or **`top`** command to find the PID of a process.

## 26. The (`ping`) Command
Use the [ping command](https://phoenixnap.com/kb/linux-ping-command-examples) (**p**acket **in**ternet **g**roper) to check internet connectivity. 

| Syntax         | ping `<option>` `<ip-address>` |
| -------------- | ------------------------------ |
| Send 3 Request | ping -c 3 google.com           |

The tool is valuable in troubleshooting networking issues. Add an address to test how it works, for example:
```
┌──(cipher㉿watchdog)-[~/TEST]
└─$ ping -c 4 google.com  
PING google.com (142.250.183.142) 56(84) bytes of data.
64 bytes from bom07s31-in-f14.1e100.net (142.250.183.142): icmp_seq=1 ttl=54 time=75.0 ms
64 bytes from bom07s31-in-f14.1e100.net (142.250.183.142): icmp_seq=2 ttl=54 time=123 ms
64 bytes from bom07s31-in-f14.1e100.net (142.250.183.142): icmp_seq=3 ttl=54 time=76.1 ms
64 bytes from bom07s31-in-f14.1e100.net (142.250.183.142): icmp_seq=4 ttl=54 time=62.2 ms

--- google.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3003ms
rtt min/avg/max/mdev = 62.249/84.142/123.220/23.209 ms
 
```

> The output shows the response time from the website. Press **CTRL**+**C** to stop the ping. If no response shows, there's a problem connecting to the host.

## 27. The ( `wget`) Command
The [wget command](https://phoenixnap.com/kb/wget-command-with-examples) ([WWW](https://phoenixnap.com/glossary/world-wide-web-definition) **get**) is used to download files from the internet. Use the following syntax to download a file:

| Syntax | wget `<URL>` |
| ------ | ------------ |
> The command is robust and can continue downloads in unstable and slow networks.

## 28. The (`uname`) Command
Use the [uname command](https://phoenixnap.com/kb/uname-linux) ([**U**nix](https://phoenixnap.com/glossary/what-is-unix) **name**) to print system information. Add the **`-a`** option to print a complete overview:
```
┌──(cipher㉿watchdog)-[~]
└─$ uname -a
Linux watchdog 6.4.0-kali3-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.4.11-1kali1 (2023-08-21) x86_64 GNU/Linux

```
The output shows the kernel version, OS, processor type, and other helpful information about the system.
## 29. The ( `history`) Command
The terminal session keeps a history log of commands. To see the list, use the [history command](https://phoenixnap.com/kb/linux-history-command):

| Syntax | history |
| ------ | ------- |


```
# Displays last 10 Commands                                           
┌──(cipher㉿watchdog)-[~]
└─$ history | tail
 2105  ping google.in
 2107  ping -a -c 3 google.in
 2108  ping -c 4 google.com
 2110  man ping
 2111  clear
 2113  man uname
 2114  uname -o
 2115  cd
 2116  uname -a
 2117  history | head
   
```

## 30. The (`hostname`) Command
To check the [DNS](https://phoenixnap.com/kb/what-is-domain-name-system-works) name of the current machine, use the [hostname command](https://phoenixnap.com/kb/linux-hostname-command):
```
┌──(cipher㉿watchdog)-[~]
└─$ hostname
watchdog
```
The hostname shows in the terminal as a result. 
Advanced features include [changing the hostname](https://phoenixnap.com/kb/ubuntu-20-04-change-hostname), viewing and changing the system's [domain](https://phoenixnap.com/glossary/what-is-a-domain), and checking the [IP address](https://phoenixnap.com/kb/how-to-find-ip-address-linux)

## 31. The (`useradd`) Command
The **`useradd`** command [creates a new user on a Linux system](https://phoenixnap.com/kb/linux-user-create). Since adding new users requires making changes to system files, add the **`sudo`** command to enable access.

| This  command creates a non-login user. | ```sudo useradd <username>``` |
| --------------------------------------- | ----------------------------- |
> Additional setup is necessary to activate the user as administrative account fully.

## 32. The ( `userdel`) Command
Use the **`userdel`** ( **user** **del**ete ) command to remove a user from the system. Add **`sudo`** to enable the elevated privileges

## 33. The (`file`) Command
The [file command](https://phoenixnap.com/kb/linux-file-command) provides information about a file, printing the file type and the contents type.

| Syntax | file `<put-any-file-here>` |
| ------ | -------------------------- |
```
┌──(cipher㉿watchdog)-[~/TEST]
└─$ file hello1.txt       
hello1.txt: ASCII text
```
> The command does not take into account the file's extension. Instead, **`file`** performs testing on the file contents to determine the type.

## 34. The ( `wc`) Command
The [wc command](https://phoenixnap.com/kb/wc-linux) (**w**ord **c**ount) counts the number of lines, words, and [bytes](https://phoenixnap.com/glossary/what-is-a-byte) in a file. Provide a filename to count the elements in the file:

| Syntax | ```wc <filename>``` |
| ------ | ------------------- |
## 35. The ( `whoami`) Command
Use the [whoami command](https://phoenixnap.com/kb/whoami-linux) to show the currently logged-in user for the shell session:
```
┌──(cipher㉿watchdog)-[~/TEST]
└─$ whoami          
cipher
```
> The name of the effective user prints to the screen. Use the command in [Bash scripts](https://phoenixnap.com/kb/write-bash-script) to show which user is running a script

## 36. The ( `ip` ) Command
The [ip command](https://phoenixnap.com/kb/linux-ip-command-examples) contains many useful networking functionalities. For example, show the private IP address of the machine with:
![[Pasted image 20240620205811.png]]
The command offers other networking functions, such as IP and routing table management.

## 37. The ( `apt` ) Command
[Package managers](https://phoenixnap.com/glossary/what-is-a-package-manager) help install, delete, and manage software packages on Linux systems. Different [distributions of Linux](https://phoenixnap.com/glossary/what-is-a-linux-distribution) use distinct package managers.

| For Ubuntu | apt install `<package-name>` |
| ---------- | ---------------------------- |
## 38. The ( `passwd`) Command
Use the [passwd command](https://phoenixnap.com/kb/passwd-command-in-linux) to alter your password from the terminal. Run without any parameters:

![[Pasted image 20240620210053.png]]
> The command also helps create a login for a new user added through **`useradd`**. Changing another account's password requires elevated privileges.

## 39. The (`mount`) Command
The [mount command](https://phoenixnap.com/kb/linux-mount-command) allows attaching additional devices to the file system.

| mount -t `<type>` `<device>` `<directory>` |
| ------------------------------------------ |
> Use the command to mount ISO files, USB drives, [NFS](https://phoenixnap.com/kb/ubuntu-nfs-server), etc

## 40. The ( `reboot` ) Command
he **`reboot`** command [restarts the system immediately from the terminal](https://phoenixnap.com/kb/restart-linux-using-command-prompt). First, save changes to all files and then run:

| reboot |
| ------ |
> The system reboots instantly.

## 41. The (`which`) Command
The [which command](https://phoenixnap.com/kb/which-command-linux) shows the path of an executable program (command)

| which `<put-any-command-here>` |
| ------------------------------ |
```
┌──(cipher㉿watchdog)-[~/TEST]
└─$ which cat        
/usr/bin/cat
```
> The output shows the location of the command. Use **`which`** to troubleshoot installed programs that do not run.

**Note:** Check out our guide on [adding directories to PATH](https://phoenixnap.com/kb/linux-add-to-path).

## 42. The ( `nano` ) Command
GNU nano (**N**ano's **ano**ther editor) is a keyboard-oriented [Linux text editor](https://phoenixnap.com/kb/best-linux-text-editors-for-coding). You can [use Nano](https://phoenixnap.com/kb/use-nano-text-editor-commands-linux) to make a new file or open an existing one by running:


| nano `<any-text-file-here>` |
| --------------------------- |
The editor automatically opens, allowing you to append text or code to the file

| Shortcut | What does it do ? |
| -------- | ----------------- |
| CTRL + X | To Save and Close |
| CTRL + O | To Save           |
| CTRL + K | Select Text & Cut |
| CTRL + U | Paste.            |

## 43. The ( `whatis`) Command4

The **`whatis`** command is a quick way to determine what a command does. Add it as a prefix to any command, for example:

| whatis `<any-command-here>` |
| --------------------------- |

![[Pasted image 20240620211345.png]]






## Sources
1. https://phoenixnap.com/kb/linux-commands
2. https://phoenixnap.com/kb/dangerous-linux-terminal-commands
3. https://phoenixnap.com/kb/uname-linux#ftoc-heading-4