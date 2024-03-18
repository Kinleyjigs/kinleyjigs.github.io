---
Title: SWS101 Flipped_class
categories: [SWS101,Flipped_2]
tags: SWS 101
---
## HackTheBox
### Connecting to the HTB VPN 
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

#### Learning Through the FAWN Machine
things learned in this machine are:
1. FTP(file transfer protocol):it is a way to download, upload, and transfer files from one location to another on the Internet and between computer system.  
2. Unix:It is a modular OS made up of a number of essential components, including the kernel, shell, file system and a core set of utilities or programs.
3. get:it is a command to download package in linux.
4. anonymous login:It allows us to log in anonymously. we don’t need to know the username or password of an existing user. This misconfiguration is a significant security flaw, as it grants unauthorized access to the FTP server's files. one key thing to learn in this machine was to login under anonymous user and all i did is download the file using get and exit the machine and used cat command to retrive the data.

### Dancing
#### Gaining Access to the System
like before i spawn the machine and got the target ip address of dancing machine.but when i ping or scan the ip address the result is not showing as i expexted. when i scan it showing blocking our ping probs. so i delete the prevoius vpn and again redownload the vpn and set up the connection and spawn the machine again.
In my scan 3 ports are detected.The port 445/tcp is open and running on microsoft-ds which includes SMB functionality.We used smblicient to exploit SMB service in this machine.i found 4 sharename, "workspace" is connected without providing any password. So, I tried navigating to the workspace and found out that there are 2 user directories, 'Amy.J' and 'James.P'.under uer James.P i found a flag.txt file which i downloaded it using get and retrive it using cat and submitted the root flag. 
#### Learning Through the Dancing Machine
1. SMB(server message block):it is a client-server communication protocol used for sharing access to files, printers, serial ports and other resources on a network.

### Redeemer
#### Gaining Access to the System
like usual I spawn machine,ping the ip address of the target machine.scan the virsion of the machine.
after the scan redis service is running on the 6379 port that is open on the machine.

![redis](/assets/img/redis.png)

Then I connected to the Redis server using redis-cli -h command, but in here i first get into the root user. root user  is something has a high access over the the system.after getting the info about the redis server i came to know there are 4 keys i used get command and got the root flag.

#### Learning Through the Redeemer Machine
Redis (Remote Dectionary Server) :is an open-source advanced NoSQL key-value data store used as a database. The data is stored in a dictionary format having key-value pairs.it is store in in-memory database unlike post posgres,My SQL,etc..


## Tire 1
### Appointment 
#### Gaining Access to the System
![appoinment](/assets/img/appoinment.png)
![appoinment](/assets/img/appoi_https.png)
Firstly, I spawned the machine and obtained the target IP address. Then, I pinged the IP address and conducted a simple scan. I discovered that port 80 is open, and the version running on it is Apache httpd 2.4.38 (Debian). The standard port used for the HTTPS protocol is 443. I copied my IP address and pasted it into the browser, which navigated to a login page where the SQL injection vulnerability occurs.

The SQL query is attempting to retrieve data from a table named "users" where the username is equal to the string "$username" and the password is equal to the string "$password123". Since it is a user-controlled application, we can manipulate the username and password. So, when I change the username from 'username' to 'admin#' it will automatically comment out the query. Thus, I entered 'admin#' as the username and typed anything for the password, thereby obtaining the root flag.

![appoinment](/assets/img/username.png)

![appoinment](/assets/img/admin.png)

![admin](/assets/img/admin11.png)
![flag](/assets/img/flag.png)

#### Learning Through the Appoinment Machine
* directory is called as folder in web-application termilogy.
* gobuster: a fast brute-force tool to discover hidden URLs, files, and directories within websites. This will help us to remove/secure hidden files and sensitive data.
* SQL injection, also known as SQLI, is a common attack vector that uses malicious SQL code for backend database manipulation to access information that was not intended to be displayed.

