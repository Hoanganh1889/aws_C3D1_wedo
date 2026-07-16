---
title: "Week 12 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.12. </b> "
---

## Week 12 Objectives

- Audit and analyze cloud resource expenditures using tracking dashboards (AWS Billing, Cost Explorer).
- Perform deep infrastructure decommission routines to release active background hardware units and protect account budgets.
- Package local configuration scripts, lambda code packages, and SQL layout profiles into archives on Windows.
- Compile and assemble the final 12-week internship notebook log document as a PDF to submit to the university.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Open the **AWS Billing Dashboard** and activate data analytics graphing tools inside the **Cost Explorer** panel.<br>- Audit resource usage histories over the past 3 months to aggregate financial metrics for the internship report. | 06/07/2026 | 06/07/2026 | AWS Billing Documentation |
| Tue | - Start infrastructure decommissioning routines: Navigate to the EC2 console, select all test virtual machines, and trigger **Terminate** instructions.<br>- Release reserved static Elastic IP resources back into the regional public AWS pool. | 07/07/2026 | 07/07/2026 | https://cloudjourney.awsstudygroup.com/ |
| Wed | - Access the RDS management panel and delete the MySQL database instance, opting out of generating final automated recovery snapshots.<br>- Open the S3 console, execute **Empty Bucket** tasks, and delete the empty bucket containers. | 08/07/2026 | 08/07/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Build a secure local backup directory archive layout named `AWS_Evidence_Backup` on the local Windows computer drive.<br>- Classify and organize JSON configuration sheets, Lambda code blocks, and database scripts used across the weeks. | 09/07/2026 | 09/07/2026 | Local Windows Storage |
| Fri | - Open **Microsoft Word on Windows** to organize weekly log spreadsheets and content structures into the format required by the school.<br>- Compose the Introduction and Technical Conclusions chapters, and export the document as a clean PDF file. | 10/07/2026 | 10/07/2026 | University Log Template |

---

## Outcomes

- Completed full accounting audits of cloud usage and generated a billing consumption analysis sheet archived as `cost_analysis_june_july.csv` to attach to the internship logs.
- Completely removed 100% of background running virtual machines, networks, and blocks using the AWS CLI directly from the Windows Terminal:
  ```bash
  # Purge and erase an object storage bucket registry container on S3 completely
  aws s3 rb s3://hoanganh-stylehub-bucket --force
  # Issue immediate cluster termination tokens to wipe active compute host server instances
  aws ec2 terminate-instances --instance-ids i-xxxxxxxxxxxxxxxxx