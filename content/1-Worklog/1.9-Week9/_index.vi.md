---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---
## Mục tiêu tuần 9

- Nghiên cứu mô hình điện toán không máy chủ Serverless (Function-as-a-Service) với AWS Lambda.
- Thực hành viết và biên soạn mã nguồn hàm xử lý chức năng độc lập (Microservice) trên đám mây.
- Cấu hình cửa ngõ kết nối bảo mật, điều hướng và phân tách định tuyến luồng dữ liệu bằng Amazon API Gateway.
- Vận dụng công cụ Postman trên Windows để thực hiện kiểm thử, đánh giá dữ liệu phản hồi API Serverless.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Học lý thuyết nền tảng kiến trúc hướng sự kiện (Event-Driven Architecture) của AWS Lambda.<br>- Nghiên cứu cơ chế vận hành tính toán tài nguyên phần cứng tối ưu chi phí theo từng đơn vị mili-giây mã nguồn thực thi. | 15/06/2026 | 15/06/2026 | Tài liệu AWS Lambda |
| 3 | - Vào Lambda Console, thực hiện tạo mới hàm chức năng mang tên `hoanganh-get-product-detail` lựa chọn môi trường chạy Node.js.<br>- Viết trực tiếp đoạn mã xử lý bóc tách tham số dữ liệu đầu vào bằng trình soạn thảo mã tích hợp. | 16/06/2026 | 16/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Nghiên cứu dịch vụ quản lý cổng kết nối mạng **Amazon API Gateway**.<br>- Thực hiện cấu hình tạo một kiến trúc **REST API** độc lập đặt tên là `hoanganh-serverless-api` làm cửa ngõ định tuyến. | 17/06/2026 | 17/06/2026 | Tài liệu API Gateway |
| 5 | - Tạo mới đường dẫn tài nguyên `/products` và nạp phương thức **GET** liên kết trực tiếp với hàm AWS Lambda.<br>- Thực hiện hành động **Deploy API** xuất bản hệ thống lên môi trường chạy thực tế `prod` để nhận đường dẫn URL Endpoint công khai. | 18/06/2026 | 18/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 6 | - Sử dụng phần mềm **Postman** cài đặt trên hệ điều hành Windows để cấu hình gửi các gói tin kiểm thử dữ liệu.<br>- Truy cập hệ thống xem nhật ký lỗi tập trung **Amazon CloudWatch Logs** để thực hiện kỹ năng gỡ lỗi debug mã nguồn Serverless. | 19/06/2026 | 19/06/2026 | Hướng dẫn Postman |

---

## Kết quả đạt được

- Triển khai xây dựng thành công một phân hệ chức năng hoàn chỉnh theo mô hình Serverless không máy chủ gánh tải phần cứng liên tục.
- Biên soạn thành công mã nguồn hàm điều phối xử lý logic (`index.js`) chạy trên môi trường AWS Lambda Node.js Runtime:
  ```javascript
  exports.handler = async (event) => {
      const productId = event.queryStringParameters ? event.queryStringParameters.productId : "Unknown";
      const response = {
          statusCode: 200,
          headers: { "Content-Type": "application/json", "Access-Control-Allow-Origin": "*" },
          body: JSON.stringify({ status: "Success", data: { id: productId, stock: 99, location: "SG-Warehouse" } }),
      };
      return response;
  };