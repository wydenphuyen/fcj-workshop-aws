---
title: "Proposal"
date: 2026-04-20
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
{{% notice warning %}}
⚠️ **Note:** Thông tin dưới đây dùng để tham khảo. Vui lòng không sao chép nguyên văn hoàn toàn cho báo cáo của bạn.
{{% /notice %}}

Trong phần này, bạn cần tổng hợp nội dung của hội thảo/đề án mà bạn **dự định** thực hiện.

# Ứng dụng Web Quy mô Doanh nghiệp trên nền tảng AWS
## Giải pháp Kiến trúc 3-Tier Hợp nhất đảm bảo Tính sẵn sàng cao và Hiệu năng vượt trội

### 1. Tóm tắt điều hành (Executive Summary)
Ứng dụng Web Quy mô Doanh nghiệp được thiết kế nhằm cung cấp một nền tảng số hóa mạnh mẽ, có tính sẵn sàng cao và bảo mật. Hệ thống tận dụng kiến trúc 3 tầng (3-tier architecture) tiêu chuẩn được triển khai trên Amazon Web Services (AWS), sử dụng **Amazon S3** để lưu trữ tĩnh Frontend, **Amazon EC2** kết hợp với **Auto Scaling Groups (ASG)** và **Application Load Balancer (ALB)** để xử lý Backend động (Node.js/Express), cùng với **Amazon RDS** (Cơ sở dữ liệu quan hệ) kết hợp **Amazon DynamoDB** (NoSQL) để lưu trữ dữ liệu toàn diện. Hiệu năng và bảo mật được tối ưu hóa thông qua **Amazon CloudFront (CDN)**, **Route 53 (DNS)**, **CloudWatch (Monitoring)** và **AWS WAF**.

### 2. Phát biểu bài toán (Problem Statement)
### Vấn đề gặp phải
Các ứng dụng web nguyên khối truyền thống lưu trữ trên một máy chủ đơn lẻ thường gặp phải các điểm nghẽn về khả năng mở rộng, điểm lỗi đơn (single point of failure) khi lượng truy cập tăng vọt, độ trễ cao đối với người dùng toàn cầu, và thiếu tính năng giám sát tập trung cũng như kiểm soát bảo mật tự động. Việc quản lý mở rộng hạ tầng và triển khai thủ công kém hiệu quả và dễ xảy ra sai sót.

### Giải pháp
Dự án triển khai kiến trúc đám mây 3 tầng có khả năng phục hồi cao trên AWS. Tài sản Frontend được phân phối toàn cầu thông qua Amazon S3 và CloudFront. Các tác vụ Backend chạy trên các máy chủ EC2 có thể mở rộng được quản lý bởi Auto Scaling Group đằng sau Application Load Balancer. Dữ liệu quan hệ được bảo mật trong Amazon RDS nằm trong Private Subnet, trong khi dữ liệu phi cấu trúc được quản lý qua DynamoDB và các S3 bucket chuyên dụng. Hệ thống giám sát toàn diện được thiết lập bằng CloudWatch và cảnh báo SNS, đảm bảo hiệu năng cao, chịu lỗi tốt và tối ưu chi phí.

### Lợi ích và Hiệu quả đầu tư
Giải pháp thiết lập một bản mẫu hạ tầng chuẩn sản xuất, đóng vai trò là khung mẫu có khả năng mở rộng cho các ứng dụng hiện đại. Nó tự động hóa định tuyến lưu lượng, mở rộng tài nguyên và quản lý chuyển đổi dự phòng (failover), giúp giảm đáng kể sự can thiệp thủ công và chi phí vận hành. Bảo mật được tăng cường thông qua việc cô lập VPC, Security Groups và bảo vệ bằng WAF. Nhìn chung, kiến trúc đạt được hiệu suất sử dụng tài nguyên tối ưu và chi phí tiết kiệm phù hợp cho môi trường vận hành thực tế.

### 3. Kiến trúc giải pháp (Solution Architecture)
Nền tảng sử dụng kiến trúc AWS đa tầng. Các yêu cầu từ người dùng được quản lý thông qua Amazon Route 53 và tăng tốc bằng Amazon CloudFront. Nội dung tĩnh được phân phối qua S3, trong khi các yêu cầu API động đi đến Application Load Balancer, bộ phân phối lưu lượng truy cập này sẽ chia tải qua các EC2 instance bên trong Private Subnet được hỗ trợ bởi Auto Scaling. Các thao tác cơ sở dữ liệu được xử lý an toàn thông qua Amazon RDS và DynamoDB.

