---
title: "Backend Development & Cloud Deployment"
date: 2026-07-22
weight: 5
chapter: false
pre: " <b> 5. </b> "
---



# Phát triển Backend và Triển khai Hệ thống Engademy trên AWS

#### Overview

**Node.js và Amazon Web Services (AWS)** kết hợp với nhau cung cấp một nền tảng Backend mạnh mẽ, khả năng mở rộng cao và bảo mật để vận hành các ứng dụng học tập thông minh.

Trong phần này, báo cáo trình bày quá trình xây dựng, cấu hình và vận hành hệ thống Backend cho ứng dụng Engademy từ môi trường phát triển cục bộ lên hệ thống đám mây chính thức.

Hệ thống được chia thành các thành phần cốt lõi phục vụ xử lý nghiệp vụ và lưu trữ:
+ **Core Backend** - Xây dựng các RESTful APIs bằng Node.js và Express.js, kết nối cơ sở dữ liệu MongoDB để quản lý tài khoản, từ vựng và dữ liệu học tập.
+ **Cloud Infrastructure** - Triển khai ứng dụng trên máy chủ ảo Amazon EC2 (Ubuntu), quản lý tiến trình bằng PM2 và tích hợp dịch vụ lưu trữ tệp tin trên Amazon S3.

#### Content

1. [Tổng quan kiến trúc Backend (Backend Overview)](#)
2. [Cấu hình Môi trường và Cơ sở dữ liệu (Environment & Database)](#)
3. [Quản lý mã nguồn với Git/GitHub (Version Control)](#)
4. [Triển khai hệ thống lên Amazon EC2 (Cloud Deployment)](#)
5. [Quản lý và Duy trì tiến trình với PM2 (Process Management)](#)
6. [Tích hợp lưu trữ đám mây Amazon S3 (Cloud Storage Integration)](#)