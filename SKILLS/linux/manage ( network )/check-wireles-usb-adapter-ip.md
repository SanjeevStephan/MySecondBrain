#skills/hacking/networking 

the iwconfig command particularly important 
1. If you have an external USB, you can use the iwconfig command to gather crucial information for wireless hacking such as the adapter’s IP address, its MAC address, what mode it’s in, and more.
2. this command is particularly important when you’re using wireless
	hacking tools like aircrack-ng.

!![[iwconfig.png]]

| wlan0            | only network interface with wireless extensions is wlan0, which is what we would expect.                                                                                          |
| ---------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 802.11 IEEE      | wireless standards our device is<br>capable of: b and g, two early wireless communication standards. Most wire-<br>less devices now include n as well (n is the latest standard). |
| Mode:Managed     | We’ll need monitor or  promiscuous mode for cracking wireless passwords.                                                                                                          |
| (Not Associated) | the wireless adapter is not connected (Not Associated)<br>to an access point (AP)                                                                                                 |
| power is 20 dBm  | that its power is 20 dBm, which represents the<br>strength of signal.                                                                                                             |
