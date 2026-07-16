---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---

## Week 10 Objectives

- Study identity verification, access isolation, and user privilege governance with AWS IAM.
- Create rigid perimeter safeguards by enabling Multi-Factor Authentication (MFA) token rules on the Root Account.
- Organize directory access boundaries by establishing specialized user groups (IAM Groups) and secondary sub-users (IAM Users) under least-privilege security mandates.
- Generate and configure program access secrets (Access Keys) to interact securely via command-line tools on Windows.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Research identity breach threat vectors and risks associated with operating daily workflows via root credentials.<br>- Synchronize a mobile device running **Google Authenticator** to set up **MFA** tokens on the Root Account. | 22/06/2026 | 22/06/2026 | AWS IAM Documentation |
| Tue | - Open the IAM administration console dashboard panel and register a new group organization unit named `Developer-Group`.<br>- Audit and assign default managed cloud platform security policies, choosing the `PowerUserAccess` rules. | 23/06/2026 | 23/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Wed | - Complete registration workflows for a secondary access identity account named `hoanganh-dev`.<br>- Assign this sub-user entity directly into the `Developer-Group` to inherit its predefined access rules. | 24/06/2026 | 24/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Thu | - Open the sub-user's credentials tab and generate a new pair of programmatic credentials (**Access Key**).<br>- Download and save the security key matrix dataset file (`.csv` format) to the local Windows machine disk storage. | 25/06/2026 | 25/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Fri | - Open **Windows PowerShell** and input the secondary identity parameters to switch local operations over to the sub-user account.<br>- Execute resource creation tests and resolve network sub-tier access token blocks. | 26/06/2026 | 26/06/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Outcomes

- Locked down the administrative Root Account using an application-generated time-based one-time password (TOTP) from Google Authenticator.
- Organized multi-tenant development workflows via the `Developer-Group`, granting full development permissions while completely blocking modifications to billing and subscription settings.
- Generated the primary programmatic access encryption key token profile file (`credentials.csv`) on local hardware to execute command-line adjustments.
- Loaded the secondary user credentials profile into the local Windows workstation profile database via the command terminal:
  ```bash
  aws configure
  # Input Access Key ID and Secret Access Key from the csv file
  # Set Default region name: ap-southeast-1 | Default output format: json