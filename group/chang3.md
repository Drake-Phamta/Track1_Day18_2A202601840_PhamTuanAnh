# Chặng 3 — Human–AI Design pass

Chỉ review critical interaction cần test: Trải nghiệm tại khoảnh khắc học viên yêu cầu/nhận được gợi ý hỗ trợ và cung cấp bối cảnh cho Lab Coach.

## 1. Bốn quyết định thiết kế

**Expectation**
- **Trước khi AI hoạt động, user có hiểu AI sắp làm gì không?** Option A nói rõ hệ thống sẽ quét terminal/bài học hiện tại để tạo bản nháp. Option B nói rõ hệ thống đang theo dõi lỗi trong phiên học và sẽ gợi ý hỗ trợ khi có tín hiệu lặp lại; pop-up cho biết tín hiệu nào đã được dùng.
- **Capability và limit nào cần nói rõ?** Cần nói rõ A chỉ tạo bản nháp, không tự chọn Coach hay tự gửi; B chỉ đưa ra gợi ý, không tự gửi ticket, và có thể báo nhầm nếu tín hiệu lỗi không đủ.

**Role and Agency**
- **User làm phần nào? AI làm phần nào?** A: AI tóm tắt, user sửa và chọn Coach. B: AI phát hiện/gợi ý, user xác nhận hoặc dismiss. C: user tự cung cấp context, hệ thống chỉ route bằng rule.
- **AI Act, Ask hay Don't Act tại critical moment?** A và B là **Ask**: AI chỉ chuẩn bị bản nháp/gợi ý và chờ quyết định. C là **Don't infer**: rule chỉ chạy sau khi user gửi đủ trường bắt buộc, không tự đoán ý định.
- **Nếu AI sai, user mất gì và sai có dễ phát hiện không?** Nếu AI lấy sai code hoặc định tuyến sai, user chỉ mất thêm vài giây đọc trước khi bấm hủy/sửa. Lỗi rất dễ phát hiện vì bản nháp và tên Lab Coach được hiển thị rõ ràng để user duyệt.

**Evidence and Uncertainty**
- **User cần biết AI dựa vào tín hiệu hoặc dữ liệu nào?** AI ghi rõ trong bản nháp hoặc pop-up là "dựa trên lỗi ở dòng số..." hoặc "dựa trên 3 lần chạy sai gần nhất".
- **Nếu AI không chắc, hệ thống thể hiện ra sao?** Sử dụng ngôn ngữ giảm nhẹ ("Có vẻ như bạn đang vướng...") hoặc trạng thái fallback ("Không tìm thấy thông báo lỗi tự động, vui lòng mô tả tay").

**Control and Recovery**
- **User preview, edit, reject, stop, undo hoặc dismiss ở đâu?** A preview/sửa context và chọn lại Coach trước khi gửi; B dismiss pop-up và tắt gợi ý trong 10 phút; C review form trước khi gửi và có thể tạo lại nếu chọn nhầm.
- **Sau khi AI sai, user tiếp tục task ban đầu bằng đường nào?** A có thể sửa bản nháp hoặc hủy ticket sau khi gửi. B có thể dismiss và gọi hỗ trợ thủ công. C có thể báo chọn nhầm danh mục hoặc reset để tạo lại.

## 2. Human–AI Decision Table

| Human–AI decision | Option A (User-Initiated + AI Context) | Option B (AI-Initiated + User Confirms) | Option C (No AI / Manual Form) |
|---|---|---|---|
| **User làm gì? AI làm gì?** | **User:** Bấm hỗ trợ, review/sửa bản nháp và tự chọn Coach. <br> **AI:** Trích xuất lỗi từ terminal/bài Lab và tạo tóm tắt; không route. | **AI:** Theo dõi tín hiệu lỗi trong phiên, phân tích và tạo pop-up gợi ý Coach. <br> **User:** Đọc bằng chứng rồi quyết định "Có/Không". | **User:** Chủ động bấm nút "Hỗ trợ", tự phân loại danh mục lỗi và tự viết/paste lỗi vào form. <br> **Hệ thống:** Chỉ áp dụng rule sau khi user gửi đủ trường bắt buộc. |
| **AI Act / Ask / Don't Act? Vì sao?** | **Ask:** AI tạo bản nháp nhưng không tự gửi/chọn người nhận; user review, chọn Coach rồi gửi. | **Ask:** AI chỉ hiện pop-up hỏi "Bạn có muốn chuyên gia X giúp không?", không tự động gửi ticket. Vì việc tự ý gọi Coach có thể làm phiền user đang muốn tự tìm hiểu và làm phiền Coach khi user chưa thực sự cần. | **Don't infer:** Không có AI suy đoán; rule chỉ route dữ liệu user đã nhập sau khi user submit. |
| **User hiểu capability/limit bằng gì?** | Dòng thông báo: *"Hệ thống quét terminal để tạo bản nháp; bạn vẫn chọn Coach và gửi."* | Pop-up ghi: *"Đã thấy lỗi này 3 lần trong 5 phút; đây là gợi ý, không phải kết luận."* | Label/placeholder hướng dẫn cách nhập; không hiển thị Coach mapping trước khi user chọn để tránh biến form thành lời giải. |
| **Evidence/uncertainty được thể hiện thế nào?** | AI show bản draft context ngay trên màn hình. Nếu terminal trống, AI hiển thị: *"Không tìm thấy thông báo lỗi tự động. Vui lòng mô tả thêm."* | AI dùng ngôn ngữ gợi ý, không khẳng định tuyệt đối: *"Có vẻ như bạn đang vướng ở phần cấu hình môi trường."* (Có vẻ như / It looks like). | Không áp dụng (vì không có AI dự đoán hay phân tích). User là người tự cung cấp bằng chứng (paste code). |
| **User kiểm soát và recovery thế nào?** | **Kiểm soát:** User có quyền chỉnh sửa (Edit) bản draft context do AI viết, hoặc xóa hết tự viết tay (Reject). <br> **Phục hồi:** Nếu gửi nhầm, có nút "Hủy yêu cầu" trong lịch sử. | **Kiểm soát:** Nút "Không, tôi muốn tự làm" (Dismiss) ngay trên pop-up. <br> **Phục hồi:** Pop-up tắt đi không xuất hiện lại trong 10 phút để không spam. User có thể gọi hỗ trợ thủ công nếu đổi ý. | **Kiểm soát:** User tự review form của mình trước khi bấm Submit. <br> **Phục hồi:** Nếu định tuyến nhầm danh mục, learner có thể tự chat vào ticket báo "Mình chọn nhầm mục" hoặc tự đóng ticket tạo lại. |

## Tự kiểm (GATE 3)
- [x] Mỗi option đã nói rõ user làm gì và AI làm gì.
- [x] Đã chọn agency phù hợp: Option A và B đều dùng chế độ "Ask" (sinh ra bản nháp hoặc gợi ý, chờ người dùng quyết định gửi) để giảm hậu quả sai lệch bối cảnh hoặc làm phiền không đáng có.
- [x] User có đường kiểm soát (Edit bản nháp ở A, Dismiss pop-up ở B) và phục hồi (Hủy yêu cầu).
