# Prototype Feedback Note — Feedback 3

*Bản gửi nhóm trưởng để ghép vào `chang6.md` mục 7. Định dạng theo đúng khung Feedback 1.*

---

## Thông tin phiên test

- **Người test:** T-01 — ngoài nhóm
- **Người facilitate:** Phạm Tuấn Anh (`2A202601840`)
- **Ngày/giờ:** 19/08/2026, 9:33
- **Thời lượng:** 10 phút
- **Tester có relevant context:** **Có**
- **Relevant context ngắn:** Tester nói có gặp khó khăn trong quá trình làm Lab _(ghi vắn tắt, chưa neo vào một buổi cụ thể)_
- **Thứ tự option:** **C → A → B**
- **Có can thiệp kỹ thuật không:** **Không**
- **Đã xin phép ghi chú:** Có

---

## Bảng quan sát

| Observation | Note — chỉ ghi hành vi/lời nói quan sát được |
|---|---|
| **First action** | Option C: bấm *Yêu cầu hỗ trợ*. Option A: vẫn bấm *Yêu cầu hỗ trợ*. Option B: bấm *Có, kết nối ngay* |
| **Chỗ dừng, do dự hoặc hiểu sai** | Chỉ do dự ở **Option A**, tại phần mô tả do AI soạn; tester quy cho *layout design chưa thông minh*. Option C và B: không do dự |
| **Evidence được đọc hay bỏ qua** | Option C: đọc lỗi nhưng chưa tự fix được nên cần Lab Coach. Option A: đọc lỗi, đọc lý do, chọn tên Lab Coach. Option B: đọc hết |
| **Cách tester sửa hoặc lấy lại control** | Tìm thấy ở cả ba option; riêng Option A ghi nhận là *dễ dàng* tìm thấy |
| **Option được chọn** | **C** |
| **Lý do và trade-off tester nói ra** | Lý do: *được quyền chủ động mô tả lỗi*. Trade-off: AI có gợi ý, tiện hơn và nhanh hơn, nhưng *chưa thể hiện rõ được nhu cầu mong muốn của tester* |
| **Evidence chống lại kỳ vọng của nhóm** | Tester chọn option **không có AI** dù nó bắt gõ nhiều nhất. Chỗ do dự duy nhất của cả phiên nằm ở bản nháp AI của Option A. Tester nói AI *mô tả chưa được chi tiết lỗi* và mình *cần chỉnh sửa nhiều* |

### Quan sát riêng ở Option C

- Có **paste code lỗi** vào form, không chỉ mô tả bằng lời.
- Đánh giá độ dài form là **vừa đủ**.
- Điền xong trong khoảng **1 phút**.
- Khi validation chặn vì thiếu trường: **không thấy phiền**, cho rằng đó là những trường cần thiết để Lab Coach hiểu.
- Danh mục đã chọn và dấu hiệu dựa vào: _chưa ghi nhận — đang hỏi lại_.

### Trích dẫn nguyên văn

> "Ban đầu tôi thích hơn C, nhưng sau khi trải nghiệm kỹ 3 option thì tôi cảm giác C vẫn chưa đủ, maybe cần có sự dung hợp của cả 3."

> "Tôi thấy AI mô tả chưa được chi tiết lỗi, tôi cần chỉnh sửa nhiều."

---

## Tách bốn lớp

### OBSERVED

Tester đã làm hoặc nói gì?

