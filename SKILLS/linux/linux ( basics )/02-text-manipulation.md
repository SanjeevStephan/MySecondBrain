#os/linux/basics/text-manipulation
`#ebook/category/hacking/linux-basics-for-hacker/02-text-manipulation`

![[index-of-linux-basics-for-hacker]]


# Viewing Files
| Title                    | Command                              | Description                               |
| ------------------------ | ------------------------------------ | ----------------------------------------- |
| Viewing Files            | cat smb.conf                         |                                           |
|                          | head smb.conf                        | Display only first 10 lines by default    |
|                          | tail smb.conf                        | Display only last 10 lines by default     |
|                          | head -20 smb.conf                    | Display only first 20 lines               |
| Numbering the Lines      | nl anytextfile.txt                   | Display the file along with numbers-lines |
| Filtering Text with grep | cat /etc/samba/smb.conf \| grep path |                                           |
|                          |                                      |                                           |

# Basics Commands for Viewing Text Files

| Command | Description                                                                                                                                                        | Syntax                                             |
| ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------- |
| cat     | The Most basic text display command is probably [ cat ]                                                                                                            | cat /etc/os-release<br><br>cat /etc/samba/smb.conf |
| head    | View the Begining of a file,this command displays the first 10 lines of a file.                                                                                    | head /etc/samba/smb.conf                           |
|         | if you want to see more or fewer than the default 10 lines, enter the quantity you want with the dash ( - ) switch after the call to head and before the filename. | head -20 /etc/samba/smb.conf                       |
| tail    | The Tail command is similar to the head command, but it's used to view the last lines of a file.                                                                   | tail /etc/samba/smb.conf                           |
| nl      | Display a file with line numbers, we use the nl ( number lines ) command                                                                                           | nl /etc/samba/smb.conf                             |
| more    | The more command displays a page of a file at a time and lets you page down through it using the enter key.                                                        |                                                    |
| less    |                                                                                                                                                                    |                                                    |

# Filtering Text with grep

|grep|filter the content of a file for display.|cat /etc/samba/smb.conf \| grep samba|
|---|---|---|

# Using ‘sed’ to Find and Replace

|sed|The sed command lets you search for occurrences of a word or a text<br><br>pattern and then perform some action on it. sed operates like the<br><br>Find and Replace function in Windows.

```bash
sed s/mysql/MySQL/g /etc/snort/snort.conf > snort2.conf
```

The s command performs the substitution:

you first give the term you are searching for (mysql ) and then the term you want to replace it with (MySQL),

separated by a slash (/). The g flag tells Linux that you want the replacement performed globally.

Then the result is saved to a new file named snort2.conf.

```
sed s/mysql/MySQL/2 snort.conf > snort2.conf
```

For instance, if you want to replace only the second occurrence of the word mysql,

simply place the number of the occurrence (in this case, 2) at the end of the command:


## Find and Replace.


```

Basic-Syntax  
└─>  sed s/<text-to-replace>/<text-to-be-replaced-with>/g old-file.txt> new-file.txt  


Example  
└─> sed s/path/HELLO/g smb.conf > new-smb.conf  
└─> sed s/HELLO/path/2 smb.conf > new-smb.conf  


```


```bash
Explaination  
└─>      sed       # Command to repalce   
		  s        # The ( s ) flag means search  
		  g        # The (g) flag means global-repalce  
		  >        # Redirect the output to new-file.txt  
		  2        # Here the number  means it only affects the second occurances of HELLO
```

## Displaying and Filtering with less

The less command is very similar to more, but with additional functionality.
With less, you can not only scroll through a file at your leisure, but you can also filter it for terms
If you press the forward slash (/) key, less will let you
search for terms in the file.
    
    Read Text files one-page at a time.
    
```bash
└─> less smd.conf  
  
/path    # forward-slash ( / ) followed by string to search that string  
	n    # press ( n ) to go to next occurences  
	p    # press ( p ) to go to previous occurances.
	q    # press ( q ) to quit [ Exit out of the text-file ]

```


This will immediately take you to the first occurrence of output and highlight it.

You can then look for the next occurrence of output by typing




## Exercise
1. Navigate to /usr/share/metasploit-framework/data/wordlists. This is a
directory of multiple wordlists that can be used to brute force passwords
in various password-protected devices using Metasploit, the most popular
pentesting and hacking framework.
2. Use the cat command to view the contents of the file password.lst.
3. Use the more command to display the file password.lst.
4. Use the less command to view the file password.lst.
5. Now use the nl command to place line numbers on the passwords in
password.lst. There should be around 88,396 passwords.
6. Use the tail command to see the last 20 passwords in password.lst.
7. Use the cat command to display password.lst and pipe it to find all the
passwords that contain 123.