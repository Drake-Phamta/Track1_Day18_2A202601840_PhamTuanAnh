# Prototype Feedback Note — phiên do tôi facilitate

> **Người facilitate:** Phạm Tuấn Anh (MHV: `2A202601840`)
> **Option tôi phụ trách:** Option C — Structured Support Form (No AI)
> **Vai trong test matrix nhóm:** Tester 3 · thứ tự **C → A → B**

Form theo [group/chang5.md](group/chang5.md) và [group/chang6.md](group/chang6.md). Chỉ ghi hành vi và lời nói quan sát được; phần diễn giải để riêng ở mục INTERPRETED.

---

## 1. Thông tin phiên test

| Mục | Nội dung |
| :--- | :--- |
| Người test (tên hoặc mã) | |
| Ngày / giờ | |
| Thời lượng | 20 phút |
| Tester có relevant context | Có / Không / Một phần |
| Relevant context ngắn — bằng lời tester | |
| Thứ tự option | C → A → B |
| Có can thiệp kỹ thuật không | Có / Không |
| Nếu có, can thiệp gì | |
| Đã xin phép ghi chú / ghi âm | Có / Không |

**Câu hỏi relevant context** — hỏi trong tối đa 2 phút, không giới thiệu trước A/B/C:

> Gần đây bạn có từng bị kẹt khi làm bài lab hoặc gặp lỗi code nhưng khi nhờ Coach hỗ trợ lại phải giải thích lại bối cảnh, hoặc gặp nhầm người hỗ trợ, không?

---

## 2. Common context dùng cho cả ba option

- Learner đang học **VLearn Lab Day 5 — Environment Setup**, ở bước cấu hình Environment Variable.
- Chạy `npm run dev`, terminal hiển thị `Error: NEXT_PUBLIC_API_KEY is not defined` tại `lib/api.js:12`.
- Hai Coach trực ca: **Le Thi Hoa** — Frontend/UI · **Nguyen Duc Minh** — DevOps/Môi trường.

**Outcome task — đọc nguyên văn cho từng option:**

> Trong tình huống này, hãy dùng phương án hiện tại để gửi một yêu cầu hỗ trợ sao cho Coach phù hợp có thể hiểu bạn đang gặp lỗi gì mà không phải hỏi lại từ đầu. Nếu phương án đưa ra một gợi ý hoặc yêu cầu bạn xác nhận, hãy quyết định như bạn sẽ làm ngoài đời.

Sau mỗi option, đưa tester về common context rồi mới chuyển sang option tiếp theo.

---

## 3. Năm observation focus

| # | Focus | Ghi hành vi trước | Ghi diễn giải sau |
| :-- | :--- | :--- | :--- |
| 1 | **First action** — làm gì đầu tiên, có tự tìm được điểm bắt đầu không | | |
| 2 | **Evidence read / ignored** — có đọc lỗi terminal, lý do AI, thông tin Coach trước khi quyết định không | | |
| 3 | **Misunderstanding / hesitation** — dừng lại, đọc lại, hỏi facilitator, hiểu sai chỗ nào | | |
| 4 | **Control and recovery** — sửa bản nháp, đổi Coach, dismiss gợi ý, xử lý validation, reset | | |
| 5 | **Option và trade-off** — chọn phương án nào, đánh đổi giữa ít thao tác, quyền kiểm soát, độ tin cậy và cảm giác bị theo dõi | | |

### Ghi theo từng option

| Observation | Option C (Manual Form) | Option A (AI Context) | Option B (AI Routing) |
| :--- | :--- | :--- | :--- |
| First action | | | |
| Chỗ dừng, do dự hoặc hiểu sai | | | |
| Evidence được đọc hay bỏ qua | | | |
| Cách tester sửa hoặc lấy lại control | | | |

| | |
| :--- | :--- |
| **Option được chọn** | A / B / C |
| **Lý do và trade-off tester nói ra** | |
| **Evidence chống lại kỳ vọng của nhóm** | |

---

## 4. Watchlist riêng cho Option C

*Đặt trước khi test, dựa trên annotation Option C trong [group/chang4.md](group/chang4.md). Không đọc cho tester nghe.*

| Điều cần quan sát | Ghi nhận |
| :--- | :--- |
| Tester chọn danh mục nào, dựa vào dấu hiệu gì | |
| Có paste code lỗi không, hay chỉ mô tả bằng lời | |
| Có thấy form dài hoặc rắc rối không | |
| Mất bao lâu để điền xong form | |
| Phản ứng khi validation chặn vì thiếu trường bắt buộc | |

---

## 5. Trích dẫn nguyên văn

> 

> 

> 

---

## 6. Tách bốn lớp

### OBSERVED
*Tester đã làm hoặc nói gì? Chỉ hành vi và lời nói, không thêm diễn giải.*



### INTERPRETED
*Tôi nghĩ điều đó có thể có nghĩa gì? Ghi rõ đây là hypothesis.*



### DECIDED — NEXT CHANGE
*Nhóm sẽ sửa, kết hợp hoặc test gì tiếp? Điền sau khi nhóm tổng hợp đủ ba Feedback Notes.*



### STILL UNPROVEN
*Điều gì chưa thể kết luận từ một người?*



---

## 7. Tự đánh giá kỹ năng facilitate

*Có lỡ narrate, giải thích icon, hay lấp im lặng chỗ nào không? Câu hỏi nào làm tester kể được tình huống cụ thể, câu nào chỉ thu được có/không?*



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
