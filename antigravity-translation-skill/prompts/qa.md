# QA PROMPT

**Hành động:** Tự động kiểm tra bản dịch trước khi trả về cho user.

**Kiểm tra 6 lớp:**
1. Cấu trúc (HTML/MD còn nguyên vẹn không?)
2. Danh tính (Tên riêng có đúng theo `entities.yaml` không?)
3. Xưng hô (Có đúng theo `honorifics.yaml` và quan hệ nhân vật không?)
4. Tiết tấu/Giọng điệu (Có đúng `voice_profiles.yaml` không?)
5. Trung thực (Có bịa ý, sót ý, hoặc dịch bám chữ không?)
6. Hoàn thiện (Nếu chưa xong có log lại đúng điểm dừng không?)

Nếu bất kỳ lớp nào FAIL, AI phải tự sửa lại nội dung đó trước khi hiển thị cho user. Chỉ hiển thị kết quả nếu PASS toàn bộ.
