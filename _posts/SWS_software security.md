---
Title: SWS101  
categories: [SWS101,journel]
Tags: SWS 101
---

### Networkings
---
### Before the knoweledge of networking  
Before this class, I used to think that a network operated by sending signals from our devices to a satellite, which then relayed them back to other devices, creating connections within our society.




### Bandit game 
### level 0 => 1
I logged into the game using shh bandit0bandit.labs.overthewire.org -p 2220 as the user name and the is password is given as bandit0.
The password for level 1 is in a readme file located in a home directory i used cat readme to retrive the password.

### level 1 => 2
then in this level the password for level 2 is in - located in a home directory.firstly i used  ls -apls which lists the names and features of file directories. Then i used cat ./- which it displays the content of the file in that directory.

### level 2 => 3
the password here is stored in a spaces in the file name. first i used the ls -apls to list all the content and used the cat command to retrive the password for next level.

### level 3 => 4
the password is stored in a hidden file so iu used the ls -all which displays all the hidden file and used cat to retrive the password which is in the .hidden. 

### level 4 => 5
The password is located within a human-readable file in the "inhere" directory. After inspecting the directory with ls -apls, it revealed 48 files. To avoid manually checking each file, the command find -type f | xargs file was utilized. This command searches for regular files within the current directory and its subdirectories, and then uses the file command to determine their types. Upon finding a file labeled as ASCII text, namely "07", the cat command was employed to extract the password for the next level.

### level 5 => 6
The password for next level is stored in a inhere directory which is human-readable,with 1033bytes in size that is not executable. so i i used like previous one that is find -type f -size 1033c ! executable. 

### level 6 => 7
the next level password is stored somewhere in a server which is owned by user bandit7 and group bandit6 in 33c in size so. i used the find / -type f -user bandit7 -group bandit6 -size 33c. after that i used cat command and retrived the password.

### level 7 => 8
The password for next level is in the next level is stored in a file called data.txt but in millionth. so i tried to use the cat data.txt but it shows lots for password. Then i used the command strings data.txt | grep "millionth" which extracts printable strings from the file "data.txt" and then searches for the occurrence of the word "millionth" within those strings.new thing i learned is grep searches for specified patterns within text files or streams and prints the lines that match those patterns.

### level 8 => 9
The password for next level is stored in the file data.txt and is the only line of text that occurs only once.The code sorts the lines in "data.txt" alphabetically and then displays only the unique lines, omitting any duplicated lines.

### level 9 => 10
the password here is stored in file data.txt in a human readable strings,  preceded by several ‘=’ characters. so i used strings data.txt | grep "="
it show the strings which has "=" character.

### level 10 => 11
the password for next level is stored in file data.txt which contain base64 encoded data.The data.txt contains 1 line that was encoded in base64. so i used  base64 -d data.txt to decode the data.txt file.

### level 11 => 12
The password is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.So the data.txt file contains 1 line that was encrypted with the ROT13 algorithm. In order to decrypt it, I have to replace every letter by the letter 13 positions ahead.i used the cybercheff website to decrypt it the message that i got using command cat data.txt

### level 12 => 13
