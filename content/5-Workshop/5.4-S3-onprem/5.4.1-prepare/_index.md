---
title : "Prepare the Environment"
date : 2026-07-22 
weight : 1 
chapter : false
pre: " <b> 5.4.1. </b> "
---

### Chuẩn bị môi trường mô phỏng On-Premises và DNS

Để thực hiện phần thực hành truy cập Amazon S3 từ môi trường mạng nội bộ giả lập (on-premises), chúng ta cần chuẩn bị các thành phần cơ sở hạ tầng mạng và phân giải tên miền (DNS).

#### Các bước chuẩn bị chính:
* Triển khai cấu hình hạ tầng thông qua **CloudFormation Stack**.
* Cập nhật và điều chỉnh bảng định tuyến **VPC Route Table**.

---

### 1. Triển khai CloudFormation Stack

Mẫu CloudFormation sẽ tự động khởi tạo các dịch vụ hỗ trợ mô phỏng mạng on-premises:
* **Route 53 Private Hosted Zone:** Lưu trữ các bản ghi Alias trỏ tới PrivateLink S3 endpoint.
* **Route 53 Inbound Resolver Endpoint:** Cho phép "VPC Cloud" tiếp nhận các yêu cầu phân giải DNS từ mạng nội bộ.
* **Route 53 Outbound Resolver Endpoint:** Giúp "VPC On-prem" chuyển tiếp các yêu cầu phân giải DNS của S3 sang hệ thống "VPC Cloud".

#### Các bước thực hiện trên AWS Console:
1. Truy cập vào giao diện quản trị **AWS CloudFormation console**.
2. Tải và cấu hình mẫu template triển khai tự động các tài nguyên mạng.
3. Nhấn **Create stack** để hệ thống tự động khởi tạo toàn bộ hạ tầng (Quá trình này mất khoảng vài phút).

---

### 2. Cập nhật On-premise Private Route Table

Để hoàn tất kết nối định tuyến giữa trung tâm dữ liệu giả lập (on-premises datacenter) và môi trường đám mây AWS thông qua mô đun VPN:
1. Truy cập vào **Amazon EC2 Console**.
2. Tìm kiếm và chọn instance có tên **`infra-vpngw-test`**.
3. Tại tab **Details**, sao chép lại mã định danh **Instance ID** để cấu hình bảng định tuyến `VPC On-prem` hướng lưu lượng truy cập cloud đi qua strongSwan VPN instance.