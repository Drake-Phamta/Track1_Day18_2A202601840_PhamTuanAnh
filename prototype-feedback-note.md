# Prototype Feedback Note — phiên do tôi facilitate

> **Người facilitate:** Phạm Tuấn Anh (MHV: `2A202601840`)
> **Option tôi phụ trách:** Option C — Structured Support Form (No AI)
> **Vai trong test matrix nhóm:** Tester 3 · thứ tự **C → A → B**

Form theo [group/chang5.md](group/chang5.md) và [group/chang6.md](group/chang6.md).
Phiếu ghi nhanh dùng trong lúc chạy phiên: [prep/phieu-ghi-test.md](prep/phieu-ghi-test.md) · [prep/ghi-test.html](prep/ghi-test.html). Chỉ ghi hành vi và lời nói quan sát được; phần diễn giải để riêng ở mục INTERPRETED.

---

## 1. Thông tin phiên test

| Mục                                        | Nội dung                      |
| :------------------------------------------ | :----------------------------- |
| Người test                                | **T-01** — ngoài nhóm |
| Ngày / giờ                                | 19/08/2026, 9:33               |
| Thời lượng                               |                                |
| Tester có relevant context                 | **Có**                  |
| Relevant context ngắn — bằng lời tester | _không ghi nhận_           |
| Thứ tự option                             | **C → A → B**          |
| Có can thiệp kỹ thuật không            | _không ghi nhận_           |
| Đã xin phép ghi chú                     | **Có**                  |

**Câu hỏi relevant context** — hỏi trong tối đa 2 phút, không giới thiệu trước A/B/C:

> Gần đây bạn có từng bị kẹt khi làm bài lab hoặc gặp lỗi code nhưng khi nhờ Coach hỗ trợ lại phải giải thích lại bối cảnh, hoặc gặp nhầm người hỗ trợ, không?

---

## 2. Common context dùng cho cả ba option

- Learner đang học **VLearn Lab Day 5 — Environment Setup**, ở bước cấu hình Environment Variable.
- Chạy `npm run dev`, terminal hiển thị `Error: NEXT_PUBLIC_API_KEY is not defined` tại `lib/api.js:12`.
- Hai Coach trực ca: **Le Thi Hoa** — Frontend/UI · **Nguyen Duc Minh** — DevOps/Môi trường.

**Outcome task — đọc nguyên văn cho từng option:**

> Trong tình huống này, hãy dùng phương án hiện tại để gửi một yêu cầu hỗ trợ sao cho Coach phù hợp có thể hiểu bạn đang gặp lỗi gì mà không phải hỏi lại từ đầu. Nếu phương án đưa ra một gợi ý hoặc yêu cầu bạn xác nhận, hãy quyết định như bạn sẽ làm ngoài đời.

---

## 3. Quan sát theo từng option

| Observation                                  | **Option C** (Manual Form)                                | **Option A** (AI Context)                                                                               | **Option B** (AI Routing) |
| :------------------------------------------- | :-------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------ | :------------------------------ |
| **First action**                       | Bấm vào*Yêu cầu hỗ trợ*                                 | Vẫn bấm vào*Yêu cầu hỗ trợ*                                                                          | Bấm*Có, kết nối ngay*     |
| **Chỗ dừng, do dự hoặc hiểu sai** | Không có sự do dự                                           | **Có do dự ở phần mô tả do AI soạn**; tester nói lý do là *layout design chưa thông minh* | Không do dự                   |
| **Evidence được đọc hay bỏ qua** | Có đọc lỗi nhưng chưa tự fix được nên cần Lab Coach | Có đọc lỗi, đọc lý do, và chọn tên Lab Coach                                                        | Đọc hết                      |
| **Cách lấy lại control**            | Có tìm thấy                                                  | Vẫn dễ dàng tìm thấy                                                                                     | Có tìm thấy                  |

|                                                               |                                                                                                                |
| :------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------- |
| **Option được chọn**                                | **C**                                                                                                    |
| **Lý do tester nói ra**                               | Được quyền chủ động mô tả lỗi                                                                        |
| **Trade-off tester nói ra**                            | AI có gợi ý, tiện hơn và nhanh hơn, nhưng chưa thể hiện rõ được nhu cầu mong muốn của tester |
| **Muốn tự làm phần nào, giao AI phần nào**       | Chỉ muốn AI tự nhận các thông báo lỗi; phần mô tả chi tiết tester muốn tự đảm nhiệm           |
| **Điều chưa thoải mái ở phương án đã chọn** | Đoạn paste code lỗi — muốn AI tự động quét thay vì phải dán tay                                    |

