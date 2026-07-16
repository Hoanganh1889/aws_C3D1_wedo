---
title: "Worklog Tuần 2"
date: 2026-04-17
weight: 1
chapter: false
pre: "<b>1.2. </b> "
---

## Mục tiêu tuần 2

- Nghiên cứu cơ chế lưu trữ đối tượng (Object Storage) với Amazon S3.
- Làm chủ kỹ năng cấu hình phân quyền truy cập, bảo mật tài nguyên S3 (Bucket Policy, Block Public Access).
- Vận dụng AWS CLI trên Windows để đồng bộ dữ liệu cục bộ lên hạ tầng Cloud.
- Triển khai chạy thực tế một ứng dụng trang web tĩnh trực tiếp trên Amazon S3.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Tìm hiểu lý thuyết Amazon S3 (Bucket, Object, Key, Metadata).<br>- Phân biệt các lớp lưu trữ (Storage Classes) như Standard, Intelligent-Tiering, Standard-IA, Glacier để tối ưu chi phí. | 27/04/2026 | 27/04/2026 | Tài liệu AWS S3 |
| 3 | - Truy cập S3 Console, tạo một Bucket mới với tên định danh duy nhất tại Region Singapore.<br>- Thực hành Upload/Download thủ công các file hình ảnh dữ liệu mẫu từ máy Windows lên S3 Bucket.<br>- Kích hoạt tính năng Bucket Versioning để quản lý đa phiên bản tệp tin. | 28/04/2026 | 28/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Tìm hiểu cơ chế bảo mật mạng của S3.<br>- Thực hành tắt tính năng Block Public Access.<br>- Viết mã cấu hình Bucket Policy bằng định dạng JSON để mở quyền truy cập đọc công khai cho các tệp tin hình ảnh sản phẩm. | 29/04/2026 | 29/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Sử dụng cửa sổ Windows PowerShell tương tác với S3 thông qua AWS CLI.<br>- Thực hành lệnh tạo bucket (`mb`) và lệnh đồng bộ dữ liệu (`sync`) toàn bộ thư mục asset từ ổ đĩa máy tính Windows lên đám mây. | 30/04/2026 | 30/04/2026 | https://cloudjourney.awsstudygroup.com/ |
| 6 | - Nghiên cứu tính năng Static Website Hosting trên S3.<br>- Thực hiện cấu hình chỉ định file `index.html` và `error.html` làm trang mặc định.<br>- Upload mã nguồn web tĩnh và kiểm thử truy cập qua đường link Endpoint. | 01/05/2026 | 01/05/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Kết quả đạt được

- Hiểu rõ nguyên lý hoạt động của S3 Object Storage và phân biệt được sự khác biệt với Block Storage (EBS).
- Khởi tạo thành công S3 Bucket có bật tính năng **Bucket Versioning**, cho phép ghi đè và khôi phục các phiên bản cũ của tệp tin một cách an toàn.
- Viết và áp dụng thành công đoạn mã cấu hình **Bucket Policy** (JSON) cho phép người dùng bên ngoài đọc file ảnh sản phẩm mà không làm lộ quyền quản trị:
  ```json
  {
      "Version": "2012-10-17",
      "Statement": [
          {
              "Sid": "PublicReadGetObject",
              "Effect": "Allow",
              "Principal": "*",
              "Action": "s3:GetObject",
              "Resource": "arn:aws:s3:::hoanganh-stylehub-bucket/*"
          }
      ]
  }