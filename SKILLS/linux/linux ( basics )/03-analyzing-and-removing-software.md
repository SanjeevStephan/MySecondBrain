#os/linux/basics/networking 
#ebook/category/hacking/linux-basics-for-hacker/

![[index-of-linux-basics-for-hacker]]

1. [[check-your-host-ip]]
2. [[check-wireles-usb-adapter-ip]]
3. [[change-your-network-info]]
4. [[spoofing-your-mac-address]]
5. [[manipulating-the-DNS]]
6. 

# Summary

| Commands                                                                                                      | What does it Do ?                                |
| ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| ifconfig eth0 192.168.181.115                                                                                 | Changing Your IP Address                         |
| kali > ifconfig eth0 down<br><br>kali >ifconfig eth0 hw ether 00:11:22:33:44:55<br><br>kali >ifconfig eth0 up | Spoofing Your MAC Address                        |
| ifconfig eth0 192.168.181.115 netmask 255.255.0.0 broadcast 192.168.1.255                                     | Changing Your Network Mask and Broadcast Address |
| kali > dhclient wlan0 -r<br><br>kali > dhclient wlan0                                                         | Assigning New IP Address from DHCP               |

# System Files

|Files|Description|
|---|---|
|/etc/resolv.conf|File in which your nameserver is located|
|/etc/hosts|This File determine which IP address your browser goes to when you enter www.microsoft.com (or any other domain) into the browser, rather than let the DNS server decide.|

eth0 - Ethernet0 (Linux starts counting at 0 rather than 1)

| Titile                          | Description                                                                                                                                                                                             | Syntax |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
| ifconfig                        | examining and interacting with active network interfaces.                                                                                                                                               |        |
| HWaddr                          | globally unique address stamped on every<br><br>piece of network hardware—in this case, the network interface card (NIC),<br><br>usually referred to as the media access control (MAC) address.         |        |
| broadcast address,              | address used to send out information to all IPs on the subnet                                                                                                                                           |        |
| network mask (netmask)          | determine what part of the IP address is connected to the local network.                                                                                                                                |        |
| loopback address ( localhost. ) | Address that connects you to your own system.<br><br>Use lo to test something on your system, such as your own web server.<br><br>The localhost is generally represented with the IP address 127.0.0.1. |        |
|                                 | This information from ifconfig enables you to connect to and manipu-<br><br>late your local area network (LAN) settings, an essential skill for hacking.                                                |        |
|                                 |                                                                                                                                                                                                         |        |

# Checking Wireless Network Devices with iwconfig

|Command|iwconfig|
|---|---|
|Syntax|wlan0 IEEE 802.11 ESSID:"SmartHome"<br><br>Mode:Managed Frequency:2.437 GHz Access Point: 26:7B:AC:83:E2:01|
|Output|The output here tells us that the only network interface with wireless extensions is wlan0|

# Changing Your IP Address

|Syntax|ifconfig eth0 192.168.181.115|
|---|---|
||Above Syntax Assigns the IP address192.168.181.115 to interface eth0|
|Description|To change your IP address, enter ifconfig followed by the interface you want to reassign and the new IP address you want assigned to that interface.|

# Changing Your Network Mask and Broadcast Address

|Syntax|ifconfig eth0 192.168.181.115 netmask 255.255.0.0 broadcast 192.168.1.255|
|---|---|
|Description|You can also change your network mask (netmask) and broadcast address withthe ifconfig command.|

# Spoofing Your MAC Address

|Command|What does it Do ?|
|---|---|
|ifconfig eth0 down|To spoof your MAC address, simply use the ifconfig command’s down option to take down the interface (eth0 in this case).|
|ifconfig eth0 hw ether 00:11:22:33:44:55|Then enter the ifconfig command followed by the interface name (hw for hardware, ether for Ethernet) and the new spoofed MAC address.|
|ifconfig eth0 up|Finally, bring the interface back up with the up option for the change to take place.|

