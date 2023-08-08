# IMPLEMENTING A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).
Client-Server refers to an architecture in which two or more computers are connected together over a network to send and receive requests between one another. In their communication, each machine has its own role: the machine sending requests is usually referred as “Client” and the machine responding (serving) is called “Server”.
![Screenshot 2023-08-07 091137](https://github.com/opeyemiogungbe/Pbl_project5/assets/136735745/db1cc7e5-de4d-425b-bcb8-95bc783f5175)
In the picture above, a machine that is trying to access a Web site using Web browser or simply ‘curl’ command is a client and it sends HTTP requests to a Web server (Apache, Nginx, IIS or any other) over the Internet.

### Step 1. reate and configure two Linux-based virtual servers (EC2 instances in AWS).

`Server A name - mysql server`

`Server B name - mysql client`

![Screenshot 2023-07-25 082849](https://github.com/opeyemiogungbe/Pbl_project5/assets/136735745/9d4fb5d6-14c5-4ee7-9bf0-3a30f774e54b)

On mysql server Linux Server install MySQL Server software and On On mysql client Linux Server install MySQL Client software. Also i'll use mysql server's local IP address to connect from mysql client by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups, allowing access only to the specific local IP address of ‘mysql client’.

![Screenshot 2023-07-25 155110](https://github.com/opeyemiogungbe/Pbl_project5/assets/136735745/7fd4d085-ffa0-41de-a72d-f23f9b68637c)

I will also be configuring MySQL server to allow connections from remote hosts by `sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf` and setting the bind adress to;
```
bind address       =0.0.0.0
```

Next i'll be creating a user 'ope' with the Mysql-client ip address and set a password for it

![Screenshot 2023-07-25 165745](https://github.com/opeyemiogungbe/Pbl_project5/assets/136735745/a4666dec-c844-4902-828c-b19a99005b15)

I'll also grant privileges  to ope to have access to Mysql-server and flush all queries

![Screenshot 2023-07-25 165807](https://github.com/opeyemiogungbe/Pbl_project5/assets/136735745/185c41ea-7e8b-452a-aa1e-56e878426e52)

![Screenshot 2023-07-25 165829](https://github.com/opeyemiogungbe/Pbl_project5/assets/136735745/3d03083a-af3f-4367-9bea-90c1e629c098)

![Screenshot 2023-07-25 170225](https://github.com/opeyemiogungbe/Pbl_project5/assets/136735745/dd13d42c-2bc6-4f6e-847a-52972ab0d34b)

Now that all my configuration is done, i will try to acess Mysql-server from Mysql-client to see if everything works fine

![Screenshot 2023-07-25 172112](https://github.com/opeyemiogungbe/Pbl_project5/assets/136735745/5bc84b00-8932-4587-816d-c10b4f40fd90)

The above image shows i can successfully make connections from Mysql-client to Mysql-server hence making this project sucessful.
