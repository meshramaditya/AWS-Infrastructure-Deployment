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

User(Internet)
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
↓
VPC → Subnets → Route Tables → Internet Gateway
↓
Security:
IAM → Security Groups

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
1. Stop EC2-1
<img width="959" height="502" alt="Screenshot 2026-06-24 194239" src="https://github.com/user-attachments/assets/e365932b-552c-4994-b535-bd059c4b91f6" />

2. Target becomes unhealthy, and the website remains accessible.
<img width="959" height="470" alt="autoscale-1" src="https://github.com/user-attachments/assets/cfa5a082-24ed-4f71-8f03-6bbab6e4e3fe" />
<img width="959" height="406" alt="Screenshot 2026-06-24 194034" src="https://github.com/user-attachments/assets/b1e2a1e6-eb6e-4a01-901d-d2874fc888a4" />


3. Start EC2-1 again.
<img width="959" height="430" alt="Ec2" src="https://github.com/user-attachments/assets/6427e418-c1bb-42b3-835a-b58de01775e4" />

4. Target becomes healthy.
   <img width="958" height="473" alt="target-group-health-check-1" src="https://github.com/user-attachments/assets/db5b32ed-c22f-4ba7-b936-73f8bdc4a7c2" />


### Test

Stopped EC2 Instance 1
<img width="959" height="469" alt="Auto-scael-demo-1" src="https://github.com/user-attachments/assets/5a8ed858-8e59-49e0-962a-7c17a2b8c44b" />

### Result

- Target Group detected failure
- Load Balancer redirected traffic
- Application remained accessible

### Outcome

High Availability validated successfully.


## Auto Scaling Validation

### Test

Terminated Auto Scaling managed instance.
<img width="959" height="469" alt="Auto-scael-demo-1" src="https://github.com/user-attachments/assets/5a8ed858-8e59-49e0-962a-7c17a2b8c44b" />

### Result

- Auto Scaling detected instance termination
- New instance launched automatically
- Target Group registered new instance
- Health Checks passed

### Outcome

Self-Healing infrastructure validated successfully.

## Implementation Screenshots

### IAM
IAM Users
<img width="956" height="409" alt="Iamusers" src="https://github.com/user-attachments/assets/1d4f8fbe-b717-46b0-9e1d-028f6a0b0ce9" />
IAM Group
<img width="958" height="432" alt="Iamgroup" src="https://github.com/user-attachments/assets/f3cacc50-ba5c-4760-9f4c-cc1d0beb2209" />


### VPC
Create VPC
<img width="947" height="427" alt="Vpc" src="https://github.com/user-attachments/assets/cb75a2ba-de81-4186-8f18-7769e3158dd5" />

Internet Gateways
<img width="959" height="434" alt="internet getway" src="https://github.com/user-attachments/assets/895ecddf-2bd0-4e8d-9198-0e7949366986" />

Subnets
<img width="956" height="430" alt="subnets" src="https://github.com/user-attachments/assets/efda2d04-8632-40be-bce2-0fb1cad71e35" />

Route Tables
<img width="959" height="424" alt="Route table" src="https://github.com/user-attachments/assets/3ad9d213-5009-4176-902c-c900fbe2eaef" />

Security Groups
<img width="959" height="433" alt="Security Group" src="https://github.com/user-attachments/assets/3312afca-185d-4f9f-8863-e56b3ce6273a" />

### EC2
EC2
<img width="959" height="430" alt="Ec2" src="https://github.com/user-attachments/assets/6427e418-c1bb-42b3-835a-b58de01775e4" />

EBS Volumes
<img width="959" height="434" alt="ebs-3" src="https://github.com/user-attachments/assets/32399918-33f2-4409-b27a-8f57a5b261a7" />

EBS mounted on EC2 Instances
<img width="959" height="502" alt="ebs-mounted-2" src="https://github.com/user-attachments/assets/e43e4c7a-5391-496d-af6b-ac6c8b7f69df" />
<img width="959" height="504" alt="ebs-mounted-1" src="https://github.com/user-attachments/assets/93d5847a-6212-4a27-983b-629910a0247a" />

Nginx on both EC2 
<img width="955" height="503" alt="nginx-2" src="https://github.com/user-attachments/assets/c6d319bb-147b-45de-925f-905b4e43db9a" />
<img width="959" height="506" alt="nginx-1" src="https://github.com/user-attachments/assets/9948de80-73a8-4c79-9741-6b8043ddcb01" />

### Load Balancer
Application Load Balancer
<img width="956" height="421" alt="Aplication-lb" src="https://github.com/user-attachments/assets/50f4bcba-f050-450a-bb8a-db2c6c9afbaf" />

Target Group
<img width="959" height="420" alt="target group" src="https://github.com/user-attachments/assets/339927d7-2907-4825-b778-fd1b7c3c40da" />

Health check on Target Group
<img width="959" height="473" alt="target-group-health-check" src="https://github.com/user-attachments/assets/d8645fea-beb0-4c11-ab72-48876e70cbfb" />

### Auto Scaling
Auto Sacling Group creates
<img width="950" height="434" alt="Auto-scale" src="https://github.com/user-attachments/assets/1a2238ed-a881-4af0-8d24-e294fefa9626" />

### Access the application on the internet 
<img width="952" height="506" alt="expose-app-1" src="https://github.com/user-attachments/assets/85fde01c-c68c-4e4b-8d8d-d4eccee0632a" />

<img width="959" height="539" alt="expose-app-2" src="https://github.com/user-attachments/assets/5a41833d-d1d2-469e-acd6-f7bea74c03f7" />



