---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

## Week 4 Objectives

- Install, configure, and manage Nginx Web Server on a Linux Ubuntu environment.
- Use secure file transfer utilities (SFTP) on Windows to manage and upload application source code to the Cloud.
- Master file permission management techniques on the Windows operating system.
- Allocate and bind a static IP address (Elastic IP) to the application instance.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Establish an SSH connection to the EC2 Ubuntu instance and execute package update commands.<br>- Install the Nginx service to function as a high-performance Web Server. | 11/05/2026 | 11/05/2026 | Linux/Nginx Docs |
| Tue | - Download and install the **WinSCP** secure file transfer utility on Windows.<br>- Configure a new session using the SFTP protocol and the `.pem` private key pair to link Windows and Linux. | 12/05/2026 | 12/05/2026 | WinSCP Guide |
| Wed | - Utilize WinSCP's drag-and-drop interface to upload template web UI source code from Windows to Nginx's root directory on the AWS server.<br>- Use Linux commands to verify and adjust file system ownership and permissions. | 13/05/2026 | 13/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Research key file permission issues (`Permission denied - Warning: Unprotected Private Key File`).<br>- Apply advanced Windows file security properties or commands to restrict access to the private key file. | 14/05/2026 | 14/05/2026 | AWS Security Docs |
| Fri | - Allocate and bind an **Elastic IP** address to the EC2 Instance to freeze the connection endpoint.<br>- Access and verify the website layout via Microsoft Edge or Google Chrome using the newly assigned static IP. | 15/05/2026 | 15/05/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Outcomes

- Successfully installed and operated an Nginx Web Server on the cloud instance using the following command sequences:
  ```bash
  sudo apt update && sudo apt upgrade -y
  sudo apt install nginx -y
  sudo systemctl start nginx
  sudo systemctl enable nginx