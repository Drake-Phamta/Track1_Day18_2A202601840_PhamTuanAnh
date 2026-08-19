# Chặng 4 — Ba Micro-prototype

**File prototype:** `chang4.html` — Mở bằng trình duyệt, chọn tab A / B / C để chuyển giữa các option.

---

## Common Context (dùng chung cho A/B/C)

| Thành phần | Nội dung cố định |
|---|---|
| **Target user** | Learner (sinh viên) đang học bài Lab thực hành trên VLearn |
| **Situation** | Learner đang ở màn hình bài Lab Day 5 — Environment Setup, chạy lệnh `npm run dev` bị lỗi |
| **Lỗi cố định (Content Fixture)** | `Error: NEXT_PUBLIC_API_KEY is not defined` tại dòng 12 của `lib/api.js` |
| **Task** | Gửi yêu cầu hỗ trợ kèm đủ bối cảnh để Coach hiểu ngay và hỗ trợ được |
| **Desired outcome** | Learner nhận được hướng dẫn từ đúng Coach chuyên môn (Coach B — DevOps) mà không phải giải thích lại từ đầu |
| **Danh sách Coach trực ca** | Coach A — Le Thi Hoa (Frontend/UI), Coach B — Nguyen Duc Minh (DevOps/Môi trường) |

---

## Build order

| Phút | Việc cần làm |
|---|---|
| **0–10** | Chốt common context, task và content fixture dùng chung cho A/B/C. |
| **10–55** | Mỗi thành viên build một option bằng shared components, giữ nguyên context và visual style chung. |
| **55–65** | Bổ sung control/recovery và evidence/uncertainty cần thiết cho critical interaction. |
| **65–75** | Mỗi thành viên tự test option do người khác build, kiểm tra link, thao tác và reset. |
| **75–80** | Chuẩn hóa tab A/B/C, nội dung task, nút reset và đường quay về common context. |

## Prototype scope

Mỗi option chỉ tập trung vào flow:

```text
COMMON CONTEXT
↓
CRITICAL INTERACTION
↓
RESULT / USER DECISION
```

Prototype dùng chung khoảng 70% context, content fixture và visual components. Điểm khác biệt chính chỉ nằm ở critical interaction:

- **A:** Learner chủ động yêu cầu, AI tạo bản nháp, Learner sửa và chọn Coach.
- **B:** AI chủ động phát hiện tín hiệu lỗi, đề xuất Coach, Learner xác nhận hoặc dismiss.
- **C:** Learner tự điền context, hệ thống chuyển theo rule, không suy đoán bằng AI.

---
## Prototype Annotation (nội bộ — không đọc cho tester)

### OPTION A — AI Context Extractor
```
OPTION A
We expect the tester to:
  Nhấn "Cần hỗ trợ", đọc/sửa bản nháp AI, tự chọn Coach và bấm "Gửi yêu cầu".

Watch for:
  - Tester có đọc kỹ bản nháp trước khi gửi không?
  - Tester có chỉnh sửa gì trong bản nháp không? Chỉnh cái gì?
  - Tester có dừng lại vì không hiểu bản nháp nói gì không?
  - Tester có tin AI lấy đúng thông tin không?
  - Tester có chọn đúng Coach từ lỗi đang thấy không? Vì sao?

Do not explain:
  Không giải thích AI lấy dữ liệu từ đâu. Không nói "AI sẽ tự động điền".
```

### OPTION B — AI-Initiated Smart Routing
```
OPTION B
We expect the tester to:
  Nhận pop-up gợi ý từ AI, đọc tín hiệu đã dùng và bấm "Có" hoặc "Không, tôi muốn tự làm".

Watch for:
  - Tester có đọc lý do AI gợi ý không hay chỉ bấm Có ngay?
  - Tester có bấm "Không" không? Vì sao?
  - Tester có cảm thấy bị làm phiền hoặc bị theo dõi không?
  - Tester có trust tên Coach được gợi ý không?

Do not explain:
  Không giải thích thêm ngoài thông tin đã hiển thị trong pop-up.
```

### OPTION C — Manual Structured Form
```
OPTION C
We expect the tester to:
  Bấm "Yêu cầu hỗ trợ", tự chọn danh mục, điền mô tả và paste code lỗi, rồi bấm Gửi.

Watch for:
  - Tester có chọn danh mục nào và dựa vào dấu hiệu nào?
  - Tester có paste code lỗi không hay chỉ mô tả bằng lời?
  - Tester có cảm thấy form quá dài/rắc rối không?
  - Tester mất bao lâu để điền xong form?

Do not explain:
  Không gợi ý tester nên chọn danh mục nào. Không giải thích mỗi danh mục dành cho ai.
```

---

## Tự kiểm GATE 4
- [x] Ba options cùng common context và task.
- [x] Mỗi option hiển thị rõ điểm user lấy lại control (Edit/Chọn hoặc đổi Coach/Dismiss/Sửa form).
- [x] Có nút reset về màn hình context ban đầu trên mỗi option.
- [x] Không cần facilitator giải thích để tester biết cần làm gì tiếp theo.
- [x] Dùng canned AI output (bản nháp cố định, không dùng API thật).

## Khai báo sử dụng AI

AI được dùng để gợi ý cơ chế tương tác, tạo canned output/data fixture, hỗ trợ viết prototype và rà soát tính nhất quán giữa các Gate. Các quote, observation và feedback của tester phải được ghi từ người thật sau buổi test; prototype không dùng model/API thật.