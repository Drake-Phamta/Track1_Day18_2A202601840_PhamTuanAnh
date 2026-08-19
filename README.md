# Track 1 — Day 18: Multiple Prototypes & Human-AI Design

> **Mã Học Viên (MHV):** `2A202601840`
> **Họ và Tên:** Phạm Tuấn Anh
> **Tên Thư Mục Repository:** `Track1_Day18_2A202601840_PhamTuanAnh`
> **Link Prototype:** https://drake-phamta.github.io/Track1_Day18_2A202601840_PhamTuanAnh/

---

## 1. Thông Tin Cá Nhân và Nhóm

- **Mã Học Viên (MHV):** `2A202601840`
- **Họ và Tên:** Phạm Tuấn Anh
- **Tên Nhóm:** Hello world
- **Danh Sách 3 Thành Viên:**
  1. Nguyễn Ngọc Chi (MHV: `2A202602024`)
  2. Nguyễn Minh Hiếu (MHV: `2A202601154`)
  3. Phạm Tuấn Anh (MHV: `2A202601840`)
- **Case Study:** Case C — AI Support Radar · chuyển giao yêu cầu hỗ trợ có đủ bối cảnh và đúng chuyên môn trên VLearn LMS
- **Option tôi phụ trách:** **Option C — Structured Support Form (No AI)**

---

## 2. Hypothesis Problem (bản nhóm dùng trong Day 18)

> Khi learner đang mắc lỗi trong buổi lab và cần chuyển yêu cầu hỗ trợ (**situation**), **Lab Coach** (**user**) gặp khó khăn trong việc xác định nhanh learner đang ở bước nào và ai nên tiếp nhận (**job**) vì **yêu cầu thường thiếu hoặc lan man về bối cảnh và có thể đến nhầm coach** (**barrier**), dẫn đến **Coach phải hỏi follow-up hoặc đi tìm từng bàn trước khi bắt đầu hỗ trợ** (**consequence**).

**Vai trò dùng trong Day 18**
- *Primary user:* Lab Coach — người cần triage và bắt đầu hỗ trợ.
- *Supporting actor:* Learner — người cung cấp hoặc xác nhận context trước khi yêu cầu được chuyển đi.

**Evidence ban đầu hỗ trợ giả thuyết** — từ ba Practice Notes của Day 17:

| Nguồn | Điều user đã thực sự làm hoặc nói |
| :--- | :--- |
| Practice Note 1 — Hiếu (Learner) | Nhắn Discord gọi Lab Coach, chờ 3–4 phút, tốn thêm thời gian vì Coach phải *"load lại thông tin từ đầu"*; learner thấy *"nản"* |
| **Practice Note 2 — Tuấn Anh (Learner)** | Đọc note không hiểu là *"la lên"* hoặc nhắn Discord ngay; Coach tiếp cận nhưng *"không phải phần đảm nhiệm chính"* nên giải thích không thỏa đáng |
| Practice Note 3 — Chi (Lab Coach) | Phải đoán hoặc đi bộ rà soát từng bàn; câu hỏi nhận được thường *"đại hải"*, phải *"hỏi follow-up lại"* nhiều lượt |

**Điều nhóm bất ngờ:** giả định ban đầu là *instructor khó phát hiện ai cần hỗ trợ* hoặc *learner ngại hỏi*. Thực tế có learner rất chủ động — điểm gãy nằm ở **bước ngay sau đó**: quy trình tiếp nhận thiếu bối cảnh và điều phối nhầm người.

**Điều vẫn chưa được chứng minh**
- Tần suất và thời lượng trung bình của việc hỏi lại hoặc đi tìm learner chưa được đo lường.
- Chưa biết chậm trễ này có làm learner trễ tiến độ, đổi workaround hay bỏ dở bài không.
- Chưa biết learner có chấp nhận việc hệ thống đọc terminal hoặc theo dõi lỗi trong phiên học không.

Chi tiết: [group/chang1.md](group/chang1.md)

---

## 3. Three Solution Options

Ba option giữ nguyên **cùng** target user, situation, task, desired outcome và content fixture. Khác nhau ở **cơ chế và cách chia việc giữa người với AI**.

**Fixture dùng chung:** VLearn Lab Day 5 — Environment Setup. Learner chạy `npm run dev` gặp `Error: NEXT_PUBLIC_API_KEY is not defined` tại `lib/api.js:12`. Hai Coach trực ca: Le Thi Hoa (Frontend/UI) và Nguyen Duc Minh (DevOps/Môi trường).

