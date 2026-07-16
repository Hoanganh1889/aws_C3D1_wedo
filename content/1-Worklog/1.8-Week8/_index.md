---
title: "Week 8 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

## Week 8 Objectives

- Study highly available (HA) distributed network patterns using an Application Load Balancer (ALB).
- Formulate a baseline machine configuration scheme for auto-scaling deployments (Launch Templates).
- Provision an Auto Scaling Group (ASG) distributing virtual nodes across distinct Multi-AZ subnet boundaries.
- Employ automated load stress simulation tools on Windows to evaluate the resiliency of the cloud architecture.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Access the EC2 Console and initialize an **Application Load Balancer (ALB)** named `hoanganh-web-alb`.<br>- Create a **Target Group**, configure runtime listening rules, and assign health check parameters. | 08/06/2026 | 08/06/2026 | AWS ELB Documentation |
| Tue | - Construct a new **Launch Template** defining hardware blueprints for cloned instances, covering: Ubuntu AMIs, compute sizing types, and security boundaries.<br>- Inject startup boot environment setup shell script commands inside the **User Data** section. | 09/06/2026 | 09/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Wed | - Bind an **Auto Scaling Group (ASG)** named `hoanganh-asg` directly to the active Launch Template baseline.<br>- Spread the virtual nodes across multiple `Public-Subnet` multi-AZ data center nodes to increase high availability. | 10/06/2026 | 10/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Configure group capacity boundaries: Set Desired to 2, Min to 1, and Max to 4 instances.<br>- Set up an automated scaling rules configuration (**Target Tracking Scaling Policy**) based on average hardware CPU utilization metrics. | 11/06/2026 | 11/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Fri | - Set up the performance validation utility toolkit **Apache JMeter** on Windows.<br>- Build an intensive query traffic load script aiming directly at the public load balancer DNS endpoint to observe auto-scaling triggers. | 12/06/2026 | 12/06/2026 | Apache JMeter Guide |

---

## Outcomes

- Successfully implemented a self-healing and load-balanced application architecture by binding the ALB to a target group pointing to the source monitor endpoints: `/actuator/health` (or `/status`).
- Wrote an automated machine boot deployment shell script embedded into the instance launch profile configuration metadata (**User Data**):
  ```bash
  #!/bin/bash
  sudo apt update
  sudo apt install nginx -y
  sudo systemctl start nginx