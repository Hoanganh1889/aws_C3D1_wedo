---
title: "Worklog Tuần 3"
date: 2026-04-17
weight: 1
chapter: false
pre: "<b>1.3. </b> "
---

## Mục tiêu tuần 3

- Nghiên cứu kiến trúc mạng ảo độc lập Amazon VPC (Virtual Private Cloud).
- Thành thạo quy trình thiết kế, chia dải mạng con bằng kỹ thuật tính toán IP Subnetting.
- Cấu hình sơ đồ tuyến đường định tuyến logic (Internet Gateway, Route Tables).
- Sử dụng các công cụ chẩn đoán mạng trên hệ điều hành Windows để kiểm thử liên thông hạ tầng Cloud.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Học lý thuyết nền tảng mạng đám mây: Địa chỉ IP, dải mạng theo chuẩn CIDR block.<br>- Phân tích và phân chia mô hình mạng 2 lớp: **Public Subnet** (cho máy chủ Web) và **Private Subnet** (cho Cơ sở dữ liệu nội bộ). | 04/05/2026 | 04/05/2026 | Tài liệu AWS Network |
| 3 | - Truy cập VPC Dashboard, khởi tạo vùng mạng ảo độc lập mang tên `HoangAnh-VPC` dải mạng `10.0.0.0/16`.<br>- Thực hiện tạo thủ công hai Subnets độc lập nằm tại Availability Zone `ap-southeast-1a` (Singapore). | 05/05/2026 | 05/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Khởi tạo cổng internet **Internet Gateway (IGW)** và liên kết trực tiếp vào mạng VPC.<br>- Tạo bảng định tuyến mới `Public-Route-Table`, thực hiện cấu hình thêm rule định tuyến hướng toàn bộ lưu lượng mạng ra ngoài cổng IGW. | 06/05/2026 | 06/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Tiến hành liên kết bảng định tuyến công khai vào vùng `Public-Subnet`. Đảm bảo cô lập hoàn toàn mạng `Private-Subnet` với môi trường internet.<br>- Launch thử một instance EC2 nằm trong VPC mới để chuẩn bị cấu hình kiểm tra định tuyến mạng. | 07/05/2026 | 07/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| 6 | - Mở cửa sổ **Windows PowerShell**, áp dụng các câu lệnh kiểm tra kết nối mạng chuyên sâu đến máy chủ AWS.<br>- Nghiên cứu nâng cao quy chế bảo mật lọc gói tin hai lớp: **Security Group** (tầng máy chủ) và **Network ACL** (tầng mạng con). | 08/05/2026 | 08/05/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Kết quả đạt được

- Thiết kế và phân hoạch thành công kiến trúc mạng an toàn độc lập (2-Tier Architecture) gồm:
  - Một mạng ảo lớn: `HoangAnh-VPC` (Dải IP: `10.0.0.0/16` chứa 65,536 địa chỉ IP).
  - Một vùng công khai: `Public-Subnet` (Dải IP: `10.0.1.0/24` cung cấp 251 IP khả dụng cho máy chủ Web Server).
  - Một vùng nội bộ: `Private-Subnet` (Dải IP: `10.0.2.0/24` cung cấp 251 IP khả dụng cô lập cho Database Server).
- Thiết lập bảng định tuyến `Public-Route-Table` cấu hình dòng định tuyến (Route) mở cửa ngõ cho phép mọi máy chủ thuộc Public Subnet đi ra ngoài internet công cộng thành công:
  - **Destination:** `0.0.0.0/0` 
  - **Target:** `igw-xxxxxxxxxxxxxxxxx` (HoangAnh-IGW)
- Làm chủ kỹ năng chẩn đoán mạng từ xa bằng các công cụ dòng lệnh hệ thống có sẵn trên Windows Terminal/PowerShell:
  ```bash
  # Kiểm tra tính thông suốt kết nối của cổng dịch vụ SSH (Port 22) từ Windows lên AWS VPC
  Test-NetConnection -ComputerName 54.254.xx.xx -Port 22
  # Phân tích các bước nhảy mạng đường truyền gói tin internet từ máy cá nhân lên Cloud
  tracert 54.254.xx.xx