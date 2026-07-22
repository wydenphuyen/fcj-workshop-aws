---
title: "Event 2: Cloud Security & Best Practices Workshop"
date: 2026-09-30
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Summary Report: “Cloud Security & Best Practices Workshop”

### Thông tin sự kiện
- **Tên sự kiện:** Cloud Security & Best Practices Workshop
- **Ngày diễn ra:** 30/09/2026
- **Địa điểm:** Trung tâm Hội thảo Công nghệ & Trực tuyến qua AWS Chime
- **Vai trò:** Người tham dự & Thành viên thảo luận (Attendee)

### Mục tiêu sự kiện
- Cung cấp hiểu biết sâu sắc về mô hình bảo mật chia sẻ (Shared Responsibility Model) trên nền tảng đám mây AWS.
- Giới thiệu các phương pháp hay nhất (Best Practices) trong việc thiết lập hệ thống mạng an toàn và cô lập tài nguyên.
- Hướng dẫn cấu hình quản lý danh tính, phân quyền truy cập và bảo vệ dữ liệu nhạy cảm trong ứng dụng web.
- Trình bày các công cụ giám sát, phát hiện mối đe dọa và tự động hóa bảo mật.

### Diễn giả chính
- **Alex Rivera** – Principal Cloud Security Architect, AWS Solutions
- **Sarah Chen** – Senior Security Compliance Specialist
- **Minh Hoàng** – Cloud Security Engineer tại đối tác AWS khu vực APAC

### Nội dung chính

#### 1. Mô hình trách nhiệm chia sẻ (Shared Responsibility Model)
- Phân định rõ ràng trách nhiệm bảo mật *của AWS* (bảo mật cơ sở hạ tầng nền tảng, phần cứng, trung tâm dữ liệu) và bảo mật *của khách hàng* (bảo mật dữ liệu, cấu hình mạng, quản lý quyền truy cập ứng dụng).
- Tầm quan trọng của việc cấu hình đúng các tham số bảo mật ngay từ giai đoạn thiết kế kiến trúc.

#### 2. Bảo mật mạng và Cô lập hệ thống (Network Security & Isolation)
- **Thiết kế VPC chuẩn:** Phân chia rõ ràng giữa Public Subnet (dành cho ALB, NAT Gateway) và Private Subnet (dành cho EC2 Backend và RDS Database).
- **Security Groups & Network ACLs:** Sử dụng như các lớp tường lửa ảo đa tầng để kiểm soát chặt chẽ lưu lượng ra vào (Inbound/Outbound traffic) theo nguyên tắc tối thiểu quyền hạn (Least Privilege).
- **AWS WAF (Web Application Firewall):** Chặn các cuộc tấn công phổ biến như SQL Injection, Cross-Site Scripting (XSS) và DDoS ở tầng ứng dụng.

#### 3. Quản lý danh tính và phân quyền (IAM & Access Management)
- Hạn chế tối đa việc sử dụng tài khoản Root; áp dụng chính sách cấp quyền chi tiết thông qua **IAM Roles** thay vì hardcode thông tin xác thực.
- Thiết lập xác thực đa yếu tố (MFA) cho toàn bộ tài khoản quản trị hệ thống.

#### 4. Bảo vệ dữ liệu (Data Protection)
- **Encryption at Rest & in Transit:** Mã hóa dữ liệu khi lưu trữ trên Amazon S3, Amazon RDS và mã hóa dữ liệu truyền tải qua giao thức HTTPS/TLS.
- Quản lý khóa mã hóa an toàn với **AWS Key Management Service (KMS)**.

#### 5. Giám sát và Phát hiện mối đe dọa (Monitoring & Compliance)
- Sử dụng **Amazon CloudTrail** để ghi lại toàn bộ lịch sử gọi API trên hệ thống AWS.
- Triển khai **Amazon GuardDuty** để phát hiện thông minh các hành vi xâm nhập độc hại hoặc hoạt động bất thường.

### Bài học và Giá trị cốt lõi thu được

#### Về tư duy thiết kế hệ thống
- Bảo mật không phải là một tính năng gắn thêm vào cuối dự án mà phải được tích hợp xuyên suốt từ những bước thiết kế kiến trúc ban đầu (Security by Design).
- Luôn áp dụng mô hình phòng thủ theo chiều sâu (Defense-in-Depth) với nhiều lớp bảo vệ khác nhau.

#### Về kỹ thuật thực tế
- Nắm vững cách cấu hình Security Group khắt khe hơn để bảo vệ các máy chủ Backend (Node.js/Express) không bị lộ thông tin ra bên ngoài Internet công cộng.
- Hiểu cách tối ưu hóa các thiết lập kết nối cơ sở dữ liệu an toàn trên RDS và DynamoDB.

### Áp dụng vào dự án thực tế (Đồ án tốt nghiệp)
- **Cấu hình mạng:** Đảm bảo toàn bộ các EC2 instance chạy ứng dụng và cơ sở dữ liệu được đặt hoàn toàn trong Private Subnet của dự án.
- **Quản lý quyền:** Sử dụng IAM Role gắn trực tiếp cho EC2 để cấp quyền truy cập S3 một cách an toàn thay vì lưu trữ các khóa truy cập (Access Keys) trong mã nguồn.
- **Kiểm tra an toàn:** Tích hợp các quy tắc bảo mật cơ bản cho API backend nhằm phòng chống các lỗ hổng bảo mật phổ biến.

### Trải nghiệm tham gia
Buổi workshop đã mang lại cho tôi góc nhìn thực tế cực kỳ giá trị về cách các doanh nghiệp lớn vận hành hệ thống đám mây an toàn. Thông qua các phiên demo trực quan và case study thực tế từ các diễn giả, tôi đã tích lũy thêm nhiều kinh nghiệm quý báu để áp dụng trực tiếp vào việc hoàn thiện cấu trúc bảo mật cho hệ thống Web Application trên AWS của mình.

