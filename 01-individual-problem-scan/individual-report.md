# 01 — Individual Problem Scan

## Thông tin cá nhân

- **Họ và tên:** Đàm Việt Hưng
- **Mã học viên:** 2A202602600
- **Vai trò / bối cảnh:** Sinh viên năm cuối — Phenikaa University
- **Chủ đề:** RoadGuardian — phát hiện sớm tai nạn giao thông từ camera và hỗ trợ cảnh báo

## Phase 1 — Scan 5+ problems

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật / cần kiểm chứng |
|---|---|---|---|---|
| 1 | Lặp lại | Phải theo dõi nhiều camera giao thông liên tục để tìm sự cố | Nhân viên trung tâm giám sát | Camera hoạt động liên tục; số camera/người trực cần validate |
| 2 | Tốn thời gian | Khi nhận tin phải tìm đúng camera hoặc vị trí xảy ra | Nhân viên điều hành / CSGT | Cần bấm thời gian xác định camera/vị trí thực tế |
| 3 | AI có thể tốt hơn | Camera ghi hình nhưng không có người nhìn đúng thời điểm tai nạn | Đơn vị giám sát, người gặp tai nạn | Candidate chính; detection latency thực tế cần validate |
| 4 | Tốn thời gian | Sau khi phát hiện phải xác định vị trí, camera và timestamp | Người tiếp nhận cảnh báo | Có thể tự động hóa nếu camera có metadata |
| 5 | Pain từ người khác | Người đi đường phải chủ động gọi/báo khi chứng kiến tai nạn | Người tham gia giao thông, cơ quan chức năng | Cần khảo sát mức phụ thuộc vào báo cáo của người dân |
| 6 | Lặp lại | Người trực phải phân biệt tai nạn thật với xe dừng, ùn tắc hoặc cảnh bình thường | Người giám sát | Cần ghi nhận false alert trong workflow thực tế |
| 7 | AI có thể tốt hơn | Camera nhà dân/cửa hàng ghi được tai nạn nhưng thường chỉ được xem lại sau sự kiện | Chủ camera, cơ quan chức năng | Cần validate consent, quyền truy cập và privacy |
| 8 | Tốn thời gian | Tìm và trích xuất đúng đoạn video trước/sau tai nạn | CSGT / quản trị camera | Baseline thời gian tìm timestamp chưa có |
| 9 | Pain từ người khác | Người trực quá tải khi số camera tăng | Trung tâm vận hành | Số camera/người trực cần validate |
| 10 | AI có thể tốt hơn | Camera ghi hình nhưng chưa tự nhận biết sự kiện bất thường cần xử lý | Đơn vị vận hành camera | Computer Vision có thể hỗ trợ event detection |

Pattern: `Camera nhìn thấy sự việc` không đồng nghĩa `hệ thống biết sự việc xảy ra` hoặc `người có trách nhiệm nhận được cảnh báo`.

### AI đã dùng ở Phase 1

- **Prompt:** Phân tích problem phát hiện tai nạn từ camera và xác định AI có thực sự cần thiết hay không.
- **Ý dùng được:** AI có thể là lớp phát hiện sự kiện, không thay thế toàn bộ hệ thống giám sát và xử lý.
- **Ý bỏ:** AI tự điều hành giao thông, tự xác định người gây tai nạn, hoặc tự điều động lực lượng vì vượt quá bottleneck đang khảo sát.

## Phase 2 — Top 3 Problem Cards

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Tai nạn trên camera không được phát hiện ngay vì không có người giám sát liên tục | Workflow rõ, impact liên quan trực tiếp detection latency, có thể thử nghiệm bằng video | Baseline latency và số camera không được giám sát |
| 2 | Sau khi biết tai nạn, xác định camera/vị trí/thời điểm còn thủ công | Có thể đo, metadata có thể hỗ trợ | Có phải bottleneck lớn nhất không |
| 3 | Tìm và trích xuất video sau tai nạn mất thời gian | Pain cụ thể, workflow và thời gian dễ đo | Impact có thấp hơn phát hiện sớm không |

### Problem Card #1 — Phát hiện sớm tai nạn

- **Problem:** Camera có thể ghi được tai nạn nhưng không có người theo dõi liên tục, khiến sự kiện chỉ được biết khi có người nhìn thấy hoặc báo lại.
- **Actor:** Nhân viên/đơn vị tiếp nhận, xác minh và xử lý sự cố; CSGT và cứu hộ là secondary actors.
- **Current workflow:** Tai nạn xảy ra → camera ghi hình → chờ người phát hiện → tiếp nhận → xác minh → xác định vị trí → chuyển thông tin.
- **Bottleneck:** Camera ghi được sự kiện nhưng chưa tạo tín hiệu để người có trách nhiệm kiểm tra.
- **Impact:** Phát hiện chậm làm thời điểm bắt đầu xác minh và chuyển thông tin cũng chậm.
- **Success metric:** Prototype có median detection latency dưới 10 giây, recall ít nhất 90% trên dataset thử nghiệm; đồng thời đo false-alert rate và human verification time.
- **Non-AI alternative:** Tăng người trực, quy trình báo cáo, hoặc rule phát hiện xe giảm tốc/đứng yên bất thường.
- **AI hypothesis:** Computer Vision tạo `Suspected Incident`, đính kèm camera ID, timestamp, location, snapshot/clip và confidence để người thật kiểm tra.
- **Quick gut:** Workflow, kết hợp Rule/Threshold và Human Verification; chưa phải Agent.

