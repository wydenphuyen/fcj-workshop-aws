---
title : "Introduction"
date : 2026-07-22 
weight : 1 
chapter : false
pre: " <b> 5.1. </b> "
---

#### Giới thiệu tổng quan kiến trúc hệ thống Backend Engademy

Trong chương này, chúng ta sẽ đi sâu vào việc xây dựng và triển khai hệ thống **Backend** (máy chủ) cho ứng dụng học tiếng Anh thông minh **Engademy**. Mục tiêu là đưa toàn bộ mã nguồn ứng dụng, cơ sở dữ liệu và hệ thống lưu trữ từ môi trường phát triển cục bộ (`localhost`) lên môi trường đám mây thực tế trên nền tảng **Amazon Web Services (AWS)**.

Hệ thống được thiết kế theo mô hình **Client-Server** hiện đại, đảm bảo tính bảo mật, ổn định và khả năng mở rộng trong tương lai.

#### Các thành phần cốt lõi của kiến trúc

Hệ thống Engademy trên AWS bao gồm các thành phần chính được trình bày trong sơ đồ kiến trúc bên dưới:

![sơ đồ kiến trúc hệ thống Engademy](/images/5-Workshop/5.1-Workshop-overview/engademy-architecture-diagram.png)

* **Client (Ứng dụng Flutter):** Giao diện trên điện thoại của người dùng, đóng vai trò gửi các yêu cầu (Request) tới Backend API.
* **Cloud Hosting (Amazon EC2):** Sử dụng máy chủ ảo Amazon EC2 (chạy hệ điều hành Ubuntu) làm môi trường Production để host trực tiếp mã nguồn Backend (Node.js/Express.js). Ứng dụng được quản lý tự động bằng PM2.
* **Database (MongoDB):** Sử dụng dịch vụ cơ sở dữ liệu đám mây MongoDB Atlas để lưu trữ dữ liệu người dùng, từ vựng và bài học một cách linh hoạt.
* **Cloud Storage (Amazon S3):** Tích hợp dịch vụ Amazon S3 để lưu trữ các tệp tin media (ảnh đại diện, âm thanh phát âm, tài liệu học tập) nhằm giảm tải cho máy chủ EC2 và tối ưu chi phí.

#### Quy trình triển khai

Quy trình phát triển và triển khai hệ thống được thực hiện qua các bước chính sau:

1.  **Phát triển Backend:** Xây dựng các RESTful API bằng Node.js và Express.js, kết nối với MongoDB, và tích hợp AWS SDK để xử lý upload ảnh lên S3.
2.  **Version Control:** Đẩy toàn bộ mã nguồn lên kho chứa Git/GitHub.
3.  **Cloud Deployment:** Kết nối SSH vào máy chủ AWS EC2, thiết lập môi trường, kéo code từ GitHub về, cài đặt các thư viện cần thiết (`npm install`) và khởi chạy ứng dụng bằng PM2.