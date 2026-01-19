# 🚀 Highly Available & Scalable Web Application on AWS

![Project Banner](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/aws-architecture-diagram.png)

## 🎯 Objective

The objective of this project is to design and deploy a **highly available, scalable, and monitored web application** on AWS by leveraging core cloud infrastructure services.
The project focuses on **availability, traffic-based scaling, monitoring, and security** best practices, aligned with real-world cloud support and operations scenarios.

---

## 🧩 Overview

In this project, a web application is deployed on **Amazon EC2 instances** running behind an **Application Load Balancer (ALB)**.
An **Auto Scaling Group (ASG)** ensures high availability and automatic scaling based on incoming traffic, while **Amazon CloudWatch** continuously monitors performance and health metrics.

The infrastructure is deployed inside a custom VPC with proper network isolation and secured using IAM roles and security groups.

---

## 🏗️ Architecture Overview

**User → Application Load Balancer → Auto Scaling Group → EC2 Instances**

• Multi-AZ deployment for high availability  

• Automatic scale-out and scale-in based on traffic 

• Continuous monitoring using CloudWatch 

---

## ✨ Key Highlights

✔ High availability using Application Load Balancer 

✔ Automatic scaling using Auto Scaling Group 

✔ Traffic-based scaling using ALB RequestCountPerTarget 

✔ Real-time monitoring and alerts via CloudWatch 

✔ Secure access using IAM roles 

✔ Custom VPC with public and private subnets 

✔ Health checks and self-healing infrastructure 

---

## 🛠️ Tools & Technologies Used

| AWS Services | Use case |
|-----------|-------|
| **Amazon EC2** | Web server hosting |
| **Elastic Load Balancing** | Traffic distribution |
| **Auto Scaling Group** | Automatic scaling & recovery |
| **Amazon VPC** | Network isolation |
| **AWS IAM** | Secure access control |
| **Amazon CloudWatch** | Monitoring & alarms |
| **Amazon EBS** | Instance storage |
| **Linux** | Ubuntu LTS |
| **Nginx** | Reverse proxy Server |

---

## ⚙️ Setup Process & Deployment Instructions

## 1️⃣ VPC & Networking
``` bash
Created a custom VPC with CIDR 172.10.0.0/16

Configured two public and private subnets across different Availability Zones

Attached an Internet Gateway with public subnet route table and updated route tables

Create a NAT Gatway and deploy on public subnets

Add NAT Gateway routes in both private subnets route table
```
## 2️⃣ Security Configuration
``` bash
Created Security Groups:

ALB SG: Allows HTTP (port 80) from the internet

EC2 SG: Allows HTTP only from ALB SG

Implemented least-privilege access
```
## 3️⃣ IAM Role
``` bash
Created an IAM role for EC2

Attached CloudWatchAgentServerPolicy

Avoided hard-coded credentials (best practice)
``` 
## 4️⃣ EC2 Launch Template
``` bash
Using with existing Amazon Machine Image(AMI) where are pre-installed Nginx web server and also pre-configured web application configuration code

These existing AMI are helps to deployed the web application across the muliple instances which will launched through Launch Template

Consistent configuration for all instances
``` 
## 5️⃣ Application Load Balancer
``` bash
Internet-facing ALB

Deployed across public subnets

Configured target group with health checks
``` 
## 6️⃣ Auto Scaling Group
``` bash
Linked to Launch Template

Minimum: 1 | Desired: 2 | Maximum: 4

Enabled ELB and EC2 health checks
``` 
## 7️⃣ CloudWatch Monitoring & Scaling
``` bash
Configured alarms for:

1. EC2 CPU Utilization

2. EC2 Status Check Failed

3. ALB UnHealthyHostCount

Enabled target tracking scaling using:

ALB RequestCountPerTarget

AWS automatically manages scaling actions
```

---

## 📊 AWS Console Snapshots & CloudWatch 


## 🌐 VPC Dashboard
![VPC Dashboard](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/vpc-dashboard.png)

---

## 📊 ALB Overview Page
![ALB Overview](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/alb-overview.png)

---

## 📊 Target Group – Healthy Targets

![TG](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/target-group-healthy-instances.png)

---
## 📊 Auto Scaling Group – Activity History


![Auto Scaling Group – Activity](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/asg-scaling-activity-history.png)

---

## 📊 CloudWatch CPU Utilization Graph
![CloudWatch CPU Utilization Graph](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/cpu-utlization-graph-cw.png)

---

## 📊 CloudWatch Target tracking RequestCountPerTarget Graph 

![CloudWatch Target tracking RequestCountPerTarget Graph](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/Target-tracking-scaling-cloudwatch-alarm-graph.png)

## 📊 CloudWatch UnHealthyHostCount Alarm
![CloudWatch UnHealthyHostCount Graph](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/unhealthy-host-count-cloudwatch-graph.png)

---
![CloudWatch UnHealthyHostCount Alert](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/unhealthy-hostcount-alert-via-cloudwatch-alarm.png)

---

## 📊 Scaling Policy (RequestCountPerTarget)
![Scaling Policy - (RequestCountPerTarget)](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/asg-target-tracking-policy.png)

---

## 📊 EC2 Instances List (Multiple Instances Running)
![ EC2 Instances](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/ec2-instances-multiples.png)

---

## 🌐 Application Preview (Deployed)
![ Netflix Web app](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/application-view-1.png)

---
![ Netflix Web app-features](https://github.com/biswarup65/Netflix-WebApp-Aws/blob/main/screenshots/application-view-2.png)

---

## 🧪 Testing & Validation

● Verified traffic distribution across EC2 instances

● Simulated instance failure and observed auto-healing

● Generated load to trigger auto scaling

● Confirmed CloudWatch alarms and scaling behavior

---

## 📈 Learning Outcomes

➤ Hands-on experience with highly available cloud architecture

➤ Practical understanding of monitoring and alerting

➤ Learned real-world troubleshooting scenarios

➤ Gained exposure to AWS best practices for operations


---

## 🏁 Conclusion

This project demonstrates a production-style AWS infrastructure focused on availability, scalability, monitoring, and security.
It reflects real-world cloud support responsibilities and provides a strong foundation in Cloud Infrastructure.

---
## References

- AWS Documentation – VPC with servers in private subnets and NAT gateway
  [https://docs.aws.amazon.com/elasticloadbalancing/](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-example-private-subnets-nat.html)


