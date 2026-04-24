# BUILD KNOWLEDGE PROMPT

**Mục tiêu:** Tạo hoặc cập nhật các file trong thư mục `knowledge/` dựa trên Master Audit.

**Quy tắc:**
1. Chỉ tạo mới nếu file chưa tồn tại (ví dụ: quét lần đầu để sinh `entities.yaml`, `titles.yaml`).
2. Không tự ý thay đổi các key đã tồn tại mà không có cờ `--force` hoặc sự chấp thuận rõ ràng của user.
