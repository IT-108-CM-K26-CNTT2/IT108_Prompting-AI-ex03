# [Bài thực hành 3] Phân tích và giải quyết tình huống khách hàng khiếu nại

## 1. Bối cảnh vấn đề

Một cửa hàng bán laptop nhận được khiếu nại từ khách hàng:

> "Tôi mua laptop cách đây 10 ngày. Máy thường xuyên bị nóng, quạt kêu to và pin chỉ sử dụng được khoảng 2 tiếng. Tôi đã mang đến cửa hàng kiểm tra nhưng nhân viên chỉ vệ sinh máy và trả lại. Sau 2 ngày, tình trạng vẫn tiếp diễn. Tôi muốn đổi máy hoặc hoàn tiền."

Nhân viên chăm sóc khách hàng cần sử dụng AI để phân tích tình huống và đề xuất phương án xử lý phù hợp. Tuy nhiên, nếu yêu cầu AI trả lời ngay, kết quả có thể thiếu căn cứ hoặc bỏ sót vấn đề quan trọng.

## 2. Yêu cầu nghiệp vụ

Thiết kế prompt để AI thực hiện:

- Xác định các vấn đề khách hàng đang gặp phải.
- Phân tích mức độ nghiêm trọng của từng vấn đề.
- Xác định thông tin còn thiếu cần xác minh.
- Đề xuất 2 phương án giải quyết phù hợp.
- Soạn phản hồi chuyên nghiệp gửi khách hàng.

## 3. Yêu cầu kỹ thuật

- Bắt buộc sử dụng kỹ thuật Chain-of-Thought.
- Yêu cầu AI phân tích theo trình tự từng bước.
- Không được tự giả định chính sách đổi trả của cửa hàng.
- Phân biệt rõ dữ kiện, giả thuyết và thông tin chưa xác định.
- Không đưa ra kết luận thiếu căn cứ.

## 4. Yêu cầu đầu ra

- Một prompt hoàn chỉnh.
- Báo cáo phân tích theo từng bước.
- Danh sách thông tin cần xác minh.
- Hai phương án xử lý, kèm ưu điểm và hạn chế.

---

## Bài làm

### Prompt 1: Trích xuất thông tin từ phản hồi của khách hàng

````text
Bạn hãy đóng vai trò là người đang phân tích tình huống về các phản hồi của khách hàng về việc sử dụng laptop.

Bạn hãy lọc ra những thông tin sau từ đoạn phản hồi của khách hàng và làm ra dạng JSON:

* Tên khách hàng
* Thời gian đã mua laptop
* Vấn đề khách hàng đang gặp
* Mong muốn của khách hàng

Phản hồi của anh Nguyen Van A: "Tôi mua laptop cách đây 10 ngày. Máy thường xuyên bị nóng, quạt kêu to và pin chỉ sử dụng được khoảng 2 tiếng. Tôi đã mang đến cửa hàng kiểm tra nhưng nhân viên chỉ vệ sinh máy và trả lại. Sau 2 ngày, tình trạng vẫn tiếp diễn. Tôi muốn đổi máy hoặc hoàn tiền."

Dạng JSON:
{
  "Tên khách hàng": "...",
  "Thời gian đã mua laptop": "...",
  "Vấn đề khách hàng đang gặp": "...",
  "Mong muốn của khách hàng": "..."
}
````

### Prompt 2: Phân tích theo Chain-of-Thought

````text
Dựa trên cấu trúc của JSON trên, hãy suy nghĩ từng bước một sau đây:

Bước 1: Xác định các vấn đề khách hàng đang gặp phải.
Bước 2: Phân tích mức độ nghiêm trọng của từng vấn đề.
Bước 3: Đề xuất 2 phương án giải quyết phù hợp.

Ràng buộc:
* Không được chào hỏi hay giải thích dài dòng.
* Phải làm đúng theo từng bước.
* Không được tự giả định chính sách đổi trả của cửa hàng.
* Không đưa ra kết luận thiếu căn cứ.
* Phải viết phản hồi lại khách hàng một cách chuyên nghiệp.
````
