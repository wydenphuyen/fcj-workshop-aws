---
title: "Blogs Posted"
date: 2026-04-20
weight: 3
chapter: false
pre: " <b> 3. </b> "
---


Phần này tổng hợp các bài viết kỹ thuật (Blog) đã chia sẻ trên AWS Study Group về quá trình thiết kế và triển khai hệ thống Web Application trên AWS.

---

## Danh sách các bài viết Blog đã đăng:

### 3.1. Tổng quan kiến trúc AWS đề xuất
* **Đường dẫn bài viết:** [Xem chi tiết tại đây](./3.1-blog1/)
* **Tóm tắt nội dung:** Bài viết giới thiệu tổng quan về mô hình kiến trúc 3 tầng (3-Tier Architecture) được áp dụng cho dự án doanh nghiệp. Phân tích cách phân tách rõ ràng giữa tầng giao diện (Frontend trên S3/CloudFront), tầng xử lý logic (Backend trên EC2/ASG/ALB) và tầng lưu trữ dữ liệu (RDS/DynamoDB).

### 3.2. Blog 2: Phân tích chi tiết luồng xử lý dữ liệu
* **Đường dẫn bài viết:** [Xem chi tiết tại đây](./3.2-blog2/)
* **Tóm tắt nội dung:** Đi sâu phân tích hành trình của một request từ người dùng đi qua hệ thống phân giải tên miền Route 53, qua CDN CloudFront, chạm tới Application Load Balancer để phân phối vào các máy chủ EC2 trong Private Subnet, và cách hệ thống truy vấn dữ liệu an toàn xuống Amazon RDS và DynamoDB.

### 3.3. Blog 3: Bảo mật và Tự động mở rộng (Auto Scaling)
* **Đường dẫn bài viết:** [Xem chi tiết tại đây](./3.3-blog3/)
* **Tóm tắt nội dung:** Trình bày giải pháp cấu hình Auto Scaling Group (ASG) để tự động co giãn tài nguyên khi lượng truy cập biến động, kết hợp với các biện pháp bảo mật như IAM Roles, Security Groups, VPC Isolation và giám sát hệ thống thời gian thực bằng Amazon CloudWatch.