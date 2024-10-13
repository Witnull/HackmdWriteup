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