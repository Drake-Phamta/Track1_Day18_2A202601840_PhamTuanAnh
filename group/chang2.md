# Chặng 2 — Chọn ba Solution Options

## 1. Mở lại Solution Parking Lot
Từ các hướng đã park ở Day 17 và điều chỉnh theo Hypothesis Problem mới (vấn đề thiếu ngữ cảnh và định tuyến sai chuyên môn), nhóm chọn/bổ sung 3 hướng đại diện cho 3 mức độ can thiệp của AI:

1. **(Cập nhật từ ý số 5)** AI tự động trích xuất bối cảnh (context) từ màn hình/terminal của learner khi họ chủ động yêu cầu hỗ trợ; learner vẫn tự chọn Coach nhận yêu cầu.
2. **(Cập nhật từ ý số 1 & 6)** AI theo dõi lỗi trong phiên học, khi phát hiện learner có dấu hiệu bị kẹt thì tự động phân tích và đề xuất Coach có chuyên môn; learner chỉ cần xác nhận.
3. **(Cập nhật từ ý số 3)** Không dùng AI. Một form "Yêu cầu hỗ trợ" có cấu trúc, buộc learner tự phân loại vấn đề (danh mục lỗi) và dán đoạn code/nội dung đang vướng để hệ thống định tuyến theo luật (rules) có sẵn.

## 2. Chọn ba cách giải

### Những thứ phải giữ nguyên
| Thành phần | Quyết định chung cho A/B/C |
|---|---|
| **Target user** | **Primary:** Lab Coach (triage và hỗ trợ). **Supporting actor:** Learner (gửi và xác nhận yêu cầu). |
| **Situation** | Learner bị kẹt (lỗi code hoặc không hiểu bài) trong buổi học và cần sự trợ giúp từ Lab Coach. |
| **Task** | Chuyển giao yêu cầu hỗ trợ đến đúng Lab Coach phụ trách kèm theo đầy đủ bối cảnh (context) hiện tại của Learner. |
| **Desired outcome** | Lab Coach nắm ngay vấn đề mà không phải hỏi đi hỏi lại; Learner nhận được hướng dẫn đúng chuyên môn và nhanh chóng. |
| **Content/data fixture** | Một trường hợp cố định: Learner bị lỗi biến môi trường (Environment Variable) khi chạy code; Danh sách Lab Coach trực ca (Coach A chuyên Frontend, Coach B chuyên DevOps/Môi trường). |

### Những thứ được phép khác
| Thành phần | Option A (User-Initiated + AI Context) | Option B (AI-Initiated + User Confirms) | Option C (No AI / Manual Form) |
|---|---|---|---|
| **Solution mechanism** | AI Context Extractor: Khi learner bấm nút "Yêu cầu hỗ trợ", AI quét màn hình/terminal hiện tại và tạo bản nháp; learner tự chọn người nhận. | AI Support Radar + Smart Routing: AI phát hiện lỗi lặp lại trong phiên học, phân tích tín hiệu và đề xuất Coach phù hợp trong một pop-up. | Structured Support Form: Learner tự chọn chủ đề, mô tả tình huống và paste lỗi; hệ thống chuyển theo rule có sẵn. |
| **User làm gì?** | Learner chủ động bấm hỗ trợ, review/sửa bản nháp và tự chọn Coach trước khi gửi. | Learner đọc tín hiệu AI, xác nhận hoặc dismiss đề xuất. | Learner tự phân loại, điền context và gửi form; Lab Coach nhận yêu cầu theo route của rule. |
| **AI làm gì?** | AI chỉ trích xuất thông tin (bài đang mở, terminal báo lỗi gì) và viết tóm tắt; không tự chọn Coach. | AI theo dõi tín hiệu trong phiên, phân tích lỗi và chủ động đề xuất Coach; không tự gửi khi chưa được xác nhận. | Không có AI suy đoán; hệ thống chỉ áp dụng rule định tuyến theo danh mục người dùng chọn. |
| **Trigger** | Learner ấn nút "Yêu cầu hỗ trợ". | AI tự phát hiện hành vi (chạy code lỗi 3 lần liên tiếp hoặc kẹt ở 1 slide > 5 phút). | Learner ấn nút "Yêu cầu hỗ trợ". |
| **Trade-off chính** | Giảm gánh nặng mô tả nhưng learner vẫn phải biết chọn đúng Coach; rủi ro AI tóm tắt sai hoặc thừa thông tin. | Giảm thao tác và có thể route sớm hơn, nhưng có rủi ro làm phiền hoặc tạo cảm giác bị theo dõi; độ chính xác chưa được chứng minh. | Dễ giải thích và không có rủi ro AI đoán sai, nhưng tạo thêm ma sát và đặt gánh nặng phân loại lên learner. |

### Distance check
- **A khác B vì** A chỉ khởi động sau khi learner chủ động yêu cầu và AI chỉ tạo context; learner vẫn chọn Coach. B chủ động phát hiện tín hiệu kẹt và AI đề xuất cả Coach, learner xác nhận.
- **B khác C vì** B dùng tín hiệu hành vi và lỗi để đề xuất route, còn C không suy đoán và buộc learner tự chọn danh mục, mô tả và cung cấp bằng chứng.
- **A khác C vì** cả hai đều do learner chủ động trigger, nhưng A dùng AI để trích xuất context còn C yêu cầu learner nhập context thủ công; A vẫn để learner chọn người nhận.
