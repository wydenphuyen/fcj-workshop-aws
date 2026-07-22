---
title : "Test the Interface Endpoint"
date : 2026-07-22 
weight : 3 
chapter : false
pre: " <b> 5.4.3. </b> "
---

### Kiểm tra kết nối S3 Interface Endpoint

Trong phần này, chúng ta sẽ tiến hành kiểm tra khả năng kết nối và truyền tải dữ liệu đến Amazon S3 thông qua Interface Endpoint vừa tạo từ môi trường mạng giả lập on-premises.

#### 1. Lấy tên miền DNS của S3 Interface Endpoint
1. Quay lại menu **Amazon VPC**, chọn **Endpoints**.
2. Click vào endpoint vừa được tạo (ví dụ: `s3-interface-endpoint`). Lấy thông tin chi tiết và lưu lại **Regional DNS name** của endpoint (chọn phần DNS name đầu tiên) để sử dụng cho bước tiếp theo.

---

#### 2. Kết nối tới EC2 Instance trong "VPC On-prem"
1. Trên thanh tìm kiếm của AWS Console, gõ và chọn **Session Manager**.
2. Nhấn **Start Session**, chọn EC2 instance có tên **Test-Interface-Endpoint**. Instance này đang chạy trong `VPC On-prem` và sẽ được sử dụng để test kết nối đến S3 qua Interface Endpoint. Session Manager sẽ mở ra một cửa sổ tab mới với giao diện dòng lệnh dạng: `sh-4.2 $`.

3. Di chuyển về thư mục home của ssm-user bằng lệnh:
```bash
cd ~