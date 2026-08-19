# Group Feedback Synthesis — Day 18

**Nhóm:** Hello world · **Case:** C — AI Support Radar

Chỉ điền phần này **sau khi đã có đủ ba Feedback Notes độc lập** từ ba tester ngoài nhóm. Nguồn form: [group/chang6.md](group/chang6.md).

---

## 1. Ba phiên test

| | Feedback 1 | Feedback 2 | **Feedback 3** |
| :--- | :--- | :--- | :--- |
| Người facilitate | | | **Phạm Tuấn Anh** |
| Tester (tên hoặc mã) | | | **T-01** |
| Ngày | | | 19/08/2026 |
| Relevant context | Có / Không / Một phần | Có / Không / Một phần | **Có** |
| Thứ tự option | A → B → C | B → C → A | **C → A → B** |
| Có can thiệp kỹ thuật | | | _không ghi nhận_ |

Thứ tự được counterbalance để giảm ảnh hưởng thứ tự — option cuối không được lợi vì tester đã quen bối cảnh.

---

## 2. Bảng so ba feedback

| Nội dung | Feedback 1 | Feedback 2 | Feedback 3 | Pattern hoặc khác biệt |
| :--- | :--- | :--- | :--- | :--- |
| First action | | | Mở luồng bằng nút *Yêu cầu hỗ trợ* ở cả C và A; ở B bấm *Có, kết nối ngay* | |
| Breakdown chính | | | Do dự ở **bản nháp do AI soạn trong Option A**; C và B không do dự | |
| Evidence được đọc hay bỏ qua | | | Đọc lỗi ở cả ba; ở A còn đọc lý do và chọn tên Coach; ở B đọc hết pop-up | |
| Cách lấy lại control | | | Tìm thấy ở cả ba option; riêng A ghi nhận là *dễ dàng* | |
| Option được chọn | | | **C** | |
| Lý do và trade-off | | | Lý do: *được quyền chủ động mô tả lỗi*. Trade-off: AI tiện và nhanh hơn nhưng *chưa thể hiện rõ được nhu cầu mong muốn* | |

---

## 3. Một Next Change nhóm chốt

*Chọn đúng một: giữ và sửa một option · kết hợp hai option nhưng giữ một cơ chế chính rõ ràng · bỏ một option · sửa cả ba rồi test tiếp.*



## 4. Evidence dẫn tới quyết định

*Phải trỏ được về observation cụ thể từ Feedback 1–3, không phải sở thích.*



## 5. Still Unproven sau ba feedback

*Điều chưa thể kết luận về value, mức độ nghiêm trọng, độ chính xác routing, sự chấp nhận việc theo dõi dữ liệu, hoặc hành vi ngoài prototype.*

- Tần suất và thời lượng thật của việc Coach phải hỏi lại — ba phiên test không đo được.
- Learner có chấp nhận để hệ thống đọc terminal và theo dõi lỗi trong phiên học hay không, khi dùng thật chứ không phải prototype.
- Phản ứng khi **AI đoán sai** — cả ba prototype dùng canned output nên không có tình huống sai để quan sát.
- Lợi thế *nhanh hơn* của A và B chưa được đo bằng thời gian thực tế ở phiên 3.
- 

---

## 6. Handover cho iteration tiếp theo

| Mục | Nội dung |
| :--- | :--- |
| Option hoặc cơ chế được giữ lại | |
| Interaction cần sửa | |
| Fixture / context cần giữ nguyên khi test lại | |
| Tester / context cần tuyển tiếp | |
| Observation cần kiểm tra lại | |

---

## Tự kiểm — GATE 5: Learning, not praise

- [ ] Có ba Feedback Notes độc lập từ ba tester ngoài nhóm.
- [ ] Mỗi tester đã dùng cả A/B/C với cùng context, task và desired outcome.
- [ ] Mỗi note tách rõ OBSERVED và INTERPRETED.
- [ ] Nhóm nêu được pattern hoặc khác biệt giữa ba người.
- [ ] Nhóm chốt đúng một Next Change.
- [ ] Nhóm ghi một điều STILL UNPROVEN.
- [ ] Không dùng câu *ba tester thích B* nếu thiếu hành vi, lý do và trade-off đi kèm.

**Không kết luận:** *User đã xác nhận solution này đúng.*

**Cách kết luận phù hợp:** *Với Hypothesis Problem này, chúng tôi đã thử ba cách giải. Tester đã làm…, vì vậy iteration tiếp theo chúng tôi sẽ…; điều vẫn chưa được chứng minh là…*
