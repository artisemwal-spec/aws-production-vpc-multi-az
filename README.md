# AWS Highly Available VPC Architecture

## Overview
This project demonstrates a **production-ready AWS VPC architecture** designed for **high availability, security, and scalability**. The setup follows AWS best practices and reflects a real-world deployment used for hosting web applications.

The architecture spans **two Availability Zones** to eliminate single points of failure and ensure resilience.

---

## Architecture Summary
- VPC deployed across **two Availability Zones**
- **Public Subnets**:
  - Application Load Balancer (ALB)
  - Bastion Host for secure SSH access
  - NAT Gateway (one per AZ)
- **Private Subnets**:
  - EC2 application servers **without public IP addresses**
  - Auto Scaling Group for elasticity
- Security Groups for controlled access

---

## Traffic & Access Flow
- Incoming traffic → Application Load Balancer
- ALB → EC2 instances in private subnets
- SSH access → Bastion Host → Private EC2 instances
- Outbound internet access → NAT Gateway

---

## Security Highlights
- No public IPs on private EC2 instances
- SSH access restricted through Bastion Host only
- Least-privilege Security Group rules
- Multi-AZ design for high availability

---

## AWS Services Used
- Amazon VPC
- Amazon EC2
- Application Load Balancer
- Auto Scaling Group
- NAT Gateway
- Bastion Host
- Security Groups
- Internet Gateway

---

## Author
**Arti Semwal**
