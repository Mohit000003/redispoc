



# REDIS POC

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer**      |
|-----------------------|----------------|-------------|----------------------------|---------------------|-------------------|
| Mohit kumar     | 10-02-2025       | Version 1 | Mohit kumar       | 10-02-2025       | Komal Jaiswal  |



## REDIS

The purpose of this POC is to evaluate Redis (Remote Dictionary Server) which is a  open-source in-memory database that stores data in key-value format. It’s widely used for caching, real-time analytics, message brokering, and more.

## Hardware Pre-requisites

| **Requirement**        | **Details**                  |
|------------------------|------------------------------|
| **OS**                 | Ubuntu 24.04 or 22.04 |
| **RAM**                | 2 GB min.                 |
| **Disk Space**         | 100 MB or more               |
| **Processor**          | Dual-core recommended   
| **Instance used**        | t2.micro
| **Network**            | Port 6379 open for redis  
  **SSH**                 |   PORT 22


## Redis Installation on Ubuntu

This document provides step by step guide to install and configure Redis-server on Ubuntu.


## Installation Steps

### Step 1: Update System Packages

Before starting the installation, ensure your system packages are up-to-date.

``` bash
sudo apt update
```
### Step 2: Install Redis and check the version 

To install Redis, use the apt package manager

``` bash
sudo apt install redis-server -y

redis-server -v
```
![image](https://github.com/user-attachments/assets/c62b0010-a148-4327-baa3-07bbbc36c77b)

### Step 3: Start Redis Service
Run the following command to start the Redis service:

``` bash
sudo systemctl status redis

sudo systemctl enable redis
```

### Step 4: Check Redis Service Status
To confirm that Redis is running successfully, use the following command:

``` bash
sudo systemctl status redis
```
![image](https://github.com/user-attachments/assets/c2233b26-43fe-42e8-9936-facd7de5e103)

### Step 5: Configure Redis
To set up a password  for Redis and change its bind address to your private ip so that you can use that internally , follow these steps:
1. Open the Redis configuration file:

``` bash
sudo nano /etc/redis/redis.conf
```
![image](https://github.com/user-attachments/assets/17334b7c-ec83-4435-b240-bc31237d9a1c)

#### 2. Set a Password:
Find the line with # requirepass foobared and replace it with:

``` bash
requirepass <your_password>
```
![image](https://github.com/user-attachments/assets/84fa6cde-d041-42ba-8019-e85a8f1dbbf4)

![image](https://github.com/user-attachments/assets/cd456993-9e48-44da-b13c-50ae419887d0)


#### 4. Save and Close the file.

#### 5. Restart Redis
To apply these changes, restart Redis service:

``` bash
sudo systemctl restart redis
```

#### 6. Connect to Redis with Password
Now, you can authenticate to Redis using the password.

Start the Redis CLI: Here if we directly enter some command after entering cli it will give error as we need to authenicate it other wise it will give error as mentioned in the below screenshot

``` bash
redis-cli
AUTH <password> 
```
![image](https://github.com/user-attachments/assets/2e890581-a1e0-404e-9c6e-7bfea5c7623b)

![image](https://github.com/user-attachments/assets/751ea85c-468e-4b0b-af9b-91c6fdf7df07)



or you can try in this way also instead of writing it manually everytime not recommed to do this as it is not best practice to do so

``` bash
redis-cli -a your_password_here
```
![image](https://github.com/user-attachments/assets/0a722712-d1be-4277-ab73-a42b4a0344c0)



#### 7. Verify the Connection: 
After authenticating, you can test the connection by running a simple command PING:

``` bash
PING
```
If you see PONG, it means authentication is successful.

![image](https://github.com/user-attachments/assets/2e890581-a1e0-404e-9c6e-7bfea5c7623b)

#### 8. SET and GET values in Redis: (Additional)
SET is used to store data in Redis.

``` bash
SET mykey "<value>"
```
GET is used to retrieve the value stored under the specified key.
``` bash
GET mykey
```
 ![image](https://github.com/user-attachments/assets/ceea7339-ddbe-4945-8049-b081f8bf7d7b)
### Contact Information

| **Name** | **Email address**            |
|----------|-------------------------------|
| Mohit kumar   |  mohit.kumar@mygurukulam.co          |


### References

| Link                                                                                                           | Description                                               |
|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|
| [Redis Documentation - Installation](https://dev.to/iqquee/how-to-setup-redis-on-linux-4h06) | Document format followed from this link.                 |
| [Introduction to Redis](https://www.geeksforgeeks.org/introduction-to-redis-server/) | This link gives the Introduction to Redis. |
| [Redis Documentation - GitHub](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/main/OT%20MS%20Understanding/Database/Redis/Redis%20POC/README.md) | Link to Redis documentation on GitHub. 
