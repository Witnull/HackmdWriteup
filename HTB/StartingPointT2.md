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

![image](HackmdWriteup/blob/main/HTB/StartingPointT2_img/c1_10_1.png)

With the hint from all above questions, this will be a SQL injection task:

I try input username: `admin' #` and password can be anything.

![image](HackmdWriteup/blob/main/HTB/StartingPointT2_img/c1_10_2.png)

After pressed login, it redirect to this page:

![image](HackmdWriteup/HTB/StartingPointT2_img/c1_f.png)

    A: Congratulations

### Task 11: Submit root flag

:::success
Flag: e3d0796d002a446c0e622226f42e9672
:::

---

![image](HackmdWriteup/HTB/StartingPointT2_img/c1_f.png)

---

---

## Machine: Sequel

### Task 1: During our scan, which port do we find serving MySQL?

![image](HackmdWriteup/HTB/StartingPointT2_img/c1_f.png)

    A: 3306
