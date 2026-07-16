---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
## Mục tiêu tuần 6

- Nghiên cứu mô hình và tư duy lưu trữ phi cấu trúc NoSQL Key-Value với Amazon DynamoDB.
- Khởi tạo bảng dữ liệu phi quan hệ, tối ưu cấu hình phân bổ tài nguyên lưu trữ theo nhu cầu sử dụng (On-Demand).
- Thực hành thao tác xử lý dữ liệu phức hợp (Document JSON) trực tiếp trên giao diện đám mây.
- Sử dụng công cụ dòng lệnh AWS CLI trên Windows để thực thi các câu lệnh quét (Scan) và truy vấn (Query) dữ liệu nâng cao.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Nghiên cứu lý thuyết thiết kế cấu trúc dữ liệu NoSQL (Schemaless).<br>- Phân tích cách thức phân tách và chọn định danh cho khóa chính bao gồm: **Partition Key** (Khóa phân vùng) và **Sort Key** (Khóa sắp xếp). | 25/05/2026 | 25/05/2026 | Tài liệu DynamoDB |
| 3 | - Vào dịch vụ DynamoDB, thực hiện tạo bảng dữ liệu mang tên `Products_Cache`. Thiết lập thuộc tính Partition Key là `ProductID` (Kiểu String).<br>- Chỉnh sửa mục cấu hình tính phí, chuyển sang chế độ **On-Demand** để tối ưu hóa ngân sách tài khoản sinh viên. | 26/05/2026 | 26/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Sử dụng bảng điều khiển web *Explore items* để thực hiện các thao tác thêm, sửa, xóa dữ liệu (CRUD).<br>- Thực hành định nghĩa các dòng bản ghi chứa các cấu trúc thuộc tính động không đồng nhất (đặc trưng linh hoạt của NoSQL). | 27/05/2026 | 27/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Sử dụng công cụ **Windows PowerShell** chạy các câu lệnh AWS CLI để truy xuất quét lấy toàn bộ mảng dữ liệu từ xa.<br>- Nghiên cứu chuyên sâu phân biệt hiệu năng và chi phí vận hành giữa hai tập lệnh: **Scan** và **Query**. | 28/05/2026 | 28/05/2026 | https://cloudjourney.awsstudygroup.com/ |
| 6 | - Xử lý vấn đề lỗi xung đột ký tự định dạng chuỗi JSON khi gõ lệnh trực tiếp trên Windows Terminal.<br>- Thực hành biên soạn tệp tin cấu hình điều kiện dạng file tĩnh độc lập để truyền tải đối số dữ liệu an toàn. | 29/05/2026 | 29/05/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Kết quả đạt được

- Khởi tạo thành công hệ thống dữ liệu phi quan hệ **Amazon DynamoDB** vận hành theo cơ chế Serverless hoàn toàn, có năng lực tự động co giãn băng thông theo lưu lượng thực tế.
- Thực hành nạp thành công các Item mẫu định dạng cấu trúc JSON phong phú dữ liệu:
  ```json
  {
    "ProductID": {"S": "P001"},
    "ProductName": {"S": "iPhone 15 Pro Max"},
    "Price": {"N": "30000000"},
    "Attributes": {"M": {"Color": {"S": "Titanium"}, "Storage": {"S": "256GB"}}}
  }