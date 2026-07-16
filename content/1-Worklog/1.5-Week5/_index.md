---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

## Week 5 Objectives

- Investigate relational database systems managed entirely by Amazon RDS (Relational Database Service).
- Plan and allocate an isolated DB Subnet Group to protect database layers.
- Establish robust network firewalls to restrict database tier entry paths (Port 3306).
- Use graphical database administration toolkits (GUI) on Windows to query and manage the remote cloud database.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Access the RDS Dashboard and initialize a new **DB Subnet Group** mapped to `HoangAnh-VPC`.<br>- Bind only the `Private-Subnet` ranges to ensure the Database Server cannot accept inbound internet connections. | 18/05/2026 | 18/05/2026 | AWS RDS Documentation |
| Tue | - Configure the launch parameters for the Database Instance:<br>&emsp;+ Engine: **MySQL Community** (Version 8.0).<br>&emsp;+ Gói tài khoản: **Free Tier** (Instance type: `db.t3.micro`).<br>&emsp;+ Setup Master Username (`admin`) and a secure Master Password.<br>&emsp;+ Storage size configuration: 20 GiB gp2 SSD. | 19/05/2026 | 19/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| Wed | - Build a dedicated firewall group for the database tier named `HoangAnh-RDS-SG`.<br>- Configure Inbound rules: Permit only **MySQL/Aurora (Port 3306)** traffic originating strictly from the EC2 Web Server's Security Group ID. | 20/05/2026 | 20/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Download and install the graphical database client **DBeaver** (or MySQL Workbench) on Windows.<br>- Monitor the RDS status until it hits `Available`, then retrieve the specialized connectivity string (**Endpoint**). | 21/05/2026 | 21/05/2026 | DBeaver Guide |
| Fri | - Configure TCP/IP parameter bindings inside DBeaver using the AWS Endpoint string.<br>- Write and run an SQL initialization script to set up sample tables for the graduation project. | 22/05/2026 | 22/05/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Outcomes

- Successfully deployed an **Amazon RDS MySQL** database running privately and securely within the isolated Private Subnet layer.
- Configured database firewall rules following the *Principle of Least Privilege*, blocking random public internet scans on port 3306.
- Connected and managed the cloud database from **DBeaver on Windows** using the following configuration inputs:
  - **Server Host (Endpoint):** `hoanganh-db.xxxxxxxxxxxx.ap-southeast-1.rds.amazonaws.com`
  - **Port:** `3306` | **Username:** `admin`
- Executed database layout schemas (`init_schema.sql`) from the graphical Windows environment:
  ```sql
  CREATE DATABASE mobileshop_db;
  USE mobileshop_db;
  CREATE TABLE products (
      id INT PRIMARY KEY AUTO_INCREMENT,
      product_name VARCHAR(255) NOT NULL,
      price DECIMAL(10,2),
      stock_quantity INT
  );