# Mini Project: Application Load Balancer Deployment
## Introduction
This project demonstrates the deployment and configuration of an **Application Load Balancer (ALB)** in AWS. An ALB distributes incoming HTTP/HTTPS traffic across multiple EC2 instances, enabling higher availability, fault tolerance, and scalability of web applications. Unlike the Classic Load Balancer, ALB operates at the application layer (Layer 7), allowing advanced routing features such as path-based routing, host-based routing, and SSL termination. It continuously performs health checks to ensure only healthy instances receive traffic.

## Prerequisites
AWS Account with access to EC2, ALB, and IAM services
- Multiple running EC2 instances the same VPC and region
- Security Groups configured to allow:

    - Inbound HTTP (80) / HTTPS (443) traffic
    - Inbound SSH (22) traffic (optional)
- Web Server Installed (e.g., Apache/Nginx) on each instance
- IAM Permissions to create and manage ALBs.

## Steps to Setup Application Load Balancer.
### Step 1: Launch Instances
1. Create 2 Instance of Home Page
![instance](1.png)

    ![instance](2.png)

2. Create 2 Instance of Laptop Page
![instance](3.png)

    ![instance](4.png)

3. Create 2 Instance of Mobile Page
![instance](5.png)

    ![instance](6.png)

### Step 2: Create an Application Load Balancer
1. Go to Load Balancer
![instance](7.png)

2. Select Application Load Balancer
![instance](8.png)

3. Name the Application Load Balancer
![instance](9.png)

4. Select all Availability Zones.
![instance](10.png)

5. Manage Security Group
![instance](11.png)

6. Create Target Group 1 (Home).
- Click on Create target group
![instance](12.png)
 - Select instance
![instance](13.png)
- Give name to target group(home-TG)
![instance](14.png)
- Insert health check path 
![instance](15.png)
- Select home instance
![instance](16.png)
- Click on include as pending below and click on create target group
![instance](18.png)

7. Create Target Group 2 (Laptop).
- Give name to target group(laptop-TG)
![instance](19.png)
- Insert health check path 
![instance](20.png)
- Click on create target group
![instance](21.png)

8. Create Target Group 3 (Mobile).
- Give name to target group(Mobile-TG)
![instance](22.png)
- Insert health check path 
![instance](24.png)
- Click on create target group
![instance](23.png)

9. Add Default action (Home-TG)
![instance](25.png)

10. Add Listener Rules
- Go to Rule and add Laptop Rule
![instance](26.png)
![instance](27.png)
![instance](28.png)
- Go to Rule and add Mobile Rule
![instance](29.png)

11. Copy the DNS Command

### Step 3: Testing the ALB
1. Output for Home Page 
![instance](30.png)

    ![instance](31.png)

2. Output for Laptop Page
![instance](32.png)

    ![instance](33.png)

3. Output for Mobile Page
![instance](34.png)

    ![instance](35.png)

## Summary
This mini project demonstrates the deployment and configuration of an AWS Application Load Balancer (ALB) to efficiently distribute incoming web traffic across three EC2 instances. By using a user-data script during instance launch, each server automatically runs a web server and serves unique content, allowing easy verification of traffic distribution.

