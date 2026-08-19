# Prototype Links

> **Case:** C — AI Support Radar · **Nhóm:** Hello world
> **Thành viên:** Nguyễn Ngọc Chi (2A202602024) · Nguyễn Minh Hiếu (2A202601154) · Phạm Tuấn Anh (2A202601840)

---

## Cách mở

| Cách | Đường dẫn |
| :--- | :--- |
| Link công khai | https://drake-phamta.github.io/Track1_Day18_2A202601840_PhamTuanAnh/ |
| Mở trực tiếp trong repo | [index.html](index.html) — double-click bằng trình duyệt, không cần server |

Dùng thanh tab trên cùng để chuyển giữa Option A, B, C. Mỗi option có nút reset để quay về common context ban đầu.

---

## Common context — dùng chung cho cả ba option

- VLearn Lab Day 5 — Environment Setup, bước cấu hình Environment Variable.
- Chạy `npm run dev` gặp `Error: NEXT_PUBLIC_API_KEY is not defined` tại `lib/api.js:12`.
- Hai Coach trực ca: **Le Thi Hoa** (Frontend/UI) · **Nguyen Duc Minh** (DevOps/Môi trường).

Ba option dùng chung khoảng 70% context, content fixture và visual components. Khác biệt chỉ nằm ở critical interaction.

---

## Option A — AI Context Extractor

- **Cơ chế:** learner bấm *Cần hỗ trợ*, AI quét terminal và bài học hiện tại để tạo bản nháp; learner sửa và tự chọn Coach trước khi gửi.
- **Chế độ AI:** Ask — AI soạn nháp nhưng không tự gửi, không tự chọn người nhận.
- **Khi test:** thử sửa bản nháp, thử đổi Coach, xem điều gì xảy ra nếu gửi mà không sửa gì.

## Option B — AI Smart Routing

- **Cơ chế:** AI phát hiện lỗi lặp lại trong phiên học, phân tích tín hiệu và hiện pop-up đề xuất Coach phù hợp; learner xác nhận hoặc dismiss.
- **Chế độ AI:** Ask — pop-up nêu rõ tín hiệu đã dùng, không tự gửi ticket.
- **Khi test:** đọc phần lý do AI đưa ra gợi ý, thử bấm *Không, tôi muốn tự làm* để xem đường dismiss.

## Option C — Structured Support Form *(Phạm Tuấn Anh phụ trách)*

- **Cơ chế:** learner bấm *Yêu cầu hỗ trợ*, tự chọn danh mục lỗi, mô tả tình huống và paste đoạn lỗi; hệ thống định tuyến theo rule sau khi submit đủ trường bắt buộc.
- **Chế độ AI:** **Don't infer** — không có AI suy đoán. Đây là option đối chứng để đo giá trị thật của AI ở A và B.
- **Khi test:** thử submit khi còn thiếu trường để thấy validation; thử chọn nhầm danh mục rồi tìm đường sửa hoặc tạo lại.

---

## Không có trong prototype, và cố ý không có

- Model hoặc API thật — toàn bộ output của AI ở Option A và B là canned output cố định.
- Onboarding, dashboard đầy đủ, responsive nhiều thiết bị, visual polish.
- Trường hợp AI đoán sai bước hoặc sai Coach — ghi vào Still Unproven, không mô phỏng.
