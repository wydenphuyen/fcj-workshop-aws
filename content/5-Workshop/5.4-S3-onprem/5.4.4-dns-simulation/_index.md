---
title : "On-premises DNS Simulation"
date : 2026-07-22 
weight : 4 
chapter : false
pre: " <b> 5.4.4. </b> "
---

### Mô phỏng DNS On-Premises

AWS PrivateLink endpoints có các địa chỉ IP cố định trong mỗi Availability Zone và giữ nguyên vòng đời của endpoint. AWS khuyến nghị sử dụng DNS để phân giải các IP của endpoint này nhằm đảm bảo các ứng dụng luôn cập nhật đúng IP mới nhất khi có sự thay đổi.

Trong phần này, chúng ta sẽ tạo một quy tắc chuyển tiếp (forwarding rule) để gửi các yêu cầu phân giải DNS từ môi trường on-premises giả lập đến Route 53 Private Hosted Zone.

---

### 1. Tạo bản ghi DNS Alias cho Interface Endpoint

1. Truy cập vào **Route 53 management console** (tại mục Hosted Zones). CloudFormation template đã tạo sẵn một Private Hosted Zone có tên dạng `s3.[region].amazonaws.com`. Click vào tên của Hosted Zone này.

2. **Tạo bản ghi đầu tiên trong Private Hosted Zone:**
   * **Record name và record type:** Giữ nguyên các tùy chọn mặc định.
   * **Alias Button:** Click để bật.
   * **Route traffic to:** Chọn **Alias to VPC Endpoint**.
   * **Region:** Chọn Region tương ứng (ví dụ: `US East (N. Virginia) [us-east-1]`).
   * **Choose endpoint:** Dán Regional VPC Endpoint DNS name mà em đã lưu từ phần 4.3 vào.

3. **Tạo bản ghi thứ hai:**
   * Click vào **Add another record**, thêm bản ghi thứ hai với các thông số:
     * **Record name:** Nhập ký tự `*`.
     * **Record type:** Giữ nguyên giá trị mặc định (`type A`).
     * **Alias Button:** Click để bật.
     * **Route traffic to:** Chọn **Alias to VPC Endpoint**.
     * **Region:** Chọn Region tương ứng.
     * **Choose endpoint:** Dán Regional VPC Endpoint DNS name đã lưu.
   * Nhấn **Create records** để hoàn tất việc tạo cả hai bản ghi.

Sau khi hoàn thành, các bản ghi mới sẽ hiển thị trong Route 53 console.

---

### 2. Tạo Quy tắc chuyển tiếp Resolver Forwarding Rule

Route 53 Resolver Forwarding Rules cho phép truyền các truy vấn DNS từ VPC ra các nguồn khác để phân giải tên miền. Ở phần này, chúng ta sẽ mô phỏng một "on-premises conditional forwarder" bằng cách tạo quy tắc chuyển tiếp các truy vấn DNS dành cho Amazon S3 về Private Hosted Zone chạy trong "VPC Cloud".

1. Từ Route 53 management console, chọn **Inbound endpoints** ở thanh bên trái.
2. Tại Inbound endpoints console, click vào **ID của inbound endpoint**.
3. Sao chép lại **hai địa chỉ IP** được hiển thị để lưu lại sử dụng cho các bước cấu hình tiếp theo.