---
title: "Event 2: GenAI-powered App-DB Modernization workshop"
date: 2026-09-30
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

{{% notice warning %}}
⚠️ **Note:** Thông tin dưới đây dùng để tham khảo. Vui lòng không sao chép nguyên văn hoàn toàn cho báo cáo của bạn.
{{% /notice %}}

# Báo cáo tóm tắt: Hội thảo “GenAI-powered App-DB Modernization”

### Mục tiêu sự kiện

- Chia sẻ các phương pháp hay nhất (best practices) trong thiết kế ứng dụng hiện đại.
- Giới thiệu Thiết kế Hướng miền (Domain-Driven Design - DDD) và kiến trúc hướng sự kiện (Event-driven Architecture).
- Cung cấp hướng dẫn chi tiết về cách lựa chọn các dịch vụ tính toán (compute services) phù hợp.
- Trình bày các công cụ AI hỗ trợ toàn bộ vòng đời phát triển phần mềm (SDLC).

### Diễn giả chính

- **Jignesh Shah** – Giám đốc Cơ sở dữ liệu Mã nguồn mở
- **Erica Liu** – Chuyên gia GTM Cấp cao, AppMod
- **Fabrianne Effendi** – Chuyên gia Hỗ trợ Kỹ thuật, Serverless Amazon Web Services

### Các điểm nổi bật chính

#### Nhược điểm của kiến trúc ứng dụng truyền thống (Legacy)
- Vòng đời phát hành sản phẩm kéo dài dẫn đến thất thu và bỏ lỡ cơ hội thị trường.
- Vận hành kém hiệu quả làm giảm năng suất và đẩy chi phí lên cao.
- Không tuân thủ các quy định bảo mật gây ra các sự cố lộ dữ liệu và tổn hại uy tín.

#### Chuyển đổi sang kiến trúc ứng dụng hiện đại – Microservices
Chuyển đổi sang hệ thống dạng mô-đun — trong đó mỗi chức năng là một **dịch vụ độc lập** giao tiếp thông qua **các sự kiện**, được xây dựng trên 3 trụ cột cốt lõi:
- **Quản lý hàng đợi (Queue Management):** Xử lý các tác vụ bất đồng bộ hiệu quả.
- **Chiến lược bộ nhớ đệm (Caching Strategy):** Tối ưu hóa hiệu năng hệ thống.
- **Xử lý thông điệp (Message Handling):** Đảm bảo giao tiếp linh hoạt giữa các dịch vụ.

#### Thiết kế Hướng miền (Domain-Driven Design - DDD)
- **Phương pháp 4 bước:** Xác định sự kiện miền → sắp xếp dòng thời gian → xác định các tác nhân → định nghĩa bối cảnh giới hạn (bounded contexts).
- **Nghiên cứu tình huống nhà sách:** Minh họa ứng dụng thực tế của mô hình DDD.
- **Ánh xạ bối cảnh (Context mapping):** 7 mẫu thiết kế để tích hợp các bối cảnh giới hạn.

#### Kiến trúc Hướng Sự kiện (Event-Driven Architecture)
- **3 mô hình tích hợp:** Publish/Subscribe, Point-to-point, Streaming.
- **Lợi ích:** Tính lỏng lẻo (loose coupling), khả năng mở rộng cao và tính chịu lỗi tốt.
- **So sánh đồng bộ và bất đồng bộ:** Hiểu rõ các đánh đổi (trade-offs) trong kiến trúc.

#### Sự tiến hóa của tính toán (Compute Evolution)
- **Mô hình trách nhiệm chia sẻ:** Từ EC2, ECS, Fargate đến Lambda.
- **Lợi ích của Serverless:** Không cần quản lý máy chủ, tự động mở rộng, trả phí theo giá trị sử dụng thực tế.
- **Hàm (Functions) và Container:** Các tiêu chí lựa chọn giải pháp phù hợp.

