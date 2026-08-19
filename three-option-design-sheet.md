# Three-Option Design Sheet — Day 18

**Case:** C — AI Support Radar · **Nhóm:** Hello world (Nguyễn Ngọc Chi · Nguyễn Minh Hiếu · Phạm Tuấn Anh)

Nguồn: [group/chang2.md](group/chang2.md) và [group/chang3.md](group/chang3.md).

---

## 1. Shared Context & Problem Hypothesis

Phần chung, giữ nguyên cho cả ba option:

| Thành phần | Quyết định chung cho A/B/C |
| :--- | :--- |
| **Target user** | *Primary:* Lab Coach — người triage và bắt đầu hỗ trợ. *Supporting actor:* Learner — người gửi và xác nhận yêu cầu |
| **Situation** | Learner bị kẹt (lỗi code hoặc không hiểu bài) trong buổi lab và cần trợ giúp từ Lab Coach |
| **Task** | Chuyển giao yêu cầu hỗ trợ đến đúng Lab Coach phụ trách, kèm đầy đủ bối cảnh hiện tại của learner |
| **Desired outcome** | Lab Coach nắm ngay vấn đề mà không phải hỏi đi hỏi lại; learner nhận hướng dẫn đúng chuyên môn và nhanh chóng |
| **Content / data fixture** | VLearn Lab Day 5 — Environment Setup. Chạy `npm run dev` gặp `Error: NEXT_PUBLIC_API_KEY is not defined` tại `lib/api.js:12`. Coach trực ca: Le Thi Hoa (Frontend/UI), Nguyen Duc Minh (DevOps/Môi trường) |
| **Critical interaction** | Khoảnh khắc learner yêu cầu hoặc nhận được gợi ý hỗ trợ và cung cấp bối cảnh cho Coach |

**Hypothesis Problem:** khi learner đang mắc lỗi trong buổi lab và cần chuyển yêu cầu hỗ trợ, Lab Coach gặp khó khăn trong việc xác định nhanh learner đang ở bước nào và ai nên tiếp nhận, vì yêu cầu thường thiếu hoặc lan man về bối cảnh và có thể đến nhầm coach, dẫn đến Coach phải hỏi follow-up hoặc đi tìm từng bàn trước khi bắt đầu hỗ trợ.

---

## 2. Three Solution Options — Comparison Contract

Ba hướng đại diện cho ba mức độ can thiệp của AI, lấy từ Solution Parking Lot của Day 17 và điều chỉnh theo Hypothesis Problem mới.

| Thành phần | **Option A** — User-Initiated + AI Context | **Option B** — AI-Initiated + User Confirms | **Option C** — No AI / Manual Form |
| :--- | :--- | :--- | :--- |
| **Solution mechanism** | AI Context Extractor: khi learner bấm *Yêu cầu hỗ trợ*, AI quét màn hình/terminal hiện tại và tạo bản nháp; learner tự chọn người nhận | AI Support Radar + Smart Routing: AI phát hiện lỗi lặp lại trong phiên học, phân tích tín hiệu và đề xuất Coach phù hợp trong một pop-up | Structured Support Form: learner tự chọn chủ đề, mô tả tình huống và paste lỗi; hệ thống chuyển theo rule có sẵn |
| **User làm gì** | Chủ động bấm hỗ trợ, review và sửa bản nháp, tự chọn Coach trước khi gửi | Đọc tín hiệu AI, xác nhận hoặc dismiss đề xuất | Tự phân loại, điền context và gửi form; Coach nhận yêu cầu theo route của rule |
| **AI làm gì** | Chỉ trích xuất thông tin (bài đang mở, terminal báo lỗi gì) và viết tóm tắt; không tự chọn Coach | Theo dõi tín hiệu trong phiên, phân tích lỗi và chủ động đề xuất Coach; không tự gửi khi chưa được xác nhận | Không có AI suy đoán; hệ thống chỉ áp dụng rule định tuyến theo danh mục người dùng chọn |
| **Trigger** | Learner ấn nút *Yêu cầu hỗ trợ* | AI tự phát hiện hành vi: chạy code lỗi 3 lần liên tiếp hoặc kẹt ở một slide quá 5 phút | Learner ấn nút *Yêu cầu hỗ trợ* |
| **Trade-off chính** | Giảm gánh nặng mô tả nhưng learner vẫn phải biết chọn đúng Coach; rủi ro AI tóm tắt sai hoặc thừa thông tin | Giảm thao tác và có thể route sớm hơn, nhưng rủi ro làm phiền hoặc tạo cảm giác bị theo dõi; độ chính xác chưa được chứng minh | Dễ giải thích và không có rủi ro AI đoán sai, nhưng tạo thêm ma sát và đặt gánh nặng phân loại lên learner |

