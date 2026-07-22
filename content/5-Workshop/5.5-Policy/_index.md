---
title : "VPC Endpoint Policies"
date : 2026-07-22
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

Khi bạn tạo một interface hoặc gateway endpoint, bạn có thể đính kèm một chính sách endpoint (endpoint policy) để kiểm soát quyền truy cập vào dịch vụ mà bạn đang kết nối. VPC endpoint policy là một chính sách tài nguyên IAM (IAM resource policy) gắn liền với endpoint. Nếu bạn không đính kèm chính sách khi tạo endpoint, AWS sẽ tự động gán một chính sách mặc định cho phép truy cập toàn quyền vào dịch vụ thông qua endpoint đó.

Bạn có thể tạo chính sách giới hạn quyền truy cập chỉ đến một số S3 bucket cụ thể. Điều này rất hữu ích nếu bạn chỉ muốn một số S3 Buckets nhất định có thể được truy cập thông qua endpoint.

Trong phần này bạn sẽ tạo một VPC endpoint policy giới hạn quyền truy cập vào S3 bucket được chỉ định trong policy.

![endpoint diagram](/fcj-workshop-aws/images/5-Workshop/5.5-Policy/s3-bucket-policy.png)

#### Connect to an EC2 instance and verify connectivity to S3

1. Start a new AWS Session Manager session on the instance named Test-Gateway-Endpoint. From the session, verify that you can list the contents of the bucket you created in Part 1: Access S3 from VPC:

```bash
aws s3 ls s3://<your-bucket-name>