### 1. Bảng so sánh Google Search và AI Assistant trong xử lý lỗi lập trình

| Tiêu chí đánh giá | Google Search (Tìm kiếm trên StackOverflow, Docs) | AI Assistant (ChatGPT, Claude, Copilot...) |
| :--- | :--- | :--- |
| **Độ chính xác** | **Ưu điểm:** Cao nếu chọn đúng bài viết có nhiều lượt bình chọn (upvote) hoặc tài liệu chính thức.<br>**Nhược điểm:** Mất thời gian sàng lọc giữa nhiều câu trả lời cũ hoặc không đúng ngữ cảnh. | **Ưu điểm:** Tổng hợp nhanh giải pháp bám sát đúng đoạn mã lỗi cụ thể của dự án.<br>**Nhược điểm:** Dễ đưa ra câu trả lời sai lệch nếu ngữ cảnh hệ thống phức tạp hoặc thiếu thông tin. |
| **Tính cập nhật** | **Ưu điểm:** Cập nhật tức thì theo thời gian thực các lỗi mới, bản vá (patch) và phiên bản thư viện vừa phát hành.<br>**Nhược điểm:** Các kết quả đứng đầu đôi khi là bài viết từ nhiều năm trước, đã lỗi thời. | **Ưu điểm:** Nắm vững các kiến thức nền tảng và các phiên bản phổ biến.<br>**Nhược điểm:** Bị giới hạn bởi mốc thời gian huấn luyện dữ liệu (trừ khi có tích hợp tìm kiếm web). |
| **Khả năng giải thích** | **Ưu điểm:** Có nhiều góc nhìn thảo luận thực tế từ cộng đồng lập trình viên.<br>**Nhược điểm:** Giải thích thường rải rác, ngắn gọn, người mới khó hiểu bản chất vấn đề. | **Ưu điểm:** Giải thích cực kỳ chi tiết, mạch lạc từng bước và có thể hỏi lại nhiều lần nếu chưa hiểu.<br>**Nhược điểm:** Đôi khi giải thích lan man hoặc quá tự tin vào một lập luận chưa chuẩn xác. |
| **Rủi ro (Hallucination - Ảo giác)** | **Ưu điểm:** Hầu như **không có** rủi ro ảo giác vì nội dung do con người viết và được cộng đồng kiểm duyệt.<br>**Nhược điểm:** Có rủi ro gặp mã độc hoặc hướng dẫn kém an toàn nếu vào nhầm trang web giả mạo. | **Ưu điểm:** Giảm thiểu tốt trên các mô hình đời mới.<br>**Nhược điểm:** **Rủi ro cao** — AI có thể tự "bịa" ra tên tham số, câu lệnh hệ thống hoặc cờ (flag) không tồn tại. |

### 2. Lựa chọn: Trường hợp bắt buộc phải dùng Google Search để đảm bảo an toàn cho máy tính

Trong quá trình xử lý lỗi (đặc biệt là lỗi xung đột cổng - Port conflict), **bắt buộc phải dùng Google Search** để kiểm chứng qua tài liệu chính thức (Official Docs) hoặc diễn đàn uy tín (StackOverflow, GitHub Issues) trong các trường hợp sau:

* **Chạy các câu lệnh can thiệp sâu vào hệ thống với quyền quản trị cao nhất (`sudo`, `Administrator`):** Ví dụ như lệnh ép buộc dừng tiến trình (`kill -9`, `taskkill /F`), mở/đóng cổng tường lửa (Firewall), chỉnh sửa tệp cấu hình mạng hoặc Windows Registry. Nếu AI bị *Hallucination* và đưa sai mã tiến trình (PID) hoặc tham số hệ thống, việc chạy mù quáng có thể làm sập hệ điều hành hoặc mất dữ liệu.
* **Cài đặt lại phần mềm, tải bản vá hoặc thay đổi biến môi trường hệ thống:** Cần dùng Google Search để truy cập đúng trang chủ chính thức của nhà phát triển, tránh tải nhầm các gói cài đặt giả mạo hoặc thực thi các đoạn script từ nguồn không xác định do AI gợi ý.
* **Lỗi liên quan đến bảo mật và dữ liệu nhạy cảm:** Tuyệt đối không dán các tệp cấu hình chứa khóa bí mật (API Key, mật khẩu database, token nội bộ) lên công cụ AI công cộng để tránh nguy cơ rò rỉ dữ liệu dự án.
