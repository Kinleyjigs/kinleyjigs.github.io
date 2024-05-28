---
Title: Ignite
categories: [SWS101,CTF]
tags: SWS 101
---

## Ignite 

![alt text](../Image/CTF/ignite/ignite.jpeg)

**HELLO guys!**
This is a ctf journal on Ignite and i will be guiding you guys how to do this machine step by steps.

### Exploring the website
Exploring the website I have got this a Fuel CMS page with version 1.4.  I search for exploit code that I could use to gain access to the machine.

![text](../Image/CTF/ignite/1.png) 

I used the **searchsploit** module to find the exploit code for Fuel CMS 1.4. It searches the Exploit Database — a comprehensive database of exploits, shellcode, and security vulnerabilities.

![text](../Image/CTF/ignite/2.png) 

Then I downloaded the first python script by running the following command:

    searchsploit -m php/webapps/50477.py

![text](../Image/CTF/ignite/3.png) 

### looking what is inside the python file 

![text](../Image/CTF/ignite/4.png) 

Changing the Ip address in the python script I ran the python file where it opens a command prompt.

![alt text](../Image/CTF/ignite/connecting_cmd.png) 

### Reverse Shell 
Then I will do a reverse shell by running a code that I copied from a cheetsheet that is pentest monkey.

![alt text](../Image/CTF/ignite/reverseshell.png)

From terminal I did netcat on port 4444 and it was successful now I can access the machine from my terminal.

![text](../Image/CTF/ignite/nc.png) 

### Rootflag
#### rootflag for user

![text](../Image/CTF/ignite/root1.png)

![text](../Image/CTF/ignite/root2.png) 
 
#### Rootflag for root

![text](../Image/CTF/ignite/1stflag1.png)

![text](../Image/CTF/ignite/rootflag.png)


**Thank you! 😊**

