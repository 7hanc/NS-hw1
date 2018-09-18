# Network-Security (hw1)
# Homework 1 
> Goal: Hack Bob’s blog at http://140.113.194.80:xxxxx/blog/, and get the intimate picture he uploaded last night.   

> Hints & Guides
  > Some useful materials related to this project
  * PHP 
    * Bob builds his website with PHP.
  * MySQL 
    * Bob uses MySQL to store his blog data.
  * phpMyAdmin 
    * handle the administration of MySQL over the web.
  * Base64 encodin
    * Frequency Analysis (break some simple encryption method over certain plaintext(such as english language).
  * XOR encryption
    * the key and the plaintext to get ciphertext
  * Hash function and Hash Collision
  * robots.txt 
    * We use robots.txt to inform the search engine crawlers or robots about which files or path of the website should not be scanned or accessed.
  * Temporary files & Git 
    * Some sensitive files may leak a lot of information if you put them on the public web server.
  
> Answer
* Step1: Find the rebots.txt   
Go to http://140.113.194.80:20025/robots.txt   
robot.txt: ![robot](https://i.imgur.com/EtDnW1c.jpg)   
However, http://140.113.194.80:20025/phpMyAdmin_NS_pRojEct_2017 need account and password, because I don’t have, so I can’t enter it.   
http://140.113.194.80:20025/backup.tar.gz there are serveral php files in the folder.   
http://140.113.194.80:20025/blog/memorandum.txt is not found.   
* Step2. Find the Temporary file   
In http://140.113.194.80:20025/blog/.memorandum.txt.swp, then opened it with notepad++ and was a encrypted file.
* Step3. Use base64 decryption method   
Type `base64 -d` in Ubuntu to decrypt the file. -> Get another encrypted file.
* Step4. Use xor brute force attack   
XOR cracker (brute force attack): https://wiremask.eu/tools/xor-cracker/   
It will anylaze the files and show the probability of the key lengths.
![1](https://i.imgur.com/8yx3qJy.png)
**Possible keys**
![2](https://i.imgur.com/F1hKdKA.jpg)
***
Get account and password to enter MySQL database.
***
* Step5. Enter MySQL database   
Find the password (Still can not enter Bob's blog)
* Step6. Use hash function decryption method   
Breake hash function: https://www.tobtu.com/mysql323.php 
***
**Finally get the password!!!** 
***
Step7. Get the intimate picture   
Use the decrypted password to enter Bob's blog.   
<img src="https://i.imgur.com/5tNAyBS.png" width=100 height=100 />
 
 
