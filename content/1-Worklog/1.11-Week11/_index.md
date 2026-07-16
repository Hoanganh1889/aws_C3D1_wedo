---
title: "Week 11 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

## Week 11 Objectives

- Study automated application lifecycle release lifecycles utilizing CI/CD (Continuous Integration / Continuous Deployment) methodologies.
- Setup automated sync delivery pipelines linking remote GitHub code repositories to the AWS cloud infrastructure.
- Configure independent deployment stage actions (Source Stage, Deploy Stage) using AWS CodePipeline.
- Perform remote code modification delivery triggers (`git push`) from Windows to test the deployment pipeline.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Research DevOps automation philosophies and pipeline architectures.<br>- Study **AWS CodePipeline** operations and learn how to construct Service Roles to permit automated cross-service actions. | 29/06/2026 | 29/06/2026 | CodePipeline Documentation |
| Tue | - Initialize a new pipeline entity named `hoanganh-stylehub-pipeline`.<br>- At the **Source Stage** wizard panel, set the source provider to GitHub (Version 2) and authenticate the target repository. | 30/06/2026 | 30/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Wed | - Configure the downstream output node (**Deploy Stage**): Route code targets toward the managed **AWS Elastic Beanstalk** instance stack built in week 7.<br>- Bind the deployment pipeline to the exact app registry and environment name. | 01/07/2026 | 01/07/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Open the source project files using **VS Code on Windows**.<br>- Perform minor modifications to static layout text elements on the index homepage file, open the integrated git shell, and push revisions to the repository. | 02/07/2026 | 02/07/2026 | Git/GitHub Version Guides |
| Fri | - Monitor pipeline stage progress visualizations on the AWS Management Console web interface.<br>- Identify and resolve permission-related pipeline jams occurring between the automated code orchestrator and S3 storage zones. | 03/07/2026 | 03/07/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Outcomes

- Successfully designed and operated a continuous automated software deployment loop (CI/CD), eliminating manual compilation builds and old file overwrite tasks over SFTP.
- Configured a webhook listener to monitor push events on the `main` branch of the GitHub repository.
- Successfully executed remote codebase updates from the local Windows terminal to the cloud repository system:
  ```bash
  git add .
  git commit -m "Fix title homepage for AWS pipeline demo"
  git push origin main