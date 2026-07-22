---
title: "Event 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.2. </b> "
---



# Summary Report: “Cloud Security & Best Practices Workshop”

### Event Objectives

- Chia sẻ các phương pháp hay nhất về bảo mật và tuân thủ trên đám mây
- Giới thiệu Mô hình Trách nhiệm Chia sẻ và các chiến lược phòng thủ theo chiều sâu
- Cung cấp hướng dẫn về cách bảo mật ranh giới mạng và cô lập các khối lượng công việc
- Trình bày các công cụ phát hiện mối đe dọa, giám sát và quản trị IAM

### Speakers

- **Alex Rivera** – Kiến trúc sư Bảo mật Đám mây Chính, AWS
- **Sarah Chen** – Chuyên gia Tuân thủ Bảo mật Cấp cao
- **Minh Hoàng** – Kỹ sư Bảo mật Đám mây, Mạng lưới Đối tác AWS

### Key Highlights

#### Nhược điểm của kiến trúc bảo mật truyền thống (Legacy)

- Thông tin đăng nhập và mật khẩu được mã cứng trong mã nguồn → Nguy cơ truy cập trái phép và rò rỉ dữ liệu cao  
- Cấu trúc mạng phẳng không được cô lập → Kẻ tấn công dễ dàng di chuyển ngang trong hệ thống sau khi vượt qua vành đai bảo vệ  
- Không tuân thủ các quy định bảo vệ dữ liệu → Gây ra các sự cố bảo mật, hình phạt pháp lý và tổn hại uy tín  

#### Chuyển đổi sang kiến trúc ứng dụng an toàn – Phòng thủ theo chiều sâu (Defense-in-Depth)

Triển khai hệ thống bảo mật đa tầng — bảo vệ khối lượng công việc ở mọi cấp độ từ vành đai mạng đến lưu trữ dữ liệu, được xây dựng trên ba trụ cột chính:

- **Cô lập mạng**: Hạn chế lưu lượng truy cập thông qua Private Subnet và Security Group  
- **Quản trị định danh**: Thực thi nguyên tắc đặc quyền tối thiểu (least privilege) và xác thực mạnh mẽ  
- **Bảo vệ dữ liệu**: Mã hóa thông tin nhạy cảm cả khi lưu trữ và khi truyền tải  

#### Mô hình trách nhiệm chia sẻ (Shared Responsibility Model)

- **Phân định trách nhiệm**: AWS bảo mật cơ sở hạ tầng của đám mây, trong khi khách hàng bảo mật các thành phần bên trong đám mây  
- **Trách nhiệm của khách hàng**: Chịu trách nhiệm về hệ điều hành, cấu hình mạng, quy tắc tường lửa và mã hóa dữ liệu  
- **Sự tuân thủ**: Đáp ứng các tiêu chuẩn bảo mật toàn cầu thông qua các khuôn khổ tuân thủ tích hợp sẵn trên đám mây  

#### Bảo mật mạng và Cô lập hệ thống (Network Security & Isolation)

- **Kiến trúc VPC**: Phân tách các tài nguyên công khai (ALB, NAT Gateway) khỏi các máy chủ backend và cơ sở dữ liệu riêng tư  
- **Bảo vệ vành đai**: Sử dụng AWS WAF để chặn các cuộc tấn công web phổ biến như SQL injection và cross-site scripting  
- **Kiểm soát lưu lượng**: Tinh chỉnh Security Group và Network ACL để kiểm tra lưu lượng truy cập đến và đi  

#### Quản lý danh tính và quyền truy cập (IAM)

- **Nguyên tắc đặc quyền tối thiểu**: Chỉ cấp quyền cần thiết để thực hiện các tác vụ cụ thể  
- **IAM Roles thay vì Access Keys**: Loại bỏ việc mã cứng thông tin xác thực bằng cách đính kèm trực tiếp các vai trò vào các máy chủ tính toán  
- **Xác thực đa yếu tố (MFA)**: Thực thi kiểm soát truy cập nghiêm ngặt đối với tài khoản quản trị  

#### Phát hiện mối đe dọa & Giám sát (Threat Detection & Monitoring)

- **Kiểm toán API**: Theo dõi hoạt động tài khoản và thay đổi tài nguyên bằng Amazon CloudTrail  
- **Phát hiện mối đe dọa thông minh**: Phát hiện hành vi độc hại và hoạt động trái phép bằng Amazon GuardDuty  
- **Cảnh báo chủ động**: Thiết lập cảnh báo Amazon CloudWatch để phát hiện bất thường và phản ứng sự cố nhanh chóng  

### Key Takeaways

#### Tư duy thiết kế (Design Mindset)

- **Security by Design**: Luôn tích hợp bảo mật từ giai đoạn thiết kế kiến trúc ban đầu thay vì coi đó là việc làm sau cùng  
- **Triết lý Zero Trust**: Không bao giờ tin tưởng ngầm định, luôn xác thực mọi yêu cầu và kết nối trong hệ thống  
- **Giảm thiểu rủi ro**: Nhận diện sớm các lỗ hổng để phòng ngừa các sự cố bảo mật tốn kém sau khi triển khai  

