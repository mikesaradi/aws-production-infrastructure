# AWS Production Infrastructure

Production-style AWS infrastructure lab focused on network architecture,
high availability, load balancing, monitoring, and security controls.

## Objective

The objective of this project was to design and deploy a production-style AWS
environment rather than a single standalone EC2 instance.

The project focuses on understanding how AWS networking, compute, load
balancing, monitoring, and access controls work together.

## AWS Services

- Amazon VPC
- Public and Private Subnets
- Internet Gateway
- Route Tables
- Application Load Balancer (ALB)
- Target Groups
- Amazon EC2
- Auto Scaling Group
- Launch Template
- Security Groups
- Amazon CloudWatch
- Amazon SNS
- AWS IAM

## Architecture

Internet
    |
    v
Internet Gateway
    |
    v
+-----------------------------+
|         AWS VPC             |
|         10.0.0.0/16         |
|                             |
|  +-----------------------+  |
|  | Public Subnets        |  |
|  |                       |  |
|  | Application Load      |  |
|  | Balancer              |  |
|  +-----------+-----------+  |
|              |              |
|         Target Group        |
|              |              |
|  +-----------------------+  |
|  | Private Subnets       |  |
|  |                       |  |
|  | Auto Scaling Group    |  |
|  |                       |  |
|  | EC2      EC2          |  |
|  +-----------------------+  |
+-----------------------------+

             |
             v
       CloudWatch
             |
             v
            SNS

## What I Built

- Created a custom VPC.
- Configured public and private subnets across multiple Availability Zones.
- Configured route tables and Internet Gateway connectivity.
- Deployed an Application Load Balancer.
- Created a Target Group with health checks.
- Created a Launch Template.
- Configured an Auto Scaling Group.
- Installed and configured Nginx on EC2 instances using User Data.
- Configured CloudWatch alarms.
- Created an SNS topic for notifications.
- Built a CloudWatch monitoring dashboard.

## Security Architecture

The infrastructure incorporates several basic security controls:

- EC2 instances are deployed in private subnets.
- The Application Load Balancer provides the public-facing entry point.
- Security Groups restrict traffic between infrastructure components.
- SSH access is restricted rather than exposed broadly.
- CloudWatch provides monitoring for infrastructure activity and health.
- SNS is used to deliver monitoring notifications.

## Monitoring

The CloudWatch dashboard monitors:

- EC2 CPU Utilization
- ALB Request Count
- Healthy Host Count

Configured alarms include:

- High CPU utilization
- Healthy target monitoring

Notifications are delivered through Amazon SNS.

## Security Considerations

This project demonstrates several important cloud security concepts:

- Network segmentation
- Public/private subnet separation
- Restricted security group rules
- Controlled administrative access
- Infrastructure monitoring
- High-availability architecture

## What I Learned

This project improved my understanding of how AWS networking and
infrastructure components interact in a production-style environment.

I gained hands-on experience with VPCs, subnets, routing, security groups,
Application Load Balancers, Auto Scaling Groups, EC2, CloudWatch, and SNS.

## Future Improvements

Potential extensions include:

- AWS WAF
- AWS GuardDuty
- AWS CloudTrail
- AWS Config
- Terraform infrastructure as code
- CI/CD integration
- Docker-based deployment

## Screenshots

Screenshots documenting the deployed infrastructure are included below.

### VPC Configuration

### Subnet Configuration

#### Public Subnets

#### Private Subnets

### Application Load Balancer

### Target Group Health Checks

The Target Group health checks confirm that the EC2 instances behind the Load
Balancer are healthy and receiving traffic correctly.

### Auto Scaling Group

### CloudWatch Monitoring

### CloudWatch Alarms
