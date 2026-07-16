---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---
## Mục tiêu tuần 10

- Nghiên cứu quy chuẩn quản lý danh tính, phân tách và quản trị quyền hạn người dùng với AWS IAM.
- Thiết lập hàng rào bảo mật, kích hoạt mã xác thực hai lớp (MFA) cho tài khoản gốc quản trị hệ thống đám mây.
- Thực hành phân chia nhóm làm việc (IAM Groups) và người dùng phụ (IAM Users) theo triết lý bảo mật hạn chế quyền tối thiểu.
- Thực hành phân bổ và liên kết mã khóa lập trình (Access Keys) phục vụ tương tác hệ thống dòng lệnh an toàn từ Windows.

---

## Các công việc triển khai

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
|:---:|-----------|:------------:|:---------------:|----------------|
| 2 | - Nghiên cứu các lỗ hổng rủi ro an ninh thông tin khi lạm dụng tài khoản Root của AWS hàng ngày.<br>- Sử dụng điện thoại cá nhân cài đặt ứng dụng **Google Authenticator**, thực hiện quét mã cấu hình lớp bảo mật **MFA** xác thực tài khoản Root. | 22/06/2026 | 22/06/2026 | Tài liệu AWS IAM |
| 3 | - Truy cập giao diện quản trị IAM Console, tiến hành tạo một cấu trúc nhóm làm việc mới mang tên `Developer-Group`.<br>- Tìm kiếm và thực hiện đính kèm chính sách quyền hạn giới hạn có sẵn của hệ thống đám mây mang tên `PowerUserAccess`. | 23/06/2026 | 23/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 4 | - Thực hiện các bước tạo mới một tài khoản người dùng phụ đặt tên danh tính làm việc là `hoanganh-dev`.<br>- Tiến hành thêm người dùng này trực tiếp vào nhóm mạng `Developer-Group` để thừa hưởng toàn bộ danh mục quyền hạn quy định. | 24/06/2026 | 24/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 5 | - Truy cập tab thông tin bảo mật của User phụ, tiến hành khởi tạo một cặp mã khóa lập trình dòng lệnh **Access Key** mới.<br>- Tải và thực hiện lưu trữ bảo mật file dữ liệu chứa thông tin khóa định dạng bảng `.csv` về ổ đĩa máy tính Windows cá nhân. | 25/06/2026 | 25/06/2026 | https://cloudjourney.awsstudygroup.com/ |
| 6 | - Mở cửa sổ **Windows PowerShell**, chạy lệnh cấu hình nạp thông số định danh để chuyển sang thao tác hoàn toàn bằng User phụ.<br>- Thực hành chạy thử các lệnh tạo tài nguyên và rà soát xử lý các lỗi chặn quyền truy cập bảo mật hệ thống mạng con. | 26/06/2026 | 26/06/2026 | https://cloudjourney.awsstudygroup.com/ |

---

## Kết quả đạt được

- Khóa và cô lập thành công hoàn toàn tài khoản tối cao Root Account bằng ứng dụng tạo mã số nhảy thời gian thực OTP Google Authenticator.
- Quy hoạch phân tách phòng ban thành công trên Cloud qua Group `Developer-Group` sở hữu quyền hạn phát triển phần mềm rộng nhưng bị chặn tuyệt đối quyền can thiệp vào sửa đổi cấu trúc thẻ tín dụng hóa đơn tiền của tài khoản.
- Khởi tạo thành công file lưu trữ dữ liệu thông tin định danh mật mã hệ thống đám mây (`credentials.csv`) chứa các chuỗi khóa phục vụ lập trình từ xa.
- Thực hiện cấu hình nạp thông tin tài khoản phụ thành công vào nền tảng hệ điều hành Windows qua câu lệnh:
  ```bash
  aws configure
  # Nạp chuỗi Access Key ID và Secret Access Key từ file csv
  # Cấu hình Default region name: ap-southeast-1 | Default output format: json