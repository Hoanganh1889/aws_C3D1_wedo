---
title: "Worklog Tuần 1"
date: 2026-04-17
weight: 1
chapter: false
pre: "<b>1.1.</b> "
---

## Mục tiêu tuần 1

- Kết nối và làm quen với các thành viên trong chương trình First Cloud Journey (FCJ).
- Hiểu tổng quan về nền tảng AWS và các nhóm dịch vụ chính.
- Làm quen với AWS Management Console và cài đặt môi trường làm việc trên Windows.
- Khởi tạo, cấu hình và remote bảo mật vào máy chủ ảo Amazon EC2 đầu tiên.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Gặp gỡ, làm quen với các thành viên và Mentor nhóm dự án FCJ.<br>- Đọc, tìm hiểu nội quy, quy định an ninh thông tin và giờ giấc làm việc tại đơn vị. | 17/04/2026 | 17/04/2026 | Sổ tay đơn vị |
| 3 | - Tìm hiểu tổng quan về Cloud Computing (IaaS, PaaS, SaaS).<br>- Nghiên cứu lý thuyết các nhóm dịch vụ AWS chính:<br>&emsp;+ Compute (EC2)<br>&emsp;+ Storage (S3, EBS)<br>&emsp;+ Networking (VPC)<br>&emsp;+ Database (RDS, DynamoDB) | 20/04/2026 | 20/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Tạo tài khoản AWS Free Tier bằng trình duyệt Windows.<br>- Thiết lập bảo mật tài khoản gốc (Root Account) bằng cách bật Multi-Factor Authentication (MFA) qua ứng dụng Google Authenticator trên điện thoại. | 21/04/2026 | 21/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Tải và cài đặt bộ công cụ AWS CLI v2 dành cho Windows.<br>- Khởi tạo Access Key ID và Secret Access Key trên IAM Console.<br>- Cấu hình AWS CLI trên Windows PowerShell và thực hành các tập lệnh kiểm tra cơ bản. | 22/04/2026 | 23/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| 6 | - Thực hành triển khai máy chủ ảo Amazon EC2 (Ubuntu 22.04 LTS, t2.micro).<br>- Cấu hình Security Group mở port 22, port 80.<br>- Khắc phục lỗi phân quyền file key `.pem` trên Windows Properties và kết nối SSH từ xa thành công.<br>- Thực hành tạo và gắn thêm ổ đĩa EBS Volume vào máy chủ. | 24/04/2026 | 24/04/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Kết quả đạt được

- Hiểu được khái niệm Cloud Computing và vai trò của AWS trong điện toán đám mây.
- Tạo thành công tài khoản AWS Free Tier và bảo mật tài khoản Root bằng lớp xác thực hai lớp MFA.
- Cài đặt thành công AWS CLI v2 trên hệ điều hành Windows. Thực hiện cấu hình môi trường bằng lệnh:
  ```bash
  aws configure
  # Cấu hình: Access Key ID, Secret Access Key, Default Region (ap-southeast-1), Output (json)