---
title : "Create an S3 Interface endpoint"
date : 2026-07-22 
weight : 2 
chapter : false
pre: " <b> 5.4.2. </b> "
---

### Tạo S3 Interface Endpoint

Trong phần này, chúng ta sẽ tiến hành tạo một S3 Interface Endpoint sử dụng môi trường mạng on-premises đã được giả lập.

#### Các bước thực hiện chi tiết:

1. Quay lại menu **Amazon VPC**, ở thanh điều hướng bên trái chọn **Endpoints**, sau đó nhấn **Create Endpoint**.
2. Tại giao diện cấu hình Endpoint:
   * **Name:** Đặt tên cho interface endpoint của bạn.
   * **Service category:** Chọn **AWS services**.

3. Tại ô tìm kiếm dịch vụ (Search), gõ `s3` và nhấn Enter. Chọn dịch vụ có tên dạng `com.amazonaws.[region].s3` (ví dụ: `com.amazonaws.us-east-1.s3`) và đảm bảo cột **Type** hiển thị là **Interface**.

4. Tại mục **VPC**, chọn **VPC Cloud** từ danh sách thả xuống.

> **⚠️ Warning:** Hãy chắc chắn bạn chọn **"VPC Cloud"** và **không** chọn **"VPC On-prem"**.

5. Mở rộng phần **Additional settings** và đảm bảo tùy chọn **Enable DNS name** **không** được tích chọn (chúng ta sẽ cấu hình phần này ở các bước tiếp theo của workshop).

6. Chọn **2 Subnets** nằm trong các vùng khả dụng tương ứng theo yêu cầu lab (ví dụ: `us-east-1a` và `us-east-1b`).

7. Tại mục **Security groups**, chọn Security Group tương ứng cho phép kết nối đến endpoint, sau đó nhấn **Create endpoint** ở cuối trang để hoàn tất.