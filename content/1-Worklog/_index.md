---
title: "Worklog"
date: 2026-04-20
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

# Phiếu Theo Dõi Tiến Độ Thực Tập Tốt Nghiệp

* **Sinh viên thực hiện:** Bùi Khôi Nguyên
* **MSSV:** 2280602103
* **Lớp:** 22DTHG4
* **Đơn vị thực tập:** Công ty TNHH Amazon Web Service Việt Nam

---

### Bảng tổng hợp tiến độ thực tập 12 tuần:

| Tuần | Ngày | Nội dung công việc thực tập |
| :---: | :---: | :--- |
| **1** | 23/04/2026 | - Tìm hiểu tổng quan về kiến trúc hệ thống trên AWS theo mô hình dự án.<br>- Thiết lập AWS IAM để quản lý quyền truy cập. Tạo và cấu hình Amazon S3 Bucket để lưu trữ tĩnh (Static Website Hosting) cho Frontend. |
| **2** | 01/05/2026 | - Xây dựng hạ tầng mạng (Networking): Khởi tạo Amazon VPC, thiết lập Public Subnet và Private Subnet.<br>- Cấu hình Internet Gateway và NAT Gateway để đảm bảo bảo mật và luồng truy cập cho hệ thống. |
| **3** | 08/05/2026 | - Triển khai Compute: Khởi tạo các Amazon EC2 instances bên trong Private Subnet để chạy ứng dụng Backend.<br>- Thiết lập Application Load Balancer (ALB) để định tuyến và chuyển tiếp request (HTTPS). |
| **4** | 15/05/2026 | - Đảm bảo tính sẵn sàng cao (High Availability): Cấu hình Auto Scaling Group (ASG) cho cụm EC2 để hệ thống tự động thu phóng tài nguyên. |
| **5** | 22/05/2026 | - Triển khai Database (Relational & Cache): Khởi tạo và cấu hình cơ sở dữ liệu quan hệ Amazon RDS trong Private Subnet.<br>- Thiết lập Amazon ElastiCache để tối ưu hóa tốc độ truy xuất dữ liệu. |
| **6** | 29/05/2026 | - Triển khai Database (NoSQL) & Quản lý File: Cấu hình Amazon DynamoDB cho các luồng dữ liệu phi cấu trúc.<br>- Tích hợp thêm S3 Bucket phục vụ tính năng Upload/Download Files. |
| **7** | 05/06/2026 | - Tối ưu phân phối nội dung (Frontend Delivery): Thiết lập Amazon CloudFront (CDN) để phân phối static files.<br>- Cấu hình Amazon Route 53 để phân giải tên miền. |
| **8** | 12/06/2026 | - Giám sát hệ thống (Monitoring & Logging): Tích hợp Amazon CloudWatch để thu thập Logs và Metrics từ các dịch vụ (EC2, RDS, VPC).<br>- Thiết lập Dashboard giám sát. |
| **9** | 19/06/2026 | - Cảnh báo & Bảo mật: Cấu hình Amazon SNS để tự động gửi email cảnh báo khi CloudWatch phát hiện sự cố.<br>- Cấu hình WAF/Security Groups để chặn truy cập độc hại. |
| **10** | 26/06/2026 | - Tích hợp hệ thống: Kết nối toàn diện luồng dữ liệu từ Frontend -> Backend -> Database/Storage.<br>- Thực hiện kiểm thử tự động (Automation Test) và Unit Test cho các API endpoints. |
| **11** | 03/07/2026 | - Tối ưu hóa hiệu năng: Kiểm tra sức chịu tải của Auto Scaling Group bằng stress test.<br>- Tối ưu hóa các câu truy vấn Database, sửa lỗi (bug fixing) và tinh chỉnh Cache. |
| **12** | 10/07/2026 | - Rà soát chi phí và bảo mật toàn bộ hệ thống AWS.<br>- Hoàn thiện tài liệu kiến trúc, đóng gói source code và viết báo cáo tổng kết thực tập tốt nghiệp. |

Typically, and as a standard, a worklog is carried out over about 3 months (throughout the internship period) with weekly contents as follows:

**Week 1:** [Getting familiar with AWS and basic AWS services](1.1-week1/)

**Week 2:** [Doing task A...](1.2-week2/)

**Week 3:** [Doing task B...](1.3-week3/)

**Week 4:** [Doing task C...](1.4-week4/)

**Week 5:** [Doing task D...](1.5-week5/)

**Week 6:** [Doing task E...](1.6-week6/)

**Week 7:** [Doing task G...](1.7-week7/)

**Week 8:** [Doing task H...](1.8-week8/)

**Week 9:** [Doing task I...](1.9-week9/)

**Week 10:** [Doing task L...](1.10-week10/)

**Week 11:** [Doing task M...](1.11-week11/)

**Week 12:** [Doing task N...](1.12-week12/)
