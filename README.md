# AWS Production Infrastructure

## Overview

This project was built to practice creating a production-style infrastructure in AWS.

Instead of launching a single EC2 instance, I wanted to build an environment that follows common AWS architecture practices such as high availability, load balancing, monitoring and network security.

The project helped me understand how different AWS services work together in a real infrastructure.

---

## AWS Services

* Amazon VPC
* Public & Private Subnets
* Internet Gateway
* Route Tables
* Application Load Balancer (ALB)
* Target Group
* EC2
* Auto Scaling Group
* Launch Template
* Security Groups
* Amazon CloudWatch
* Amazon SNS
* IAM

---

## What I Built

* Created a custom VPC.
* Configured public and private subnets across multiple Availability Zones.
* Deployed an Application Load Balancer.
* Created a Target Group with health checks.
* Created a Launch Template.
* Configured an Auto Scaling Group.
* Installed and configured Nginx on EC2 instances using User Data.
* Configured CloudWatch alarms.
* Created an SNS topic for notifications.
* Built a CloudWatch dashboard for monitoring.

---

## Security

Some security practices used in this project include:

* EC2 instances are deployed inside private subnets.
* The Application Load Balancer receives incoming HTTP traffic.
* Security Groups allow only the required traffic between resources.
* SSH access is restricted.
* CloudWatch alarms notify when important metrics change.

---

## Monitoring

The CloudWatch dashboard monitors:

* EC2 CPU Utilization
* Healthy Host Count
* ALB Request Count

CloudWatch alarms were also created for:

* High CPU utilization
* Healthy target monitoring

Notifications are delivered through Amazon SNS.

---

## What I Learned

Building this project helped me understand how AWS networking and infrastructure components work together.

I became more comfortable working with VPCs, subnets, security groups, Application Load Balancers, Auto Scaling Groups and CloudWatch. It also gave me a better understanding of designing a more secure and highly available environment instead of deploying a single server.

---

## Future Improvements

In the future I would like to extend this project by adding:

* AWS WAF
* AWS GuardDuty
* AWS CloudTrail
* AWS Config
* Terraform
* CI/CD pipeline
* Docker deployment

---

## Architecture

The infrastructure follows this design:

```text
Internet
    |
Internet Gateway
    |
Application Load Balancer
    |
Target Group
    |
+-----------------------------+
| Auto Scaling Group          |
|                             |
| EC2 Instance (Private)      |
| EC2 Instance (Private)      |
+-----------------------------+
    |
CloudWatch
    |
SNS Notifications
```
