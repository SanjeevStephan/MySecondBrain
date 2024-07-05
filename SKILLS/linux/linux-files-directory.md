#os/linux/basics/directory-structures
#os/linux/important/linux-directories 


## Linux File System

```javascript
The Linux filesystem structure is somewhat different from that of Windows.

Linux doesn’t have a physical drive (such as the C: drive) at the base of the

file­system but uses a logical filesystem instead.

The following are the most important subdirectories to know:

The root (/) of the filesystem is at the top of the tree.
```

| Directory | Description                                                                                                            |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| /         | The root (/ ) of the filesystem is at the top of the tree                                                              |
| /root     | The home directory of the all-powerful root user                                                                       |
| /etc      | Generally contains the Linux configuration files<br><br>The Files that control when & how programs startup             |
| /home     | The user’s home directory                                                                                              |
| /mnt      | Where other filesystems are attached or mounted to the filesystem                                                      |
| /media    | Where CDs and USB devices are usually attached or mounted to the filesystem                                            |
| /bin      | Where application binaries (the equivalent of executables in<br><br>Microsoft Windows or applications in macOS) reside |
| /lib      | Where you’ll find libraries (shared programs that are similar to Windows DLLs)                                         |
Understanding these first-level directories is important to navigating through the filesystem from the command line.


# The Linux Configuration Files
#os/linux/important/linux-config-files

| Title (Config-File ) | Location                  | Description        | Command                       |
| -------------------- | ------------------------- | ------------------ | ----------------------------- |
| Local DNS Nameserver | /etc/resolv.conf          | Local DNS          | sudo leafpad /etc/resolv.conf |
| The iptable          | /etc/hosts                | Local IP-Table     | sudo leafpad /etc/hosts       |
| The Samba            | /etc/samba/smb.conf       | Samba              |                               |
| The Apache2          | /etc/apache2/apache2.conf | Apache2 Web-Server |                               |
| The SSH              | /etc/ssh/sshd_config      | Secure-Shell       |                               |

# The Window Configuration Files
#os/windows/important/window-config-files

| Title             | Location                               | Learn More                                       |
| ----------------- | -------------------------------------- | ------------------------------------------------ |
| Window Hosts file | c:\Windows\System32\Drivers\etc\hosts. | https://www.nublue.co.uk/guides/edit-hosts-file/ |
|                   |                                        |                                                  |

# Kali Linux Directories
#os/linux/important/linux-directories

|Title|Directory|Description|
|---|---|---|
|Wordlist (Kali)|/usr/share/wordlists|This Directory stores all the wordlists ockyou.txt for for metasploit, wifite|
|Wordlist (Ubuntu)|/usr/share/dict||
||/usr/share/images/desktop-base|Kali Desktop Wallpapers|
|login background|/usr/share/desktop-base/kali-theme/login/|login background images|
||/etc/apt/sources.list.d/||
||/etc/apt/trusted.gpg.d/||

## Background Wallpaper Directory
#os/linux/important/background-wallpaper-directory

|Title|Directory|Description|
|---|---|---|
|Wordlist (Kali)|/usr/share/images/desktop-base|This Directory stores all the wordlists ockyou.txt for for metasploit, wifite|
|Desktop-Wallpapers|/usr/share/backgrounds/kali-16x9||
|Grub Boot Background|/usr/share/grub/themes/kali/|Kali Desktop Wallpapers|
|Login-Backgrounds|/usr/share/desktop-base/kali-theme/login|login background images|
