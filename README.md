# AWS Three-Tier Web Architecture

![AWS Architecture Diagram](<img width="801" height="491" alt="Image" src="https://github.com/user-attachments/assets/08c60902-8d3c-415f-b71d-43b576b14ba6" />)

A production-grade implementation of AWS's three-tier web architecture pattern, featuring high availability, auto-scaling, and secure networking.

## Key Features

- **Multi-AZ Deployment**: Fault-tolerant design across 2+ Availability Zones
- **Auto-scaling**: Horizontal scaling for both web and application tiers
- **Secure Networking**: Public/private subnet isolation with NACLs and security groups
- **Managed Database**: Aurora MySQL with automated backups and failover
- **Infrastructure as Code**: Deployable via AWS CloudFormation/Terraform

## Architecture Components

### Core AWS Services
| Tier           | Services                          | Key Configuration |
|----------------|-----------------------------------|-------------------|
| **Web**        | EC2, ALB, WAF, Auto Scaling       | Nginx reverse proxy, React frontend |
| **Application**| EC2, Internal ALB, Auto Scaling   | Node.js API servers |
| **Database**   | RDS Aurora MySQL                  | Multi-AZ, Read Replicas |
| **Networking** | VPC, NAT Gateway, Route 53        | Public/private subnets |

## Deployment

### Prerequisites
- AWS account with admin permissions
- AWS CLI configured
- Terraform v1.2+ (if using IaC)

### Quick Start
```bash
# Clone repository
git clone https://github.com/your-repo/aws-three-tier-architecture.git

# Deploy infrastructure
cd infrastructure/terraform
terraform init
terraform apply -var="db_password=your_secure_password"
