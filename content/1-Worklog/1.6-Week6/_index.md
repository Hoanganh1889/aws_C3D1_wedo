---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
## Week 6 Objectives

- Learn the principles of NoSQL schema-less Key-Value data models using Amazon DynamoDB.
- Initialize a non-relational database table and optimize provisioning configurations by utilizing the On-Demand capacity mode.
- Practice performing CRUD tasks on complex JSON document streams directly on the AWS Console interface.
- Employ AWS CLI commands on a Windows terminal to execute advanced table scans and queries.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Research NoSQL database architectural designs (Schemaless).<br>- Analyze key partitioning strategies and primary key definitions including: **Partition Key** and **Sort Key**. | 25/05/2026 | 25/05/2026 | DynamoDB Documentation |
| Tue | - Open the DynamoDB dashboard and create a new data table named `Products_Cache` with the Partition Key set to `ProductID` (String).<br>- Choose the **On-Demand** billing capacity mode to eliminate fixed uptime running fees for the student account. | 26/05/2026 | 26/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| Wed | - Utilize the *Explore items* tab to run standard create, read, update, and delete (CRUD) operations.<br>- Create records that incorporate dynamic, heterogeneous properties (a core feature of NoSQL). | 27/04/2026 | 27/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Input AWS CLI statements inside **Windows PowerShell** to fetch full data batches remotely.<br>- Perform performance and operational cost trade-offs analyses between two primary fetch methods: **Scan** and **Query**. | 28/05/2026 | 28/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| Fri | - Troubleshoot JSON string syntax escaping anomalies encountered when running direct command lines inside Windows PowerShell.<br>- Practice writing standalone configuration files to safely pass query conditions to the CLI. | 29/05/2026 | 29/05/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Outcomes

- Successfully deployed a fully serverless **Amazon DynamoDB** non-relational table capable of auto-scaling storage throughput on demand.
- Successfully inserted dynamic document items containing rich nested JSON attribute data streams:
  ```json
  {
    "ProductID": {"S": "P001"},
    "ProductName": {"S": "iPhone 15 Pro Max"},
    "Price": {"N": "30000000"},
    "Attributes": {"M": {"Color": {"S": "Titanium"}, "Storage": {"S": "256GB"}}}
  }