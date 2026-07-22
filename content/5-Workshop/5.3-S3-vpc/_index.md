---
title : "Thiết lập Database (MongoDB)"
date : 2026-07-22 
weight : 3 
chapter : false
pre: " <b> 5.3. </b> "
---

### Cài đặt và cấu hình MongoDB trên EC2

Thiết lập cơ sở dữ liệu trên máy chủ **Engademy-MongoDB** nằm trong Private Subnet (không có Public IP) để bảo mật tối đa cho hệ thống.

#### 1. Kết nối vào máy chủ Database
Sử dụng máy chủ Backend làm Bastion Host để kết nối SSH vào máy chủ Database thông qua Private IP:

```bash
ssh -i "engademy-key.pem" ubuntu@10.0.142.235

![Trạng thái MongoDB active running](/fcj-workshop-aws/images/5-Workshop/5.3-S3-vpc/3.png)