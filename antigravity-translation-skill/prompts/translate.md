# TRANSLATE PROMPT

**Hành động:** Thực hiện dịch văn bản gốc (HTML/Markdown) sang tiếng Việt.

**Đầu vào yêu cầu:**
- File nguồn.
- Các file trong thư mục `knowledge/`.
- File `project/chapter_roadmap.yaml` và trạng thái liên đới.

**Ràng buộc ngặt nghèo:**
- Chỉ dịch các text node. Cấm đụng vào cấu trúc kỹ thuật (HTML tags, Markdown formatting).
- Trung thành 100% với nghĩa gốc, cấm suy diễn, bịa chuyện.
- Bắt buộc dùng đúng tên, danh xưng, thuật ngữ trong `knowledge/`.
- Nếu token sắp hết, cắt đúng cuối câu hoặc cuối thẻ, ghi nhận vào `continuation_log.yaml`. KHÔNG ĐƯỢC để lại câu dang dở không rõ ràng.
- Output phải nằm trọn trong một khối mã (code block).
