---
Title: SWS101 Flipped_class
categories: [SWS101,Flipped_2]
tags: SWS 101
---
### connecting to the HTB VPN 
Before starting the hack the box challanges i connected to the VPN of US server by downloading the VPN(.ovpn) configuration file and run it into the terminal.
![starting machine](/assets/img/start_machine.png)

## Tire 0 
### MEOW 
#### Gaining Access to the System
Firstly I spawn the meow machine and got the target ip address.
To test whether i am connected to the machine i ping the ip address. after that i scan the machine and
found out service i was running was telnet. 
i log into the target over telnet with a blank password that is root and submitted the root flag.

#### Learning Through the Meow Machine
New things learned in this machine are:
1. nmap: it is a network scanning tool. 
2. openvpn: it is the service that we used to form our vpn connection into HTB labs.
3. ICMP echo request (Internet Control Message Protocol): it also known as ping messages.it is mostly used as a troubleshooting tool to see the connection between devices.
4. telnet: Telnet is a very vulnerable service to run on any machine. It allows anonymous login sometimes, misconfigurations, and weak passwords.i found out service i was running on was telnet.
![port23](/assets/img/port23.png)
5. root: it is the superuser account in unix and linux.It has the highest access rights on the system therefore it has the power to execute any command and modify any file. This makes it an necessary tool for system administrators for performing tasks that regular users cannot.

### FAWN
#### Gaining Access to the System
like before i spawn the machine, got the target ip address and ping the ip address to see if i can communicate with the machine.
After that i scan the version of the machine running on using -sV.I also used the -F command this command can scan the machine faster by scanning few important parts.
In this machine key task was to login into the root user using anonymous username and password and download the file and submited the root flag.

#### Learning Through the Meow Machine
things learned in this machine are:
1. FTP(file transfer protocol):it is a way to download, upload, and transfer files from one location to another on the Internet and between computer system.  
2. Unix:It is a modular OS made up of a number of essential components, including the kernel, shell, file system and a core set of utilities or programs.
3. get:it is a command to download package in linux.
4. anonymous login:It allows us to log in anonymously. we don’t need to know the username or password of an existing user. This misconfiguration is a significant security flaw, as it grants unauthorized access to the FTP server's files. one key thing to learn in this machine was to login under anonymous user and all i did is download the file using get and exit the machine and used cat command to retrive the data.

### Dancing
#### Gaining Access to the System
like before i spawn the machine and got the target ip address of dancing machine.but when i ping or scan the ip address the result is not showing as i expexted. when i scan it showing blocking our ping probs. so i delete the prevoius vpn and again redownload the vpn and set up the connection and spawn the machine again.
In my scan 3 ports are detected.The port 445/tcp is open and running on microsoft-ds which includes SMB functionality.We used smblicient to exploit SMB service in this machine.i found 4 sharename, "workspace" is connected without providing any password. So, I tried navigating to the workspace and found out that there are 2 user directories, 'Amy.J' and 'James.P'.under uer James.P i found a flag.txt file which i downloaded it using get and retrive it using cat and submitted the root flag. 
#### Learning Through the Meow Machine
1. SMB(server message block):it is a client-server communication protocol used for sharing access to files, printers, serial ports and other resources on a network.

### Redeemer
#### Gaining Access to the System
like usual I spawn machine,ping the ip address of the target machine.scan the virsion of the machine.
after the scan redis service is running on the 6379 port that is open on the machine.

![redis](/assets/img/redis.png)

Then I connected to the Redis server using redis-cli -h command, but in here i first get into the root user. root user  is something has a high access over the the system.after getting the info about the redis server i came to know there are 4 keys i used get command and got the root flag.

### Learning Through the Redeemer Machine
Redis (Remote Dectionary Server) :is an open-source advanced NoSQL key-value data store used as a database. The data is stored in a dictionary format having key-value pairs.it is store in in-memory database unlike post posgres,My SQL,etc..


## Tire 1
 