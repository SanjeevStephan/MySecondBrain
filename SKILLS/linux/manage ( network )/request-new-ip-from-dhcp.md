#skills/networking 

## Linux has a Dynamic Host Configuration Protocol (DHCP) server

## called

### dhcpd

## The DHCP server assigns IP addresses to all the systems on the

## subnet and keeps log files of

## which IP address is allocated to which machine

## at any one time. This makes it a great resource for forensic analysts to trace

## hackers with after an attack

.

## For that reason, its useful to understand how the DHCP server works

## Usually, to connect to the internet from a LAN, you must have a DHCP-assigned IP.

## Kali is built on Debian, which uses

### dhclient

## . Therefore, you can assign a new address like this:

## To request an IP address from DHCP,

1. ## 1.
    
    # 1. first you need to release the existing IP Address.
    

# └─>

# sudo dhclient -v -r eth0

1. ## 2.
    
    # 2. after that simply call the DHCP server with the command dhclient followed by the interface you want the address assigned to
    
    # └─>
    
    # sudo dhclient eth0
    
2. 3.
    
    # 3. Now when you enter
    
    _
    
    # ifconfig
    
    _
    
    # , you should see that the DHCP server has
    
    ## assigned a new IP address, a new broadcast address, and new netmask to your network interface
    
    ### eth0
    
    ## .
    
    # └─>
    
    # ifconfig
    

[![file:///tmp/.728SO2/1.png](file:///tmp/.728SO2/1.png)](https://www.cyberciti.biz/media/new/faq/2007/11/Am-I-using-DHCPD-as-a-client-or-server-daemon-under-Linux-498x599.png)


```
┌──(root㉿Watchdog)-[~]
└─# dhclient -v -r eth0

Killed old client process

Internet Systems Consortium DHCP Client 4.4.3-P1

Copyright 2004-2022 Internet Systems Consortium.

All rights reserved.

For info, please visit [https://www.isc.org/software/dhcp/](https://www.isc.org/software/dhcp/)

Listening on LPF/eth0/00:11:22:33:44:55

Sending on LPF/eth0/00:11:22:33:44:55

Sending on Socket/fallback

DHCPRELEASE of 192.168.29.28 on eth0 to 192.168.29.1 port 67
```

```
┌──(root㉿Watchdog)-[~]
└─# dhclient -v eth0

Internet Systems Consortium DHCP Client 4.4.3-P1

Copyright 2004-2022 Internet Systems Consortium.

All rights reserved.

For info, please visit [https://www.isc.org/software/dhcp/](https://www.isc.org/software/dhcp/)

Listening on LPF/eth0/00:11:22:33:44:55

Sending on LPF/eth0/00:11:22:33:44:55

Sending on Socket/fallback

DHCPDISCOVER on eth0 to 255.255.255.255 port 67 interval 5

DHCPOFFER of 192.168.29.28 from 192.168.29.1

DHCPREQUEST for 192.168.29.28 on eth0 to 255.255.255.255 port 67

DHCPACK of 192.168.29.28 from 192.168.29.1

bound to 192.168.29.28 -- renewal in 13896 seconds.
```





Sources

1. [https://geeksadvice.com/release-and-renew-ip-address/](https://geeksadvice.com/release-and-renew-ip-address/)
2. [https://www.cyberciti.biz/faq/howto-linux-renew-dhcp-client-ip-address/](https://www.cyberciti.biz/faq/howto-linux-renew-dhcp-client-ip-address/)