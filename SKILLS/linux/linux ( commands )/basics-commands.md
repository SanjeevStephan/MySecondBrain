#os/linux/commands/basic-commands

# Basic Commands in Linux

| Title   | Description                                                                                                                                                                                                                                                                                                                                                                        | Syntax              |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- |
| pwd     | The present working directory (or print working directory) command, pwd, returns your<br><br>location within the directory structure.                                                                                                                                                                                                                                              |                     |
| whoami  | Checking Your Login with whoami                                                                                                                                                                                                                                                                                                                                                    |                     |
| cd      | Changing Directories with                                                                                                                                                                                                                                                                                                                                                          |                     |
| ls      | To see the contents of a directory (the files and subdirectories)                                                                                                                                                                                                                                                                                                                  |                     |
| ls -l   | To get more information about the files and directories, such as their<br><br>permissions, owner, size, and when they were last modified, you can add<br><br>the -l switch after ls (the l stands for long). This is often referred to as<br><br>long listing                                                                                                                      |                     |
| ls -R   | Display all the sub-folder files at the same time.                                                                                                                                                                                                                                                                                                                                 |                     |
| help    | Nearly every command, application, or utility has a dedicated help file in<br><br>Linux that provides guidance for its use                                                                                                                                                                                                                                                         | aircrack-ng --help  |
| man     | Most commands and applications have a<br><br>manual (man) page with more information, such as a description and syn-<br><br>opsis of the command or application                                                                                                                                                                                                                    | man aircrack-ng     |
| whereis | looking for a binary file, you can use the whereis command to<br><br>locate it                                                                                                                                                                                                                                                                                                     | whereis aircrack-ng |
| which   | returns the location of<br><br>the binaries in the PATH variable in Linux Environment                                                                                                                                                                                                                                                                                              | which aircrack-ng   |
| find    | search in any designated directory and<br><br>looking for a number of different parameters, including, of course, the file-<br><br>name but also the date of creation or modification, the owner, the group,<br><br>permissions, and the size.<br><br>Here’s the basic syntax for find<br><br>find directory options expression<br><br>Example<br><br>find / -type f -name apache2 |                     |
|         |                                                                                                                                                                                                                                                                                                                                                                                    |                     |
| grep    | The grep command is often used when output is piped from one command to another.<br><br>This is called piping, and we use the \| command to do it<br><br>ps aux \| grep apache2<br><br>here we piped the output from ps to grep and to find out whether the apache2 service is running,                                                                                            |                     |
| ps aux  | I want to see all the processes running on my Linux sys-<br><br>tem. In this case, I can use the ps (processes) command followed by the aux switches to specify which process information to display                                                                                                                                                                               |                     |

Navigating the Linux Filesystem

Navigating the filesystem from the terminal is an essential Linux skill. To get anything done, you need to be able to move around to find applications, files, and directories located in other directories. In a GUI-based system, you can visually see the directories, but when you’re using the command ine interface, the structure is entirely text based, and navigating the file­ system means using some commands.

You would use .. to move up one level.

You would use ../.. to move up two levels.

You would use ../../.. to move up three levels, and so on.

# Modifying Files and Directories

Once you’ve found your files and directories, you’ll want to be able to per-

form actions on them.

|Title|Description|Syntax\|Command|
|---|---|---|
|touch|Let’s create newfile with touch :|touch newfile|
|cat|To create a file, we follow the cat command with a redirect, denoted<br><br>with the > symbol, and a name for the file we want to create.<br><br>To exit and return to the prompt, I press ctrl-D|cat > hackingskills|
||To add, or append, more content to a file, you can use the cat command with a double redirect (>>), followed by whatever you want to add to the end of the file|cat >> hackingskills|
||Display the contents of that file|cat hackingskills|
|mkdir|To create a directory named newdirectory, enter the following<br><br>command|mkdir newdirectory|
|cd|To navigate to this newly created directory, simply enter this:|cd newdirectory|
|cp|To copy files, we use the cp command. This creates a duplicate of the file in<br><br>the new location and leaves the old one in place<br><br>kali > touch oldfile<br><br>kali > cp oldfile /root/newdirectory/newfile||
||The mv command can also be used to give an existing file a new name.<br><br>To rename newfile to<br><br>newfile2, you would enter the following:|mv newfile newfile2|
|rm|To remove a file, you can simply use the rm command,|rm newfile2|
||The command for removing a directory is similar to the rm command for<br><br>removing files which is ‘rmdir’ but<br><br>If you do want to remove a directory and its content all in one go, you can use the -r switch after rm|rm -r newdirectory|