# Assigning New IP Addresses from the DHCP Server

1. Linux has a Dynamic Host Configuration Protocol (DHCP) server that runs a daemon

—a process that runs in the background—called dhcpd, or thedhcp daemon.

1. The DHCP server assigns IP addresses to all the systems on thesubnet and keeps log files of which IP address is allocated to which machine at any one time.
2. This makes it a great resource for forensic analysts to trace hackers with after an attack.
3. For that reason, it’s useful to understand how the DHCP server works.
4. Usually, to connect to the internet from a LAN, you must have a DHCP- assigned IP.

|Syntax|kali >dhclient eth0 -r -> Release the Current IP Address<br><br>kali >dhclient eth0 ->Request a new IP Address.|
|---|---|
|Description|The dhclient command sends a DHCPDISCOVER request from the network interface specified (here, eth0).<br><br>It then receives an offer (DHCPOFFER) from the DHCP server (192.168.181.131 in this case) and confirms the IP assignment to the DHCP server with a dhcp request.|
|||

# Manipulating the Domain Name System

Hackers can find a treasure trove of information on a target in its Domain Name System (DNS).

DNS is a critical component of the internet, and although it’s designed to translate domain names to IP addresses, a hacker can use it to garner information on the target.

|Title|Syntax|Command|
|---|---|---|
|Find Name-Server|dig <website.com> ns|dig hackers-arise.com ns|
|Find Email-Server|dig <website.com> mx|dig hackers-arise.com mx|

Examining DNS with dig
```bash

┌──(cipher㉿watchdog)-[~]  
└─$ dig hackers-arise.com ns  
  
; <<>> DiG 9.19.21-1-Debian <<>> hackers-arise.com ns  
;; global options: +cmd  
;; Got answer:  
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 1164  
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1  
  
;; OPT PSEUDOSECTION:  
; EDNS: version: 0, flags:; udp: 1280  
;; QUESTION SECTION:  
;hackers-arise.com.             IN      NS  
  
;; ANSWER SECTION:  
hackers-arise.com.      86400   IN      NS      ns7.wixdns.net.  
hackers-arise.com.      86400   IN      NS      ns6.wixdns.net.  
  
;; Query time: 291 msec  
;; SERVER: 192.168.10.88#53(192.168.10.88) (UDP)  
;; WHEN: Mon Mar 18 16:28:58 IST 2024  
;; MSG SIZE  rcvd: 92

Also note in the ADDITIONAL SECTION that this dig query reveals the IP address (216.239.32.100) of the DNS server servin hackers-arise.com.
```

# Changing Your DNS Server

In some cases, you may want to use another DNS server. To do so, you’ll edit a plaintext file named /etc/resolv.conf on the system


| Command to Edit | leafpad /etc/resolv.conf                                    |
| --------------- | ----------------------------------------------------------- |
| Command to View | cat /etc/resolv.conf                                        |
| Output          | nameserver 192.168.10.88                                    |
| Explaination    | my nameserver is set to a local DNS server at 192.168.181.2 |

That works fine, but if I want to replace that DNS server with, say, Google’s public DNS server at 8.8.8.8, I could place the following line in the /etc/resolv.conf file to specify the nameserver:

Then I would just need to save the file. However, you can also achieve the

same result exclusively from the command line by entering the following:

|Oneliner Command|echo "nameserver 8.8.8.8"> /etc/resolv.conf|
|---|---|

# Mapping Your Own IP Addresses

1. A special file on your system called the hosts file also performs domain name– IP address translation.
2. The hosts file is located at /etc/hosts, and kind of as with DNS, you can use it to specify your own IP address–domain name mapping.
3. In other words, you can determine which IP address your browser goes to when you enter [www.microsoft.com](http://www.microsoft.com) (or any other domain) into the browser, rather than let the DNS server decide.

|IP address–domain name MAP File Located At|/etc/hosts|
|---|---|
