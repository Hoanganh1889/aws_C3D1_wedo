---
title: "Worklog Tuần 4"
date: 2026-04-17
weight: 1
chapter: false
pre: "<b>1.4. </b> "
---

## Mục tiêu tuần 4

- Cài đặt, cấu hình và quản trị dịch vụ Nginx Web Server trên môi trường Linux Ubuntu.
- Sử dụng các công cụ giao thức kết nối bảo mật (SFTP) trên Windows để quản lý, truyền tải dữ liệu mã nguồn lên Cloud.
- Làm chủ kỹ năng xử lý phân quyền bảo mật tệp tin nâng cao trên hệ điều hành Windows.
- Khởi tạo và thiết lập cơ chế IP tĩnh cố định (Elastic IP) cho máy chủ ứng dụng.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Kết nối SSH vào máy chủ EC2 Ubuntu, chạy các tập lệnh cập nhật gói hệ thống mạng nội bộ.<br>- Thực hiện cài đặt dịch vụ Nginx làm ứng dụng Web Server gánh tải. | 11/05/2026 | 11/05/2026 | Tài liệu Linux/Nginx |
| 3 | - Tải và cài đặt phần mềm quản lý truyền tải dữ liệu **WinSCP** trên Windows.<br>- Cấu hình khởi tạo phiên làm việc (Session) mới qua giao thức bảo mật SFTP sử dụng file cặp khóa `.pem` để liên thông giữa Windows và Linux. | 12/05/2026 | 12/05/2026 | Hướng dẫn WinSCP |
| 4 | - Sử dụng tính năng kéo-thả trực quan của WinSCP để chuyển bộ mã nguồn trang giao diện web mẫu từ máy Windows lên thư mục lưu trữ gốc của Nginx trên máy chủ AWS.<br>- Sử dụng dòng lệnh Linux cấu hình kiểm tra phân quyền tệp tin hệ thống. | 13/05/2026 | 13/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Nghiên cứu sâu về lỗi phân quyền file khóa (`Permission denied - Warning: Unprotected Private Key File`).<br>- Thực hành dùng lệnh hệ thống hoặc giao diện đồ họa nâng cao trên Windows để cô lập quyền truy cập tệp dữ liệu khóa bí mật. | 14/05/2026 | 14/05/2026 | Tài liệu AWS Security |
| 6 | - Thực hiện đăng ký và gán địa chỉ IP tĩnh **Elastic IP** vào Instance EC2 để cố định đường dẫn kết nối.<br>- Sử dụng trình duyệt Edge/Chrome trên Windows truy cập kiểm tra hiển thị trang web thông qua địa chỉ IP mới. | 15/05/2026 | 15/05/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Kết quả đạt được

- Triển khai cài đặt thành công dịch vụ Nginx Web Server chạy ổn định trên nền tảng Linux đám mây bằng các câu lệnh:
  ```bash
  sudo apt update && sudo apt upgrade -y
  sudo apt install nginx -y
  sudo systemctl start nginx
  sudo systemctl enable nginx