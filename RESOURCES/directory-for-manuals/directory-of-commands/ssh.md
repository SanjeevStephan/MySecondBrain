#collections-of/manuals/ssh
#os/linux/commands/manuals/ssh
# Overview

> Generate SSH-Keys

| Generates a New SSH Key | **ssh-keygen -t rsa** |
| ----------------------- | --------------------- |

> Works on Linux

| TRANSFER | THE SSH-PUBLIC-KEY TO THE SERVER VIA `ssh-copy-id`              |
| -------- | --------------------------------------------------------------- |
| Syntax   | ssh-copy-id -i `<public-key>` `<username@ip-address-of-server>` |
| Example  | `ssh-copy-id -i id_rsa.pub stephanware@192.168.40.45`           |
> Works on Windows

| TRANSFER | THE SSH-PUBLIC-KEY TO THE SERVER VIA `scp`                              |
| -------- | ----------------------------------------------------------------------- |
| Syntax   | scp `<public-key>` `<username@ip-address-of-server>:<destination-path>` |
| Example  | `scp id_rsa.pub stephanware@192.168.40.45:~\.ssh`                       |
> Login { With Password }

| LOGIN   | INTO SEVER - SIMPLY USING USERNAME@IP_ADDRESS |
| ------- | --------------------------------------------- |
| SYNTAX  | `ssh <username@ip_address>`                   |
| EXAMPLE | `ssh stephanware@192.168.40.45`               |
> Login { With Private-Key }

| Syntax  | `ssh -i <private identity-file> user@host_ip`     |
| ------- | ------------------------------------------------- |
| Example | `ssh -i .\kali_linux_id_rsa cipher@192.168.40.95` |

# Generating New SSH-Keys


```bash
┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (C:\Users\Samst/.ssh/id_rsa): kali_linux_rsa
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in kali_linux_rsa
Your public key has been saved in kali_linux_rsa.pub
The key fingerprint is:
SHA256:+BGkZshf4YV1rO3sO8dEfCzSOK/M2hQ0s5xwSxoodyE samst@SuperUser
The key's randomart image is:
+---[RSA 3072]----+
|        Eo+..    |
|   . . +.= o.    |
|    o = * +o*+ . |
|     + = o.O=*= o|
|      o S .o*= o |
|       . .  o.o  |
|        .  +.+   |
|           o* o  |
|          ..o+   |
+----[SHA256]-----+

┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS> ls

    Directory: C:\Users\Samst\.ssh

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---          14-06-2024    14:15            568 authorized_keys
-a---          22-06-2024    08:40            292 config
-a---          20-05-2023    21:59           2610 ctsmartnet_hostinger_id_rsa
-a---          20-05-2023    21:59            576 ctsmartnet_hostinger_id_rsa.pub
-a---          29-03-2024    03:25           2602 id_rsa
-a---          29-03-2024    03:25            570 id_rsa.pub
-a---          23-06-2024    06:38           2602 kali_linux_rsa
-a---          23-06-2024    06:38            570 kali_linux_rsa.pub
-a---          22-06-2024    08:40           1727 known_hosts
-a---          14-06-2024    14:02           2018 known_hosts.backup
-a---          14-06-2024    15:14            790 known_hosts.old
-a---          29-03-2024    04:03             73 SSH-KEY-NOTE.md

┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh-copy-id -i .\kali_linux_rsa.pub cipher@192.168.40.95
ssh-copy-id: The term 'ssh-copy-id' is not recognized as a name of a cmdlet, function, script file, or executable program.
Check the spelling of the name, or if a path was included, verify that the path is correct and try again.

┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>scp .\kali_linux_rsa.pub cipher@192.168.40.95:~/.ssh
cipher@192.168.40.95's password:
kali_linux_rsa.pub                                                                                                100%  570    35.8KB/s   00:00

┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh cipher@192.168.40.95
Linux watchdog 6.4.0-kali3-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.4.11-1kali1 (2023-08-21) x86_64

The programs included with the Kali GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Kali GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sat Jun 22 09:18:04 2024 from 192.168.40.53

┌──(cipher㉿watchdog)-[~]
└─$ cd .ssh

┌──(cipher㉿watchdog)-[~/.ssh]
└─$ ls
authorized_keys  bkp  config  id_rsa  id_rsa.pub  known_hosts  rpi_server  rpi_server.pub  kali_linux_rsa.pub


┌──(cipher㉿watchdog)-[~]
└─$ cat kali_linux_rsa.pub >> authorized_keys


┌──(cipher㉿watchdog)-[~]
└─$ exit

┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh -i .\kali_linux_rsa.pub cipher@192.168.40.95


┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>nano .\config
┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh cipher
Linux watchdog 6.4.0-kali3-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.4.11-1kali1 (2023-08-21) x86_64

The programs included with the Kali GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Kali GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sun Jun 23 06:49:56 2024 from 192.168.40.53
┌──(cipher㉿watchdog)-[~]
└─$ exit
Connection to 192.168.40.95 closed.~

```

