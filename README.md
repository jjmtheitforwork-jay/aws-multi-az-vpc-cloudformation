# Multi-AZ AWS Cloud Infrastructure Architecture & Automation

## Project Overview
Automated deployment of a resilient, highly available Multi-Availability Zone (Multi-AZ) Virtual Private Cloud (VPC) network architecture on Amazon Web Services using AWS CloudFormation (IaC)

## Tech Stack
- Cloud Provider: Amazon Web Services (AWS)
- Core Services:** VPC, Subnets, Internet Gateway (IGW), NAT Gateways, Route Tables, IAM
- Infrastructure as Code (IaC): AWS CloudFormation (YAML)
- Tooling:** AWS CLI, PowerShell, Visual Studio Code

## Network Architecture Highlights
- Multi-AZ Deployment:** Provisioned across 3 Availability Zones (`ap-southeast-1a`, `ap-southeast-1b`, `ap-southeast-1c`)
- Subnet Segmentation:** Divided the `172.31.0.0/16` CIDR block into 3 Public Subnets and 3 Private Subnets using `/20` subnets
- Routing & Security:
  * Direct internet access for public subnets via Internet Gateway
  * Secure outbound internet traffic for private subnets via dedicated NAT Gateways per AZ with custom Route Tables

## Automation Pipeline
1. Authored declarative YAML templates in VS Code
2. Executed local validation using `aws cloudformation validate-template`
3. Automated stack lifecycle (create/delete) in PowerShell using AWS CLI via the `dev-practice-admin` profile
