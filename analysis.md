# UX exercise — Vietnam Airlines — Chatbot NEO

## Sản phẩm: Vietnam Airlines — Chatbot NEO(Hỗ trợ khách hàng, tra cứu chuyến bay).
## 4 paths

### 1. AI đúng
-Kịch bản: User hỏi "Chuyến bay VN123 hôm nay mấy giờ bay?"

-Kết quả: NEO trả về đúng bảng thông tin: Giờ đi, giờ đến, trạng thái (On-time).

-UI: Hiển thị card thông tin chuyến bay trực quan, nút "Làm thủ tục ngay".

-Hành động: User hài lòng, kết thúc luồng.

### 2. AI không chắc
-Kịch bản: User hỏi "Hành lý ký gửi mang được gì?" (Câu hỏi quá rộng).

-Vấn đề: NEO không chắc user hỏi về số lượng, cân nặng hay danh mục vật phẩm cấm.

-UI hiện tại: Trả về một link bài viết dài dằng dặc về quy định hành lý chung.

-Hành động: User phải tự đọc và tìm kiếm thông tin mình cần trong trang web.

### 3. AI sai
-Kịch bản: User muốn "Đổi vé bay sớm hơn" → NEO hiểu lầm thành "Hủy vé" hoặc trả về quy trình "Mua vé mới".

-Hậu quả: User làm theo hướng dẫn sai dẫn đến mất phí hoặc mất chỗ.

-Sửa: User phải thoát chatbot → Tìm hotline hoặc ra quầy vé → 5-10 bước chờ đợi.

-Vấn đề: Chatbot không có nút "Đây không phải ý tôi" để quay lại bước trước hoặc chuyển ngay cho human agent (tổng đài viên)

### 4. User mất niềm tin
-Kịch bản: Sau 2-3 lần hỏi về hoàn vé/đổi tên nhưng NEO chỉ trả về các câu trả lời mẫu vô thưởng vô phạt.

-Tâm lý: User mặc định "Chatbot này vô dụng", lần sau có vấn đề sẽ gọi thẳng hotline hoặc lên Group Facebook hỏi, dù phải chờ đợi lâu.

-Vấn đề: Không có lối thoát (Escaping point) rõ ràng sang hỗ trợ người thật khi AI bế tắc.

## Path yếu nhất: Path 3 + 4
-Thiếu sự hội thoại (Conversation): Khi không chắc, AI thay vì hỏi lại ("Bạn muốn hỏi về cân nặng hay vật phẩm cấm?") thì lại đẩy một tảng thông tin (Data dump).

-Friction (Ma sát) khi sửa lỗi: Không có cơ chế phản hồi tức thì để AI điều chỉnh hướng tư vấn. User cảm thấy bị "kẹt" trong một vòng lặp máy móc.

## Gap marketing vs thực tế
-Marketing: "Trợ lý ảo thông minh, hỗ trợ 24/7 mọi nhu cầu hành trình."

-Thực tế: Chỉ xử lý tốt các câu hỏi tra cứu thông tin tĩnh (giờ bay, số hiệu). Các nghiệp vụ thay đổi (đổi vé, xử lý sự cố) AI thường trả lời sai hoặc không đủ thẩm quyền giải quyết.

-Gap lớn nhất: Khách hàng kỳ vọng NEO có quyền hạn như một nhân viên phòng vé, nhưng thực tế NEO chỉ là một bộ máy tra cứu FAQ.
##sketch
(Ảnh đính kèm: sketch.jpg)
-As-is (Hiện tại): User đặt câu hỏi → Chatbot trả lời cứng nhắc (hoặc đưa link bài viết dài) → User đọc không thấy ý cần tìm → Phải thoát ra gọi Hotline hoặc tự tìm kiếm lại từ đầu.

-To-be (Cải tiến): User đặt câu hỏi → Chatbot trả lời kèm các lựa chọn làm rõ (Clarification Chips) → Nếu mức độ tự tin (confidence) thấp: hiện "Moni đang hiểu bạn muốn hỏi về [Hành lý cấm], có đúng không?" → User chọn hoặc nhấn "Chưa đúng ý tôi" → Hệ thống hiện nút "Kết nối nhân viên thật" hoặc gợi ý lại dựa trên lựa chọn mới → AI ghi nhận dữ liệu sai lệch → Hiện: "Cảm ơn bạn, NEO đã ghi nhớ lỗi này để hỗ trợ tốt hơn vào lần sau!"
