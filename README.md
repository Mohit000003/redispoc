




# REDIS POC

| **Author**            | **Created on** | **Version** | **Last updated by**       | **Last edited on** | **Reviewer**      |
|-----------------------|----------------|-------------|----------------------------|---------------------|-------------------|
| Mohit kumar     | 10-02-2025       | Version 1 | Mohit kumar       | 11-02-2025       | Komal Jaiswal  |



## REDIS

The purpose of this POC is to evaluate Redis (Remote Dictionary Server) which is a  open-source in-memory database that stores data in key-value format. It’s widely used for caching, real-time analytics, message brokering, and more.


## Redis Installation on Ubuntu

This document provides step by step guide to install and configure Redis-server on Ubuntu.


## Installation Steps

### Step 1: Update System Packages

Before starting the installation, ensure your system packages are up-to-date.

``` bash
sudo apt update
```
### Step 2: Install Redis and check the version 

To install Redis, use the apt package manager and check the version of redis

``` bash
sudo apt install redis-server -y

redis-server -v
```

### Step 3: Start Redis Service
Run the following command to start the Redis service: When you start the Redis service, it will begin running and be available for use. Enabling Redis ensures it will automatically start every time the system boots, providing persistent availability.

``` bash
sudo systemctl status redis

sudo systemctl enable redis
```

### Step 4: Check Redis Service Status
To confirm that Redis is running successfully, use the following command:

``` bash
sudo systemctl status redis
```


### Step 5: Configure Redis
To set up a password  for Redis and change its bind address to your private ip so that you can use that internally not allowing access to everyone we can use following steps  :
1. Open the Redis configuration file:

``` bash
sudo nano /etc/redis/redis.conf
```


#### 2. Set a Password:
Find the line with # requirepass foobared and replace it with:

``` bash
requirepass <your_password>
```


#### 4. Save and Close the file.

#### 5. Restart Redis
To apply these changes, restart Redis service:

``` bash
sudo systemctl restart redis
```

#### 6. Connect to Redis with Password after entering to the  cli 

Now, you can authenticate to Redis using the password.

Start the Redis CLI: Here if we directly enter some command after entering  into the cli it will give error as we need to authenicate it other wise it will show below thing

``` bash
redis-cli
Enter something 
(ERROR) NOAUTH Authentication Required
```

thats why use the below command to get access inside the redis-cli


``` bash
redis-cli
AUTH <password> 
```

or you can try in this way also instead of writing it manually everytime not recommed to do this as it is not best practice to do so

``` bash
redis-cli -a your_password_here
```




#### 7. Verify the Connection: 
After authenticating, you can test the connection by running a simple command PING:

``` bash
PING
```
If you see PONG, it means authentication is successful.



#### 8. SET and GET values in Redis (Additional) to check further if it is working fine for Storing and Retrieving Data in Redis :- 
SET is used to store data in Redis.

``` bash
SET mykey "<value>"
```
GET is used to retrieve the value stored under the specified key.
``` bash
GET mykey
```

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