#### Kiến trúc kỹ thuật (Technical Architecture)

- **Kỹ thuật phân đoạn mạng**: Phương pháp thực tế để cô lập logic ứng dụng và cơ sở dữ liệu khỏi việc tiếp xúc công khai trên internet  
- Sử dụng **vai trò và chính sách IAM** thay vì nhúng thông tin xác thực dài hạn vào mã nguồn ứng dụng  
- **Thực thi mã hóa**: Bảo mật dữ liệu thông qua AWS KMS trên tất cả các lớp lưu trữ và truyền thông  

#### Chiến lược tuân thủ (Compliance Strategy)

- **Giám sát liên tục**: Duy trì khả năng hiển thị trên tất cả các tài nguyên đám mây để đảm bảo tuân thủ chính sách  
- **Khắc phục tự động**: Tận dụng các công cụ gốc của AWS để tự động phản hồi các mối đe dọa bảo mật được phát hiện  
- **Sẵn sàng kiểm toán**: Lưu giữ nhật ký toàn diện để dễ dàng đáp ứng các tiêu chuẩn quy định của ngành  

### Applying to Work

- **Triển khai backend an toàn**: Đặt tất cả các phiên bản Amazon EC2 và cơ sở dữ liệu trong Private Subnet để cô lập chúng khỏi internet công cộng  
- **Tái cấu trúc cách xử lý thông tin xác thực**: Xóa bỏ các access key được mã cứng và triển khai các IAM Role bảo mật cho giao tiếp giữa instance và dịch vụ  
- **Triển khai quy tắc tường lửa**: Cấu hình Security Group nghiêm ngặt để chỉ cho phép lưu lượng truy cập đến các cổng và dải IP cần thiết  
- **Bật tính năng mã hóa**: Kích hoạt mã hóa dữ liệu lưu trữ (encryption at rest) cho các bucket Amazon S3 và lưu trữ Amazon RDS  
- **Triển khai công cụ giám sát**: Tích hợp cảnh báo từ Amazon CloudTrail và CloudWatch vào quy trình phát triển và triển khai  

### Event Experience

Tham gia hội thảo **“Cloud Security & Best Practices”** là một trải nghiệm cực kỳ giá trị, cung cấp cho tôi cái nhìn toàn diện về cách bảo mật các ứng dụng và dữ liệu trên đám mây bằng các cơ chế bảo mật nâng cao của AWS. Những trải nghiệm nổi bật bao gồm:

#### Học hỏi từ các chuyên gia hàng đầu
- Các chuyên gia từ AWS và lĩnh vực bảo mật doanh nghiệp đã chia sẻ **các phương pháp hay nhất** trong việc bảo vệ cơ sở hạ tầng đám mây.  
- Thông qua các nghiên cứu tình huống sự cố thực tế, tôi đã hiểu sâu hơn về việc áp dụng các nguyên tắc **phòng thủ theo chiều sâu** vào các dự án phức tạp.  

#### Tiếp cận kỹ thuật thực tế
- Tham gia các bài tập cấu hình **cô lập mạng và chính sách IAM** giúp tôi hình dung rõ cách cấu trúc môi trường đám mây an toàn.  
- Học cách **cấu hình VPC subnet**, quản lý security group và thực thi quyền truy cập theo đặc quyền tối thiểu.  
- Hiểu rõ cơ chế hoạt động của khóa mã hóa và các dịch vụ phát hiện mối đe dọa như GuardDuty.  

#### Tận dụng công cụ hiện đại
- Khám phá **AWS WAF và KMS**, các công cụ thiết yếu để lọc lưu lượng web và bảo vệ dữ liệu bằng mật mã.  
- Học cách **tự động hóa việc theo dõi kiểm toán** với CloudTrail để cải thiện tính minh bạch tổng thể và tư thế bảo mật của hệ thống.  

#### Thảo luận và kết nối
- Hội thảo mang lại cơ hội trao đổi các chiến lược bảo mật với các đồng nghiệp và chuyên gia trong ngành, nhấn mạnh các thách thức tuân thủ chung.  
- Các ví dụ về mối đe dọa thực tế củng cố tầm quan trọng của việc mô hình hóa bảo mật chủ động thay vì vá lỗi phản ứng.  

#### Bài học rút ra
- Phân đoạn mạng và quản lý định danh đúng cách giúp giảm đáng kể **bề mặt tấn công** của bất kỳ ứng dụng web nào.  
- Bảo mật là một quá trình liên tục đòi hỏi phải giám sát thường xuyên, kiểm toán nhật ký và tuân thủ các chuẩn mực tuân thủ đã thiết lập.  
- Sử dụng các dịch vụ bảo mật gốc của AWS làm giảm đáng kể gánh nặng kỹ thuật cần thiết để duy trì mức độ an toàn cấp doanh nghiệp.  

 

> Nhìn chung, sự kiện không chỉ cung cấp kiến thức kỹ thuật quan trọng về bảo mật đám mây mà còn thay đổi góc nhìn của tôi về kỹ thuật xây dựng các ứng dụng đáng tin cậy, có khả năng phục hồi và được bảo vệ chuyên sâu.