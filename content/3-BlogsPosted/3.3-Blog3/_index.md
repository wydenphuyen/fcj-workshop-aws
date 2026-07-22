---
title: "Blog 3: Bảo mật và Tự động mở rộng (Auto Scaling)"
date: 2024-01-03
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

# Tối ưu hóa hiệu suất và Bảo mật trên AWS

Để một hệ thống web hoạt động ổn định và an toàn, kiến trúc này đã áp dụng các cơ chế quan trọng về mạng và giám sát tự động.

![Sơ đồ kiến trúc AWS](/fcj-workshop-aws/images/2-Proposal/kien-truc-aws.jpg)

### 1. Bảo mật bằng Private Subnet
Như trên sơ đồ, toàn bộ các máy chủ xử lý logic (**Amazon EC2**) và hệ quản trị cơ sở dữ liệu (**Amazon RDS/DynamoDB**) đều được đặt trong **Private Subnet** (màu xanh nhạt). Điều này có nghĩa là chúng bị cách ly hoàn toàn khỏi Internet công cộng. Hacker không thể truy cập trực tiếp vào các máy chủ này, giúp dữ liệu được bảo vệ nghiêm ngặt.

### 2. Khả năng chịu tải (Auto Scaling)
Các máy chủ EC2 được đặt trong một **Auto Scaling Group**. Tính năng này cho phép hệ thống tự động sinh thêm máy chủ mới khi lượng người dùng tăng đột biến, và tự động tắt bớt máy chủ khi ít người dùng để tiết kiệm chi phí.

### 3. Giám sát liên tục
Tất cả các hoạt động, từ truy cập mạng đến hiệu suất máy chủ, đều được **Amazon CloudWatch** ghi lại (Logs & Metrics). Nếu có bất kỳ sự cố nào, hệ thống sẽ tự động kích hoạt cảnh báo qua email cho đội ngũ vận hành.