### Distance check

- **A khác B vì** A chỉ khởi động sau khi learner chủ động yêu cầu, và AI chỉ tạo context — learner vẫn chọn Coach. B chủ động phát hiện tín hiệu kẹt và AI đề xuất cả Coach, learner chỉ xác nhận.
- **B khác C vì** B dùng tín hiệu hành vi và lỗi để đề xuất route, còn C không suy đoán gì cả và buộc learner tự chọn danh mục, mô tả và cung cấp bằng chứng.
- **A khác C vì** cả hai đều do learner chủ động trigger, nhưng A dùng AI để trích xuất context còn C yêu cầu learner nhập context thủ công; A vẫn để learner chọn người nhận.

### Tự kiểm — GATE 2: Meaningful options

- [x] Ba option cùng user, situation, task và desired outcome.
- [x] Khác nhau ở mechanism và cách phân chia công việc, quyền quyết định giữa user với AI — không phải khác màu, layout hay wording.
- [x] Có một option **không dùng AI** làm đối chứng để đo giá trị thật của AI ở hai option còn lại.

---

## 3. Bốn quyết định thiết kế Human-AI

Chỉ review critical interaction cần test.

**Expectation**
- Option A nói rõ hệ thống sẽ quét terminal và bài học hiện tại để tạo bản nháp. Option B nói rõ hệ thống đang theo dõi lỗi trong phiên học và sẽ gợi ý khi có tín hiệu lặp lại; pop-up cho biết tín hiệu nào đã được dùng.
- Capability và limit cần nói rõ: A chỉ tạo bản nháp, không tự chọn Coach hay tự gửi; B chỉ đưa gợi ý, không tự gửi ticket, và có thể báo nhầm nếu tín hiệu lỗi không đủ.

**Role and Agency**
- A: AI tóm tắt, user sửa và chọn Coach. B: AI phát hiện và gợi ý, user xác nhận hoặc dismiss. C: user tự cung cấp context, hệ thống chỉ route bằng rule.
- A và B là **Ask** — AI chuẩn bị bản nháp hoặc gợi ý rồi chờ quyết định. C là **Don't infer** — rule chỉ chạy sau khi user gửi đủ trường bắt buộc, không tự đoán ý định.
- Nếu AI lấy sai code hoặc định tuyến sai, user chỉ mất thêm vài giây đọc trước khi bấm hủy hoặc sửa. Lỗi dễ phát hiện vì bản nháp và tên Coach được hiển thị rõ để user duyệt.

**Evidence and Uncertainty**
- AI ghi rõ trong bản nháp hoặc pop-up là *dựa trên lỗi ở dòng số…* hoặc *dựa trên 3 lần chạy sai gần nhất*.
- Khi không chắc, dùng ngôn ngữ giảm nhẹ (*Có vẻ như bạn đang vướng…*) hoặc trạng thái fallback (*Không tìm thấy thông báo lỗi tự động, vui lòng mô tả tay*).

**Control and Recovery**
- A: preview và sửa context, chọn lại Coach trước khi gửi. B: dismiss pop-up và tắt gợi ý trong 10 phút. C: review form trước khi gửi, tạo lại nếu chọn nhầm.
- Sau khi AI sai: A sửa bản nháp hoặc hủy ticket sau khi gửi; B dismiss và gọi hỗ trợ thủ công; C báo chọn nhầm danh mục hoặc reset để tạo lại.