| | **Option A** — User-Initiated + AI Context | **Option B** — AI-Initiated + User Confirms | **Option C** — No AI / Manual Form |
| :--- | :--- | :--- | :--- |
| Cơ chế | AI Context Extractor: learner bấm *Yêu cầu hỗ trợ*, AI quét màn hình/terminal và tạo bản nháp; learner tự chọn người nhận | AI Support Radar + Smart Routing: AI phát hiện lỗi lặp lại trong phiên, phân tích tín hiệu và đề xuất Coach qua pop-up | Structured Support Form: learner tự chọn danh mục, mô tả tình huống và paste lỗi; hệ thống chuyển theo rule có sẵn |
| User làm gì | Bấm hỗ trợ, review và sửa bản nháp, tự chọn Coach rồi gửi | Đọc tín hiệu AI, xác nhận hoặc dismiss | Tự phân loại, điền context và gửi form |
| AI làm gì | Chỉ trích xuất và tóm tắt; **không** route | Theo dõi tín hiệu, phân tích, đề xuất Coach; **không** tự gửi | **Không có AI suy đoán** — chỉ rule định tuyến theo danh mục user chọn |
| Trigger | Learner bấm nút | AI tự phát hiện: chạy code lỗi 3 lần liên tiếp hoặc kẹt ở một slide quá 5 phút | Learner bấm nút |
| Trade-off chính | Giảm gánh nặng mô tả nhưng learner vẫn phải biết chọn đúng Coach; rủi ro AI tóm tắt sai hoặc thừa | Giảm thao tác và route sớm hơn, nhưng rủi ro làm phiền và cảm giác bị theo dõi; độ chính xác chưa được chứng minh | Dễ giải thích, không có rủi ro AI đoán sai, nhưng thêm ma sát và đặt gánh nặng phân loại lên learner |

**Distance check**
- **A khác B vì** A chỉ khởi động sau khi learner chủ động yêu cầu và AI chỉ tạo context, learner vẫn chọn Coach; B chủ động phát hiện tín hiệu kẹt và AI đề xuất cả Coach.
- **B khác C vì** B dùng tín hiệu hành vi để đề xuất route, còn C không suy đoán và buộc learner tự chọn danh mục, mô tả và cung cấp bằng chứng.
- **A khác C vì** cả hai đều do learner trigger, nhưng A dùng AI trích xuất context còn C yêu cầu learner nhập tay; A vẫn để learner chọn người nhận.

**Prototype:** [index.html](index.html) — chọn tab A / B / C. Chi tiết: [three-option-design-sheet.md](three-option-design-sheet.md) · [prototype-link.md](prototype-link.md)

---

## 4. Đóng Góp Của Cá Nhân Trong Nhóm

*Trình bày theo bảng phân công chung/riêng của BTC. Trọng tâm của tôi xuyên suốt sáu chặng là **Option C — Structured Support Form** và **Practice Note 2**.*

| Chặng | Nhóm làm chung | **Phần tôi làm riêng** |
| :--- | :--- | :--- |
| **1 — Evidence** | Đọc 3 Practice Notes, chọn evidence, chốt Hypothesis Problem | Cung cấp và giải thích **Practice Note 2** — interview learner do tôi thực hiện ở Day 17. Diễn giải từ note này, rằng điểm nghẽn nằm ở khâu routing sai người hỗ trợ chứ không phải ở việc learner ngại hỏi, trở thành **barrier** trong Hypothesis Problem của nhóm |
| **2 — Solution Options** | Chọn A/B/C, khoá chung user, situation, task, content fixture, desired outcome | Nhận **Option C — Structured Support Form**; lập luận vì sao nhóm cần một option **không dùng AI** làm đối chứng thay vì ba option đều có AI |
| **3 — Human-AI Design** | Cùng lập Decision Table cho cả A/B/C | Đào sâu **cột Option C**: agency **Don't infer** — rule chỉ chạy sau khi user submit đủ trường bắt buộc; không hiển thị Coach mapping trước khi user chọn để form không biến thành lời giải; đường phục hồi khi learner chọn nhầm danh mục |
| **4 — Build** | Dùng chung context, fixture, visual components và chuẩn hoá flow | Build **Option C** trong prototype: danh mục lỗi, ô mô tả tình huống, ô paste code lỗi, validation trường bắt buộc, rule routing sau submit, nút reset về common context |
| **5 — Test preparation** | Chốt chung relevant context, outcome task, 5 observation focus và luật facilitation | Chuẩn bị cách ghi Feedback Note cho tester của mình, kèm **watchlist riêng cho Option C**: tester chọn danh mục dựa vào dấu hiệu nào, có paste code hay chỉ mô tả bằng lời, có thấy form dài quá không, mất bao lâu để điền xong |
| **6 — Test & synthesis** | Tổng hợp 3 Feedback Notes và chốt Group Next Change | **Test cả A/B/C với 1 tester ngoài nhóm** theo thứ tự **C → A → B** và ghi [prototype-feedback-note.md](prototype-feedback-note.md) |

