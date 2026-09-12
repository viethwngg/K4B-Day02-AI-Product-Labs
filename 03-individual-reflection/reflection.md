# 03 — Individual Reflection

## Thông tin cá nhân

- **Họ và tên:** Đàm Việt Hưng
- **Mã học viên:** 2A202602600
- **Nhóm:** zone C nhóm buổi chiều
- **Candidate nhóm chọn:** Phát hiện sớm tai nạn từ camera không được giám sát liên tục.

## 1. Tôi đã tham gia phần nào?

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng |
|---|---|---|
| Scan cá nhân | Scan 10 problems theo 4 lăng kính và chọn top 3. | Có danh sách rộng, không bắt đầu bằng một solution AI duy nhất. |
| Pitch Problem Card | Trình bày Card #1 về khoảng trống camera ghi hình nhưng chưa có cảnh báo. | Làm rõ actor, workflow và bottleneck cần validate. |
| Challenge | Đặt câu hỏi về detection latency và false-alert fatigue. | Giữ nhóm không biến giả thuyết thành fact. |
| Cluster / candidate | Gom các hướng phát hiện, mapping và hậu kiểm thành 3 cluster. | Chọn candidate phát hiện sớm để đào sâu. |
| Workflow | Viết current/future workflow và human boundary. | Chốt AI chỉ tạo suspected incident, người thật confirm/reject. |
| Decision | So sánh Rule, Workflow và Agent. | Chọn Workflow cho pilot, quyết định hiện tại là Not Yet. |

**Dấu tay rõ nhất:** Tôi tập trung thu hẹp RoadGuardian từ “AI phát hiện tai nạn” thành workflow có điểm review của con người, đồng thời ghi rõ baseline và quyền camera còn thiếu.

## 2. Bảng dùng AI

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Gợi ý thêm problem theo 4 lăng kính. | Mở rộng danh sách candidate. | Dễ gợi ý solution quá rộng hoặc không có pain thật. | Giữ problem có actor, workflow và dấu hiệu cần đo. |
| Problem Card | Phản biện bottleneck và rủi ro. | Gợi ý câu hỏi challenge. | Không thể cung cấp baseline camera tại Việt Nam. | Đánh dấu các số liệu là cần validate. |
| Workflow | Gợi ý flow trước/sau. | Làm rõ handoff, fallback và human boundary. | Có xu hướng tự động hóa nhiều bước. | Giữ người thật trước mọi action chính thức. |
| Research | Gợi ý hướng tìm tool và pattern. | So sánh Rule/Workflow/Agent. | Không dùng số liệu chưa kiểm link. | Chỉ giữ nguồn kiểm được và ghi rõ khoảng trống. |
| Problem Statement | Đề xuất cách viết chặt hơn. | Kiểm tra actor, metric và boundary. | Có thể viết chắc chắn dù evidence thiếu. | Chọn Not Yet thay vì khẳng định Go. |
| Rule / Workflow / Agent | Hỏi phản biện các mức tự động hóa. | Làm rõ vì sao Agent là quá mức. | Không tự quyết định rủi ro vận hành. | Chọn Workflow, Rule làm baseline. |
| Decision | Kiểm tra điều kiện Go/Not Yet/No-Go. | Làm lộ dependency còn thiếu. | Không thay interview, log hoặc dataset. | Yêu cầu validation trước pilot thật. |

## 3. Reflection

Tôi học được rằng một ý tưởng AI nghe hấp dẫn chưa chắc là một problem đủ rõ để triển khai. Khi tách workflow RoadGuardian thành các bước, tôi thấy bottleneck có thể nằm ở việc phát hiện sự kiện chứ không phải ở việc tự điều động lực lượng. Tôi cũng nhận ra các con số như detection latency dưới 10 giây hay recall 90% mới chỉ là target cho prototype, chưa phải bằng chứng hệ thống thực tế. Phần khó nhất là phân biệt context về mức độ nghiêm trọng của tai nạn với bằng chứng trực tiếp rằng camera không được giám sát là nguyên nhân gây chậm. AI giúp tôi mở rộng góc nhìn và phản biện rủi ro, nhưng không thể thay interview, log, dataset hoặc quyền truy cập camera. Tôi đã sửa hướng solution bằng cách giữ suspected incident và human review ở giữa workflow. Tôi không chọn Agent vì các bước hiện tại vẫn có thể đi theo một flow xác định và cần kiểm soát chặt. Dấu tay của tôi trong artifact là problem scan 10 ý, top 3 cards, workflow và boundary không tự ra quyết định pháp lý. Nếu làm lại, tôi sẽ validation sớm hơn với nhân viên vận hành camera và đo một workflow thật trước khi đặt target. Quyết định hợp lý hiện tại là Not Yet, vì problem đáng kiểm chứng nhưng dữ liệu và điều kiện triển khai chưa đủ.

## 4. Tự kiểm cuối bài

- [x] Có 10 problems và top 3 Problem Cards.
- [x] Có pitch, challenge và vai trò cá nhân.
- [x] Có workflow trước/sau, metric, boundary và fallback.
- [x] Có so sánh Rule/Workflow/Agent.
- [x] Reflection có AI hữu ích, điểm hời hợt và phần tự sửa.
- [x] Tự giải thích được problem → workflow → metric → boundary → AI fit.