### Evidence chống lại kỳ vọng của nhóm

*Rút từ chính các quan sát ghi được trong phiên này — cần người facilitate xác nhận lại.*

Nhóm đi vào Day 18 với giả định ngầm rằng **AI trích xuất và soạn context là chỗ tạo giá trị**, nên A và B đều xây quanh việc AI viết hộ phần mô tả. Phiên này cho tín hiệu ngược ở ba chỗ:

1. Tester **chọn C** — option **không có AI** — dù nó bắt gõ nhiều nhất trong ba phương án.
2. Chỗ do dự duy nhất của cả phiên nằm ở **phần mô tả do AI soạn của Option A**, không phải ở form thủ công của C.
3. Tester nói thẳng bản nháp AI *chưa được chi tiết* và **cần chỉnh sửa nhiều** — tức phần AI làm hộ không tiết kiệm được công như thiết kế kỳ vọng.

Điều tester muốn AI làm lại **hẹp hơn** những gì A và B đang làm: chỉ **tự nhận thông báo lỗi và quét đoạn code lỗi**, còn phần diễn đạt vấn đề thì giữ cho người.

---

## 4. Watchlist riêng cho Option C

*Đặt trước khi test, dựa trên annotation Option C trong [group/chang4.md](group/chang4.md). Không đọc cho tester nghe.*

| Điều cần quan sát                                          | Ghi nhận                                                                                         |
| :------------------------------------------------------------- | :------------------------------------------------------------------------------------------------ |
| Tester chọn danh mục nào, dựa vào dấu hiệu gì          | _không ghi nhận_                                                                              |
| Có paste code lỗi không, hay chỉ mô tả bằng lời        | **Có paste lỗi**                                                                          |
| Có thấy form dài hoặc rắc rối không                     | Vừa đủ                                                                                         |
| Mất bao lâu để điền xong form                            | Khoảng**1 phút**                                                                          |
| Phản ứng khi validation chặn vì thiếu trường bắt buộc | Không thấy phiền — tester cho rằng đó là những trường cần thiết để Lab Coach hiểu |

---

## 5. Trích dẫn nguyên văn

> "Ban đầu tôi thích hơn C, nhưng sau khi trải nghiệm kỹ 3 option thì tôi cảm giác C vẫn chưa đủ, maybe cần có sự dung hợp của cả 3."

> "Tôi thấy AI mô tả chưa được chi tiết lỗi, tôi cần chỉnh sửa nhiều."

---

## 6. Tách bốn lớp

### OBSERVED

*Tester đã làm hoặc nói gì. Chỉ hành vi và lời nói.*

- Ở cả Option C và Option A, tester đều mở luồng bằng nút **Yêu cầu hỗ trợ**. Ở Option B, tester bấm **Có, kết nối ngay**.
- Option C: không do dự chỗ nào; đọc lỗi terminal, paste đoạn lỗi vào form, điền xong trong khoảng 1 phút; đánh giá độ dài form là *vừa đủ*; khi validation chặn thì không thấy phiền, cho rằng các trường đó là cần thiết để Coach hiểu.
- Option A: **do dự ở phần mô tả do AI soạn**; có đọc lỗi, đọc lý do và chọn tên Lab Coach; nói rằng AI *mô tả chưa được chi tiết lỗi* và mình *cần chỉnh sửa nhiều*.
- Option B: không do dự, đọc hết nội dung pop-up.
- Cả ba option: tester **tìm thấy** đường sửa hoặc lấy lại control; riêng Option A ghi nhận là *dễ dàng* tìm thấy.
- Chọn **Option C**, lý do là *được quyền chủ động mô tả lỗi*.
- Nói muốn AI **chỉ tự nhận các thông báo lỗi**, còn phần mô tả chi tiết thì tự đảm nhiệm.
- Điều còn chưa thoải mái ở chính option đã chọn: **phải dán tay đoạn code lỗi**, muốn AI tự quét.
- Sau khi dùng cả ba, nói *C vẫn chưa đủ* và *maybe cần có sự dung hợp của cả 3*.

### INTERPRETED

*Đây là hypothesis của tôi, chưa phải kết luận.*

