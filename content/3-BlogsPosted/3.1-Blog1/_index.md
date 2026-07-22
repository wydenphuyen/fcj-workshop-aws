---
title: "Tổng quan kiến trúc AWS đề xuất"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Đề xuất Kiến trúc Hệ thống đa tầng trên AWS

Dưới đây là sơ đồ kiến trúc hệ thống triển khai trên nền tảng AWS Cloud mà tôi đề xuất, đảm bảo các yếu tố cốt lõi cho một ứng dụng web hiện đại: **Bảo mật (Security), Mở rộng tự động (Scalability), và Tính sẵn sàng cao (High Availability).**

Hệ thống tách biệt rõ ràng giữa luồng xử lý giao diện (Frontend), logic nghiệp vụ (Backend) và cơ sở dữ liệu (Database), đồng thời tích hợp các cơ chế bảo mật, giám sát và lưu trữ đám mây.

![Sơ đồ kiến trúc AWS](/images/2-Proposal/kien-truc-aws.jpg)

*(Lưu ý: Bạn nhớ đảm bảo file ảnh sơ đồ đã được lưu đúng vào thư mục `static/images/2-Proposal/` với tên `kien-truc-aws.jpg` như mình hướng dẫn ở bước trước nhé. Nếu bạn lưu tên khác, hãy sửa lại tên file trong đoạn mã trên).*