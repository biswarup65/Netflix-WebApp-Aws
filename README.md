# 🚀 Highly Available & Scalable Web Application on AWS

![Project Banner]()

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

✔ Custom VPC with public subnets 

✔ Health checks and self-healing infrastructure 

---

## 🛠️ Tools & Technologies Used

▪ **Amazon EC2 – Web server hosting**
▪ **Elastic Load Balancing – Traffic distribution**
▪ **Auto Scaling Group – Automatic scaling & recovery**
▪ **Amazon VPC – Network isolation**
▪ **AWS IAM – Secure access control**
▪ **Amazon CloudWatch – Monitoring & alarms**
▪ **Amazon EBS – Instance storage**
▪ **Linux (Ubuntu LTS)**
▪ **Nginx Reverse proxy Server**

