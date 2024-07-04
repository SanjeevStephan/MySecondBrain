
#os/linux/terminology/terminal
#collections-of/manuals/terminal

### Open the Terminal with Keyboard Shortcut
#os/linux/shortcut-keys/terminal/launch-terminal
You can [open the terminal in Ubuntu](https://itsfoss.com/open-terminal-ubuntu/) by looking for it in the system menu. 
However, my favorite way is to use the Ctrl+Alt+T [keyboard shortcut in Ubuntu](https://itsfoss.com/ubuntu-shortcuts/).

| `Ctrl+Alt+T` |
| ------------ |
### Terminal vs shell vs prompt vs command line

![[Pasted image 20240621065104.png]]

| Title    | Descripton                                                                                                                                                                                                                                                                  |
| -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Terminal | The terminal is a graphical application that runs a shell by default.                                                                                                                                                                                                       |
| Shell    | Shell is difficult to visualize separately from the terminal. The terminal runs a shell, usually Bash shell by default in Ubuntu. Like terminals, there are various shells as well. Bash is the most popular of them all and the default shell on most Linux distributions. |
| Prompt   | Prompt is what you see before the space where you type the commands. There is no set standard for the prompt.In the Ubuntu terminal, prompt gives you some information which you’ll see in detail in the later sections of this article.                                    |
| Commands | The commands you type are interpreted by the shell.                                                                                                                                                                                                                         |
The Command line is not something specific to Linux. Every operating system has a command line interface. Many programming languages have command line interfaces. It’s a term for the interface where you can run and execute commands.


### Understanding the prompt
You know it by now. What you see before the space where you type the command is called the prompt. It is configurable and looks different in different distributions, terminal applications and shells.

Ubuntu terminal has configured the prompt to show you a few things. You can get the following information at a glance:


| Title                           | Command  |
| ------------------------------- | -------- |
| User name                       | whoami   |
| Hostname (name of the computer) | hostname |
| Current working directory       | pwd      |
|                                 |          |

A few more things you may wonder about.

The colon (:) in the prompt is a separator to distinguish between the hostname and the current location.

Tilde (~) means the home directory of the present user.

| For regular users | the prompt ends with dollar ($) symbol |
| ----------------- | -------------------------------------- |
| For the root user | it ends with pound or hash (#) symbol. |
|                   |                                        |
![[Pasted image 20240621072831.png]]

> Did you notice that when I switched to the root user, the command prompt looked different without any colors? This is another reminder that prompt is not a standard and is configured explicitly. For regular users, Ubuntu has a different configuration of the prompt than the root.


### Directory and files
The two terms you hear the most in Linux are directory and files.

You probably know what a file is but you may get confused with the term ‘directory’. The directory is nothing but a folder. It keeps files and folders inside it.

You can go inside the directories but you cannot enter files. You can read files of course.


### Path: Absolute and relative
The [directory structure in Linux resembles](https://linuxhandbook.com/linux-directory-structure/?ref=itsfoss.com) the root of a tree. Everything starts at root and spreads out from there.

If you have to access a file or directory, you need to tell how to reach its location by providing its ‘path’. This path is composed of directory names and separators (/). If a path starts with / (i.e., root), it is an absolute path otherwise it is a relative path.

![[Pasted image 20240621073324.png]]
The absolute path starts from the root and can be easily referenced from anywhere in the system. The relative path depends upon your current location in the directory structure.

![[Pasted image 20240621073425.png]]

If you are in the location /home/abhishek which has a directory named scripts containing a file my_script.sh and you want the path for this file:

| its absolute path will be | ``home/abhishek/scripts/my_script.sh`` |
| ------------------------- | -------------------------------------- |
| Its relative path will be | ```scripts/my_script.sh```             |
![[Pasted image 20240621073642.png]]


##  TheDot-Notations ( `.`) and ( `..`)

You may often come across (`.`) and (`..`) notations while using the Linux terminal.

| Single dot (.) means the current directory. |
| ------------------------------------------- |
| Single dot (.) means the current directory. |
You’ll often use the double dot (..) in the relative path or for changing the directory. Single dot (.) is also used in relative path; more importantly, you can use it in the commands to specify the current locations.

![[Pasted image 20240621073854.png]]

### Understand the command structure

A typical Linux command consists of a command name followed by options and arguments.


| `command [options] argument` |
| ---------------------------- |
Option, as the name suggests, are optional. When used, they might change the output based on their properties.

For example, the cat command is used for viewing files. You can add option -n, which will also display line numbers.

Options are not standardized. Usually, they are used as a single letter with single dash (-). They may also have two dashes (--) and a word.

Same options may have different meanings in a different command. If you use -n with head command, you specify the number of lines you want to see, not the lines with numbers.

![[Pasted image 20240621074441.png]]

### Getting help

As you start using commands, you may remember some of the options of frequently used commands but it is simply impossible for you to remember all the options of any command.

Why? Because a single command may have more than ten or twenty options.

So, what do you do when you cannot recall all the options? You take help.

Every standard Linux command has a quick help page that can be accessed with -h or –help or both.


| `<command-name> --help` |
| ----------------------- |
| `<command-name> -h`     |

It gives you a quick glimpse of the command syntax, common options with their meaning, and command examples in some cases.

![[Pasted image 20240621074933.png]]
If you need more help, you can refer to the [manpage](https://itsfoss.com/linux-man-page-guide/) i.e. manual of a command:

| man `<command-name>` |
| -------------------- |

It goes into all the details and could be overwhelming to read and understand. Alternatively, you can always search on the internet for ‘examples of xyz commands in Linux’.


### Linux is case-sensitive

Linux is case-sensitive. Everything you type in the terminal is case-sensitive. If you do not take that into account, you’ll often run into [bash: command not found](https://itsfoss.com/bash-command-not-found/) or file not found errors.

![[Pasted image 20240621075122.png]]

In the home directory, you have all the folders' names starting with the upper case. If you have to switch to the Documents directory, keep the first letter as D and not d. Otherwise, the terminal will complain.



You can have two separate files named `file.txt` and `File.txt` because file and File are not the same for Linux.


### Running the Scripts
You can [run a shell script](https://itsfoss.com/run-shell-script-linux/) in following ways : 

| by specifying the shell:                       | ```bash script.sh``` |
| ---------------------------------------------- | -------------------- |
| Or you can execute the shell script like this: | ``./script.sh``      |
The second one will only work when the file has the execute permission. More on [Linux file permission here](https://linuxhandbook.com/linux-file-permissions/?ref=itsfoss.com).

![[Pasted image 20240621075531.png]]

## Use tab completion instead of typing it all
The Ubuntu terminal is pre-configured with tab completion. This means that if you start writing something in the terminal and then hit tab, it tries to automatically complete it or provide options if there is more than one possible match.

It works for both commands as well as arguments and filenames.
![[Pasted image 20240621075909.png]]
This saves a great time because you don’t have to write everything completely.


## Ctrl+C and Ctrl+V is not for copy pasting in terminal


Ctrl+C, Ctrl+V might be the ‘universal’ keyboard shortcuts for copy paste but it doesn’t work in the Linux terminal.

Linux inherits a lot of stuff from UNIX and in UNIX, Ctrl+C was used for stopping a running process.

Since the Ctrl+C was already taken for stopping a command or process, it cannot be used for copy-paste any more.

## You can surely copy paste in the terminal
#os/linux/shortcut-keys/terminal/copy-paste


In the Ubuntu terminal, the default keyboard shortcut

| for copying | Ctrl+Shift+C; |
| ----------- | ------------- |
| for pasting | Ctrl+Shift+V  |
>Note 
* You can use Ctrl+C to copy text and commands from outside the terminal (like a web browser) and paste it using Ctrl+Shift+V. 
* Similarly, you can highlight the text and use Ctrl+Shift+C to copy the text from the terminal and paste it to an editor or other applications using Ctrl+V.

## Avoid using Ctrl+S in the terminal
#os/linux/shortcut-keys/terminal/avoid-using-CTRL-plus-S

Another common mistake beginners do is to use the ‘universal’ Ctrl+S keyboard shortcut for save. If you use Ctrl+S in the terminal, your terminal ‘freezes’.

This comes from legacy computing where there was no scope for scrolling back up. Hence, if there were many output lines, Ctrl+S was used to stop the screen so that text on the screen could be read.

| Command  | What does it Do ?   |
| -------- | ------------------- |
| Ctrl + S | Freezes the Screen  |
| Ctrl + Q | Unfreeze the Screen |

You can unfreeze your terminal with Ctrl+Q. But again, avoid using Ctrl+S in the terminal.

## Pay attention to $ and <> in command examples


If you are referring to some online tutorial or documentation, you’ll see some command examples with text inside <>. This indicates that you need to replace the content along with < and > with a suitable value.

For example, if you see a command like this:

| `grep -i <search_term> <file_name>` |     |
| ----------------------------------- | --- |
|                                     |     |

You should replace the <search_term> and <file_name> with their respective actual values.

It is an indication that the command is just an example and you have to complete it with actual values.

Another thing to note here is that some tutorials show command examples that start with $ like this:
![[Pasted image 20240621080541.png]]
This is a way for them to indicate that it is command (not command output). But many new Linux users copy the preceding $ along with the actual command and when they paste it in the terminal, it throws an error, obviously.

So, when copying some commands, don’t copy the $ if it is at the beginning. You should also avoid copying random commands for random websites specially when you do not understand what it does.

Since you are reading about copying commands, when you see commands in multiple lines together, you should copy one line at a time and run them one by one:

![[Pasted image 20240621080628.png]]

### You can run multiple commands at once
You can [run multiple commands at once](https://itsfoss.com/run-multiple-commands-linux/) without user intervention. You might have seen it already as an Ubuntu user in the form of this command:

````
sudo apt update && sudo apt upgrade
````

There are three different ways to combine commands in the terminal:

|     |                                |                                                  |
| --- | ------------------------------ | ------------------------------------------------ |
| ;   | `<Command 1>` ; `<Command 2>`  | Run command 1 first and then command 2           |
| &&  | `<Command 1>` && `<Command 2>` | Run command 2 only if command 1 ends sucessfully |
| \|  | `<Command 1>` \| `<Command 2>` | Run command 2 only if command 1 fails            |

### Stop a running Linux command
#os/linux/shortcut-keys/terminal/stop-a-running-command

If a Linux command is running in the foreground, i.e., it is showing output or you cannot enter any other command, you can stop it using the Ctrl+C keys.

So, the next time you see a command like top or ping running continuously and you want the terminal control back, just use these two keys:

| `Ctrl+C` |
| -------- |
### Clear the terminal
When I find that my screen is too cluttered with different kinds of output, I clear the terminal screen before starting some other work. It is just a habit but I find it helpful.


| To clear the terminal, use the command: | `clear` |
| --------------------------------------- | ------- |
### Exiting the terminal
You could do that but the proper way to exit a terminal is to use the exit command:

| `exit` |
| ------ |
You may also use the keyboard shortcut `Ctrl+Shift + W` for Ubuntu terminal.


### Source
1. https://itsfoss.com/basic-terminal-tips-ubuntu/
2. https://itsfoss.com/linux-command-tricks/
3. https://itsfoss.com/essential-ubuntu-commands/
4. 