# Building Multi-Tier Java Web Application on AWS Cloud Using Shell Scripts

## Overview
This project demonstrates how to deploy a **multi-tier Java web application** on **AWS Cloud** using **EC2 instances and shell scripts**. It is part of a series where we first deployed the application on-premises manually and then automated it with scripts. Now, we are taking the same architecture to AWS!

## Project Structure
```
               
│   ├── nginx_setup.sh      # Configures Nginx as a reverse proxy
│   ├── mysql_setup.sh      # Installs and sets up MySQL
│   ├── memcache_setup.sh   # Installs Memcached
│   ├── tomcat_setup.sh     # Deploys Tomcat server
│   ├── rabbitmq_setup.sh   # Configures RabbitMQ
│── README.md               # Project documentation
```

## Prerequisites
- AWS Account
- IAM Role with EC2 permissions
- AWS CLI installed
- SSH Key Pair for EC2 access

## Tools & Technologies Used
- **Amazon EC2** – Virtual Machines
- **Security Groups** – Access Control

- **Tomcat** – Java Application Server
- **Nginx** – Reverse Proxy & Load Balancing
- **RabbitMQ** – Message Broker
- **Memcached** – Caching
- **MySQL** – Relational Database
- **Shell Scripting** – Automation

## Setup & Deployment Steps
### Step 1: Configure AWS Environment
1. Create an **AWS IAM role** with necessary permissions.
2. Set up **Security Groups** for EC2 instances.
3. Install **AWS CLI** and configure credentials:
   ```sh
   aws configure
   ```
## Notes
⚠️ **You must update the IP addresses of your machines based on your AWS setup!**

### Step 2: Launch EC2 Instances
Use **AWS Management Console** or **AWS CLI** to create EC2 instances:
```sh
aws ec2 run-instances --image-id ami-12345678 --count 1 --instance-type t2.micro --key-name MyKeyPair --security-groups MySecurityGroup
```

### Step 3: Deploy and Configure Services
1. **SSH into each instance** and run the corresponding shell script:
   ```sh
   ssh -i MyKey.pem ec2-user@your-ec2-public-ip
   sudo bash nginx_setup.sh
   ```
2. Repeat for **MySQL, Memcached, RabbitMQ, and Tomcat**.

### Step 4: Integration & Testing
- Ensure that **Nginx routes traffic** correctly.
- Verify that **RabbitMQ handles messages** properly.
- Confirm that **Memcached improves caching** performance.
- Check **database connectivity** with MySQL.
- Deploy a sample **Java web app** on **Tomcat** and test end-to-end functionality.

## Architecture Diagram
![Project Architecture](./architecture.gif)![2025-02-0813-52-45online-video-cutter com-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/c6fa3901-e807-496b-9ca5-ade8203fc0b8)




## Next Steps
- Optimize deployment using **Terraform & Ansible**
- Integrate **AWS Managed Services** for scalability
- Implement **CI/CD pipelines** for automation

## Contributors
- **Mohamed Elteir**  


