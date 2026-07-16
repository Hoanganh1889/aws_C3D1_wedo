---
title: "Week 1 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

## Week 1 Objectives

- Connect and get familiar with members of the First Cloud Journey (FCJ) program.
- Understand the high-level overview of the AWS platform and its core service groups.
- Get familiar with the AWS Management Console and set up the local working environment on Windows.
- Launch, configure, and securely remote connect into the first Amazon EC2 virtual server.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Meet and get familiar with members and Mentors of the FCJ project team.<br>- Read and study the internal regulations, information security policies, and working hours of the organization. | 17/04/2026 | 17/04/2026 | Company Handbook |
| Tue | - Explore the fundamentals of Cloud Computing (IaaS, PaaS, SaaS).<br>- Study the theory of core AWS service groups:<br>&emsp;+ Compute (EC2)<br>&emsp;+ Storage (S3, EBS)<br>&emsp;+ Networking (VPC)<br>&emsp;+ Database (RDS, DynamoDB) | 20/04/2026 | 20/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| Wed | - Create an AWS Free Tier account using a Windows browser.<br>- Configure basic security for the Root Account by enabling Multi-Factor Authentication (MFA) via Google Authenticator on a mobile device. | 21/04/2026 | 21/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Download and install the AWS CLI v2 for Windows.<br>- Generate an Access Key ID and Secret Access Key on the IAM Console.<br>- Configure the AWS CLI on Windows PowerShell and practice basic verification commands. | 22/04/2026 | 23/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| Fri | - Deploy an Amazon EC2 virtual server (Ubuntu 22.04 LTS, t2.micro).<br>- Configure a Security Group to open port 22 and port 80.<br>- Troubleshoot private key file `.pem` permission issues via Windows Properties and establish a successful SSH connection.<br>- Create and attach an additional EBS Volume to the instance. | 24/04/2026 | 24/04/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Outcomes

- Gained a clear understanding of Cloud Computing concepts and the role of AWS in the cloud industry.
- Successfully activated an AWS Free Tier account and secured the Root Account using two-factor authentication (MFA).
- Successfully installed AWS CLI v2 on the Windows operating system. Configured the environment using the command:
  ```bash
  aws configure
  # Configurations: Access Key ID, Secret Access Key, Default Region (ap-southeast-1), Output (json)