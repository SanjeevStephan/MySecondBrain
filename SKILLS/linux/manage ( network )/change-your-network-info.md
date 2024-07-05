#skills/hacking/networking 

Being able to change your IP address and other network information is a
useful skill because it will help you access other networks while appearing
as a trusted device on those networks.

For example, in a denial-of-service (DoS) attack, you can spoof your IP so that that the attack appears to come from another source, thus helping you evade IP capture during forensic analysis. 
This is a relatively simple task in Linux, and it’s done with the ifconfig command.

## Change Your IP Address

| Command                       | Change Your IP Address                                                                                                                                            |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ifconfig eth0 192.168.181.115 | To change your IP address , enter ***ifconfig*** followed by the interface you want to reassign and the new IP address you want assigned to that interface.       |
|                               | When you do this correctly, Linux will simply return the command<br>prompt and say nothing. This is a good thing!                                                 |
|                               | Then, when you again check your network connections with ifconfig,<br>you should see that your IP address has changed to the new IP address you<br>just assigned. |



