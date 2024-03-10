---
Title: SWS101 Flipped_class
categories: [SWS101,Flipped_1]
tags: SWS 101
---

## Networkings
----
### Before and after the knoweledge of Internet and Wifi
I used to think that the internet operated by sending signals from our devices to a satellite, which then relayed them back to other devices, creating connections within our society. Then, about Wi-Fi, I thought it was another form of the internet that didn't necessarily require us to carry a SIM card to have internet access.

After taking this class on networking, I've learned a lot about how the internet works, including concepts like IP addresses and NAT. This class has sparked my interest in cybersecurity, as I can now see the beauty in communication through networks.

Understanding networking has shown me the intricate connections and protocols that facilitate communication between devices, whether they're in the same room or across the globe. It's fascinating to see how data travels through networks, and it has opened my eyes to the importance of securing these pathways to protect sensitive information

### NAT(Network Address Translation)
NAT is a service used in routers, and its purpose is to translate a set of IP addresses to another set of IP addresses. The reason for having NAT services is to help preserve the limited amount of IPv4 addresses available around the world. When IPv4 was created, engineers didn't realize how large the internet would become because there were only 4 billion IPv4 addresses available, and they thought that would be enough. However, they were wrong. So, in order to prevent a shortage of public IPv4 addresses, engineers developed NAT and IPv4 private addresses.

There are two types of IPv4 addresses: private and public IP addresses. Public IP addresses are publicly registered on the internet, and we must have a public IP address to access the internet. Private IP addresses are not publicly registered, and we cannot directly access the internet with a private IP address. Private IP addresses are used internally, such as inside homes or businesses. If every device had a public IP address, we would run out of public IP addresses. So, we can have our own router in our home, and the private IP addresses will be translated by NAT in the router to the public IP address. In this way, it also translates the public IP address to private IP addresses because if a computer on the internet wants to communicate with a computer on a private network, the public IP address should also be translated by NAT to a private IP address for that computer.

In the future, we won't need NAT or private IP addresses because engineers developed a new version called IPv6. This is because IPv4 can produce over 340 undecillion IP addresses. With that many numbers, we will never run out of IP addresses.

### Bandit game 
#### level 0 => 1
I logged into the game using shh bandit0bandit.labs.overthewire.org -p 2220 as the user name and the is password is given as bandit0.
The password for level 1 is in a readme file located in a home directory i used cat readme to retrive the password.

#### level 1 => 2
then in this level the password for level 2 is in - located in a home directory.firstly i used  ls -apls which lists the names and features of file directories. Then i used cat ./- which it displays the content of the file in that directory.

#### level 2 => 3
the password here is stored in a spaces in the file name. first i used the ls -apls to list all the content and used the cat command to retrive the password for next level.

#### level 3 => 4
the password is stored in a hidden file so iu used the ls -all which displays all the hidden file and used cat to retrive the password which is in the .hidden. 

#### level 4 => 5
The password is located within a human-readable file in the "inhere" directory. After inspecting the directory with ls -apls, it revealed 48 files. To avoid manually checking each file, the command find -type f | xargs file was utilized. This command searches for regular files within the current directory and its subdirectories, and then uses the file command to determine their types. Upon finding a file labeled as ASCII text, namely "07", the cat command was employed to extract the password for the next level.

#### level 5 => 6
The password for next level is stored in a inhere directory which is human-readable,with 1033bytes in size that is not executable. so i i used like previous one that is find -type f -size 1033c ! executable. 

#### level 6 => 7
the next level password is stored somewhere in a server which is owned by user bandit7 and group bandit6 in 33c in size so. i used the find / -type f -user bandit7 -group bandit6 -size 33c. after that i used cat command and retrived the password.

#### level 7 => 8
The password for next level is in the next level is stored in a file called data.txt but in millionth. so i tried to use the cat data.txt but it shows lots for password. Then i used the command strings data.txt | grep "millionth" which extracts printable strings from the file "data.txt" and then searches for the occurrence of the word "millionth" within those strings.new thing i learned is grep searches for specified patterns within text files or streams and prints the lines that match those patterns.

#### level 8 => 9
The password for next level is stored in the file data.txt and is the only line of text that occurs only once.The code sorts the lines in "data.txt" alphabetically and then displays only the unique lines, omitting any duplicated lines.

#### level 9 => 10
the password here is stored in file data.txt in a human readable strings,  preceded by several ‘=’ characters. so i used strings data.txt | grep "="
it show the strings which has "=" character.

#### level 10 => 11
the password for next level is stored in file data.txt which contain base64 encoded data.The data.txt contains 1 line that was encoded in base64. so i used  base64 -d data.txt to decode the data.txt file.

#### level 11 => 12
The password is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.So the data.txt file contains 1 line that was encrypted with the ROT13 algorithm. In order to decrypt it, I have to replace every letter by the letter 13 positions ahead.i used the cybercheff website to decrypt it the message that i got using command cat data.txt

#### level 12 => 13
This is the most challanging level than the rest as the password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed.
The main this i did on this level was i  created a directory under /tmp and moved the data in it then i compressed and decompressed it for a multiple times until the it opens a file with ascii text.

#### level 13 => 14
For this level, I don't get the next password, but I get a private SSH key that can be used to log into the next level. I ran "ls" I saw a file named sshkey.private which must be the SSH private key the hint was talking about. In order to log into the bandit14 users profile I ran "ssh -i sshkey.private bandit14@localhost". The -i means that I am using an identity file in order to login to bandit14 on the server since all of the bandit users are on the same machine. After I logged into bandit14 I ran "cd /etc/bandit_pass/" as specified on the hint and then I read file bandit14 password.

#### level 14 => 15
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost. According to the hint we have to connect to port 30000 on localhost and we have to send a string containing the current password. To do this I ran "nc localhost 30000" and once I saw that I was connected I pasted the password for bandit14 and then I received the password for next level.

#### level 15 => 16
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.After establishing the SSL/TLS connection using openssl s_client -connect localhost:30001, then I encountered the "HEARTBEATING" and "Read R BLOCK" messages, indicating potential issues with the connection. Following the helpful note, the user utilized the -ign_eof option with openssl s_client to ignore the input eof, resolving the connection problem. then I submitted the password for the current level and received the password for the next level.

#### level 17 => 18
In the home directory, there are two files: "passwords.old" and "passwords.new." The password for the next level is in "passwords.new" and is the only line different from "passwords.old." As per the instruction upon discovering two files, "passwords.old" and "passwords.new," the I employed the diff command to compare their contents. This revealed that only one line had changed between the files, containing the password for the next level. With this password extracted, the I moved to the next level.

#### level 18 => 19
To overcome the ".bashrc" modification that logs me out upon login, I used the "ssh" command with the "-t" option. This simulates a real terminal session. By connecting to Bandit Level 18 and executing "ls", I found the "readme" file with the next level's password.

#### level 19 => 20
This level involves using a special program, "bandit20-do", which allows running commands as if I were another user. Ordinarily, we can't read files that we don't have permission to access, but this program bypasses that restriction.

