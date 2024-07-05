#os/linux/basics


![[index-of-linux-basics-for-hacker]]


A hacker—needs to under­stand how to manage their processes to optimize their systems. For example, once a hacker takes control of a target system, they might want to find and stop a certain process, like an antivirus application or firewall.

To do so, the hacker would first need to know how to find the process. The hacker might also want to set a scanning script to run periodically to find vul­nerable systems, so we’ll also look at how to schedule such a script.

| S.No | What You'll Learn Today                                                                                                  |
| ---- | ------------------------------------------------------------------------------------------------------------------------ |
| 1.   | view and find processes and how to discover which processes are using the most resources.                                |
| 2.   | manage processes byrunning them in the background, prioritizing them, and killing them if necessary (no blood involved). |
| 3.   | schedule processes to run on specified days and dates and at specific times.                                             |

|Command|What Does it Do ?|
|---|---|
|ps|The Linux kernel, the inner core of the operating system that con­trols nearly everything, assigns a unique process ID (PID) to each process sequentially, as the processes are created. When working with these processes. In Linux, you often need to specify their PIDs, so it is far more important to note the PID of the process than the name of the process.|
|ps aux|Running the ps command with the options aux will show all processes running on the system for all users|
|top|dis­plays the processes ordered by resources used, starting with the largest.|
||op refreshes the list dynamically—by default, every 3 seconds.|
||System administrators often keep top running in a terminal to monitor use of process resources. As a hacker, you may want to do the same, espe­cially if you have multiple tasks running on your system|
|||

# Filtering by Process Name

|Syntax Commands|Steps to Follow|
|---|---|
|msfconsole|First Launch Any Program ( eg - Metasploit exploitation framework )|
|ps aux \| grep msfconsole|Now, use the ps aux command and then pipe it (\|) to grep looking for the string msfconsole.|
|||

```bash
┌──(cipher㉿watchdog)-[~]  
└─$ ps aux                    
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND  
cipher    328933 44.8 39.8 1518748 734232 pts/0  Sl+  01:06   3:18 ruby /usr/bin/msfconsole  
cipher    334474  0.0  0.1   6344  2304 pts/3    S+   01:13   0:00 grep --color=auto msfconsole  
```

# Managing Processes

Hackers often need to multiprocess, and an operating system like Kali is ideal for this.

The hacker may have a port scanner running while running a vulnerability scanner and an exploit simultaneously.

This requires that the hacker manage these processes efficiently to best use system resources and complete the task

|Command|What does it Do ?|
|---|---|
||Changing Process Priority with nice|
||The values for nice range from −20 to +19, with zero being the default value (see Figure 6-1).<br><br>A high nice value translates to a low priority, and<br><br>A low nice value translates to a high priority (when you’re not being so nice to other users and processes). When a process is started, it inherits the nice value of its parent process.|
|nice -n -10 /bin/slowprocess|This command would increment the nice value by -10, increasing its ­priority and allocating it more resources.|
|nice -n 10 /bin/slowprocess|On the other hand, if we want to be nice to our fellow users and pro­<br><br>cesses and give slowprocess a lower priority, we could increment its nice value<br><br>positively by 10 :|

## Commonly Used Kill Signals

|Signal Name|Number for Option|Description|
|---|---|---|
|SIGHUP|1|This is known as the Hangup (HUP) signal. It stops the designated process and restarts it with the same PID.|
|SIGINT|2|This is the Interrupt (INT) signal. It is a weak kill signal that isn’t guaranteed to work, but it works in most cases.|
|SIGQUIT|3|This is known as the core dump. It terminates the process<br><br>and saves the process information in memory, and then it<br><br>saves this information in the current working directory to<br><br>a file named core. (The reasons for doing this are beyond<br><br>the scope of this book.)|
|SIGTERM|15|This is the Termination (TERM) signal. It is the kill com-<br><br>mand’s default kill signal.|
|SIGKILL|9|This is the absolute kill signal. It forces the process to<br><br>stop by sending the process’s resources to a special<br><br>device, /dev/null.|

# Killing Processes

Using the top command, you can identify which processes are using too many resources;

|Kill Command|What does it do ?|
|---|---|
|kill -1 6996|If you just want to restart a process with the HUP signal, enter the -1 option with kill|
|kill -9 6996||
||If you don’t know a process’s PID, you can use the killall command to<br><br>kill the process. This command takes the name of the process, instead of<br><br>the PID, as an argument.|
|killall -9 rogueprocess|killall command to kill the process|

# Running Processes in the Background

All commands that run are executed from within that shell, even if they run from the graphical interface.

When you execute a command, the shell waits until the command is completed before offering another command prompt.

At times, you may want a process to run in the background, rather than having to wait for it to complete in that terminal.

|leafpad newscript &|To start the text editor in the background, just append an ampersand<br><br>(&) to the end of the command, like so -> it will return with the Proccess ID.|
|---|---|

# Moving a Process to the Foreground

If you want to move a process running in the background to the fore­

ground, you can use the fg (foreground) command. The fg command

requires the PID of the process you want to return to the foreground

|fg 1234|if you don’t know the PID, you can use the ps command to find it.|
|---|---|
