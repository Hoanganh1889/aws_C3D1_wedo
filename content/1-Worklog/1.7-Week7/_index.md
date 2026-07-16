---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

## Week 7 Objectives

- Research PaaS (Platform as a Service) automated deployment models using AWS Elastic Beanstalk.
- Master packaging backend web application components (Spring Boot/Node.js) inside a Windows environment.
- Configure and decouple sensitive runtime environment variables (Environment Properties) for secure database handshakes.
- Learn cloud log retrieval and analysis techniques to isolate reverse proxy container failures.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Open the backend codebase on a Windows workstation and execute compilation build sequences to archive the deployment artifact.<br>- Study AWS Elastic Beanstalk automated platform abstraction mechanisms. | 01/06/2026 | 01/06/2026 | Maven/Node.js Tooling Guides |
| Tue | - Access the Beanstalk Dashboard and initialize a new application registry called `hoanganh-backend-app`.<br>- Select the runtime container environment platform that matches the code: Java (or Node.js). | 02/06/2026 | 02/06/2026 | AWS Beanstalk Docs |
| Wed | - Locate the Application code section and opt for the **Upload your code** feature package deployment path.<br>- Upload the compiled binary software application bundle from the local Windows disk storage directly up to AWS. | 03/06/2026 | 03/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Navigate to the *Configuration -> Software* settings inside Beanstalk to configure variables.<br>- Inject secure connection environment attributes pointing directly to the **Amazon RDS** endpoint built in week 5. | 04/06/2026 | 04/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Fri | - Monitor the automatic compute infrastructure initialization steps taken by AWS. Access the allocated app URL.<br>- Practice pulling clustered system log traces down to Windows to diagnose container reverse proxy listening failures. | 05/06/2026 | 05/06/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Outcomes

- Packaged the local source project files on a Windows environment into a deployable cloud artifact using terminal commands:
  ```bash
  # For Java Spring Boot Maven compilation profiles
  mvn clean package
  # Output artifact binary file location: target/mobileshop_backend-0.0.1-SNAPSHOT.jar