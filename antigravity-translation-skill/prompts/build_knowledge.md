# BUILD KNOWLEDGE PROMPT

**Mục tiêu:** Tạo hoặc cập nhật các file trong thư mục `knowledge/` dựa trên Master Audit hoặc file song ngữ.

**Quy tắc:**
1. Chỉ tạo mới nếu file chưa tồn tại (ví dụ: quét lần đầu để sinh `entities.yaml`, `titles.yaml`).
2. Khi hợp nhất từ song ngữ đã duyệt, tuân thủ nguyên tắc: Master Audit > Song ngữ.
3. Không tự ý thay đổi các key đã tồn tại mà không có cờ `--force` hoặc sự chấp thuận rõ ràng của user.
