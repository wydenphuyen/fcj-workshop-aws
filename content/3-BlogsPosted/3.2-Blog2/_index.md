---
title: "Blog 2: Phân tích chi tiết luồng xử lý dữ liệu"
date: 2024-01-02
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# Luồng di chuyển của dữ liệu trong hệ thống AWS

Tiếp nối bài viết tổng quan, bài này sẽ đi sâu vào cách hệ thống xử lý các yêu cầu (request) từ người dùng. Hệ thống được thiết kế để tách biệt rõ ràng giữa xử lý tĩnh và xử lý động.

![Sơ đồ kiến trúc AWS](/fcj-workshop-aws/images/2-Proposal/kien-truc-aws.jpg)

### Quy trình xử lý request:
1. **Tiếp nhận & Định tuyến:** Khi người dùng truy cập, **Amazon Route 53** sẽ đảm nhiệm việc phân giải tên miền. Cùng lúc đó, **AWS WAF** sẽ kiểm tra và chặn các truy cập độc hại.
2. **Xử lý nội dung tĩnh (Frontend):** Nếu người dùng yêu cầu các tài nguyên tĩnh (HTML, CSS, JS, hình ảnh), **Amazon CloudFront** sẽ lấy dữ liệu từ **Amazon S3** và trả về ngay lập tức với tốc độ cao.
3. **Xử lý nội dung động (Backend):** Nếu là các thao tác cần tính toán (như đăng nhập, truy vấn dữ liệu), request sẽ được đẩy vào VPC (mạng ảo). Tại đây, **Application Load Balancer (ALB)** sẽ phân phát đều lượng truy cập xuống các máy chủ **Amazon EC2**.
4. **Truy xuất cơ sở dữ liệu:** Các máy chủ EC2 sẽ gọi xuống tầng Database (như Amazon RDS hoặc DynamoDB) để lấy hoặc lưu dữ liệu, sau đó trả kết quả ngược lại cho người dùng.