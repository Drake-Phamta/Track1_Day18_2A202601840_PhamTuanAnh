# Chặng 1 — Tổng hợp evidence

## 1. Evidence huddle

| Practice Note | User đã thực sự làm/nói gì? | Điều nhóm đang diễn giải |
|---|---|---|
| **1 (Hieu - Learner)** | Khi gặp lỗi code, nhắn qua Discord gọi Lab Code. Phải chờ 3-4 phút vì Lab Code bận, và tốn thêm thời gian giải thích vì Lab Code phải "load lại thông tin từ đầu" (thiếu context). Learner cảm thấy "nản". | Learner có chủ động tìm hỗ trợ nhưng thời gian chờ lâu và khâu truyền đạt bối cảnh (context) gặp khó khăn, làm chậm quá trình gỡ lỗi. |
| **2 (TuanAnh - Learner)** | Đọc note không hiểu, lập tức "la lên" hoặc nhắn Discord "Anh ơi, em vướng phần này". Lab Coach tiếp cận nhưng "không phải phần đảm nhiệm chính" nên giải thích không thỏa đáng. | Khó khăn không nằm ở việc learner ngại hỏi hay không biết mình vướng ở đâu, mà điểm nghẽn nằm ở khâu định tuyến (routing) sai người hỗ trợ. |
| **3 (NgocChi - Coach)** | Coach phải đoán hoặc đi bộ rà soát từng bàn vì nhiều bạn ngại hỏi. Khi nhận được câu hỏi, câu hỏi thường "đại hải" (thiếu thông tin), Coach phải "hỏi follow-up lại" để xác định đúng bối cảnh. | Việc phát hiện/nhận diện học viên khó khăn là một vấn đề, nhưng rào cản lớn hơn nằm ở việc thiếu hụt ngữ cảnh câu hỏi, buộc coach tốn thời gian gạn lọc thông tin trước khi có thể hỗ trợ. |

**Thảo luận nhanh:**
- **Situation lặp lại:** Learner gặp trở ngại, khi yêu cầu hỗ trợ (hoặc được tiếp cận) thì quá trình xử lý bị kéo dài do thiếu thông tin bối cảnh (context) dự án hoặc người hỗ trợ không nắm đúng chuyên môn.
- **Mâu thuẫn hoặc bất ngờ:** Nhóm từng giả định rào cản lớn nhất là "instructor khó phát hiện ai cần hỗ trợ" (Pain A) hoặc "learner ngại hỏi" (Pain B). Nhưng thực tế có những learner rất chủ động ("la lên", nhắn liền), điểm gãy lại nằm ở bước ngay sau đó: quy trình tiếp nhận thiếu bối cảnh và điều phối nhầm người.
- **Điều vẫn là suy đoán:** Hậu quả (consequence) thực sự lên tiến độ học tập. Việc chờ đợi 3-4 phút hay một phần note không hiểu có thực sự khiến learner học sai hướng, trễ tiến độ hay bỏ dở bài không, hay chỉ gây ra sự khó chịu nhất thời?

## 2. Chốt Hypothesis Problem

**Hypothesis Problem nhóm tiếp tục:**
Khi learner đang mắc lỗi trong buổi lab và cần chuyển yêu cầu hỗ trợ (situation), **Lab Coach** gặp khó khăn trong việc xác định nhanh learner đang ở bước nào và ai nên tiếp nhận (job) vì **yêu cầu thường thiếu/lan man về bối cảnh và có thể đến nhầm coach** (barrier), dẫn đến **Coach phải hỏi follow-up hoặc đi tìm từng bàn trước khi bắt đầu hỗ trợ** (consequence).

**Evidence ban đầu hỗ trợ giả thuyết:**
- Learner (Note 1) than phiền Lab Code mất thời gian "load lại thông tin từ đầu" khiến việc giải thích lỗi trở nên khó khăn.
- Learner (Note 2) phản ánh Lab Coach đến hỗ trợ nhưng "không phải phần đảm nhiệm chính" nên không giải quyết được vấn đề.
- Lab Coach (Note 3) thừa nhận câu hỏi của học viên thường lan man, phải tốn thời gian "hỏi follow-up lại" nhiều lần mới xác định được lỗi ở bước nào.

**Điều vẫn chưa được chứng minh:**
- Tần suất và thời lượng trung bình của việc hỏi lại/đi tìm learner chưa được đo lường.
- Chưa biết việc chậm trễ này có làm learner trễ tiến độ, đổi workaround hay bỏ dở bài hay không.
- Chưa biết learner có chấp nhận việc hệ thống đọc terminal hoặc theo dõi lỗi trong phiên học hay không.

**Vai trò dùng trong Day 18:**
- **Primary user:** Lab Coach, người cần triage và bắt đầu hỗ trợ.
- **Supporting actor:** Learner, người cung cấp hoặc xác nhận context trước khi yêu cầu được chuyển đi.
