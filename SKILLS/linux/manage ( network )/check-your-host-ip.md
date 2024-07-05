#skills/hacking/networking 

# Analyzing Networks with

# ifconfig
The ifconfig command is one of the most basic tools for examining and
interacting with active network interfaces

!![[ifconfig.png]]

```
The type of network being used (Ethernet) is listed next, followed by
HWaddr and an address; this is the globally unique address stamped on every
piece of network hardware—in this case, the network interface card (NIC),
usually referred to as the media access control (MAC) address.
```

| s.no | interface                   | what does it do ?                                                                                                                         |     |
| ---- | --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | --- |
| 1.   | eth0                        | the name of the first detected interface, eth0. which is short for Ethernet0 (Linux starts counting at 0 rather than 1)                   |     |
| 2.   | inet                        | contains information on the IP address currently<br>assigned to that network interface (in this case, 192.168.181.131                     |     |
|      | netmask                     | and finally the network mask (netmask), which is<br>used to determine what part of the IP address is connected to the local net-<br>work. |     |
| 3.   | Bcast, or broadcast address | the address used to send out informa tion to all IPs on the subnet;                                                                       |     |
| 4.   | loopback address            | sometimes called localhost. This is a special software address that connects you to your own system.                                      |     |
|      | wlan0                       | a wireless interface or adapter and it also displays<br>the MAC address of that device (HWaddr).                                          |     |

This information from ifconfig enables you to connect to and manipulate your local area network (LAN) settings, an essential skill for hacking.