### Các dịch vụ AWS được sử dụng
* **Amazon S3**: Lưu trữ tài nguyên tĩnh Frontend và quản lý kho lưu trữ tải lên/tải xuống tệp của người dùng.
* **Amazon EC2**: Chạy các máy chủ ứng dụng Backend bên trong các subnet riêng tư (private subnets).
* **Application Load Balancer (ALB)**: Phân phối lưu lượng HTTP/HTTPS đến giữa các EC2 instance.
* **Auto Scaling Group (ASG)**: Tự động điều chỉnh dung lượng tính toán dựa trên các chỉ số tải công việc.
* **Amazon RDS**: Quản lý khối lượng công việc cơ sở dữ liệu quan hệ một cách an toàn.
* **Amazon DynamoDB**: Xử lý lưu trữ dữ liệu NoSQL hiệu suất cao.
* **Amazon CloudFront**: Đóng vai trò là CDN để phân phối nội dung toàn cầu nhanh chóng.
* **Amazon Route 53**: Xử lý phân giải tên miền và định tuyến DNS.
* **Amazon CloudWatch & SNS**: Cung cấp tính năng giám sát hệ thống, số liệu và gửi cảnh báo email tự động.
* **AWS WAF & Security Groups**: Bảo vệ và an toàn vòng đài mạng chống lại các truy cập độc hại.

### Thiết kế thành phần
* **Tầng Frontend**: Giao diện mẫu hoặc mã nguồn lưu trữ trên S3 và phân phối qua CloudFront.
* **Tầng Mạng (Networking)**: VPC tùy chỉnh với Public và Private Subnets, Internet Gateway và NAT Gateway.
* **Tầng Tính toán (Compute)**: Các EC2 instance được cấu hình phía sau ALB và quản lý bởi ASG.
* **Tầng Cơ sở dữ liệu**: Các Multi-AZ RDS instance và bảng DynamoDB được cô lập trong private subnets.
* **Giám sát & Bảo mật**: Cảnh báo CloudWatch liên kết với các chủ đề SNS để quản lý sự cố chủ động.

### 4. Triển khai kỹ thuật (Technical Implementation)
**Các giai đoạn triển khai**
* Giai đoạn 1: Phân tích yêu cầu, thiết kế mạng (VPC, Subnets) và thiết lập bảo mật IAM (Tháng 1).
* Giai đoạn 2: Triển khai tính toán (EC2, ALB, ASG) và khởi tạo cơ sở dữ liệu (RDS, DynamoDB) (Tháng 2).
* Giai đoạn 3: Tích hợp phân phối nội dung (CloudFront, Route 53) và thiết lập giám sát (CloudWatch, SNS) (Tháng 3).
* Giai đoạn 4: Tích hợp hệ thống, kiểm thử tự động (Unit/Automation tests) và ra mắt sản xuất (Tháng 3).

**Yêu cầu kỹ thuật**
* Hạ tầng đám mây: Tài khoản AWS được cấu hình với các IAM role, định tuyến VPC và security group phù hợp.
* Môi trường Backend: Ứng dụng Node.js/Express chạy trên Linux EC2 instance, tích hợp điểm kiểm tra `/health` phục vụ cho kiểm tra sức khỏe của ALB.

### 5. Lộ trình & Mốc thời gian (Timeline & Milestones)
* **Tuần 1 - 2**: Thiết lập mạng (VPC, subnet, IAM, S3 static hosting).
* **Tuần 3 - 4**: Thiết lập tính toán và mở rộng (EC2, ALB, Auto Scaling Group).
* **Tuần 5 - 6**: Tích hợp cơ sở dữ liệu (RDS, DynamoDB, quản lý tệp S3).
* **Tuần 7 - 8**: Cấu hình CDN và DNS (CloudFront, Route 53).
* **Tuần 9 - 10**: Giám sát, ghi nhật ký và bảo mật (CloudWatch, SNS, WAF).
* **Tuần 11 - 12**: Kiểm thử tích hợp toàn diện, tối ưu hóa hiệu năng và hoàn thiện báo cáo.

### 6. Ước tính ngân sách (Budget Estimation)
* Hạ tầng được tối ưu hóa cho AWS Free Tier và các loại instance chi phí thấp (t3.micro/t4g.micro, sử dụng tối thiểu RDS/DynamoDB, cùng với các bậc truyền dữ liệu chuẩn của S3/CloudFront) nhằm đảm bảo hoạt động cực kỳ tiết kiệm kinh tế.

### 7. Đánh giá rủi ro (Risk Assessment)
#### Ma trận rủi ro & Biện pháp giảm thiểu
* **Sự cố mạng / Lưu lượng tăng vột**: Giảm thiểu bằng cách triển khai Multi-AZ, Auto Scaling Groups và bộ nhớ đệm CloudFront.
* **Điểm nghẽn cơ sở dữ liệu**: Giảm thiểu bằng cách tinh chỉnh chỉ mục (index tuning) và mở rộng quy mô RDS.
* **Vi phạm bảo mật**: Giảm thiểu bằng các quy tắc Security Group nghiêm ngặt, cô lập subnet riêng tư và bảo vệ bằng WAF.

### 8. Kết quả kỳ vọng (Expected Outcomes)
* Một ứng dụng web 3 tầng hoạt động đầy đủ, có tính sẵn sàng cao và bảo mật được triển khai thành công trên AWS.
* Tài liệu kỹ thuật toàn diện và hệ thống giám sát tự động đảm bảo khả năng duy trì bảo trì và độ tin cậy về hiệu năng lâu dài.