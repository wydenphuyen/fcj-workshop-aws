---
title : "Prerequisites"
date : 2026-07-22 
weight : 2 
chapter : false
pre: " <b> 5.2. </b> "
---

### Các công cụ và tài nguyên cần thiết

Để triển khai hệ thống Backend của ứng dụng **Engademy** lên AWS với kiến trúc bảo mật cao (phân tách rõ ràng giữa Web Server và Database Server), chúng ta cần chuẩn bị các tài nguyên sau:

#### 1. Môi trường phát triển cục bộ (Local Environment)
* **Node.js & npm:** Môi trường thực thi mã nguồn JavaScript phía máy chủ.
* **Git & GitHub:** Quản lý phiên bản và lưu trữ mã nguồn.
* **Postman:** Công cụ để kiểm thử các API (Endpoint) trước và sau khi đưa lên Cloud.

#### 2. Tài nguyên đám mây (AWS Cloud Services)
Hệ thống sử dụng kiến trúc gồm 2 máy chủ ảo (Amazon EC2) chạy hệ điều hành Ubuntu, được cấu hình mạng riêng biệt:

* **Máy chủ 1: Engademy-Backend**
  * Đóng vai trò là Web Server chạy mã nguồn Node.js/Express.
  * Được cấp **Public IP** để có thể nhận các yêu cầu (Request) trực tiếp từ ứng dụng điện thoại của người dùng qua Internet.

{{< figure src="/fcj-workshop-aws/images/5-Workshop/5.2-Prerequisite/1.png" title="Máy chủ EC2 dành cho Engademy Backend (Có Public IP)" position="center" >}}

* **Máy chủ 2: Engademy-MongoDB**
  * Đóng vai trò là Database Server chuyên biệt để chạy cơ sở dữ liệu MongoDB.
  * Được cấu hình bảo mật chỉ sử dụng **Private IP** (không có Public IP). Điều này ngăn chặn hoàn toàn các cuộc tấn công trực tiếp từ Internet, Database chỉ cho phép kết nối nội bộ từ máy chủ Backend.

{{< figure src="/fcj-workshop-aws/images/5-Workshop/5.2-Prerequisite/2.png" title="Máy chủ EC2 dành cho MongoDB (Chỉ có Private IP bảo mật)" position="center" >}}

#### 3. Cấu hình biến môi trường (.env)
Các thông tin cấu hình nhạy cảm sẽ được thiết lập trực tiếp trên máy chủ Backend thông qua file `.env`:
* `PORT`: Cổng ứng dụng (ví dụ: 3000 hoặc 8080).
* `MONGO_URI`: Chuỗi kết nối trỏ tới địa chỉ **Private IP** của máy chủ MongoDB.
* `AWS_ACCESS_KEY_ID` & `AWS_SECRET_ACCESS_KEY`: Thông tin xác thực để Backend có quyền đẩy file media lên Amazon S3.
* `JWT_SECRET`: Khóa bí mật dùng cho xác thực token của người dùng.