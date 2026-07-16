---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

## Week 9 Objectives

- Research Serverless (Function-as-a-Service) compute execution architectures with AWS Lambda.
- Implement and author a cloud microservice function handler to run backend code logic natively.
- Configure secure client endpoints, path routing, and request transformations using Amazon API Gateway.
- Use Postman on Windows to execute, parse, and evaluate JSON schema payload data responses from serverless functions.

---

## Implemented Tasks

| Day | Task | Start Date | End Date | Resource / Documentation |
|:---:|------|:----------:|:--------:|--------------------------|
| Mon | - Learn about Event-Driven Architecture concepts using AWS Lambda compute runtimes.<br>- Analyze operational billing structures configured around exact processing time metrics (measured in milliseconds). | 15/06/2026 | 15/06/2026 | AWS Lambda Documentation |
| Tue | - Open the Lambda console and create a new function entity named `hoanganh-get-product-detail` configured for Node.js runtimes.<br>- Write parameter parsing logic inside the integrated web code editor engine. | 16/06/2026 | 16/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Wed | - Investigate secure ingress API proxy endpoints with **Amazon API Gateway**.<br>- Provision a decoupled **REST API** entry system registry called `hoanganh-serverless-api` to route traffic. | 17/06/2026 | 17/06/2026 | API Gateway Docs |
| Thu | - Create a new network routing resource sub-path named `/products` and bind a **GET** verb execution path to the Lambda function.<br>- Execute an **API Deployment** step publishing to a live environment stage named `prod` to obtain the entry URL. | 18/06/2026 | 18/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| Fri | - Open the **Postman** testing software installed on a local Windows machine to send network test payloads.<br>- Access the cloud consolidated analytics engine **Amazon CloudWatch Logs** to troubleshoot serverless code bugs. | 19/06/2026 | 19/06/2026 | Postman Guide |

---

## Outcomes

- Successfully built a modular serverless backend feature pipeline without needing to deploy or maintain 24/7 active compute cluster host instances.
- Penned the serverless functional event router logic execution handler (`index.js`) targeting AWS Lambda Node.js runtimes:
  ```javascript
  exports.handler = async (event) => {
      const productId = event.queryStringParameters ? event.queryStringParameters.productId : "Unknown";
      const response = {
          statusCode: 200,
          headers: { "Content-Type": "application/json", "Access-Control-Allow-Origin": "*" },
          body: JSON.stringify({ status: "Success", data: { id: productId, stock: 99, location: "SG-Warehouse" } }),
      };
      return response;
  };