#### Amazon Q Developer
- **Tự động hóa SDLC:** Hỗ trợ từ khâu lên ý tưởng, lập kế hoạch đến bảo trì hệ thống.
- **Chuyển đổi mã nguồn:** Nâng cấp phiên bản Java, hiện đại hóa ứng dụng .NET.
- **AWS Transform agents:** Hỗ trợ di chuyển từ VMware, Mainframe và .NET.

---

### Bài học cốt lõi thu được

#### Tư duy thiết kế (Design Mindset)
- **Tiếp cận lấy kinh doanh làm trọng tâm:** Luôn bắt đầu từ nghiệp vụ kinh doanh thay vì chỉ chăm chăm vào công nghệ.
- **Ngôn ngữ phổ quát (Ubiquitous language):** Tầm quan trọng của việc xây dựng từ vựng chung giữa đội ngũ kinh doanh và kỹ thuật.
- **Bối cảnh giới hạn:** Nhận diện và quản lý độ phức tạp trong các hệ thống lớn.

#### Kiến trúc kỹ thuật (Technical Architecture)
- **Kỹ thuật Event storming:** Phương pháp thực tế để mô hình hóa các quy trình nghiệp vụ.
- Ưu tiên sử dụng **giao tiếp hướng sự kiện** thay vì các lời gọi đồng bộ truyền thống.
- **Mô hình tích hợp:** Biết rõ khi nào nên dùng đồng bộ, bất đồng bộ, pub/sub hay streaming.

#### Chiến lược hiện đại hóa (Modernization Strategy)
- **Tiếp cận theo giai đoạn:** Không vội vã, tuân thủ theo lộ trình rõ ràng.
- **Khung 7Rs:** Nhiều con đường hiện đại hóa tùy thuộc vào đặc thù của ứng dụng.
- **Đo lường ROI:** Đánh giá hiệu quả dựa trên việc giảm chi phí kết hợp tăng tính linh hoạt trong kinh doanh.

---

### Ứng dụng vào công việc và Đồ án thực tế

- **Áp dụng DDD:** Đưa các buổi thảo luận event storming vào quy trình làm việc với nhóm.
- **Tái cấu trúc Microservices:** Sử dụng các bối cảnh giới hạn để xác định ranh giới rõ ràng cho từng dịch vụ backend.
- **Triển khai mô hình hướng sự kiện:** Thay thế một số lời gọi đồng bộ bằng hệ thống nhắn tin bất đồng bộ.
- **Ứng dụng Serverless:** Thử nghiệm AWS Lambda cho các tác vụ phù hợp trong đồ án web 3 tầng.
- **Trải nghiệm Amazon Q Developer:** Tích hợp công cụ AI vào quy trình phát triển để tăng năng suất lập trình.

---

### Trải nghiệm tham gia sự kiện

Tham gia hội thảo **“GenAI-powered App-DB Modernization”** là một trải nghiệm cực kỳ giá trị, cung cấp cho tôi cái nhìn toàn diện về cách hiện đại hóa ứng dụng và cơ sở dữ liệu bằng các phương pháp, công cụ tiên tiến. Những điểm ấn tượng nhất bao gồm:

- **Học hỏi từ các chuyên gia hàng đầu:** Lắng nghe chia sẻ về các phương pháp hay nhất từ các chuyên gia AWS và các tổ chức công nghệ lớn.
- **Tiếp cận kỹ thuật thực tế:** Tham gia các phiên thảo luận mô hình hóa quy trình nghiệp vụ và nắm bắt cách chia nhỏ microservices, phân định bối cảnh giới hạn.
- **Tận dụng công cụ hiện đại:** Trải nghiệm thực tế Amazon Q Developer và tìm hiểu cách tự động hóa chuyển đổi mã nguồn để cải thiện hiệu suất.
- **Bài học rút ra:** Việc áp dụng DDD và kiến trúc hướng sự kiện giúp giảm sự phụ thuộc lẫn nhau giữa các thành phần, đồng thời nâng cao khả năng mở rộng và độ ổn định cho toàn bộ hệ thống ứng dụng web.

#### Hình ảnh sự kiện
*(Thêm hình ảnh sự kiện của bạn tại đây)*

