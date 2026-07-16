---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---
## Mục tiêu tuần 8

- Nghiên cứu kiến trúc phân tán tính sẵn sàng cao (High Availability) dùng Application Load Balancer (ALB).
- Khởi tạo khuôn mẫu cấu hình máy chủ tự động khởi sinh (Launch Template).
- Thiết lập nhóm tự động co giãn co giãn (Auto Scaling Group) phân tách hạ tầng đa vùng mạng.
- Sử dụng các công cụ chuyên dụng trên Windows để thực hiện kiểm thử ép tải (Stress Test) hạ tầng hệ thống đám mây.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Vào EC2 Dashboard, tiến hành khởi tạo một bộ cân bằng tải **Application Load Balancer (ALB)** tên `hoanganh-web-alb`.<br>- Khởi tạo một **Target Group** cấu hình cổng dịch vụ, nạp đường dẫn theo dõi kiểm tra sức khỏe hệ thống (**Health Check Path**). | 08/06/2026 | 08/06/2026 | Tài liệu AWS ELB |
| 3 | - Tạo mới một **Launch Template** định hình sẵn các thông số máy chủ ảo tự động nhân bản bao gồm: AMI Ubuntu, Instance type máy trạm, Security Group mạng.<br>- Nhúng mã lệnh cấu hình tự động cài cắm môi trường web vào phần cấu hình dữ liệu mở rộng **User Data**. | 09/06/2026 | 09/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Thiết lập nhóm tự động co giãn **Auto Scaling Group (ASG)** liên kết trực tiếp với Launch Template.<br>- Quy hoạch phân bổ đều máy chủ ảo vào cả hai vùng mạng `Public-Subnet` đa trung tâm dữ liệu để tăng mức độ chịu tải dự phòng. | 10/06/2026 | 10/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Chỉnh sửa cấu hình kích thước nhóm quản lý máy chủ (Group Size): Đặt mức Desired: 2, Min: 1, Max: 4.<br>- Định nghĩa chính sách co giãn tự động co giãn co giãn (**Target Tracking Scaling Policy**) dựa trên chỉ số mức độ tiêu thụ tài nguyên phần cứng CPU trung bình. | 11/06/2026 | 11/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 6 | - Cài đặt công cụ kiểm thử hiệu năng chuyên sâu **Apache JMeter** trên hệ điều hành Windows.<br>- Thiết lập kịch bản giả lập lưu lượng truy cập lớn chạy ép tải liên tục vào địa chỉ DNS định danh của bộ cân bằng tải để theo dõi phản ứng tự động mở rộng mạng của AWS. | 12/06/2026 | 12/06/2026 | Hướng dẫn JMeter |

---

## Kết quả đạt được

- Triển khai thành công kiến trúc hạ tầng tự phục hồi dữ liệu và cân bằng tải phân tán thông minh bằng cách liên kết ALB với Target Group trỏ vào đường dẫn giám sát của mã nguồn: `/actuator/health` (hoặc `/status`).
- Biên soạn thành công đoạn mã Script tự động triển khai môi trường Web chạy ngầm nhúng vào cấu trúc tệp tin máy chủ (**User Data**):
  ```bash
  #!/bin/bash
  sudo apt update
  sudo apt install nginx -y
  sudo systemctl start nginx