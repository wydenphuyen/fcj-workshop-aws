---
title : "Truy cập Amazon S3 từ hệ thống"
date : 2026-07-22 
weight : 4 
chapter : false
pre: " <b> 5.4. </b> "
---

### Cấu hình kết nối Amazon S3 cho Engademy

Trong hệ thống ứng dụng học tiếng Anh **Engademy**, Amazon S3 được sử dụng làm giải pháp lưu trữ đám mây để quản lý các tệp tin người dùng như ảnh đại diện (avatar), tài liệu học tập và file âm thanh từ vựng.

Để đảm bảo bảo mật và tốc độ truyền tải nội bộ, ta thiết lập **VPC Interface Endpoint** cho dịch vụ S3.

#### 1. Mục đích kết nối
* **Bảo mật tuyệt đối:** Cho phép các máy chủ EC2 bên trong VPC giao tiếp trực tiếp với Amazon S3 thông qua mạng nội bộ của AWS mà không cần đi qua Internet công cộng.
* **Tối ưu tốc độ:** Giảm độ trễ khi ứng dụng Backend thực hiện các tác vụ tải lên (upload) và tải xuống (download) file dữ liệu.

#### 2. Thiết lập VPC Interface Endpoint cho S3
1. Trên giao diện quản trị AWS VPC, chọn **Endpoints** -> **Create Endpoint**.
2. Tìm kiếm dịch vụ S3 và chọn loại **Interface** (để tạo điểm cuối mạng riêng tư trong Subnet).
3. Gắn kết endpoint này vào VPC của dự án Engademy và chọn các Subnet tương ứng.

![Giao diện cấu hình S3 Interface Endpoint trong AWS VPC](/fcj-workshop-aws/images/5-Workshop/5.4-S3-onprem/s3-endpoint.png)

#### 3. Kiểm tra kết nối từ Backend
Sau khi cấu hình Endpoint, từ máy chủ Backend, ta có thể tích hợp SDK của AWS để kết nối trực tiếp đến S3 Bucket và thực hiện các thao tác quản lý file một cách ổn định, an toàn.