- Ở Option C và Option A, tester đều mở luồng bằng nút *Yêu cầu hỗ trợ*; ở Option B bấm *Có, kết nối ngay*.
- Option C: không do dự chỗ nào; đọc lỗi terminal; paste đoạn lỗi vào form; điền xong trong khoảng 1 phút; đánh giá độ dài form *vừa đủ*; khi validation chặn thì không thấy phiền, cho rằng các trường đó cần thiết để Coach hiểu.
- Option A: do dự ở phần mô tả do AI soạn; có đọc lỗi, đọc lý do, chọn tên Lab Coach; nói AI *mô tả chưa được chi tiết lỗi* và mình *cần chỉnh sửa nhiều*.
- Option B: không do dự, đọc hết nội dung pop-up.
- Cả ba option: tìm thấy đường sửa hoặc lấy lại control; riêng Option A là *dễ dàng*.
- Chọn **Option C**, lý do *được quyền chủ động mô tả lỗi*.
- Nói muốn AI **chỉ tự nhận các thông báo lỗi**, phần mô tả chi tiết thì tự đảm nhiệm.
- Điều còn chưa thoải mái ở chính option đã chọn: **phải dán tay đoạn code lỗi**, muốn AI tự quét.
- Sau khi dùng cả ba: nói *C vẫn chưa đủ* và *maybe cần có sự dung hợp của cả 3*.

### INTERPRETED

Nhóm nghĩ điều đó có thể có nghĩa gì? *(hypothesis, chưa phải kết luận)*

- Tester có thể đang tách hai việc mà cả ba option đang gộp làm một: **thu thập bằng chứng lỗi** (máy làm tốt hơn) và **diễn đạt vấn đề** (người muốn tự giữ). Việc chọn C nhưng vẫn khó chịu vì phải dán code tay khớp với cách đọc này.
- Do dự duy nhất rơi vào bản nháp Option A kèm nhận xét *cần chỉnh sửa nhiều* gợi ý rằng AI soạn hộ mô tả có thể **không giảm công mà chỉ dời công** — từ gõ sang đọc và sửa. Nếu đúng, lợi thế *nhanh hơn, tiện hơn* của A và B nhỏ hơn nhóm giả định.
- Tester quy do dự ở Option A cho *layout design chưa thông minh*. Đây là lời giải thích của tester; chưa tách được là do trình bày hay do chất lượng nội dung bản nháp — cần đối chiếu với hai phiên còn lại.
- Validation không gây khó chịu gợi ý ma sát của form **không phải** chi phí chính mà nhóm lo; chi phí đáng kể hơn có thể nằm ở thao tác dán code.
- Câu *cần có sự dung hợp của cả 3* cho thấy lựa chọn C là **tương đối** trong ba phương án được đưa ra, không phải sự hài lòng tuyệt đối.

### DECIDED — NEXT CHANGE

*Điền sau khi nhóm tổng hợp đủ ba Feedback Notes.*

Ứng viên từ phiên này, để nhóm cân nhắc khi tổng hợp:

> Giữ cơ chế của **Option C**, nhưng để hệ thống **tự quét và điền sẵn đoạn lỗi terminal**; phần mô tả và phần chọn Coach vẫn của người.

Đây là phần giao nhau giữa điều tester nói muốn (*AI chỉ tự nhận thông báo lỗi*) và điều tester khó chịu (*phải dán tay đoạn code*).

### STILL UNPROVEN

- Kết quả đến từ **một** tester; chưa biết hai phiên còn lại có cùng hướng không.
- Relevant context chỉ ghi được ở mức chung (*có gặp khó khăn khi làm Lab*), chưa neo vào một buổi cụ thể có mốc thời gian, nên chưa kiểm chứng được trải nghiệm nền của tester khớp tới đâu với case của nhóm.
- Chưa ghi nhận được danh mục tester chọn ở Option C và dấu hiệu họ dựa vào — đây là chỗ kiểm rule routing có chạy đúng không.
- Không đo được thời gian ở Option A và B nên chưa so sánh được *nhanh hơn* mà nhóm giả định.
- Chưa quan sát được phản ứng khi **AI đoán sai** — prototype dùng canned output nên không có tình huống sai.
- Chưa biết lựa chọn có đổi không khi lỗi phức tạp hơn lỗi biến môi trường, hoặc khi tester đang gấp.

---

*Mục còn ghi `chưa ghi nhận` (danh mục chọn ở Option C) đang được hỏi lại tester và sẽ bổ sung; nếu bổ sung, sẽ đánh dấu rõ là **thu thập sau phiên test** để không lẫn với quan sát tại chỗ.*
