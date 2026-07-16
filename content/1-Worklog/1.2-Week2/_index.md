---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

## Week 2 Objectives

- Study the mechanisms of object storage using Amazon S3.
- Master the configuration of access control and resource security on S3 (Bucket Policy, Block Public Access).
- Utilize the AWS CLI on Windows to synchronize local data to the Cloud infrastructure.
- Deploy a live static website directly on Amazon S3.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Study the theory of Amazon S3 (Bucket, Object, Key, Metadata).<br>- Differentiate S3 Storage Classes (Standard, Intelligent-Tiering, Standard-IA, Glacier) to optimize infrastructure costs. | 27/04/2026 | 27/04/2026 | AWS S3 Documentation |
| Tue | - Access the S3 Console and create a new Bucket with a globally unique name in the Singapore Region.<br>- Practice uploading and downloading sample image assets from a local Windows machine to the S3 Bucket.<br>- Enable Bucket Versioning to manage multi-version files. | 28/04/2026 | 28/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| Wed | - Study the network security mechanisms of S3.<br>- Disable the Block Public Access feature.<br>- Compose and apply a Bucket Policy in JSON format to grant public read permissions (`s3:GetObject`) for product images. | 29/04/2026 | 29/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Interact with S3 via AWS CLI using Windows PowerShell.<br>- Execute bucket creation (`mb`) and data synchronization (`sync`) commands to upload asset directories from the local Windows drive to the cloud. | 30/04/2026 | 30/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| Fri | - Investigate the Static Website Hosting feature on Amazon S3.<br>- Configure designated file paths for `index.html` and `error.html` as default routing pages.<br>- Upload static web source code and test access via the public S3 Endpoint URL. | 01/05/2026 | 01/05/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Outcomes

- Understood the core concepts of S3 Object Storage and distinguished it from Block Storage (EBS).
- Successfully initialized an S3 Bucket with **Bucket Versioning** enabled, allowing safe file overwrite and historical version recovery.
- Developed and applied a valid **Bucket Policy** (JSON) to allow external clients to fetch product images without compromising root administrative rights:
  ```json
  {
      "Version": "2012-10-17",
      "Statement": [
          {
              "Sid": "PublicReadGetObject",
              "Effect": "Allow",
              "Principal": "*",
              "Action": "s3:GetObject",
              "Resource": "arn:aws:s3:::hoanganh-stylehub-bucket/*"
          }
      ]
  }