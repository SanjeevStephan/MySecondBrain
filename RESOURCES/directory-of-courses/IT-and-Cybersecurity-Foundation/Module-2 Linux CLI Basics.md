Upon completing this lab, you should be able to:

- Define Command Line Interface (CLI).
- Identify practical applications of the Linux CLI.
- Identify common Linux commands.
- Use the CLI to execute common Linux commands.
---


| Commands                                           | What Does it Do ?                                          |
| -------------------------------------------------- | ---------------------------------------------------------- |
| whoami                                             | Displays the name of the Current User                      |
| hostname                                           | Displays the name of the machine                           |
| pwd                                                | Display the current/present working directory              |
| cd ..                                              | Stands for Change Directory                                |
| cd ~                                               | Returns to Home Directory ( /home/cipher )                 |
| cd /                                               | Returns to Root Directory of Linux OS                      |
| ls                                                 | Displays the list of files and directory                   |
| ls -l                                              | Displays a long directory listing                          |
| ls -la                                             | Displays a long directory listing along with hidden-files  |
| touch anyfile.txt                                  | Creates file name ( anyfile.txt )                          |
| echo "This is A Simple Text File "  >> anyfile.txt | Appends the quoted text into the ( anyfile.txt ) file.     |
| cat anyfile.txt                                    | Displays the content of the ( anyfile.txt )                |
|                                                    | The cat command stands for con **cat** enate.              |
| file anyfile.txt                                   | Displays the file's type, even if a file has no extension. |
| mkdir TEST                                         | Creates a new directory with the name ( TEST )             |
| cp anyfile.txt TEST/                               | Copy ( anyfile.txt ) to the TEST Directory                 |
| ls -R                                              | Displays all files and folders under the TEST Directory.   |
| b                                                  |                                                            |
# ls -l

![[linuxcli_009.png]]

Notice that with the -l option, you can see important information about the directories and files in /home/cipher.

In the output, the "d" means that the object is a directory. 
Next are three sets of permissions. 
* Permissions are read (r), write (w), and execute (x). 
* A dash (-) means that a given permission is not set. 
* For example, r-x grants read and execute permission but not write. 
* The first set of three applies to a file or folder owner, the next set applies to the group, and the last set applies to everyone else. 
* Thus, for the /home/cipher/Desktop directory, 
	* user cipher has permission to read, write and execute, 
	* group cipher has permission to read and execute, and 
	* everyone else has permission to read and execute.

# ls -la

![[linuxcli_010.png]]

The -a option shows all files, including hidden files. 
* Notice the files that start with a dot (.)  These are hidden files. 
* Typically these files are used to manage terminal settings, collect command history, and other shell-related settings. 
* They are hidden to prevent users from making accidental changes to these important files and to keep the directory listing clean.


