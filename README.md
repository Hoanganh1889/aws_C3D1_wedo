# 🏢 WeDo Workspace

> Nền tảng Quản lý Không gian làm việc cộng tác trên AWS Cloud

<div align="center">

![React](https://img.shields.io/badge/Frontend-ReactJS-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Backend-Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Docker](https://img.shields.io/badge/Container-Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/Cloud-AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![ECS](https://img.shields.io/badge/Deploy-ECS_Fargate-FF9900?style=for-the-badge&logo=amazonecs&logoColor=white)
![MySQL](https://img.shields.io/badge/Database-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

🌐 [Báo cáo Workshop cá nhân](https://hoanganh1889.github.io/aws_C3D1_wedo/) &nbsp; | &nbsp;
🎥 [Video Demo](https://drive.google.com/file/d/19jLMrXjSZSN6gKfXB3MJ4Kub92MRf-f-/view?usp=drive_link) &nbsp; | &nbsp;
🚀 [Trải nghiệm WeDo Workspace](http://wedo-frontend-2026.s3-website-ap-southeast-1.amazonaws.com/)

</div>

---

## 📖 Tổng quan dự án (Executive Summary)

Việc quản lý dự án và làm việc nhóm thường gặp nhiều khó khăn do dữ liệu bị phân tán trên các công cụ rời rạc, khiến việc theo dõi tiến độ trở nên thủ công và dễ sai sót.

**WeDo Workspace** giải quyết bài toán này bằng cách cung cấp một không gian làm việc tập trung. Hệ thống kết hợp sức mạnh của **Frontend ReactJS** và **Backend Spring Boot**, được đóng gói hoàn toàn bằng **Docker** và vận hành trên hạ tầng **AWS Cloud**.

Khác với các mô hình đơn giản, dự án được thiết kế với kiến trúc **Multi-AZ**, đảm bảo tính **High Availability**, tự động mở rộng theo tải và bảo mật tối đa từ ngoài rìa vào tận lõi cơ sở dữ liệu.

Đây là dự án **Capstone** trong khuôn khổ kỳ thực tập **AWS First Cloud AI Journey (FCAJ) - Workforce Bootcamp 2026**, thể hiện năng lực triển khai toàn diện từ thiết kế kiến trúc hạ tầng đến vận hành thực tế.

---

## 🏗️ Kiến trúc Hệ thống (System Architecture)

```
Client
   │
   ▼
CloudFront + WAF
   │
   ▼
S3 Static Hosting
   │
   ▼
Application Load Balancer (ALB)
   │
   ▼
ECS Fargate Cluster (Spring Boot)
   │
   ├── Amazon RDS MySQL (Multi-AZ)
   └── Amazon EFS / S3 Storage
```

### Các quyết định thiết kế cốt lõi

| Thành phần | Công nghệ | Lý do thiết kế |
|------------|------------|----------------|
| Frontend | ReactJS + S3 + CloudFront | Phân phối nội dung toàn cầu với Edge Caching |
| Load Balancing | ALB | Định tuyến HTTPS an toàn vào Private Subnet |
| Compute Core | ECS Fargate + Spring Boot | Serverless Container, Auto Scaling |
| Database | Amazon RDS MySQL Multi-AZ | High Availability và tự động đồng bộ dữ liệu |
| Storage | Amazon EFS & S3 | Lưu trữ tệp đính kèm an toàn |
| Security | VPC, NAT Gateway, Secrets Manager | Cách ly Backend và Database khỏi Internet |

---

## 🔍 Phân tích đa góc nhìn (Dual-Perspective Analysis)

### 🛠️ Góc nhìn Kỹ sư Đám mây (Cloud Engineer Lens)

- Thiết kế VPC với Public / Private Subnets
- Backend và Database không có Public IP
- Sử dụng VPC Endpoints để giảm chi phí NAT Gateway
- Quản lý mật khẩu bằng AWS Secrets Manager
- Auto Scaling theo CPU / Memory

### 💡 Góc nhìn Phân tích Kinh doanh (BA/SA Lens)

- Tối ưu trải nghiệm người dùng nhờ CloudFront CDN
- Giảm chi phí vận hành với mô hình Fargate pay-as-you-go
- CloudWatch Alarms cảnh báo khi CPU > 80%
- Giảm rủi ro gián đoạn dịch vụ với RDS Multi-AZ

---

## 📁 Cấu trúc Kho lưu trữ (Repository Structure)

```
AWS_C3D1_WEDO/
├── 1-Worklog/
├── 2-Proposal/
├── 3-BlogsPosted/
├── 4-EventParticipated/
├── 5-Workshop/
├── 6-Self-evaluation/
├── 7-Feedback/
└── README.md
```

---

## 🚀 Triển khai hệ thống (Deployment)

Hệ thống được triển khai theo mô hình CI/CD với GitHub Actions:

1. Push source code lên GitHub
2. GitHub Actions tự động build Hugo site
3. Deploy lên GitHub Pages
4. Frontend React deploy lên S3 + CloudFront
5. Backend Spring Boot deploy lên ECS Fargate

### Production URLs

- 📄 Workshop Report: https://hoanganh1889.github.io/aws_C3D1_wedo/
- 🌐 Frontend Demo: http://wedo-frontend-2026.s3-website-ap-southeast-1.amazonaws.com/

---

## 👨‍💻 Tác giả

**Nguyễn Hoàng Anh**

- GitHub: https://github.com/Hoanganh1889
- Internship Program: AWS First Cloud AI Journey 2026
- Project: AWS_C3D1_WEDO

---

<div align="center">

</div>
