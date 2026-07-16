---
title: "Các bài blogs đã đăng"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

###  [Blog 1 - ĐƯA AI VÀO XÂY DỰNG ỨNG DỤNG NHẬN DIỆN CALO & PROTEIN CÙNG AWS SERVERLESS](3.1-Blog1/)
Bài viết giới thiệu kiến trúc thực chiến ứng dụng nền tảng AWS Serverless kết hợp cùng trí tuệ nhân tạo để phát triển "AI Diet Tracker" – một trợ lý cá nhân tự động phân tích và theo dõi chế độ dinh dưỡng. Giải pháp này giúp chuyển hóa công việc cân đo đong đếm thủ công, tra cứu từng lạng ức gà hay thịt bò khô khan thành một thao tác chụp ảnh đơn giản. Từ đó, giải quyết triệt để rào cản thời gian trong việc theo dõi macro (calo, protein) cho những người duy trì lịch tập luyện cường độ cao.

###  [Blog 2 - Tối ưu hóa hiệu năng ứng dụng Spring Boot Serverless trên AWS Lambda với tính năng SnapStart](3.2-Blog2/)
Giải pháp triển khai Spring Boot theo mô hình Serverless trên AWS Lambda kết hợp SnapStart nhằm giảm thời gian Cold Start, nâng cao hiệu năng xử lý yêu cầu. Hệ thống tích hợp Amazon API Gateway, AWS Secrets Manager và Amazon RDS để xây dựng một kiến trúc vừa tối ưu tốc độ, vừa đảm bảo tính bảo mật và khả năng mở rộng trên nền tảng AWS.

###  [Blog 3 - TỐI ƯU HIỆU NĂNG VÀ GIẢM TẢI DB: KIẾN TRÚC CACHING CHIẾN LƯỢC CACHE-ASIDE VỚI SPRING BOOT VÀ AMAZON ELASTICACHE](3.3-Blog3/)

Bài viết chia sẻ một giải pháp kiến trúc thực chiến giúp tăng tốc độ phản hồi API đáng kể và giải quyết triệt để bài toán nghẽn cổ chai (bottleneck) cho cơ sở dữ liệu quan hệ khi traffic tăng đột biến. Bằng cách sử dụng chiến lược Cache-Aside (Lazy Loading) với Amazon ElastiCache (Redis), hệ thống giảm thiểu chi phí scale-up đắt đỏ, tối ưu I/O và mang lại độ trễ cực thấp cho các ứng dụng backend Spring Boot.