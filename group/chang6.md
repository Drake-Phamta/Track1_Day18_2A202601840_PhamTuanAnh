# Chặng 6 — Test với ba người

## Mục tiêu

Nhóm mang cùng một context, task và desired outcome cho cả A/B/C. Mỗi thành viên test cả ba option với một tester khác nhóm và ghi một Feedback Note độc lập.

Đây là test interaction ban đầu, không phải bài kiểm tra tester và chưa đủ để tuyên bố solution đã được validated.

## 1. Trách nhiệm cá nhân

| Người phụ trách | Tester | Phạm vi bắt buộc | Feedback Note |
|---|---|---|---|
| Thành viên 1 | Tester 1 — ngoài nhóm | Dùng cả A/B/C | Feedback 1 |
| Thành viên 2 | Tester 2 — ngoài nhóm | Dùng cả A/B/C | Feedback 2 |
| Thành viên 3 | Tester 3 — ngoài nhóm | Dùng cả A/B/C | Feedback 3 |

Tester nên có relevant context với case: từng làm lab, gặp lỗi code, hoặc từng nhờ Coach hỗ trợ. Nếu tester chưa từng gặp tình huống tương tự, vẫn ghi nhận interaction breakdown nhưng không đưa ra value claim mạnh.

Người build Option A vẫn phải test cả A/B/C; tương tự người build Option B và C.

## 2. Common test setup

### Relevant context

Hỏi ngắn, không giới thiệu trước cơ chế A/B/C:

> Gần đây bạn có từng bị kẹt khi làm bài lab hoặc gặp lỗi code nhưng khi nhờ Coach hỗ trợ lại phải giải thích lại bối cảnh, hoặc gặp nhầm người hỗ trợ, không?

Ghi lại:

- Tester có relevant context: Có / Không / Một phần.
- Mô tả context ngắn của tester: `[điền sau khi hỏi]`.

### Common fixture

- VLearn Lab Day 5 — Environment Setup.
- Learner đang ở bước cấu hình Environment Variable.
- Chạy `npm run dev` gặp lỗi:

  `Error: NEXT_PUBLIC_API_KEY is not defined`

  tại `lib/api.js:12`.
- Coach A — Le Thi Hoa, Frontend/UI.
- Coach B — Nguyen Duc Minh, DevOps/Môi trường.

### Outcome task

Đọc cùng một task cho cả ba option:

> Trong tình huống này, hãy dùng phương án hiện tại để gửi một yêu cầu hỗ trợ sao cho Coach phù hợp có thể hiểu bạn đang gặp lỗi gì mà không phải hỏi lại từ đầu. Nếu phương án đưa ra một gợi ý hoặc yêu cầu bạn xác nhận, hãy quyết định như bạn sẽ làm ngoài đời.

Sau mỗi option, reset về common context trước khi chuyển sang option tiếp theo.

Thứ tự test:

- Tester 1: A → B → C
- Tester 2: B → C → A
- Tester 3: C → A → B

Nếu không thể counterbalance, ghi rõ thứ tự thực tế và lý do.

## 3. Timeline 20 phút

| Thời gian | Hoạt động |
|---|---|
| **0–2 phút** | Make comfortable và hỏi relevant context ngắn. |
| **2–14 phút** | Tester dùng A/B/C, khoảng 4 phút mỗi option. |
| **14–18 phút** | So sánh option, lý do và trade-off. |
| **18–20 phút** | Hoàn thành Feedback Note cá nhân. |

### Opening

> Chúng mình đang thử ba cách thiết kế, không kiểm tra bạn. Không có câu trả lời đúng hoặc sai. Bạn hãy tự thao tác và nói to điều mình đang nghĩ; mình sẽ cố gắng không hướng dẫn.

### Compare — chỉ hỏi sau khi tester đã dùng cả A/B/C

- “Trong tình huống này, bạn chọn A, B hay C? Vì sao?”
- “Bạn muốn tự làm phần nào và giao cho AI phần nào?”
- “Điều gì ở phương án đã chọn khiến bạn chưa thoải mái?”

Không hỏi “Bạn có thích không?” và không gợi ý option nào tốt hơn.

## 4. Facilitation rules

1. Tester tự điều khiển prototype.
2. Dùng cùng task cho cả A/B/C.
3. Không narrate hoặc giải thích icon, AI, Coach mapping hay bước tiếp theo.
4. Không lấp im lặng quá sớm.
5. Nếu tester hỏi cách hoạt động, hỏi lại: “Theo bạn, nó nên hoạt động như thế nào?”
6. Chỉ can thiệp khi prototype bị lỗi kỹ thuật hoặc tester không thể tiếp tục; ghi rõ lần can thiệp.
7. Không tự tạo quote, observation hoặc feedback mà tester chưa nói/làm.

## 5. Prototype Feedback Note — Feedback 1

### Thông tin phiên test

- Người test: `[tên/mã tester]`
- Người facilitate: `[tên thành viên]`
- Ngày/giờ: `[điền]`
- Tester có relevant context: Có / Không / Một phần
- Relevant context ngắn: `[điền bằng lời tester hoặc mô tả trung thực]`
- Thứ tự option: `[A → B → C / B → C → A / C → A → B]`
- Có can thiệp kỹ thuật không: Có / Không
- Nếu có, can thiệp gì: `[điền]`

