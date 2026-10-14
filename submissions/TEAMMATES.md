# Báo cáo đóng góp thành viên

## Thành viên

| Họ và tên | Mã số sinh viên |
|---|---|
| Nguyễn Đình Lâm Phúc | 2A202602986 |
| Hồ Thái Hòa | 2A202602915 |

## Phân công và phần việc đã thực hiện

### Nguyễn Đình Lâm Phúc

Phụ trách phần agent và chiến lược thực thi lệnh:

- Hoàn thiện `agent/gateway.py` để phân tích lệnh, chọn server/tool, chuẩn hóa tham số và định tuyến yêu cầu; xử lý lựa chọn replica, lease và field mask.
- Bổ sung các kiểm tra quyền và giao thức trước khi gọi tool, gồm danh tính learner, scope, điều kiện ghi dữ liệu và ủy quyền A2A.
- Quản lý chi phí/credits và các giới hạn gọi tool; xử lý tool deprecated và các trường hợp lệnh không hợp lệ.
- Mở rộng `agent/guardrails.py` để kiểm tra mức độ grounding, nội dung chỉ thị không đáng tin cậy, dữ liệu nhạy cảm và các khẳng định số liệu.
- Cập nhật `agent/prompt.md` để hướng dẫn agent lập kế hoạch gọi tool, chọn trường cần lấy, trích dẫn nguồn, xử lý mâu thuẫn và từ chối an toàn.
- Điều chỉnh `deck/deck.json` nhằm cải thiện cách agent xử lý các tình huống trong trận.
- Hỗ trợ kiểm tra luồng phát lại trận trên giao diện arena.

### Hồ Thái Hòa

Phụ trách phần prosecutor và đánh giá khả năng phát hiện lỗi:

- Phát triển `eval/prosecute.py` để đọc trace của đối thủ, nhận diện lỗi và tạo claim có tham chiếu bằng chứng theo đúng định dạng.
- Bổ sung detector cho các nhóm lỗi hạ tầng, tính đúng đắn của câu trả lời/citation, an toàn, chất lượng phản hồi và chi phí tool; ưu tiên claim `enforcement_failure` khi các lỗi cùng family A tranh giới hạn claim.
- Dùng `ProsecutionBudget` để giới hạn số claim và số claim trong mỗi family, đồng thời kiểm tra schema trước khi nộp claim.
- Đối chiếu prosecutor với 40 fixture gồm tình huống dương, near-miss và sạch; kết quả ghi nhận precision, recall và F1 đều đạt 1.000 trên bộ fixture, không có claim sai hoặc bị từ chối.
- Chạy spar với Rookie, Operator và Adversary; cả ba trận đều thắng. Rà soát cảnh báo `MISSED` còn xuất hiện trong trận để nhận diện giới hạn phát hiện ngoài fixture.
- Chạy bộ test của repo trong WSL: 4608 test đạt, 7 test được bỏ qua.
- Cập nhật `eval/README.md` để mô tả trạng thái prosecutor và cách chạy đánh giá.

## Phối hợp và hỗ trợ

Hai thành viên cùng hoàn thiện agent, chiến lược và phần đánh giá để hệ thống vừa thực thi lệnh có kiểm soát vừa có thể lập luận bằng chứng về lỗi của đối thủ. AI được dùng để hỗ trợ giải thích cấu trúc repo, rà soát code và đề xuất cải thiện; các thành viên tự kiểm tra kết quả và chịu trách nhiệm với nội dung nộp.
