---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---
## Mục tiêu tuần 7

- Nghiên cứu mô hình triển khai ứng dụng tự động hóa dạng PaaS (Platform as a Service) với AWS Elastic Beanstalk.
- Làm chủ quy trình đóng gói sản phẩm mã nguồn Backend (Spring Boot/Node.js) từ môi trường Windows.
- Cấu hình quản lý, tách biệt các thông số môi trường bảo mật (Environment Properties) kết nối hệ thống cơ sở dữ liệu.
- Thành thạo kỹ năng tra cứu, phân tích nhật ký lỗi (Logs) trên Cloud để xử lý các sự cố Reverse Proxy mạng.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Mở mã nguồn dự án Backend trên máy tính Windows, thực hiện chạy các tập lệnh build để đóng gói toàn bộ mã nguồn ứng dụng.<br>- Nghiên cứu tổng quan cơ chế quản lý hạ tầng tự động của dịch vụ **AWS Elastic Beanstalk**. | 01/06/2026 | 01/06/2026 | Hướng dẫn Maven/Node.js |
| 3 | - Truy cập Beanstalk Console, tiến hành khởi tạo một Application mới mang tên `hoanganh-backend-app`.<br>- Cấu hình lựa chọn môi trường chạy mạng (Platform) tương ứng phù hợp với mã nguồn đồ án: Java (hoặc Node.js). | 02/06/2026 | 02/06/2026 | Tài liệu Elastic Beanstalk |
| 4 | - Tại mục Application code, tích chọn tính năng **Upload your code** để nạp file chạy.<br>- Thực hiện hành động đẩy trực tiếp tệp tin ứng dụng đã đóng gói từ ổ đĩa máy Windows lên hệ thống lưu trữ đám mây của AWS. | 03/06/2026 | 03/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Vào mục cấu hình cấu trúc phần mềm *Configuration -> Software* trên Beanstalk để thiết lập các biến môi trường.<br>- Ánh xạ thông tin cấu hình chuỗi kết nối an toàn trỏ đến Endpoint của cơ sở dữ liệu **Amazon RDS** (đã dựng ở tuần 5). | 04/06/2026 | 04/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 6 | - Theo dõi tiến trình khởi tạo hạ tầng mạng tự động của AWS. Thực hiện truy cập vào URL Endpoint kiểm thử hệ thống.<br>- Thực hành kỹ năng bóc tách, tải tệp tin log tập trung về máy Windows để chẩn đoán, sửa lỗi proxy cổng dịch vụ sập mạng. | 05/06/2026 | 05/06/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Kết quả đạt được

- Đóng gói thành công mã nguồn dự án ứng dụng từ hệ điều hành Windows thành tệp tin sản phẩm độc lập sẵn sàng triển khai qua các câu lệnh terminal:
  ```bash
  # Đối với dự án Java Spring Boot Maven
  mvn clean package
  # Kết quả sinh ra file chạy: target/mobileshop_backend-0.0.1-SNAPSHOT.jar