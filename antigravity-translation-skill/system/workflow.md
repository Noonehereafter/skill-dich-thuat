# RUNTIME WORKFLOW

Luồng vận hành chuẩn của AI khi nhận một yêu cầu dịch:

1. **Khởi tạo và Quét (scan_project)**
   - Đọc `project/chapter_roadmap.yaml` để biết thứ tự xử lý.
   - Kiểm tra `project/project_status.yaml` để biết trạng thái file (done, in_progress, untouched, broken_continue).

2. **Cập nhật và Nạp tri thức (build_or_update_knowledge)**
   - Đọc hệ thống file trong `knowledge/` (entities, honorifics, terminology, voice_profiles).

3. **Dịch trực tiếp từ bản gốc (translate)**
   - Ưu tiên áp dụng: Roadmap -> Bảng danh tính -> Ma trận xưng hô -> Giọng điệu.

4. **Kiểm soát chất lượng (qa_gate)**
   - Chạy kiểm tra theo 6 lớp: cấu trúc, danh tính, xưng hô, tiết tấu, độ trung thực, độ hoàn thiện.

5. **Xuất kết quả**
   - Nếu output bị cắt ngang do giới hạn token, ghi lại vào `project/continuation_log.yaml`.
   - Nếu tất cả các cổng QA pass (`release_gate = pass`), xuất bản dịch hoàn chỉnh vào trong code block.
