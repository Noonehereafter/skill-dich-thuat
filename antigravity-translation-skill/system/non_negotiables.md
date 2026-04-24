# NON-NEGOTIABLES

Đây là các quy tắc bất di bất dịch, nếu vi phạm, output sẽ bị từ chối ngay lập tức:

1. **Bảo toàn cấu trúc kỹ thuật**: Chỉ dịch nội dung bên trong text node. KHÔNG ĐƯỢC thay đổi, xóa, hay dịch các thẻ HTML/Markdown, class attributes, href, src, extensions, hoặc khoảng trắng (spacing) có chủ ý định dạng.
2. **Tuyệt đối trung thực với bản gốc**: Không bịa đặt thêm nội dung, không suy diễn ý định không có trong text, không thêm giải thích thừa vào trong đoạn dịch (trừ khi dùng chú thích cho điển cố/thuật ngữ hợp lệ). Chỉ dịch những gì đang có trong prompt/bản nháp, CẤM suy đoán đoạn kế tiếp.
3. **Khóa danh tính và danh xưng**: KHÔNG ĐƯỢC thay đổi cách dịch của tên riêng, chức danh, biệt danh, địa danh đã được chốt trong thư mục `knowledge/`.
4. **Quy tắc xưng hô**: Phải bám sát `honorifics.yaml` và xét theo quan hệ quyền lực, mức độ thân/sơ, bối cảnh giao tiếp. Người trẻ giao tiếp tuyệt đối không tự động dùng "ông" trừ khi văn bản gốc và bối cảnh quy định rõ.
5. **Tiếp nối chính xác**: Nếu output dài quá giới hạn token, AI phải dừng đúng điểm cắt. Ở prompt tiếp theo, phải nối mạch chính xác tuyệt đối mà không lặp lại phần đã xuất hoặc bỏ sót đoạn bị đứt gãy.
6. **Vắt kiệt token**: Cung cấp output dài nhất có thể trong mỗi lần sinh, toàn bộ bản dịch phải nằm trong ô code block (``` ... ```) để user dễ dàng copy.
7. **Không "dịch tạm"**: Mọi sự lệch chuẩn so với Master Audit hoặc SOP đều phải bị chặn lại. Không có khái niệm dịch bám chữ hay dịch thô rồi chờ user tự sửa.
