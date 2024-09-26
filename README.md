# AWS Application Load Balancer Demo

This repository provides a demonstration of how to configure and deploy an **AWS Application Load Balancer (ALB)** to distribute web traffic across multiple EC2 instances. The demo covers step-by-step instructions on setting up an ALB, configuring IIS on EC2 instances, and testing the traffic distribution.

## Aim
The goal of this demo is to improve application scalability and ensure high availability by routing incoming HTTP requests to healthy instances efficiently.

## Steps

### 1. Launch EC2 Instances
- Launch two **EC2 instances** with **Windows Server 2022** (or a version of your choice) using the **t2.micro** instance type.
- Configure instance details, set up storage, and create a security group to allow **RDP (port 3389)** and **HTTP (port 80)** access.
- Launch the instances and connect to them using **RDP**.

### 2. Install IIS on EC2 Instances
- Once connected via RDP, use **Server Manager** to install the **IIS Web Server** on both EC2 instances.
- After installation, verify by navigating to `http://localhost` on both instances to see the IIS default page.

### 3. Create a Target Group
- Go to **Target Groups** under the EC2 Dashboard.
- Create a target group for the **EC2 instances** with **HTTP (port 80)** as the protocol.
- Configure health checks and register both instances in the target group.

### 4. Create an Application Load Balancer (ALB)
- In the EC2 Dashboard, navigate to **Load Balancers** and create an **Application Load Balancer**.
- Name the ALB, set it to **internet-facing**, and configure it to route **HTTP (port 80)** traffic.
- Assign a security group to allow HTTP traffic and associate the ALB with the previously created target group.
- Review and create the load balancer.

### 5. Test the ALB
- Once the ALB is created, copy its **DNS name** and open it in a web browser.
- The ALB will distribute traffic between the two EC2 instances running IIS.
- Refresh the page to verify that the traffic is balanced across both instances.

## Screenshots
- **EC2 instances launched successfully**
- **IIS installed on both EC2 instances**
- **Target group created and EC2 instances registered**
- **Application Load Balancer created successfully**
- **Testing the ALB DNS name to verify load balancing**

## Conclusion
By following these steps, you can set up and test an **Application Load Balancer** that efficiently distributes traffic, ensuring high availability and scalability for web applications.
