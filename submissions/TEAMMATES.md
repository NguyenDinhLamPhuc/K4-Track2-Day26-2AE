# Thành viên và đóng góp

| Thành viên | Mã số sinh viên | Đóng góp |
|---|---|---|
| Nguyễn Đình Lâm Phúc | 2A202602986 | Phát triển gateway cho các bước định tuyến và ghim replica, kiểm tra lease và tool deprecated, xác thực learner, scope và A2A delegation, đồng thời quản lý ngân sách cùng field mask. Bổ sung các guardrail kiểm tra grounding, phát hiện chỉ thị bị tiêm, che dữ liệu nhạy cảm và kiểm tra số liệu. Cập nhật prompt về kế hoạch gọi tool, citation, từ chối an toàn và xử lý nguồn mâu thuẫn; điều chỉnh deck và tùy chọn mở trình duyệt của giao diện phát lại trận. |
| Hồ Thái Hòa | 2A202602915 | Cải thiện prosecutor trong `eval/prosecute.py`: phát hiện lệnh `slides.get_frame` thiếu lease và citation không xuất hiện trong kết quả tool; tạo claim kèm tham chiếu bằng chứng và nối detector vào luồng prosecution. Ưu tiên `enforcement_failure` hơn `protocol_misuse` khi cả hai cùng tranh suất claim nhóm A. Kiểm tra bằng test prosecution, toàn bộ test trong WSL và validate deck trên world thật. |

## Hỗ trợ từ AI

AI hỗ trợ giải thích cấu trúc repo, rà soát prosecutor và đề xuất/chỉnh sửa detector. Nhóm đã chạy lại test và tự xem xét kết quả spar; các thành viên chịu trách nhiệm rà soát nội dung cuối cùng trước khi nộp.