| Observation | Note — chỉ ghi hành vi/lời nói quan sát được |
|---|---|
| First action | `[điền]` |
| Chỗ dừng, do dự hoặc hiểu sai | `[điền]` |
| Evidence được đọc hay bỏ qua | `[điền]` |
| Cách tester sửa hoặc lấy lại control | `[điền]` |
| Option được chọn | A / B / C |
| Lý do và trade-off tester nói ra | `[điền]` |
| Evidence chống lại kỳ vọng của nhóm | `[điền]` |

### Tách bốn lớp

#### OBSERVED

Tester đã làm hoặc nói gì?

`[điền observation cụ thể, không thêm diễn giải]`

#### INTERPRETED

Nhóm nghĩ điều đó có thể có nghĩa gì?

`[điền diễn giải và ghi rõ đây là hypothesis]`

#### DECIDED — NEXT CHANGE

Nhóm sẽ sửa, kết hợp hoặc test gì tiếp?

`[điền sau khi nhóm tổng hợp đủ ba Feedback Notes]`

#### STILL UNPROVEN

Điều gì chưa thể kết luận từ một người?

`[điền]`

## 6. Prototype Feedback Note — Feedback 2

Sao chép nguyên mẫu Feedback 1 và thay thông tin phiên:

- Người test: `[tên/mã tester]`
- Người facilitate: `[tên thành viên]`
- Relevant context: `[Có / Không / Một phần + mô tả]`
- Thứ tự option: `[điền]`
- First action: `[điền]`
- Chỗ dừng, do dự hoặc hiểu sai: `[điền]`
- Evidence đọc/bỏ qua: `[điền]`
- Cách lấy lại control: `[điền]`
- Option được chọn: `A / B / C`
- Lý do và trade-off: `[điền]`
- Evidence chống lại kỳ vọng: `[điền]`
- OBSERVED: `[điền]`
- INTERPRETED: `[điền]`
- DECIDED — NEXT CHANGE: `[điền sau synthesis]`
- STILL UNPROVEN: `[điền]`

## 7. Prototype Feedback Note — Feedback 3

Sao chép nguyên mẫu Feedback 1 và thay thông tin phiên:

- Người test: `[tên/mã tester]`
- Người facilitate: `[tên thành viên]`
- Relevant context: `[Có / Không / Một phần + mô tả]`
- Thứ tự option: `[điền]`
- First action: `[điền]`
- Chỗ dừng, do dự hoặc hiểu sai: `[điền]`
- Evidence đọc/bỏ qua: `[điền]`
- Cách lấy lại control: `[điền]`
- Option được chọn: `A / B / C`
- Lý do và trade-off: `[điền]`
- Evidence chống lại kỳ vọng: `[điền]`
- OBSERVED: `[điền]`
- INTERPRETED: `[điền]`
- DECIDED — NEXT CHANGE: `[điền sau synthesis]`
- STILL UNPROVEN: `[điền]`

## 8. Group Feedback Synthesis

Chỉ điền phần này sau khi đã có đủ ba Feedback Notes độc lập.

| Nội dung | Feedback 1 | Feedback 2 | Feedback 3 | Pattern hoặc khác biệt |
|---|---|---|---|---|
| First action | `[điền]` | `[điền]` | `[điền]` | `[điền]` |
| Breakdown chính | `[điền]` | `[điền]` | `[điền]` | `[điền]` |
| Evidence được đọc/bỏ qua | `[điền]` | `[điền]` | `[điền]` | `[điền]` |
| Cách lấy lại control | `[điền]` | `[điền]` | `[điền]` | `[điền]` |
| Option được chọn | `[điền]` | `[điền]` | `[điền]` | `[điền]` |
| Lý do và trade-off | `[điền]` | `[điền]` | `[điền]` | `[điền]` |

### Một Next Change nhóm chốt

`[điền một thay đổi duy nhất: giữ và sửa một option / kết hợp hai option / bỏ một option / sửa cả ba rồi test tiếp]`

### Evidence dẫn tới quyết định

`[điền các observation cụ thể từ Feedback 1–3]`

### Still Unproven sau ba feedback

`[điền điều chưa thể kết luận về value, mức độ nghiêm trọng, độ chính xác routing, sự chấp nhận theo dõi dữ liệu hoặc hành vi ngoài prototype]`

## 9. Handover cho iteration tiếp theo

- Option/cơ chế được giữ lại: `[điền]`
- Interaction cần sửa: `[điền]`
- Fixture/context cần giữ nguyên khi test lại: `[điền]`
- Tester/context cần tuyển tiếp: `[điền]`
- Observation cần kiểm tra lại: `[điền]`

## Tự kiểm — GATE 5: Learning, not praise

- [ ] Có ba Feedback Notes độc lập từ ba tester ngoài nhóm.
- [ ] Mỗi tester đã dùng cả A/B/C với cùng context, task và desired outcome.
- [ ] Mỗi note tách rõ OBSERVED và INTERPRETED.
- [ ] Nhóm nêu được pattern hoặc khác biệt giữa ba người.
- [ ] Nhóm chốt đúng một Next Change.
- [ ] Nhóm ghi một điều STILL UNPROVEN.
- [ ] Không dùng câu “ba tester thích B” nếu thiếu hành vi, lý do và trade-off đi kèm.

## Lưu ý

Ba feedback chỉ là input cho iteration tiếp theo. Không kết luận:

> “User đã xác nhận solution này đúng.”

Cách kết luận phù hợp:

> “Với Hypothesis Problem này, chúng tôi đã thử ba cách giải. Tester đã làm…, vì vậy iteration tiếp theo chúng tôi sẽ…; điều vẫn chưa được chứng minh là…”
