# # Project Title
# AWS Highly Available React Application Infrastructure

# # Overview
This project demonstrates the design and deployment of a highly available and fault-tolerant React web application infrastructure on AWS.

The solution uses:

- IAM
- VPC
- Public Subnets
- Internet Gateway
- Route Tables
- Security Groups
- EC2
- EBS
- Target Groups
- Application Load Balancer
- Auto Scaling Group

The infrastructure was deployed as part of a DevOps Foundation assignment.

## Architecture
<img width="2816" height="1536" alt="AWS-Infra" src="https://github.com/user-attachments/assets/5b74f05a-0750-4fc6-a2b6-0f3e2f4045e6" />

## Services Used

| Service | Purpose |
|----------|----------|
| IAM | Access Management |
| VPC | Network Isolation |
| Subnets | High Availability |
| Internet Gateway | Internet Access |
| Route Table | Traffic Routing |
| Security Groups | Firewall |
| EC2 | Application Hosting |
| EBS | Persistent Storage |
| Target Group | Health Monitoring |
| ALB | Traffic Distribution |
| ASG | Self-Healing Infrastructure |

## Request Flow

User
↓
Application Load Balancer
↓
Target Group
↓
EC2 Instance
↓
Nginx
↓
React Application
↓
EBS Storage

## Features

- High Availability Architecture
- Multi Availability Zone Deployment
- Load Balancing
- Persistent Storage with EBS
- Health Checks
- Self-Healing Infrastructure
- Auto Scaling
- Fault Tolerance

## Failure Testing

### Test

Stopped EC2 Instance 1

### Result

- Target Group detected failure
- Load Balancer redirected traffic
- Application remained accessible

### Outcome

High Availability validated successfully.


## Auto Scaling Validation

### Test

Terminated Auto Scaling managed instance.

### Result

- Auto Scaling detected instance termination
- New instance launched automatically
- Target Group registered new instance
- Health Checks passed

### Outcome

Self-Healing infrastructure validated successfully.

## Implementation Screenshots

### IAM

![IAM](screenshots/iam/iam-users.png)

### VPC

![VPC](screenshots/vpc/vpc.png)

### EC2

![EC2](screenshots/ec2/ec2.png)

### Load Balancer

![ALB](screenshots/load-balancer/alb.png)

### Auto Scaling

![ASG](screenshots/autoscaling/asg.png)
