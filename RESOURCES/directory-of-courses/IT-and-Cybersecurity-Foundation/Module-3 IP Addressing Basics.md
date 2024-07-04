Upon completing this lab, you should be able to:

- Identify the key components of the IP addressing scheme.
- Given an IP address and subnet mask, determine the network address and device address.
- Use the ifconfig command to display network interfaces on a Linux system.
- Use the arp command to display the arp table on a Linux system.
- 
---
# Introduction

In this lab, we will explore the building blocks of modern networking: the Transmission Control Protocol/Internet Protocol (TCP/IP) and the Address Resolution Protocol (ARP).

# The TCP/IP Network Model

TCP/IP is a suite of networking protocols that provides a set of rules and conventions that govern how data is transmitted, routed, and received between devices on a network. TCP/IP is a layered protocol, meaning it's organized into four distinct areas, each with specific functions:

![[IPA_001.png]]
# Transmission Control Protocol

The TCP half of TCP/IP provides reliable, connection-oriented communication. It establishes a connection between two devices before data transfer, ensuring that data is sent and received in the correct order without errors. TCP uses port numbers to distinguish between services running on the same device. For example, port 80 is typically associated with HTTP (web) traffic, while port 25 is used for SMTP (email) traffic. Below is a list of the more common TCP and UDP ports:

![[IPA_002.png]]

Note: UDP stands for User Datagram Protocol. UDP offers faster, connectionless communication but doesn't provide the same reliability and error correction as TCP.
# Internet Protocol

The IP half of TCP/IP is responsible for routing data packets from the source to the destination across networks using routers. A router is a special device that can forward packets to and from different networks using IP addresses.

Note: There are two main types of IP address: IPv4 (Internet Protocol version 4) and IPv6 (Internet Protocol version 6. IPv4 uses 32-bit addresses, while IPv6 uses 128-bit addresses to accommodate the growing number of devices on the internet. Although IPv6 is gradually gaining wider adoption, most networks (including the Internet) still rely on IPv4

Every host on a network is assigned at least one IP Address. An IPv4 address comprises four octets (a number from 0 to 255) and a subnet mask. The mask's purpose is to determine which part of the IP address represents the host and which part represents the network. Let's look at an example:

![[IPA_003.png]]

n the example above, 192.168.10.100 is the IP Address, and 255.255.255.0 is the subnet mask.A subnet mask of 255 means "the entire octet" is part of the network, while 0 (zero) means the entire octet represents the host.

Thus, the first three octets (192.168.10) are the network, and the fourth octet (.100) is the host.

In TCP/IP networking, hosts on the same network can speak to each other directly, while hosts on another network must have messages forwarded using a router. In the example below, we see two hosts that share the same network (192.168.10), and thus, they can reach each other without a router. However, the third IP does not use the same network and will require a router to communicate with the first two.

![[IPA_004.png]]

Note: It is common to see 255.255.255.0 written as /24 ("slash" 24). This means that 192.168.10.100/24 is the same as 192.168.10.100 255.255.255.0.

# Routing and Subnetting

Routing and subnetting are complex topics, with entire books dedicated to each. Many learners need help with subnetting. For this lab, you only need to understand that an IP address is made up of two parts (network and host) and that only hosts on the same network can speak to each other without a router. In the example below, 192.168.10.10 can speak directly to 192.168.10.20, but it will need the router at 192.168.10.1 (called a gateway) to speak with 192.168.11.10 or 192.168.11.20. Notice the gateway has two IP Addresses, one in each network. It's important to note that routers do not need to be part of a given network to route traffic. A router can attach to its own gateway, sending packets far beyond the local networks (e.g., to the Internet).

![[IPA_005.png]]

# Media Access Control (MAC) and Address Resolution Protocol (ARP)
When a device on a local network segment wants to communicate with another device on the same segment, it needs to know the destination device's Media Access Control (MAC) address. The MAC address is a 12-digit hexadecimal number unique on a given network segment. However, a host typically only knows the IP address of another host, not the MAC address. ARP is used to map local IP Addresses to MAC addresses. ARP works as follows:
1. A host broadcasts an ARP request packet to the local network.
2. When the device with the target IP address sees the ARP request, it replies with an ARP response packet
3. After receiving the ARP response, the requesting device stores the mapping of the target IP address to the target MAC address in its ARP cache.

Note: The ARP cache is used to avoid sending ARP requests for the same IP address frequently. Entries in the ARP cache typically have a timeout, after which they are considered stale and need to be refreshed.

With the MAC address now known, the sending device can encapsulate its IP packet within an Ethernet frame and send it to the target device using the destination MAC address. The local switches and routers use the MAC address to route the data packet within the local network. Returning to the previous example network, 192.168.10 .10 will use ARP to build a MAC to IP mapping for 192.168.10.20 and 192.168.10.1. This mapping will allow 192.168.10.10 to speak directly to 192.168.10.1 and 192.168.10.20 using Ethernet frames. The same holds true for the 192.168.11.0 network.

In the next part of this lab, you will explore TCP/IP and ARP using GNS3: a popular network simulator.

# Resources
* https://app.cybrary.it/immersive/18073699/activity/71524
* 