# Lab 5 – Build a Database Server (AWS)

## Author

* **Name**: Swetha D
* **Register Number**: 212223040222
* **Date of Submission**: 13/03/2026

---

## Objective

The objective of this experiment is to understand how to deploy and configure a database server in AWS. This lab focuses on launching an EC2 instance, installing a database management system (DBMS), configuring basic database settings, creating a sample database, and validating connectivity to the database server.

---

## Prerequisites

* Basic understanding of cloud computing concepts
* AWS account or AWS Academy Lab access
* An existing VPC and EC2 knowledge (from previous labs)
* Basic knowledge of Linux commands and SQL

---

## Tools Used

* AWS Management Console
* Amazon EC2
* Security Groups
* SSH Client (Terminal / PuTTY)
* MySQL / MariaDB / PostgreSQL (any one)

---

## Tasks Performed

### Task 1: Launch EC2 Instance for Database Server

Launch a new EC2 instance using Amazon Linux 2 AMI. Select an appropriate instance type and configure key pair and security group.

---

### Task 2: Configure Security Group for Database Access

Modify the security group to allow:

* SSH (Port 22) for remote access
* Database port (e.g., MySQL – 3306 or PostgreSQL – 5432)

---

### Task 3: Connect to EC2 Instance

Connect to the EC2 instance using SSH from your local machine.

---

### Task 4: Install Database Server

Install a database server software such as MySQL, MariaDB, or PostgreSQL on the EC2 instance using package manager commands.

---

### Task 5: Start and Configure Database Service

Start the database service and configure basic settings such as root password and user privileges.

---

### Task 6: Create a Sample Database

Create a sample database and a table inside it. Insert a few records into the table.

---

### Task 7: Test Database Connectivity

Test the database server by connecting to it locally or remotely and performing basic SQL queries.

---

## Workflow (Student Explanation)

1. I logged in to the AWS Management Console and launched a new EC2 instance using the Amazon Linux 2 AMI. I selected a suitable instance type (such as t2.micro), created or selected an existing key pair, and configured a security group during the setup process.

2. I modified the security group settings to allow inbound traffic for SSH (Port 22) from my IP address and enabled the required database port (for example, MySQL – 3306) so that the database server could be accessed when needed.

3. After the instance was launched, I connected to it from my local machine using SSH with the key pair file:
   `ssh -i mykey.pem ec2-user@<public-ip-address>`

4. Once connected to the instance, I updated the system packages and installed the database server (for example, MySQL) using the package manager:
   `sudo yum update -y`  
   `sudo yum install mysql-server -y`

5. I started the database service and enabled it to start automatically on boot. Then, I secured the installation by setting a root password and configuring basic security settings:
   `sudo systemctl start mysqld`  
   `sudo mysql_secure_installation`

6. After configuring the database server, I logged in to MySQL and created a sample database and table. I inserted a few records into the table using SQL commands such as CREATE DATABASE, CREATE TABLE, and INSERT.

7. Finally, I tested the database connectivity by logging into the database locally and running SELECT queries to verify that the inserted data was stored and retrieved successfully.

---

## Output Screenshots (Attach 3)

### Screenshot 1: EC2 Instance for Database Server

<img width="1920" height="967" alt="image" src="https://github.com/user-attachments/assets/52feb724-2997-452e-9cd7-cfcf9ae1ca97" />


---

### Screenshot 2: Database Service Running

<img width="1920" height="967" alt="image" src="https://github.com/user-attachments/assets/09886eba-953a-4f31-905f-0fa78f42a8a3" />


---

### Screenshot 3: Sample Database and Table

<img width="1920" height="967" alt="image" src="https://github.com/user-attachments/assets/c4de12ea-a2d7-4464-956e-157936a45441" />


---

## Result

This experiment demonstrated how to build a database server in AWS using an EC2 instance. By installing and configuring a DBMS, creating a sample database, and testing connectivity, the fundamentals of hosting and managing a cloud-based database server were underst
