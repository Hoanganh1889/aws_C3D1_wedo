---
title: "Worklog Tuần 12"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.12 </b> "
---
## Mục tiêu tuần 12

- Phân tích thống kê và kiểm toán chi phí tài khoản điện toán đám mây bằng các công cụ chuyên sâu (AWS Billing, Cost Explorer).
- Thực hiện quy trình dọn dẹp hạ tầng mạng và giải phóng hoàn toàn các tài nguyên phần cứng chạy ngầm để bảo mật ví tiền tài khoản.
- Đóng gói cấu trúc tệp tin mã lệnh cấu hình, script hệ thống lưu trữ dự phòng trên hệ điều hành Windows.
- Biên soạn, hoàn thiện nội dung cuốn báo cáo kết quả nhật ký thực tập 12 tuần định dạng văn bản PDF gửi lên hệ thống nhà trường.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Truy cập giao diện quản trị **AWS Billing Dashboard**, kích hoạt tính năng phân tích dữ liệu đồ thị **Cost Explorer**.<br>- Rà soát các dịch vụ tiêu tốn dung lượng tài nguyên phần cứng lớn trong suốt 3 tháng vừa qua để thống kê số liệu. | 06/07/2026 | 06/07/2026 | Tài liệu AWS Billing |
| 3 | - Bắt đầu chu trình dọn dẹp hệ thống: Vào EC2 Console, chọn toàn bộ danh mục máy chủ ảo đang hoạt động và thực hiện lệnh **Terminate** xóa sổ vĩnh viễn.<br>- Gỡ bỏ liên kết và hoàn trả tài nguyên địa chỉ IP tĩnh Elastic IP về kho của AWS. | 07/07/2026 | 07/07/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Vào dịch vụ RDS Console, tiến hành ra lệnh xóa bỏ máy chủ cơ sở dữ liệu MySQL (Tích chọn xác nhận không tạo file sao lưu Snapshot).<br>- Truy cập S3 Console, thực hiện lệnh rỗng hóa dữ liệu (**Empty Bucket**) và xóa bỏ hoàn toàn các cấu trúc Bucket trống. | 08/07/2026 | 08/07/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Tạo lập cấu trúc thư mục sao lưu lưu trữ an toàn đặt tên `AWS_Evidence_Backup` trên ổ đĩa máy tính Windows cá nhân.<br>- Gom và phân loại toàn bộ các file cấu hình mạng JSON, file mã nguồn Lambda, script cấu hình SQL đã làm để lưu giữ làm phụ lục. | 09/07/2026 | 09/07/2026 | Thư mục Windows Local |
| 6 | - Sử dụng ứng dụng văn phòng **Microsoft Word trên Windows** để tổng hợp toàn bộ số liệu biểu mẫu nhật ký 12 tuần thực tập.<br>- Biên soạn nội dung Lời mở đầu, Kết luận kiến thức, xuất bản file tệp tin kết quả định dạng PDF chính thức gửi trường. | 10/07/2026 | 10/07/2026 | Biểu mẫu nhà trường |

---

## Kết quả đạt được

- Hoàn thành thống kê số liệu chi phí tài khoản, xuất file dữ liệu báo cáo tài chính định dạng tệp tin `cost_analysis_june_july.csv` phục vụ đối chiếu công việc thực tập.
- Giải phóng triệt để hoàn toàn 100% các tài nguyên tính toán và dung lượng ổ đĩa cứng chạy ngầm trên Cloud AWS bằng các câu lệnh CLI dọn dẹp trực tiếp từ Windows Terminal:
  ```bash
  # Lệnh xóa sổ dọn dẹp nhanh một Bucket chứa tài liệu dữ liệu trên S3
  aws s3 rb s3://hoanganh-stylehub-bucket --force
  # Tập lệnh ra lệnh tắt và hủy vĩnh viễn Instance máy chủ gánh tải trên hạ tầng đám mây
  aws ec2 terminate-instances --instance-ids i-xxxxxxxxxxxxxxxxx