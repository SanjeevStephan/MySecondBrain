#collections-of/manuals/vscode




## Remote Development { using SSH }

The **Remote - SSH** extension lets you use any remote machine with a SSH server as your development environment. This can greatly simplify development and troubleshooting in a wide variety of situations. You can:
- Develop on the same operating system you deploy to or use larger, faster, or more specialized hardware than your local machine.
- Quickly swap between different, remote development environments and safely make updates without worrying about impacting your local machine.
- Access an existing development environment from multiple machines or locations.
- Debug an application running somewhere else such as a customer site or in the cloud.

No source code needs to be on your local machine to gain these benefits since the extension runs commands and other extensions directly on the remote machine. You can open any folder on the remote machine and work with it just as you would if the folder were on your own machine.




> Installation
1. Install [VS Code](https://code.visualstudio.com/ "https://code.visualstudio.com/") or [VS Code - Insiders](https://code.visualstudio.com/insiders "https://code.visualstudio.com/insiders") and this extension.
2. Install [an OpenSSH compatible SSH client](https://aka.ms/vscode-remote/ssh/supported-clients "https://aka.ms/vscode-remote/ssh/supported-clients").
3. If you do not have a SSH host set up, follow the directions for [Linux](https://aka.ms/vscode-remote/ssh/ssh-server "https://aka.ms/vscode-remote/ssh/ssh-server"), [Windows 10 / Server (1803+)](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse "https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse"), or [macOS](https://support.apple.com/guide/mac-help/allow-a-remote-computer-to-access-your-mac-mchlp1066/mac "https://support.apple.com/guide/mac-help/allow-a-remote-computer-to-access-your-mac-mchlp1066/mac") or create a [VM on Azure](https://docs.microsoft.com/azure/virtual-machines/linux/quick-create-portal?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json "https://docs.microsoft.com/azure/virtual-machines/linux/quick-create-portal?toc=%2fazure%2fvirtual-machines%2flinux%2ftoc.json").

> Getting started

- Search for `remote ssh` & you should see below extension - install them

![[Pasted image 20240630080154.png]]

Once Installed

**[Follow the step-by-step tutorial](https://aka.ms/vscode-remote/ssh/tutorial "https://aka.ms/vscode-remote/ssh/tutorial")** or if you have a simple SSH host setup, connect to it as follows:

1. Press `F1` and run the **Remote-SSH: Open SSH Host...** command.

You can press `F1` to bring up the Command Palette and type in `Remote-SSH` for a full list of available commands. Select the first one `Remote-SSH: Add New SSH Host`. Press `[Enter]`.

![[Pasted image 20240630081834.png]]

 If prompted to save the configuration on the file ( `C:\Users\Samst\.ssh\config` ). Press `[Enter]`

2. Here, You Can Either Enter your user and host/IP in the following format in the input box that appears and press enter: `user@host-or-ip` or `user@domain@host-or-ip`. Which would eventually require you to enter the password everytime you want to connect. 
	If prompted, enter your password (but we suggest setting up [key based authentication](https://aka.ms/vscode-remote/ssh/key-based-auth "https://aka.ms/vscode-remote/ssh/key-based-auth")).

![[Pasted image 20240630081936.png]]
3. Or You can login using the [[ssh]] keys if you have ssh-client setup as with it, it would not require you to enter the password to connect.

`[OPTION-01]` Input the Below using your `<identity-key file>` along with `<user>@<host-ip>`
``` bash
ssh -i C:\Users\Samst\.ssh\kali_linux_id_rsa cipher@192.168.40.95
```

`[OPTION-02]` Simply we have to modify the `( ~./ssh/config )` file by adding below details.
```javascript
#Syntax
Host "<Specify-the-name-of-host>"
        User "<username-of-the-machine>"
        HostName "<ip-address-of-host-machine"
        Port 22
        PreferredAuthentications publickey
        IdentityFile ~/.ssh/"put-name-of-the-private-key-here-without-quotes"
--------------------------------------------------------------------------------
#Example
Host cipher
        User cipher
        HostName 192.168.40.95
        Port 22
        PreferredAuthentications publickey
        IdentityFile ~/.ssh/kali_linux_id_rsa
```

4. Select the Operating System of the Host & Press `[Enter]`
![[Pasted image 20240630084224.png]]
	Once Selected It will begin connecting to that host via ssh using the private-key you provide 
![[Pasted image 20240630084257.png]]
```javascript
#Security_Note
Using Remote-SSH opens a connection between your local machine and the remote. Only use Remote-SSH to connect to secure remote machines that you trust and that are owned by a party whom you trust. A compromised remote could use the VS Code Remote connection to execute code on your local machine.
```

5. After you are connected, use **File > Open Folder** to open a folder on the host.


![[ssh-readme.gif]]

You Should See Something like below :

| ![[Pasted image 20240630091320.png]] | ![[Pasted image 20240630091351.png]] |
| ------------------------------------ | ------------------------------------ |

Congratulation.. You are now connected. 

| Select `Open Folder`                 | on the VSCode to access the files hosted on the remote machine |
| ------------------------------------ | -------------------------------------------------------------- |
| ![[Pasted image 20240630091627.png]] | ![[Pasted image 20240630091612.png]]                           |
```javascript
By Default, you can select "OK" but here i would like to access the entire files & directories on the remote machine over ssh.
so i will remove the `/home/cipher/` and leave the `/` forward slash for root access
```

![[Pasted image 20240630092102.png]]

| If Promoted. Press `Yes,I Trust the authors` |
| -------------------------------------------- |
| ![[Pasted image 20240630092129.png]]         |
