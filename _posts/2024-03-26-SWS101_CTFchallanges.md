---
Title: Pickle Rick
categories: [SWS101,CTF]
tags: SWS 101
---
## Pickle Rick
![alt text](../Image/pickle_rick.jpeg)
https://tryhackme.com/r/room/picklerick 


**HELLO guys!**
This is a ctf journal on pickle rick and i will be guiding you guys how to do this machine step by steps.

First don't forget to turn on the machine.

![alt text](../Image/CTF/Pickle_rick/pickle_rick1.png)

### Exploring the website
After I got my target ip Address and I browse that on my browser and I got this.

![alt text](../Image/CTF/Pickle_rick/pickle_rick2.png)

I inspect the page and got the username that is 'R1ckRul3s'

![alt text](../Image/CTF/Pickle_rick/pickle_rick3.png)

### Brute-forcing directories and files from the website
I brute force the ip adddress using **gobuster** and got a bunch of sites.

![alt text](../Image/CTF/Pickle_rick/pickle_rick4.png)

First I have checked the assets site and I have found a bunch of other files which were not important for me so I haven't focus on that much.

![alt text](../Image/CTF/Pickle_rick/pickle_rickassets.png)

In login.php I have got a login site.

![alt text](../Image/CTF/Pickle_rick/pickle_ricklogin.png)

In robots.txt site I have found a password 'Wubbalubbadubdub' 

![alt text](../Image/CTF/Pickle_rick/pickle_rickpass.png)

#### Trying the username and password on login page 
Now I will try login the page using the following username and password that I have got.
**Username**

    R1ckRul3s

**Password**

    Wubbalubbadubdub

![alt text](../Image/CTF/Pickle_rick/pickle_ricklogin1.png)

By di=oing that I have got a command panel site.

![alt text](../Image/CTF/Pickle_rick/pickle_rickl2.png)

Now I have tried the 'ls' command to list the file in there which I have found lists of files.ohh! one of them says 'Sup3rS3cretPickl3Ingred.txt' did I just get the  first ingredient.

![alt text](../Image/CTF/Pickle_rick/pickle_rickl3.png)

I have used 'cat' command to retrieve the data but the command was disabled.

![alt text](../Image/CTF/Pickle_rick/1_fail.png)

### Reverse shell
Now I have decided to pop open a reverse shell by executing a reverse shell script into the command section.

#### pentest monkey
I have used the pentest monkey python code to create a reverse shell because it is  comprehensive, ready-to-use scripts and cheat sheets that streamline and simplify penetration testing tasks.

![alt text](../Image/CTF/Pickle_rick/pentestmonkey.png)

Then use netcat to listen on my terminal 

![alt text](../Image/CTF/Pickle_rick/nc.png)

Now I have access to the machine.

![alt text](../Image/CTF/Pickle_rick/nc1.png)

#### first ingredient 

![alt text](../Image/CTF/Pickle_rick/firstingredient.png)

#### second ingredient

![alt text](../Image/CTF/Pickle_rick/1.png) 
![alt text](../Image/CTF/Pickle_rick/2.png)

#### Third ingredient

![alt text](../Image/CTF/Pickle_rick/3rdingredient.png)