**Vì sao Option C tồn tại.** C là option **không dùng AI** duy nhất, và trong Human-AI Decision Table nó là ô **Don't infer** duy nhất. Không có nó thì nhóm không có đối chứng để biết AI ở A và B thật sự thêm giá trị, hay chỉ làm giao diện nhìn hiện đại hơn. Đây cũng là option chịu áp lực ngược: nếu tester vẫn chọn C dù phải điền tay nhiều hơn, thì giả định *learner muốn AI làm hộ* của nhóm cần được xem lại.

---

## 5. Prototype Feedback & Testing Synthesis

- **Ghi chép phiên do tôi facilitate:** [prototype-feedback-note.md](prototype-feedback-note.md)
- **Tổng hợp cả nhóm:** [group-feedback-synthesis.md](group-feedback-synthesis.md)

| Mục | Nội dung |
| :--- | :--- |
| Tester phiên của tôi | **T-01** — ngoài nhóm, 19/08/2026 |
| Relevant context | **Có** |
| Thứ tự option | C → A → B |
| Option được chọn | **C — Structured Support Form** |
| Lý do tester nói ra | Được quyền chủ động mô tả lỗi |
| Breakdown chính | Chỗ do dự duy nhất của cả phiên nằm ở **bản nháp do AI soạn trong Option A**; tester nói AI *mô tả chưa được chi tiết lỗi* và mình *cần chỉnh sửa nhiều* |
| Evidence chống lại kỳ vọng của nhóm | Tester chọn option **không có AI** dù nó bắt gõ nhiều nhất. Điều họ muốn AI làm hẹp hơn những gì A và B đang làm: chỉ **tự nhận thông báo lỗi và quét đoạn code lỗi**, còn phần diễn đạt vấn đề thì giữ cho người |

**Next Change nhóm chốt:** _(chờ đủ ba Feedback Notes)_

**Ứng viên tôi sẽ đưa ra khi nhóm tổng hợp:** giữ cơ chế của C nhưng để hệ thống **tự quét và điền sẵn đoạn lỗi terminal**, giữ nguyên phần mô tả và phần chọn Coach cho người — đây là phần giao nhau giữa điều tester nói muốn và điều tester khó chịu.

**Still Unproven:** kết quả từ **một** tester; không ghi nhận được relevant context bằng lời tester và danh mục chọn ở Option C; chưa đo được thời gian ở A và B nên chưa so sánh được *nhanh hơn* mà nhóm giả định; chưa quan sát được tình huống **AI đoán sai** vì prototype dùng canned output.

---

## 6. AI Support Log

Chi tiết: [ai-support-log.md](ai-support-log.md)

- **Công cụ:** Claude Code (Claude Opus).
- **AI đã giúp ở đâu:** hệ thống hoá tài liệu Day 16–17 của tôi thành evidence snapshot mang vào Chặng 1; dựng bản chuẩn bị riêng trước buổi, sau không dùng đến vì nhóm chốt hướng khác; soạn khung kịch bản test và biểu mẫu quan sát; chuyển bộ tài liệu `chang1–6` của nhóm thành đúng cấu trúc file BTC yêu cầu cho repo cá nhân.
- **Điểm AI sai hoặc hời hợt:** _(tôi tự đánh giá — chờ điền)_
- **Can thiệp của tôi:** _(chờ điền)_

---

## Hồ sơ quá trình của nhóm

Sáu chặng do nhóm thực hiện, giữ nguyên bản: [chang1](group/chang1.md) · [chang2](group/chang2.md) · [chang3](group/chang3.md) · [chang4](group/chang4.md) · [chang5](group/chang5.md) · [chang6](group/chang6.md)
