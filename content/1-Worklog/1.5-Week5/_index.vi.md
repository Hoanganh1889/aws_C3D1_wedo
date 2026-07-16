---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

## Mục tiêu tuần 5

- Nghiên cứu mô hình cơ sở dữ liệu quan hệ được quản lý hoàn toàn với Amazon RDS (Relational Database Service).
- Quy hoạch vùng mạng con an toàn độc lập (DB Subnet Group) phục vụ cô lập dữ liệu.
- Thiết lập tường lửa bảo mật, phân tách quyền truy cập tầng dữ liệu (Port 3306).
- Sử dụng các phần mềm quản trị giao diện GUI trên hệ điều hành Windows để quản lý, truy vấn dữ liệu đám mây từ xa.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Truy cập RDS Dashboard, tiến hành khởi tạo một **DB Subnet Group** mới gắn với vùng mạng `HoangAnh-VPC`.<br>- Chọn liên kết duy nhất dải mạng con `Private-Subnet` nhằm đảm bảo máy chủ Database không có lối thoát trực tiếp ra mạng internet. | 18/05/2026 | 18/05/2026 | Tài liệu AWS RDS |
| 3 | - Tiến hành cấu hình các thông số khởi tạo Database Instance:<br>&emsp;+ Engine: **MySQL Community** (Version 8.0).<br>&emsp;+ Gói tài khoản: **Free Tier** (Instance type: `db.t3.micro`).<br>&emsp;+ Thiết lập Master Username (`admin`), Master Password bảo mật.<br>&emsp;+ Cấu hình bộ nhớ lưu trữ ổ đĩa: 20 GiB gp2. | 19/05/2026 | 19/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Tạo một Group bảo mật mới dành riêng cho tầng dữ liệu mang tên `HoangAnh-RDS-SG`.<br>- Cấu hình quy tắc Inbound rules: Chỉ cho phép giao thức **MySQL/Aurora (Port 3306)** với nguồn (Source) trỏ đích danh về ID của Security Group thuộc máy chủ EC2. | 20/05/2026 | 20/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Tải và cài đặt phần mềm quản trị dữ liệu đồ họa **DBeaver** (hoặc MySQL Workbench) trên hệ điều hành Windows.<br>- Chờ trạng thái RDS chuyển sang `Available`, tiến hành sao chép chuỗi đường dẫn dữ liệu kết nối chuyên biệt (**Endpoint**). | 21/05/2026 | 21/05/2026 | Hướng dẫn DBeaver |
| 6 | - Thực hiện cấu hình thông số kết nối TCP/IP trên DBeaver thông qua Endpoint của AWS.<br>- Viết bản cấu hình lệnh SQL chạy thực tế để khởi tạo các cấu trúc bảng dữ liệu mẫu cho đồ án thực tập. | 22/05/2026 | 22/05/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Kết quả đạt được

- Thiết lập thành công hệ thống cơ sở dữ liệu quan hệ **Amazon RDS MySQL** chạy khép kín an toàn bên trong phân vùng Private Subnet mạng nội bộ.
- Cấu hình tường lửa lớp dữ liệu vững chắc, thực thi nguyên tắc *"Quyền hạn tối thiểu"*, ngăn chặn tuyệt đối các dải mạng bên ngoài internet dò quét cổng 3306.
- Sử dụng thành thạo công cụ **DBeaver trên Windows** kết nối quản trị hệ thống Cloud từ xa qua chuỗi thông số cấu hình:
  - **Server Host (Endpoint):** `hoanganh-db.xxxxxxxxxxxx.ap-southeast-1.rds.amazonaws.com`
  - **Port:** `3306` | **Username:** `admin`
- Thực thi thành công file mã lệnh cấu hình khởi tạo cấu trúc schema cơ sở dữ liệu mẫu (`init_schema.sql`) ngay trên môi trường Windows đồ họa:
  ```sql
  CREATE DATABASE mobileshop_db;
  USE mobileshop_db;
  CREATE TABLE products (
      id INT PRIMARY KEY AUTO_INCREMENT,
      product_name VARCHAR(255) NOT NULL,
      price DECIMAL(10,2),
      stock_quantity INT
  );