---

## 4. Human-AI Decision Table

| Human-AI decision | **Option A** (User-Initiated + AI Context) | **Option B** (AI-Initiated + User Confirms) | **Option C** (No AI / Manual Form) |
| :--- | :--- | :--- | :--- |
| **User làm gì? AI làm gì?** | **User:** bấm hỗ trợ, review và sửa bản nháp, tự chọn Coach.<br>**AI:** trích xuất lỗi từ terminal/bài Lab và tạo tóm tắt; không route | **AI:** theo dõi tín hiệu lỗi trong phiên, phân tích và tạo pop-up gợi ý Coach.<br>**User:** đọc bằng chứng rồi quyết định Có hoặc Không | **User:** chủ động bấm nút hỗ trợ, tự phân loại danh mục lỗi và tự viết hoặc paste lỗi vào form.<br>**Hệ thống:** chỉ áp dụng rule sau khi user gửi đủ trường bắt buộc |
| **AI Act / Ask / Don't Act? Vì sao?** | **Ask** — AI tạo bản nháp nhưng không tự gửi hay chọn người nhận; user review, chọn Coach rồi gửi | **Ask** — AI chỉ hiện pop-up hỏi *Bạn có muốn chuyên gia X giúp không?*, không tự động gửi ticket. Vì tự ý gọi Coach có thể làm phiền user đang muốn tự tìm hiểu, và làm phiền Coach khi user chưa thực sự cần | **Don't infer** — không có AI suy đoán; rule chỉ route dữ liệu user đã nhập sau khi user submit |
| **User hiểu capability/limit bằng gì?** | Dòng thông báo: *Hệ thống quét terminal để tạo bản nháp; bạn vẫn chọn Coach và gửi* | Pop-up ghi: *Đã thấy lỗi này 3 lần trong 5 phút; đây là gợi ý, không phải kết luận* | Label và placeholder hướng dẫn cách nhập; không hiển thị Coach mapping trước khi user chọn, để form không biến thành lời giải |
| **Evidence/uncertainty thể hiện thế nào?** | AI hiển thị bản nháp context ngay trên màn hình. Nếu terminal trống: *Không tìm thấy thông báo lỗi tự động. Vui lòng mô tả thêm* | AI dùng ngôn ngữ gợi ý, không khẳng định tuyệt đối: *Có vẻ như bạn đang vướng ở phần cấu hình môi trường* | Không áp dụng — không có AI dự đoán. User là người tự cung cấp bằng chứng bằng cách paste code |
| **User kiểm soát và recovery thế nào?** | **Kiểm soát:** sửa (Edit) bản nháp do AI viết, hoặc xóa hết tự viết tay (Reject).<br>**Phục hồi:** nếu gửi nhầm, có nút *Hủy yêu cầu* trong lịch sử | **Kiểm soát:** nút *Không, tôi muốn tự làm* (Dismiss) ngay trên pop-up.<br>**Phục hồi:** pop-up tắt và không xuất hiện lại trong 10 phút; user có thể gọi hỗ trợ thủ công nếu đổi ý | **Kiểm soát:** user tự review form trước khi bấm Submit.<br>**Phục hồi:** nếu định tuyến nhầm danh mục, learner có thể chat vào ticket báo *Mình chọn nhầm mục* hoặc tự đóng ticket và tạo lại |

### Tự kiểm — GATE 3: Human control

- [x] Mỗi option đã nói rõ user làm gì và AI làm gì.
- [x] Agency phù hợp với hậu quả khi sai: A và B dùng **Ask** để giảm hậu quả sai lệch bối cảnh hoặc làm phiền không đáng có; C **Don't infer** nên không có rủi ro AI đoán sai.
- [x] Mỗi option có đường kiểm soát (Edit ở A, Dismiss ở B, review form ở C) và đường phục hồi (Hủy yêu cầu, gọi thủ công, tạo lại ticket).
