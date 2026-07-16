---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---
## Mục tiêu tuần 11

- Nghiên cứu triết lý vận hành tự động hóa quy trình phát triển phần mềm theo mô hình CI/CD (Continuous Integration / Continuous Deployment).
- Thiết lập đường ống tự động giám sát liên thông giữa kho chứa mã nguồn GitHub và môi trường đám mây Cloud AWS.
- Cấu hình các giai đoạn xử lý dữ liệu tự động (Source Stage, Deploy Stage) trong dịch vụ AWS CodePipeline.
- Thực hành đẩy lệnh cập nhật mã nguồn (Git Push) từ máy Windows để kiểm thử chu trình tự động hóa triển khai sản phẩm.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Tìm hiểu lý thuyết về mô hình tự động hóa DevOps.<br>- Nghiên cứu kiến trúc hoạt động của công cụ đường ống **AWS CodePipeline** và cách thức tạo lập Service Role cấp quyền hoạt động nội bộ dịch vụ. | 29/06/2026 | 29/06/2026 | Tài liệu CodePipeline |
| 3 | - Khởi tạo một Pipeline mới đặt tên quản trị là `hoanganh-stylehub-pipeline`.<br>- Tại mục cấu hình **Source Stage**, lựa chọn kết nối xác thực tài khoản qua giao thức GitHub (Version 2) trỏ vào đúng Repository đồ án. | 30/06/2026 | 30/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Cấu hình giai đoạn đầu ra **Deploy Stage**: Lựa chọn dịch vụ đích đến là nền tảng quản lý ứng dụng **AWS Elastic Beanstalk** đã dựng sẵn.<br>- Chọn liên kết chính xác tên ứng dụng và môi trường máy chủ đang chạy để nạp luồng dữ liệu tự động. | 01/07/2026 | 01/07/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Mở mã nguồn dự án bằng công cụ **VS Code trên Windows**.<br>- Thực hiện thao tác chỉnh sửa thay đổi một đoạn text giao diện nhỏ tĩnh trên file trang chủ, mở cửa sổ terminal gõ tập lệnh Git truyền thống để thực hiện đẩy code lên internet. | 02/07/2026 | 02/07/2026 | Hướng dẫn Git/GitHub |
| 6 | - Theo dõi tiến độ chạy đồ thị trực quan của các trạm xử lý trong đường ống trên giao diện Web Console.<br>- Phát hiện và thực hiện chỉnh sửa cấu hình phân quyền hệ thống để xử lý các lỗi ách tắc dữ liệu giữa đường ống và S3 storage. | 03/07/2026 | 03/07/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Kết quả đạt được

- Thiết lập và vận hành thành công hệ thống đường ống tự động hóa CI/CD hoàn chỉnh khép kín. Loại bỏ hoàn toàn quy trình đóng gói thủ công bằng tay và việc dùng các phần mềm SFTP để upload đè file lên server như giai đoạn trước.
- Cấu hình liên kết thành công Webhook lắng nghe sự kiện từ nhánh `main` của kho chứa GitHub.
- Thực thi thành công chuỗi lệnh đẩy mã nguồn cập nhật từ hệ điều hành Windows cá nhân lên hệ thống quản lý phiên bản:
  ```bash
  git add .
  git commit -m "Fix title homepage for AWS pipeline demo"
  git push origin main