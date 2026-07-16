---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

## Week 3 Objectives

- Research virtual network architectures using Amazon VPC (Virtual Private Cloud).
- Master the design and allocation of network subnets using IP Subnetting techniques.
- Configure logical routing paths and gateways (Internet Gateway, Route Tables).
- Use network diagnostic utilities on Windows to verify cloud network interconnectivity.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Study the theoretical foundations of cloud networking: IP addresses and subnet allocation using CIDR blocks.<br>- Analyze and partition a 2-Tier network model: **Public Subnet** (for Web Servers) and **Private Subnet** (for isolated internal databases). | 04/05/2026 | 04/05/2026 | AWS Networking Docs |
| Tue | - Access the VPC Dashboard and initialize an isolated virtual private network named `HoangAnh-VPC` with a CIDR block of `10.0.0.0/16`.<br>- Manually create two separate subnets within the `ap-southeast-1a` (Singapore) Availability Zone. | 05/05/2026 | 05/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| Wed | - Initialize an **Internet Gateway (IGW)** and attach it directly to the custom VPC.<br>- Create a new routing table named `Public-Route-Table` and configure a route to direct all outbound traffic (`0.0.0.0/0`) through the IGW. | 06/05/2026 | 06/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Associate the public route table with the `Public-Subnet`. Ensure the `Private-Subnet` remains completely isolated from the internet.<br>- Launch a test EC2 instance inside the new VPC to prepare for routing validations. | 07/05/2026 | 07/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| Fri | - Open **Windows PowerShell** and apply advanced network diagnostic commands to check connectivity to the AWS server.<br>- Learn about two-layer packet filtering mechanisms: **Security Groups** (instance-level) and **Network ACLs** (subnet-level). | 08/05/2026 | 08/05/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Outcomes

- Designed and successfully partitioned a secure, isolated 2-Tier network architecture consisting of:
  - Main Virtual Network: `HoangAnh-VPC` (CIDR: `10.0.0.0/16`, containing up to 65,536 IP addresses).
  - Public Zone: `Public-Subnet` (CIDR: `10.0.1.0/24`, providing 251 usable IPs for Web Servers).
  - Private Zone: `Private-Subnet` (CIDR: `10.0.2.0/24`, providing 251 usable IPs isolated for Database Servers).
- Configured the `Public-Route-Table` with an outbound rule, enabling all servers inside the Public Subnet to access the internet:
  - **Destination:** `0.0.0.0/0` 
  - **Target:** `igw-xxxxxxxxxxxxxxxxx` (HoangAnh-IGW)
- Mastered network troubleshooting from a local Windows machine using built-in terminal utilities:
  ```bash
  # Test the network connectivity of the SSH service port (Port 22) from Windows to the AWS VPC
  Test-NetConnection -ComputerName 54.254.xx.xx -Port 22
  # Analyze the network routing hops of network packets traveling from the local machine to the Cloud
  tracert 54.254.xx.xx