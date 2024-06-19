---
Title: Brute it 
categories: [SWS101,CTF]
tags: SWS 101
---

## Brute it 

### Scanning the Ip Address 

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 6.34.56 PM.png>)

2 port are open on this machine that are port 22 and port 80.

### Exploring the website 

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 6.35.23 PM.png>) 

I didn't find any inportant things on the IP when i browse. it was just a apache ubuntu default page.

### Bruteforcing the IP Address 

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 6.38.23 PM.png>) 

I found one hidden dorectory while bruteforcing the ip address.

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 6.38.53 PM.png>)

Browsing the website I got this login form.

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 6.39.28 PM.png>)

I Inspect the page a got the username for the login form it was **admin**

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 8.28.31 PM.png>)

Then I used hydra to crack the password using the username. and the password is **xavier**

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 8.31.27 PM.png>)

Then I got the web flag. There is a RSA private key let's see what is inside that.

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 8.34.57 PM.png>)

Ohh I got the RSA private key now let's encode that using a special tool called **john the ripper**

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 8.03.40 PM.png>) 

I have created a file called bruteit and paste the RSA private. Now the following code will tell john to figure out which kind of hash to brute force.

    john bruteit --wordlist=/usr/share/wordlists/rockyou.txt

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 8.46.18 PM.png>)

Then I will convert the SSH key file to John the Ripper format

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 8.04.14 PM.png>) 

Using the following code will attempt to crack the password hashes in a file named bi using the passwords listed in the rockyou.txt wordlist.

    john bi --wordlist=/usr/share/wordlists/rockyou.txt 

### User flag

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 8.05.11 PM.png>) 

Now I to secure sensitive files, such as private keys, by ensuring that only the file's owner can access and modify it. For instance, IN here I have kept file name bruteit which contains a private SSH key, setting its permissions to 600 ensures that only the owner can use the key, which enhances security.For that run the following command.

    chmod 600 bruteit 

The we will use shh to secure SSH connection to the remote server 10.10.28.13 as the user john, using the private key file bruteit for authentication.If the private key bruteit matches the corresponding public key on the remote server and the server accepts the key, the connection will be established without requiring a password.For that run the following command.

    ssh -i bruteit john@10.10.28.13

Thus I got the user flag

### Root flag 

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 9.04.15 PM.png>)

Again the root was encrypted so we will do the same for what we did in the user flag.

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 8.06.01 PM.png>)

I created a folder called **root** and paste the encrypted key i just got.Then I  got the password for root it is football.

![alt text](<../Image/CTF/brute_it/Screenshot 2024-06-11 at 8.06.17 PM.png>)

following the previous step that i did on the user flag I got the root flag.