---
# SSH-LOGIN on Linux

#os/linux/how-to/setup/ssh-key
 SSH is ideal for managing remote systems because of its password-less option that uses keys instead of passwords, keeping system passwords safe. This article uses **ssh-copy-id**, a utility that greatly simplifies the procedure by copying the local host’s public key to the remote host’s authorized keys file and by verifying file permissions and ownership.

The following procedure configures password-less SSH:

  
```bash
	cd ~/.ssh
```

| STEP-1 | Generates a New SSH Key | **ssh-keygen -t rsa** |
| ------ | ----------------------- | --------------------- |

## Generate New-Keys Pairs on the Client Machine 
Start by generating a key pair ( for the server machine, which we'll a copy of our public key to the server machine. A key pair includes a .pub (public key) that you share with remote computers and a private key that you never share.

**Note:** When you generate these keys, **_do not_** enter a passphrase.

The following is an example of the command and subsequent prompt:

```bash
ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/home/cipher/.ssh/id_rsa): rpi_server
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in rpi_server
Your public key has been saved in rpi_server.pub
The key fingerprint is:
SHA256:NkcDuvsZb6BoJyTqtn+gOBiyF6hG0yIO6Ul2XJ9RdBk cipher@watchdog
The key's randomart image is:
+---[RSA 3072]----+
|        o. Eo    |
|       . o..     |
|      . . o      |
|     . o . .     |
| oo . o S .      |
|B*o=.  =.o       |
|&+*+......       |
|BB. +.o. +.      |
|+=oo.o  o..      |
+----[SHA256]-----+

```

## 2. Verify the Keys
Navigate to the directory in which you created the keys and verify that the process succeeded. The following is a continuation of the example.

```
┌──(cipher㉿watchdog)-[~/.ssh]
└─$
ls -l
total 28
-rw-r--r-- 1 cipher cipher  767 Mar 29 10:01 authorized_keys
-rw-r--r-- 1 cipher cipher    0 Sep  2  2023 config
-rw------- 1 cipher cipher 2602 Jun 29  2023 id_rsa
-rw-r--r-- 1 cipher cipher  569 Jun 29  2023 id_rsa.pub
-rw------- 1 cipher cipher  979 Jun 22 20:25 known_hosts
-rw------- 1 cipher cipher 2602 Jun 23 02:34 rpi_server
-rw-r--r-- 1 cipher cipher  569 Jun 23 02:34 rpi_server.pub
```

## Transfer it to the Server ( _from_linux_machine_ )
Copying the public key ( from linux machine to the destination linux system ) is easy using the Command `ssh-copy-id` . That is, in this case, copy it to the `raspberry pi server (rpi_server)` that you want password-less SSH access to, which in this example is `rpi_server`.


| STEP-2 | TRANSFER | THE SSH-PUBLIC-KEY TO THE SERVER VIA `ssh-copy-id`              |
| ------ | -------- | --------------------------------------------------------------- |
|        | Syntax   | ssh-copy-id -i `<public-key>` `<username@ip-address-of-server>` |
|        | Example  | `ssh-copy-id -i id_rsa.pub stephanware@192.168.40.45`           |

### Case-1 | Default-Key ( _id_rsa.pub_ )

```bash
┌──(cipher㉿watchdog)-[~/.ssh]
└─$ ssh-copy-id -i id_rsa.pub stephanware@192.168.40.45    
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "id_rsa.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
stephanware@192.168.40.45's password: 

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'stephanware@192.168.40.45'"
and check to make sure that only the key(s) you wanted were added.

 
```
> Now, Simply login into the Server using below Credentials

| STEP-3 | LOGIN   | INTO SEVER - SIMPLY USING USERNAME@IP_ADDRESS |
| ------ | ------- | --------------------------------------------- |
|        | SYNTAX  | `ssh <username@ip_address>`                   |
|        | EXAMPLE | `ssh stephanware@192.168.40.45`               |

---
### Case-2 | Custom-Key ( _rpi_server.pub_ )
```bash
┌──(cipher㉿watchdog)-[~/.ssh]
└─$
ssh-copy-id -i rpi_server.pub stephanware@192.168.40.45
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "rpi_server.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
stephanware@192.168.40.45's password:
```
> Enter the Server's Password ( used for login ) 
```bash
Number of key(s) added: 1

Now try logging into the machine, with:   "ssh -i rpi_server stephanware@192.168.40.45"
and check to make sure that only the key(s) you wanted were added.
```

## TRY TO LOGIN WITHOUT PASSWORD

| STEP-3 | LOGIN   | INTO THE SERVER USING SSH-PRIVATE KEY          |
| ------ | ------- | ---------------------------------------------- |
|        | Syntax  | `ssh -i <private-key> <username@ip-address>`   |
|        | Example | `ssh -i rpi_server stephanware@192.168.40.45 ` |


## Make Sure for Necessary Changes
If the public key is disabled, check the configuration file named **/etc/ssh/sshd** on the target computer for the following settings:  
```bash
RSAAuthentication yes 
PubkeyAuthentication yes
```


## A STEP FURTHER
Create a ( `config` ) file in the `~/.ssh` directory where all you 
* username, 
* ip-address
* which-port-to-connect-to
* preferred authentication-method
* and lastly which private-key to use to connect to the server

of every machine you remote ssh to are stored in one place.

```java
Host rpi
        User stephanware
        Hostname 192.168.40.45
        Port 22
        PreferredAuthentications publickey
        IdentityFile ~/.ssh/rpi_server
```


## Login - Simply using custom-name ( _host_ )

```bash
┌──(cipher㉿watchdog)-[~/.ssh]
└─$ ssh rpi                                    
Linux raspberrypi 6.6.31+rpt-rpi-v8 #1 SMP PREEMPT Debian 1:6.6.31-1+rpt1 (2024-05-29) aarch64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sun Jun 23 05:44:57 2024 from 192.168.40.95
stephanware@raspberrypi:~ $ 

```


---
# SSH-Login on Window

#os/windows/how-to/setup/ssh-key

## Generate New-Keys Pairs on the Client Machine

Start by generating a key pair ( for the server machine, which we'll a copy of our public key to the (linux) server machine. A key-pair includes a .pub (_public key_) that you share with remote computers and a private key (_without any extension_) that you never share.

**Note:** When you generate these keys, **_do not_** enter a passphrase.

The following is an example of the command and subsequent prompt:
ss
```bash
┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (C:\Users\Samst/.ssh/id_rsa): kali_linux_id_rsa
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in kali_linux_id_rsa
Your public key has been saved in kali_linux_id_rsa.pub
The key fingerprint is:
SHA256:+BGkZshf4YV1rO3sO8dEfCzSOK/M2hQ0s5xwSxoodyE samst@SuperUser
The key's randomart image is:
+---[RSA 3072]----+
|        Eo+..    |
|   . . +.= o.    |
|    o = * +o*+ . |
|     + = o.O=*= o|
|      o S .o*= o |
|       . .  o.o  |
|        .  +.+   |
|           o* o  |
|          ..o+   |
+----[SHA256]-----+
```


## 2. Verify the Keys

Navigate to the directory in which you created the keys and verify that the process succeeded. The following is a continuation of the example.

```bash

┌──(superuser㉿192.168.40.95)-[C:\Users\Samst\.ssh]
└─$

    Directory: C:\Users\Samst\.ssh

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---          14-06-2024    14:15            568 authorized_keys
-a---          22-06-2024    08:40            292 config
-a---          20-05-2023    21:59           2610 ctsmartnet_hostinger_id_rsa
-a---          20-05-2023    21:59            576 ctsmartnet_hostinger_id_rsa.pub
-a---          29-03-2024    03:25           2602 id_rsa
-a---          29-03-2024    03:25            570 id_rsa.pub
-a---          23-06-2024    06:38           2602 kali_linux_rsa
-a---          23-06-2024    06:38            570 kali_linux_rsa.pub
-a---          22-06-2024    08:40           1727 known_hosts
```

## 3. Transfer it to the Server ( _from_window_machine_ )
Copying the public key ( from window machine to the destination linux system ) on linux we use the Command `ssh-copy-id`  to copy but on windows it will be different as command `ssh-copy-id` isn't available so we will use the old-school way `scp` . That is, in this case, copy it to the `kali-linux server ` that you want password-less SSH access to.

> `ssh-copy-id` command is not available in windows
```bash
┌───(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh-copy-id -i .\kali_linux_rsa.pub cipher@192.168.40.95
ssh-copy-id: The term 'ssh-copy-id' is not recognized as a name of a cmdlet, function, script file, or executable program.
Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
```
> Therefore, we have to use the command `scp` instead of `ssh-copy-id` such as below.

| STEP-2 | TRANSFER | THE SSH-PUBLIC-KEY TO THE SERVER VIA `scp`                              |
| ------ | -------- | ----------------------------------------------------------------------- |
|        | Syntax   | scp `<public-key>` `<username@ip-address-of-server>:<destination-path>` |
|        | Example  | `scp id_rsa.pub stephanware@192.168.40.45:~\.ssh`                       |

#### Copying Public-Key ( _kali_linux_id_rsa.pub_ ) 
> Send the Public-Key over ssh using the command `scp` (_secure-copy_)
```bash
┌──(cipher㉿watchdog)-[~/.ssh]
└─$
scp .\kali_linux_id_rsa.pub cipher@192.168.40.95:~/.ssh
kali_linux_id_rsa.pub                                  100% 570 35.8KB/s  00:00
```

>Login using the password to make necessary changes on the (linux) server

| STEP-3 | LOGIN   | INTO SEVER - SIMPLY USING USERNAME@IP_ADDRESS |
| ------ | ------- | --------------------------------------------- |
|        | SYNTAX  | `ssh <username@ip_address>`                   |
|        | EXAMPLE | `ssh cipher@192.168.40.95`                    |

```bash
Public key(s) Copied: 1

Now try logging into the machine, with: "ssh cipher@192.168.40.95"
and check to make sure that only the key(s) you wanted were copied.
stephanware@192.168.40.45's password: 7642 
```
> Verify for the Copied Public-Key ( To check if it is received at the designated directory )
```bash
┌──(cipher㉿watchdog)-[~/.ssh]
└─$ ls -l
total 40
-rw-r--r-- 1 cipher cipher  767 Jun 23 06:47 authorized_keys
-rw-r--r-- 1 cipher cipher  285 Jun 23 05:13 config
-rw------- 1 cipher cipher 2602 Jun 29  2023 id_rsa
-rw-r--r-- 1 cipher cipher  569 Jun 29  2023 id_rsa.pub
-rw-rw-r-- 1 cipher cipher  570 Jun 23 06:46 kali_linux_id_rsa.pub
-rw------- 1 cipher cipher  979 Jun 22 20:25 known_hosts
-rw------- 1 cipher cipher 2602 Jun 23 02:34 rpi_server
-rw-r--r-- 1 cipher cipher  569 Jun 23 02:34 rpi_server.pub
```

> Append the Public-Key on to the `authorized_keys` file.

| STEP-4 | APPEND THE PUBLIC-KEY ONTO THE AUTHORIZED_KEYS |
| ------ | ---------------------------------------------- |
|        | cat `<public_key.pub> >> authorized_keys`      |
|        | cat `kali_linux_id_rsa.pub >> authorized_keys` |
> Login in without password using the private key

| STEP-5 | LOGIN WITHOUT PASSWORD USING THE PRIVATE-KEY           |
| ------ | ------------------------------------------------------ |
|        | ssh -i `<private-key> <username@ip-address>`           |
|        | ssh `ssh -i .\kali_linux_rsa.pub cipher@192.168.40.95` |

```bash
┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh -i .\kali_linux_rsa.pub cipher@192.168.40.95
```

```bash
┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh -i .\kali_linux_id_rsa cipher@192.168.40.95
Linux watchdog 6.4.0-kali3-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.4.11-1kali1 (2023-08-21) x86_64

The programs included with the Kali GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Kali GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sun Jun 23 07:34:19 2024 from 192.168.40.53
```

## Make changes to (_~/.ssh/config_) file.
In order for us to remotely login quickly and easily without having to type long username along with its ip-address and then the password. we'll be making use of the (_~/.ssh/config_) file to store all those information and access the remote machine over ssh using the preferred custom host name (which could be anything).

```
Host cipher
        User cipher
        Hostname 192.168.40.95
        Port 22
        PreferredAuthentications publickey
        IdentityFile ~/.ssh/kali_linux_id_rsa

```

| STEP-6 | LOGIN EASILY |
| ------ | ------------ |
|        | ssh cipher   |
```bash
┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh cipher
Linux watchdog 6.4.0-kali3-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.4.11-1kali1 (2023-08-21) x86_64

The programs included with the Kali GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Kali GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sun Jun 23 08:20:47 2024 from 192.168.40.53
┌──(cipher㉿watchdog)-[~]
└─$

```

---
#os/linux/how-to/setup/ssh-key 
#os/windows/how-to/setup/ssh-key 
# SSH-LOGIN with Different Keys
## SSH-LOGIN { without Identity-File }

```bash
┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh cipher@192.168.40.95
cipher@192.168.40.95's password:

┌──(cipher㉿watchdog)-[~]
└─$ exit
Connection to 192.168.40.95 closed
```

## SSH-LOGIN { with Private Identity-File }

> syntax

| Syntax  | `ssh -i <private identity-file> user@host_ip`     |
| ------- | ------------------------------------------------- |
| Example | `ssh -i .\kali_linux_id_rsa cipher@192.168.40.95` |

> Terminal Log

```bash
┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh -i .\kali_linux_id_rsa cipher@192.168.40.95
Linux watchdog 6.4.0-kali3-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.4.11-1kali1 (2023-08-21) x86_64

The programs included with the Kali GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Kali GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Sun Jun 23 07:34:19 2024 from 192.168.40.53
```

## SSH-LOGIN { with Public Identity-File }

> Syntax

| Syntax  | `ssh -i <public identity-file> user@host_ip`      |
| ------- | ------------------------------------------------- |
| Example | `ssh -i .\kali_linux_id_rsa cipher@192.168.40.95` |

> Terminal Log

```bash
┌──(SUPERUSER㉿192.168.40.53)-[C:\Users\Samst\.ssh]
└─$ PS>ssh -i .\kali_linux_id_rsa.pub cipher@192.168.40.95
Bad permissions. Try removing permissions for user: \\Everyone (S-1-1-0) on file C:/Users/Samst/.ssh/kali_linux_id_rsa.pub.
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions for '.\\kali_linux_id_rsa.pub' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key ".\\kali_linux_id_rsa.pub": bad permissions
cipher@192.168.40.95's password:
```
## Conclusion

```javascript
Using the above login cases we can clear see that `ssh-login ssh -i <identity-file>` fails with `public-key` it only works only with `private-key`.
You need to have an access to the `private-key` in order to login with `ssh -i ` command syntax.
```