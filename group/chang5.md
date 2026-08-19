# Chặng 5 — Chuẩn bị test

## 1. Chốt context và task

### Relevant context

Nói trong tối đa 2 phút, không giới thiệu trước về A/B/C:

> Gần đây bạn có từng bị kẹt khi làm bài lab hoặc gặp lỗi code nhưng khi nhờ Coach hỗ trợ lại phải giải thích lại bối cảnh, hoặc gặp nhầm người hỗ trợ, không?

Nếu tester chưa từng gặp đúng tình huống, tiếp tục test để quan sát interaction breakdown. Không dùng kết quả của tester đó để kết luận pain hoặc value đã được xác nhận.

### Common context trong prototype

- Bạn đang học VLearn Lab Day 5 — Environment Setup.
- Bạn đang ở bước cấu hình Environment Variable.
- Khi chạy `npm run dev`, terminal hiển thị:

  `Error: NEXT_PUBLIC_API_KEY is not defined`

  tại `lib/api.js:12`.
- Có hai Coach trực ca:
  - Le Thi Hoa — Frontend/UI.
  - Nguyen Duc Minh — DevOps/Môi trường.

Không đọc trước cho tester cách mỗi option hoạt động. Hãy để thông tin xuất hiện trong prototype tự dẫn dắt họ.

### Outcome task

Đọc nguyên văn cho từng option:

> Trong tình huống này, hãy dùng phương án hiện tại để gửi một yêu cầu hỗ trợ sao cho Coach phù hợp có thể hiểu bạn đang gặp lỗi gì mà không phải hỏi lại từ đầu. Nếu phương án đưa ra một gợi ý hoặc yêu cầu bạn xác nhận, hãy quyết định như bạn sẽ làm ngoài đời.

Sau mỗi option, đưa tester về context ban đầu rồi mới chuyển sang option tiếp theo.

Thứ tự test nên được counterbalance nếu có thể: A/B/C, B/C/A hoặc C/A/B để giảm ảnh hưởng thứ tự.

## 2. Observation focus

Chọn tối đa năm focus sau cho mỗi tester:

1. **First action** — Tester làm gì đầu tiên và có tự tìm được điểm bắt đầu không?
2. **Evidence read/ignored** — Tester có đọc lỗi terminal, lý do AI hoặc thông tin Coach trước khi quyết định không?
3. **Misunderstanding / hesitation** — Tester dừng lại, đọc lại, hỏi facilitator hoặc hiểu sai điểm nào?
4. **Control and recovery** — Tester có sửa bản nháp, đổi Coach, dismiss gợi ý, xử lý validation hoặc reset được không?
5. **Option và trade-off** — Tester chọn/ưu tiên phương án nào, dựa trên đánh đổi nào giữa ít thao tác, quyền kiểm soát, độ tin cậy và cảm giác bị theo dõi?

### Dấu hiệu cần ghi cụ thể

| Focus | Ghi hành vi trước | Ghi diễn giải sau |
|---|---|---|
| First action | Click/navigate đầu tiên, mất bao lâu, có quay lại không | Tester có hiểu điểm bắt đầu không |
| Evidence | Đọc lỗi, đọc số lần lặp, đọc tên Coach, bỏ qua phần nào | Bằng chứng nào ảnh hưởng đến quyết định |
| Hesitation | Im lặng, rê chuột, đọc lại, hỏi “cái này là gì?” | Có thể đang thiếu expectation hoặc wording |
| Recovery | Sửa text, đổi Coach, dismiss, điền lại form, reset | Control nào hữu ích hoặc còn thiếu |
| Trade-off | Chọn A/B/C, lý do, điều họ đánh đổi | Hypothesis nào cần kiểm tra tiếp |

## 3. Luật facilitation

1. Tester tự điều khiển prototype.
2. Dùng đúng một task cho A/B/C.
3. Không narrate hoặc giải thích icon, AI, Coach mapping hay bước tiếp theo.
4. Không lấp im lặng quá sớm.
5. Không hỏi “Bạn có thích không?” hoặc “Bạn thấy option nào tốt hơn?” trước khi ghi nhận hành vi.
6. Nếu tester hỏi cách hoạt động, hỏi lại:

   > Theo bạn, nó nên hoạt động như thế nào?

7. Chỉ can thiệp khi prototype bị lỗi hoặc tester không thể tiếp tục vì lỗi kỹ thuật. Ghi rõ lần can thiệp đó vào Feedback Note.
8. Không sửa câu trả lời của tester và không nói đáp án đúng.

### Ba câu cứu hộ

- “Bạn cứ nói to suy nghĩ của mình nhé.”
- “Bạn sẽ làm gì tiếp theo?”
- “Theo bạn, nó nên hoạt động như thế nào?”

## 4. Script ngắn cho facilitator

### Mở đầu

> Mình muốn quan sát cách bạn xử lý một tình huống hỗ trợ trong bài lab. Không có đáp án đúng hay sai. Bạn hãy tự thao tác và nói ra điều bạn đang nghĩ; mình sẽ không giải thích giao diện trong lúc bạn làm.

### Chuyển option

> Đây là một phương án khác cho cùng tình huống và cùng mục tiêu. Bạn hãy thực hiện lại task ban đầu.

### Kết thúc sau A/B/C

Chỉ hỏi sau khi đã ghi nhận hành vi:

- “Ở phương án nào bạn phải suy nghĩ nhiều nhất? Điều gì khiến bạn dừng lại?”
- “Bạn đã dựa vào thông tin nào để quyết định?”
- “Bạn thấy phương án nào cho bạn nhiều quyền kiểm soát hơn? Vì sao?”
- “Bạn đã đánh đổi điều gì khi chọn phương án đó?”

Không chuyển các câu trả lời này thành claim về product value; chỉ ghi lại lý do và trade-off mà tester nói.

## 5. Test matrix

| Tester | Relevant context | Thứ tự | A | B | C | Can thiệp kỹ thuật |
|---|---|---|---|---|---|---|
| Tester 1 | Có / Chưa có | A → B → C | Đã test | Đã test | Đã test | |
| Tester 2 | Có / Chưa có | B → C → A | Đã test | Đã test | Đã test | |
| Tester 3 | Có / Chưa có | C → A → B | Đã test | Đã test | Đã test | |

## 6. Ghi chú đạo đức và dữ liệu

- Xin phép trước khi ghi âm hoặc chụp màn hình.
- Không ghi thông tin cá nhân hoặc code thật nếu không cần thiết.
- Không tạo quote, observation hoặc feedback khi tester chưa nói/làm điều đó.
- Kết quả của Chặng 5 chỉ cho biết interaction breakdown, hành vi và trade-off ban đầu; chưa đủ để tuyên bố solution đã được validated.

## Tự kiểm — GATE 5

- [x] A/B/C dùng cùng relevant context, task và desired outcome.
- [x] Task mô tả kết quả cần đạt, không chỉ dẫn nút cần bấm.
- [x] Observation focus không vượt quá năm mục.
- [x] Có cùng luật facilitation cho cả ba option.
- [x] Có đường reset về common context giữa các option.
- [x] Có ghi nhận context của tester và mọi lần facilitator phải can thiệp.
