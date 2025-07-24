# ECS Cluster on AWS Fargate

This project provisions an AWS ECS Cluster using Fargate launch type, with an Application Load Balancer, VPC, security groups, IAM roles and policies, and supporting resources using Terraform.

## Resources

- **VPC & Subnets:** Defined in [`vpc.tf`](vpc.tf)
- **Security Group:** Allows HTTP traffic on port 80 ([`Security-Group.tf`](Security-Group.tf))
- **Internet Gateway & Route Table:** For public subnets ([`vpc.tf`](vpc.tf))
- **Application Load Balancer & Listener:** For routing traffic ([`Load-Balancer.tf`](Load-Balancer.tf))
- **Target Group:** For ECS service ([`Target-Group.tf`](Target-Group.tf))
- **IAM Role & Policy:** For ECS task execution ([`iam-role.tf`](iam-role.tf), [`iam-policy.tf`](iam-policy.tf))
- **ECS Cluster:** Defined in [`ecs-cluster.tf`](ecs-cluster.tf)
- **ECS Task Definition:** Specifies container details ([`ecs-taskdefiniton.tf`](ecs-taskdefiniton.tf))
- **ECS Service:** Manages running tasks ([`ecs-service.tf`](ecs-service.tf))
- **Terraform Backend:** S3 remote state ([`backend.tf`](backend.tf))
- **Provider Configuration:** AWS region ([`provider.tf`](provider.tf))
- **Outputs:** ALB DNS name ([`output.tf`](output.tf))

## Usage

1. **Initialize Terraform:**
   ```sh
   terraform init
   terraform validate
   terraform apply