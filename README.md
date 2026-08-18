# Track 1 - Day 18: Human-AI Design Options for AI Support Radar

> **Mã Học Viên (MHV):** `2A202601840`  
> **Họ và Tên:** Phạm Tuấn Anh  
> **Tên Thư Mục Repository:** `Track1_Day18_2A202601840_PhamTuanAnh`  
> **Link Prototype:** [https://drake-phamta.github.io/Track1_Day18_2A202601840_PhamTuanAnh/](https://drake-phamta.github.io/Track1_Day18_2A202601840_PhamTuanAnh/)

---

## 1. Thông Tin Cá Nhân và Nhóm
- **Mã Học Viên (MHV):** `2A202601840`
- **Họ và Tên:** Phạm Tuấn Anh
- **Tên Nhóm:** Hello world
- **Danh Sách 3 Thành Viên:**
  1. **Nguyễn Ngọc Chi** (MHV: `2A202602024`) 
  2. **Nguyễn Minh Hiếu** (MHV: `2A202601154`) 
  3. **Phạm Tuấn Anh** (MHV: `2A202601840`) 
- **Case Study / Đề Tài:** Case C — AI Support Radar & Smart Context Routing cho Học viên thực hành Giải thuật (VLearn LMS)

---

## 2. Hypothesis Problem (Bản nhóm dùng trong Day 18)
- **Vấn Đề Gốc (Problem Statement):** Khi học viên thực hành giải thuật bị kẹt lỗi kỹ thuật (`Segmentation Fault` do thiếu Base Case đệ quy trong bài Cây nhị phân BST Slide 8) và cần chuyển giao yêu cầu hỗ trợ, quá trình xử lý bị kéo dài và gián đoạn.
- **Giả Thuyết Trung Tâm (Core Hypothesis):** **Giảng viên/Lab Coach** gặp khó khăn trong việc xác định nhanh học viên đang ở bước nào và ai nên tiếp nhận hỗ trợ vì **yêu cầu của học viên thường thiếu/lan man về bối cảnh kỹ thuật và có thể đến nhầm Coach chuyên môn** (do học viên ngại hỏi hoặc không biết phân loại lỗi), dẫn đến **Coach phải tốn nhiều thời gian hỏi follow-up từ đầu hoặc rà soát từng bàn trước khi bắt đầu hỗ trợ**.
- **Đối Tượng Người Dùng Mục Tiêu (Target User):** 
  - *Primary User:* Lab Coach (người triage và tiếp nhận hỗ trợ đúng chuyên môn).
  - *Supporting Actor:* Learner (người thực hành bị kẹt lỗi và nhận hướng dẫn).
- **Kết Quả Mong Đợi (Expected Outcome):** Giảm thời gian chờ đợi và hỏi lại bối cảnh; đưa đúng câu hỏi tới đúng Coach chuyên môn trong vòng dưới 1 phút mà không làm đứt mạch học của học viên.

---

## 3. Three Solution Options (Mô tả ngắn & Link Prototype)

### 🎨 Option A: Standard — Manual / Rule-based Dashboard (AI Context Extractor)
- **Cơ chế (Mechanism):** Khi học viên bấm nút "Yêu cầu hỗ trợ", AI tự động quét log terminal/màn hình code để trích xuất thông báo lỗi `Segmentation Fault` tại `bst.cpp` (Slide 8) và soạn sẵn draft ticket. Học viên tự kiểm tra, chỉnh sửa bối cảnh và tự chọn Coach từ danh sách trước khi gửi.
- **Role / Trigger:** User-Initiated (Học viên tự bấm nút hỗ trợ) | Chế độ AI: Ask/Assist (AI chỉ gợi ý draft context, học viên duyệt và tự chọn Coach).
- **Prototype Link:** [Option A Live Prototype](https://drake-phamta.github.io/Track1_Day18_2A202601840_PhamTuanAnh/) *(Chọn Tab Option A trên Header)*

### 🎨 Option B: Standard++ — Collaborative AI Co-pilot Support (AI Support Radar)
- **Cơ chế (Mechanism):** AI âm thầm phân tích telemetry phiên học (phát hiện học viên chạy code crash `Segmentation Fault` 3 lần liên tiếp hoặc dừng ở Slide 8 > 14 phút), chẩn đoán lỗ hổng đệ quy và đưa ra pop-up gợi ý đúng Coach B (DevOps/Giải thuật C++) kèm bối cảnh soạn sẵn để học viên duyệt 1-click.
- **Role / Trigger:** AI-Initiated (AI Radar tự kích hoạt khi phát hiện tín hiệu bị kẹt) | Chế độ AI: Ask/Suggest (AI đề xuất bối cảnh và Coach, chờ học viên xác nhận hoặc từ chối).
- **Prototype Link:** [Option B Live Prototype](https://drake-phamta.github.io/Track1_Day18_2A202601840_PhamTuanAnh/) *(Chọn Tab Option B trên Header)*

### 🎨 Option C: Wild — Peer Micro-Match (Kết nối bạn học tức thì)
- **Cơ chế (Mechanism):** Hệ thống AI đóng vai trò môi giới real-time, tự động ghép nối ẩn danh học viên đang bị kẹt lỗi BST với một bạn học cùng lớp vừa giải bài xuất sắc. Hệ thống mở cửa sổ Mini-Chat 3 phút để hai bạn học tự hỗ trợ gỡ lỗi đệ quy mà không cần chờ Coach.
- **Role / Trigger:** AI-Initiated / Event-Driven (Tự động kích hoạt khi dừng kẹt lỗi) | Chế độ AI: Act with Confirmation (AI mở kết nối ghép đôi ngay khi cả 2 học viên bấm đồng ý).
- **Prototype Link:** [Option C Live Prototype](https://drake-phamta.github.io/Track1_Day18_2A202601840_PhamTuanAnh/) *(Chọn Tab Option C trên Header)*

> 📌 Chi tiết Bảng So sánh 3 Options & Human-AI Decision Table: Xem file [three-option-design-sheet.md](three-option-design-sheet.md)

---

## 4. Đóng Góp Của Cá Nhân Trong Nhóm
*Chi tiết phân công nhiệm vụ và vai trò của học viên **Phạm Tuấn Anh** (MHV: `2A202601840`) trong dự án nhóm:*

- [x] **Phụ trách Solution Option C — Peer Micro-Match (Wild):** Thiết kế cơ chế ghép nối ngang hàng thay cho luồng ticket truyền thống tới Coach. Quy định chế độ **Act with Confirmation** với opt-in hai phía — học viên bị kẹt chấp nhận match, bạn học được gợi ý giữ quyền Opt-in/Opt-out — để tốc độ ghép đôi không đánh đổi bằng quyền tự quyết của cả hai người.
- [x] **Xây dựng luồng tương tác Option C trong [index.html](index.html):**
  - Dải trạng thái *"AI Co-learning Peer Match Active"* ở khung học viên, báo cho người dùng biết radar ghép đôi đang bật trước khi nó hành động.
  - Widget nổi góc dưới bên phải đề xuất kết nối với bạn Trần Minh — bạn học vừa pass bài BST Slide 8.
  - Luồng `openPeerChatC()` mở phiên **chat ẩn danh 3 phút**, kèm hàng đợi tin nhắn, phản hồi của peer và bộ đếm tự đóng phiên khi hết giờ.
  - **Dashboard Giám Sát Học Nhóm Ngang Hàng (Peer Learning Monitor)** ở vai Giảng viên, để Coach vẫn nhìn được lớp đang tự hỗ trợ nhau tới đâu.
- [x] **Điền cột Option C trong Human-AI Decision Table** ([three-option-design-sheet.md](three-option-design-sheet.md)): mental model *Social Peer Matcher*; phân chia việc giữa Algorithmic Matcher và hai học viên; quyền Opt-in/Opt-out; và đường phục hồi **Escalate to Coach** khi bạn học giải thích sai hoặc không phản hồi.
- [x] **Góp luận điểm Distance Check:** chỉ ra *B khác C* ở chỗ B giữ luồng **Expert-Student Support** còn C bứt sang **Peer-to-Peer Micro-Matching** không qua ticket của Coach; và *A khác C* ở chỗ A chuẩn hoá công cụ cá nhân còn C xã hội hoá việc gỡ lỗi.
- [x] **Mang evidence Day 17 vào Hypothesis Problem của nhóm:** vế *"yêu cầu có thể đến nhầm Coach chuyên môn"* xuất phát từ interview learner (L-01) do tôi thực hiện ở Day 17 — nguyên văn: *"Có một vài lần mình raise lên rồi mình hỏi, nhưng mà các anh ấy… phần đó không phải phần đảm nhiệm chính của các anh ấy. Các anh ấy cũng chưa trả lời cho mình thỏa đáng."*
- [x] **Facilitate một phiên Usability Testing** với người ngoài nhóm và ghi [prototype-feedback-note.md](prototype-feedback-note.md).

---

## 5. Prototype Feedback & Testing Synthesis

- **Ghi chép quan sát phiên do tôi facilitate:** [prototype-feedback-note.md](prototype-feedback-note.md)
- **Báo cáo tổng hợp phản hồi cả nhóm:** [group-feedback-synthesis.md](group-feedback-synthesis.md)

| Mục | Nội dung |
| :--- | :--- |
| Tester phiên của tôi | Bách (ngoài nhóm) |
| Thứ tự dùng | C → A → B *(đảo thứ tự giữa ba phiên để option cuối không được lợi vì tester đã quen bối cảnh)* |
| Option được chọn | _(chờ kết quả phiên test)_ |
| Breakdown đáng chú ý nhất | _(chờ kết quả phiên test)_ |
| Evidence chống lại kỳ vọng của nhóm | _(chờ kết quả phiên test)_ |

**Next Change nhóm chốt:** _(chờ Group Feedback Synthesis sau khi đủ ba Feedback Notes)_

**Evidence dẫn tới quyết định đó:** _(chờ)_

**Still Unproven — điều chưa thể kết luận từ ba người:**
- Phản ứng dài hạn với cơ chế ghép đôi khi số học viên "vừa pass bài" trong lớp biến động — một phiên test không đo được.
- Chất lượng giải thích của peer so với Coach: prototype dùng canned output nên chưa kiểm được trường hợp bạn học giải thích sai.
- Mức độ e ngại khi lộ code cho bạn cùng lớp ở lớp học thật, nơi hai người biết nhau chứ không ẩn danh hoàn toàn.

---

## 6. AI Support Log & Human-in-the-Loop Summary

> Chi tiết đầy đủ tại [ai-support-log.md](ai-support-log.md).

- **Công cụ AI đã dùng:** Claude Code (Claude Opus).
- **AI đã giúp ở đâu:** đọc lại và hệ thống hoá tài liệu Day 16–17 của tôi thành evidence snapshot mang vào Chặng 1; dựng một bản chuẩn bị riêng trước buổi (khung ba option theo hai trục *ai khởi xướng / ai viết ngữ cảnh* kèm prototype HTML) — **bản này cuối cùng không dùng** vì nhóm chốt hướng khác; hỗ trợ chuyển repo fork của nhóm thành bài nộp cá nhân; soạn khung kịch bản test và biểu mẫu quan sát.
- **Điểm AI sai / hời hợt:** _(chờ tôi tự đánh giá sau khi hoàn tất bài)_
- **Can thiệp của tôi:** _(chờ)_
