# ANTIGRAVITY TRANSLATION SKILL

## Purpose
Tạo bản dịch tiếng Việt chuẩn xuất bản trực tiếp từ file gốc HTML/MD với chất lượng của một dịch giả chuyên nghiệp 20 năm kinh nghiệm.
Mặc định đầu ra là bản cuối dùng ngay, không phải bản nháp.

## Source of Truth
1. project/chapter_roadmap.yaml
2. knowledge/entities.yaml
3. knowledge/honorifics.yaml
4. knowledge/terminology.yaml
5. knowledge/voice_profiles.yaml
6. qa/qa_rules.yaml

## Non-negotiables
- Chỉ dịch text node.
- Giữ nguyên 100% cấu trúc HTML/MD, class, href, src, extension, spacing kỹ thuật.
- Không bịa, không thêm ý, không suy diễn.
- Không đổi tên riêng, chức danh, biệt danh, địa danh đã khóa.
- Xưng hô phải theo quan hệ quyền lực, thân-sơ, mục đích thoại.
- Nếu output bị cắt, dừng đúng điểm cắt và nối mạch chính xác ở lượt sau.
- Chỉ được dịch phần văn bản đã đọc thấy trong source hiện hành; cấm suy đoán đoạn kế tiếp dù chỉ một câu.
- Tuân thủ chặt chẽ instruction, SOP và master audit trong nội dung dịch.
- Văn phong đa bối cảnh (multi-context): Mềm mại, uyển chuyển, tự nhiên không cứng nhắc. Mỗi câu/từ sử dụng cần phải được nghiên cứu/cân nhắc, đảm bảo chuẩn một bản dịch hoàn chỉnh cho người Việt, không gây xa lạ kể cả tiếng lóng/chửi tục. Từ ngữ ít dùng (thuật ngữ/thành ngữ/tục ngữ/điển cố) có thể chấp nhận nếu có tương đồng trong tiếng Việt. Xưng hô phù hợp bối cảnh (bối phận trên dưới, người lạ, trong ngành cảnh sát/giang hồ, lãng mạn ...).
- Văn phong phù hợp bối cảnh giao tiếp: nghiêm túc, hài hước (ví dụ: đồng đội phá bĩnh -> đồng đội heo, từ ngữ trending), bách thái nhân sinh. Lưu ý: người trẻ nói chuyện không dùng "ông" mà căn cứ văn bản gốc để xác định.
- Vắt kiệt token: không tự động hoàn thành file nếu chưa dịch toàn bộ. Ngưng và bắt đầu ở phản hồi tiếp theo đúng nội dung bị ngắt. Toàn bộ đầu ra đặt trong ô code để copy.

## Runtime Workflow
1. Đọc chapter_roadmap.yaml và project_status.yaml.
2. Xác định chương hiện tại và continuity state.
3. Nạp knowledge base đã khóa.
4. Áp dụng văn phong linh hoạt, chuyên nghiệp, dịch thẳng từ source.
5. Dịch theo text node.
6. Chạy QA gate.
7. Chỉ xuất nếu release_gate = pass.

## Release Rule
Một bản chỉ được phát hành khi:
- structure_ok = true
- entity_ok = true
- honorific_ok = true
- terminology_ok = true
- style_ok = true
- fidelity_ok = true
- completion_ok = true

## Auto-Generation Rules
- Nếu thiếu `chapter_roadmap.yaml`, AI phải quét tên file chương và tự dựng roadmap theo thứ tự logic.
- Nếu thiếu `project_status.yaml`, AI phải tạo từ trạng thái hiện có như done, scan_done, in_progress, untouched, broken_continue.
- Nếu thiếu `entities.yaml`, `titles.yaml`, `locations.yaml`, `terminology.yaml`, AI phải sinh lần đầu từ Master audit.
- Nếu gặp cách dịch mới mâu thuẫn với khóa cũ, AI phải mở mục pending_conflicts thay vì âm thầm sửa chuẩn dự án. Cấm "dịch tạm rồi sửa sau".
- Nếu output đang nối dở, AI phải tạo `continuation_log.yaml` với file, last_exact_tail, status, resume_mode. Dừng đúng điểm đứt và nối nguyên mạch.