```text
CURRENT: Tai nạn → Camera ghi hình → Chờ người phát hiện [BOTTLENECK]
         → Tiếp nhận → Xác minh → Chuyển thông tin

FUTURE:  Tai nạn → Camera → AI phát hiện → Suspected Incident
         → Human Review → Confirm/Reject → Official Workflow
Fallback: AI sai hoặc false alert cao thì tắt detection layer và quay về quy trình cũ.
```

### Problem Card #2 — Xác định camera, vị trí và thời điểm

- **Problem:** Sau khi nhận tin tai nạn, người tiếp nhận có thể phải mapping thủ công từ sự cố sang camera, location và timestamp.
- **Actor:** Nhân viên tiếp nhận/điều hành.
- **Current workflow:** Nhận tin → xác định khu vực → tìm camera → xác định timestamp → xác minh → chuyển thông tin.
- **Bottleneck:** Mapping `Sự cố → Camera → Location → Timestamp`.
- **Impact:** Tăng thời gian trước khi incident đủ dữ liệu để xử lý.
- **Success metric:** Đo thời gian mapping; baseline hiện tại cần validate, target thử nghiệm là giảm ít nhất 50%.
- **Non-AI alternative:** Database camera ID/GPS/khu vực/đơn vị phụ trách và rule mapping.
- **AI hypothesis:** AI không bắt buộc; metadata và workflow automation có thể giải quyết phần lớn.
- **Quick gut:** Rule + Workflow.

```text
CURRENT: Nhận tin → Khu vực → Tìm camera [BOTTLENECK] → Location/timestamp → Chuyển tin
FUTURE:  Nhận incident → Camera ID mapping → Location/timestamp → Human Review → Chuyển tin
Fallback: Metadata thiếu hoặc mapping sai thì người trực xác định thủ công.
```

### Problem Card #3 — Tìm và trích xuất video

- **Problem:** Sau khi biết tai nạn, người quản lý camera phải tìm timestamp và export đoạn video trước/sau sự kiện.
- **Actor:** CSGT, nhân viên quản trị camera hoặc người xác minh.
- **Current workflow:** Nhận yêu cầu → xác định camera → xác định thời điểm → tìm recording → xem lại → export clip.
- **Bottleneck:** Tìm đúng timestamp trong recording dài.
- **Impact:** Chậm cung cấp bằng chứng video sau sự cố.
- **Success metric:** Đo thời gian từ yêu cầu đến clip đúng; baseline cần validate, target thử nghiệm là giảm ít nhất 50%.
- **Non-AI alternative:** Tìm theo timestamp, chuẩn hóa Camera ID, lưu bookmark và metadata incident.
- **AI hypothesis:** Khi có suspected incident, hệ thống tự lưu X giây trước và Y giây sau event để người thật review.
- **Quick gut:** Workflow, không cần Agent.

```text
CURRENT: Nhận yêu cầu → Tìm camera → Tìm timestamp [BOTTLENECK] → Xem → Export
FUTURE:  Incident → Bookmark timestamp → Lưu pre/post-event clip → Human Review → Export
Fallback: Giữ recording gốc và tìm theo workflow hiện tại nếu tự tạo clip thất bại.
```

## Card muốn pitch nhất

**Card #1 — Phát hiện sớm tai nạn từ camera không được giám sát liên tục.**

Camera ghi được tai nạn không đồng nghĩa có người biết sự việc vừa xảy ra. Cần kiểm chứng detection latency, recall, false-alert rate và human verification time trước khi kết luận AI cần thiết.

**Câu hỏi challenge:** Việc camera ghi được tai nạn nhưng không có người phát hiện có đủ thường xuyên để là bottleneck không? Ngưỡng false alert nào khiến người vận hành bị alert fatigue?

**AI phản biện và phần tôi sửa:** AI chỉ ra thiếu baseline, thiếu dữ liệu số camera/người trực, rủi ro privacy và false positive. Vì vậy tôi thu hẹp AI vào suspected accident, giữ human review, yêu cầu opt-in với camera tư nhân và so sánh AI với Rule/Workflow.

## Self-check

- [x] Có 10 problems và dùng đủ 4 lăng kính.
- [x] Có top 3 cards, workflow trước/sau, metric và fallback.
- [x] Có một card pitch và câu hỏi challenge.