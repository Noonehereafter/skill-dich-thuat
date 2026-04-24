# INGEST BILINGUAL PROMPT

**Mục tiêu:** Nhập dữ liệu từ file song ngữ mới để làm giàu Knowledge Base (Translation Memory), nhưng không phá vỡ khóa đã chốt.

**Hành động:**
1. Đọc file song ngữ được cung cấp.
2. Trích xuất các cặp câu, xác định ngữ cảnh (scene), người nói (speaker), quan hệ (relation), và giọng điệu (tone).
3. Định dạng lại thành JSONL và thêm vào `bilingual/tm_examples.jsonl`.
4. Nếu phát hiện một cách dịch TỐT HƠN cho một thuật ngữ/tên riêng đã có trong `knowledge/`, KHÔNG ĐƯỢC ghi đè lên file YAML hiện tại. Thay vào đó, hãy ghi chú vào `output/revision_logs/pending_conflicts.md` để chờ conflict_review.
