#os/linux/basics

![[index-of-linux-basics-for-hacker]]

To get the most from your Linux hacking system, you need to understand environment variables and be adept at managing them for optimal performance, convenience, and even stealth.

Technically, there are two types of variables: shell and environment

| Environment variables | Environment variables are process-wide variables built into your system and<br><br>interface that control the way your system looks, acts, and “feels” to the<br><br>user, and they are inherited by any child shells or processes.                          |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Shell variables,      | Shell variables, on the other hand, are typically listed in lowercase and are only valid in the shell they are set in. To avoid over-explanation, I just cover some of the most basic and useful skills for environment and shell variables in this chapter. |
|                       |                                                                                                                                                                                                                                                              |


Variables are simply strings in key-value pairs. Generally, each pair will flook like KEY=value.

### 1. What is an environment variable

Environment variables are process-wide variables built into your system and

interface that control the way your system looks, acts, and “feels” to the

user, and they are inherited by any child shells or processes

Variables are simply strings in key-value pairs. Generally, each pair will

look like **KEY=value.** In cases where there are multiple values, they will look

like **KEY=value1:value2.**
### 2. Listing variables

1. Printing specific variables
2. Echo command
3. Creating variables
4. Creating persistent user variables
5. Creating persistent global variables
6. Removing variables

Sources

1. [https://www.youtube.com/watch?v=yM8v5i2Qjgg](https://www.youtube.com/watch?v=yM8v5i2Qjgg)


## Find Variable Files

```bash
┌──(cipher㉿watchdog)-[~]
└─$ find /etc -type f -name environment

find: ‘/etc/ipsec.d/private’: Permission denied

/etc/postgresql/15/main/environment

find: ‘/etc/redis’: Permission denied

find: ‘/etc/openvas/gnupg’: Permission denied

find: ‘/etc/polkit-1/localauthority’: Permission denied

find: ‘/etc/polkit-1/rules.d’: Permission denied

find: ‘/etc/vpnc’: Permission denied

find: ‘/etc/ssl/private’: Permission denied

/etc/environment

┌──(cipher㉿watchdog)-[~]
└─$ find $HOME -type f -name .bashrc

/home/cipher/.bashrc
```

