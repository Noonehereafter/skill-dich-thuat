# OUTPUT CONTRACT

Mọi phản hồi chứa bản dịch/biên tập từ AI phải tuân thủ nghiêm ngặt hợp đồng sau:

1. **Format**: Toàn bộ bản dịch phải được bao bọc trong một khối mã (code block) duy nhất để người dùng sao chép dễ dàng bằng một cú nhấp chuột. KHÔNG in ra từng đoạn mã lẻ tẻ.

   ```text
   Nội dung bản dịch sẽ xuất hiện toàn bộ ở đây, giữ nguyên cấu trúc HTML/MD gốc.
   ```

2. **Completeness**: Sử dụng tối đa dung lượng token cho phép. Nếu đoạn dịch không thể hoàn thành trong một phản hồi, văn bản phải dừng ở một ranh giới rõ ràng (ví dụ, hết một câu hoặc hết một đoạn HTML tag).

3. **Continuation**: Khi nhận được lệnh tiếp tục, AI KHÔNG ĐƯỢC lặp lại văn bản đã sinh ra trước đó, và KHÔNG ĐƯỢC để mất một ký tự nào ở điểm nối. Cập nhật file log trong nền để theo dõi.

4. **Tone & Style**: Văn phong phải mềm mại, uyển chuyển, tự nhiên. Từ ngữ phải phù hợp với bối cảnh giao tiếp (nghiêm túc trong công việc, cợt nhả với đồng đội, ngôn ngữ giang hồ v.v.). Thành ngữ, tục ngữ, hoặc tiếng lóng được phép sử dụng nếu phản ánh đúng nguyên gốc tiếng Anh, có thể kèm theo ngoặc đơn chú thích ngắn nếu đó là thuật ngữ đặc thù khó hiểu.

5. **No AI Chatter**: Hạn chế tối đa việc giải thích dông dài ở đầu hoặc cuối phản hồi trừ khi thông báo về việc đứt gãy token hoặc báo cáo QA thất bại cần người dùng can thiệp.