- Tester có thể đang phân biệt hai việc mà cả ba option đang gộp làm một: **thu thập bằng chứng lỗi** (máy làm tốt hơn người) và **diễn đạt vấn đề** (người muốn tự giữ). Việc chọn C nhưng vẫn khó chịu vì phải dán code tay khớp với cách đọc này.
- Do dự duy nhất rơi vào bản nháp của Option A, kèm nhận xét *cần chỉnh sửa nhiều*, gợi ý rằng AI soạn hộ mô tả có thể **không giảm công mà chỉ dời công** — từ gõ sang đọc và sửa. Nếu đúng thì lợi thế *nhanh hơn, tiện hơn* của A và B nhỏ hơn nhóm giả định.
- Tester quy do dự ở Option A cho *layout design chưa thông minh*. Đây là lời giải thích của tester, chưa tách được là do trình bày hay do chất lượng nội dung bản nháp — cần quan sát thêm ở hai phiên còn lại.
- Việc validation không gây khó chịu gợi ý rằng ma sát của form **không phải** là chi phí chính mà nhóm lo; chi phí đáng kể hơn có thể nằm ở thao tác dán code.
- Câu *cần có sự dung hợp của cả 3* cho thấy lựa chọn C là **tương đối** trong ba phương án được đưa ra, không phải sự hài lòng tuyệt đối.

### DECIDED — NEXT CHANGE

*Điền sau khi nhóm tổng hợp đủ ba Feedback Notes.*

Chưa chốt — mới có một trong ba Feedback Note. Ứng viên tôi sẽ đưa ra khi nhóm tổng hợp:

- Giữ cơ chế của **C** nhưng cắt bớt đúng một việc: để hệ thống **tự quét và điền sẵn đoạn lỗi terminal**, giữ nguyên phần mô tả và phần chọn Coach cho người. Đây là phần giao nhau giữa điều tester nói muốn và điều tester khó chịu.

### STILL UNPROVEN

- Kết quả này đến từ **một** tester. Chưa biết hai phiên còn lại có cùng hướng hay không.
- **Không ghi nhận được relevant context bằng lời tester**, nên chưa kiểm chứng được trải nghiệm nền của họ khớp tới đâu với case của nhóm.
- **Không ghi nhận được danh mục tester chọn ở Option C và dấu hiệu họ dựa vào** — đây đúng là chỗ kiểm tra xem rule routing có chạy đúng không, và nó vẫn còn trống.
- Không đo được thời gian ở Option A và B nên chưa so sánh được *nhanh hơn* mà nhóm giả định.
- Chưa biết tester phản ứng thế nào khi **AI đoán sai** — prototype dùng canned output nên không có tình huống sai để quan sát.
- Chưa biết lựa chọn có đổi không khi lỗi phức tạp hơn lỗi biến môi trường, hoặc khi tester đang gấp.

---

## 7. Tự đánh giá kỹ năng facilitate

Tôi không vi phạm luật facilitation trong phiên này.

*Chỗ cần làm tốt hơn ở phiên sau:* ba mục bị bỏ trống — thời lượng phiên, câu trả lời relevant context bằng lời tester, và danh mục tester chọn ở Option C — đều là dữ liệu phải ghi ngay lúc chạy, không hồi cứu được. Riêng danh mục ở Option C là watchlist do chính tôi đặt ra trước phiên mà lại quên ghi.

---

## Luật facilitation đã áp dụng

1. Tester tự điều khiển prototype.
2. Dùng đúng một task cho cả A/B/C.
3. Không narrate hoặc giải thích icon, AI, Coach mapping hay bước tiếp theo.
4. Không lấp im lặng quá sớm.
5. Không hỏi *Bạn có thích không?* hoặc *Bạn thấy option nào tốt hơn?* trước khi ghi nhận hành vi.
6. Tester hỏi cách hoạt động thì hỏi lại: *Theo bạn, nó nên hoạt động như thế nào?*
7. Chỉ can thiệp khi prototype lỗi kỹ thuật; ghi rõ lần can thiệp vào mục 1.
8. Không sửa câu trả lời của tester và không nói đáp án đúng.

Ba câu cứu hộ: *Bạn cứ nói to suy nghĩ của mình nhé.* · *Bạn sẽ làm gì tiếp theo?* · *Theo bạn, nó nên hoạt động như thế nào?*
