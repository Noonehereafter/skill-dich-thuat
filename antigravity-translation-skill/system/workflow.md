# RUNTIME WORKFLOW

Luồng vận hành chuẩn của AI khi nhận một yêu cầu dịch:

1. **Khởi tạo và Quét (scan_project)**
   - Đọc `project/chapter_roadmap.yaml` để biết thứ tự xử lý.
   - Kiểm tra `project/project_status.yaml` để biết trạng thái file (done, in_progress, untouched, broken_continue).

2. **Cập nhật và Nạp tri thức (build_or_update_knowledge)**
   - Đọc hệ thống file trong `knowledge/` (entities, honorifics, terminology, voice_profiles).
   - Nếu có file song ngữ mới trong `bilingual/`, trích xuất thông tin nhưng chỉ cập nhật nếu KHÔNG mâu thuẫn với chuẩn đã khóa. Đưa mâu thuẫn vào `pending_conflicts`.

3. **Căn chỉnh bộ nhớ (align_bilingual_memory)**
   - Phân tích file song ngữ hiện có, loại bỏ các cặp dịch lỗi.
   - Gắn nhãn ngữ cảnh (ví dụ: `scene: interrogation`, `tone: casual`) vào các cặp dịch mẫu.

4. **Dịch hoặc Biên tập (translate_or_revise)**
   - Ưu tiên áp dụng: Roadmap -> Bảng danh tính -> Ma trận xưng hô -> Giọng điệu -> TM examples.
   - Nếu ở chế độ `revise_only`, chỉ chỉnh sửa file song ngữ hiện tại để gọt giũa câu chữ, loại bỏ "mùi dịch bám chữ".

5. **Kiểm soát chất lượng (qa_gate)**
   - Chạy kiểm tra theo 6 lớp: cấu trúc, danh tính, xưng hô, tiết tấu, độ trung thực, độ hoàn thiện.

6. **Xuất kết quả**
   - Nếu output bị cắt ngang do giới hạn token, ghi lại vào `project/continuation_log.yaml`.
   - Nếu tất cả các cổng QA pass (`release_gate = pass`), xuất bản dịch hoàn chỉnh vào trong code block.
