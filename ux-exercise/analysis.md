# UX exercise — Chatbot Neo

## Sản phẩm: Chatbot Neo AI Assistant (Trợ lý AI)

## 4 paths

### 1. AI đúng
- User quy định điều khoản -> chatbot: trả lời đúng
- UI: hiện tag + icon category, không hỏi confirm

### 2. AI không chắc
- User hỏi giá vé cụ thể -> chatbot: trả lời giá trong 1 khoảng giá không có giá chính xác
- UI: không hiện gợi ý nào, user phải tự hỏi
- Vấn đề: không trả lời câu hỏi của user vè chuyến bay, giá vé, giờ bay cụ thể được

### 3. AI sai
- User hỏi "quy đinh chất lỏng được mang lên máy bay" -> chatbot: trả lời ko biết -> hỏi lại -> chatbot: trả lời kết quả
- User hỏi ngoài phạm vi (ví dụ: gấu nam cực là gì) -> chatbot: "hủy chuyến bay"
- Vấn đề: không có khả năng nhớ ngữ cảnh, trả lời sai ngoài phạm vi

### 4. User mất niềm tin
- User hỏi chatbot thường trả lời chung chung gợi ý link chứ không trả lời trực tiếp vào câu hỏi hay hỗ trợ khách thực hiện đặt chuyến
- Không có gợi ý sau câu hỏi khiến khách không biết chatbot hỗ trợ gì, kém tương tác
- Câu trả lời chatbot thường bị lặp lại (2 lần) khi người dùng hỏi 1 lần

## Path yếu nhất: Path 2
- Khi AI không chắc -> user không nắm được thông tin cụ thể ,realtime
- Không có gợi ý sau câu hỏi khiến khách không biết chatbot hỗ trợ gì, kém tương tác
- Không có exit/fallback cho user mất niềm tin

## Gap marketing vs thực tế
- Marketing: "Trợ lý thông minh trả lời nhanh chóng"
- Thực tế: Trả lời chung chung, không có khả năng trả lời câu hỏi của user vè chuyến bay, giá vé, giờ bay cụ thể được, thời gian trả lời rất lâu (khoảng 30 giây-2 phút)
- Gap lớn nhất: Sự đứt gãy giữa "Kỳ vọng về sự chủ động" và "Thực tế bị động".
    Marketing: Định vị là "Trợ lý thông minh" – một thực thể có khả năng giải quyết vấn đề trọn gói.
Thực tế: Neo chỉ là một "Máy tra cứu chậm" – hoạt động như một công cụ tìm kiếm từ khóa nhưng tốc độ phản hồi kém xa Google.

## Sketch
- As-is: user hỏi -> chatbot check từ khóa --> trả lời chung chung 
- To-be: user hỏi -> LLM(intent, entity extraction) -> gọi tool(nếu cần) -> LLM(generate answer) -> UI hiện gợi ý + hỏi kết quả có đúng không -> user feedback -> LLM(update knowledge base)