# 02 — Group Problem Statement (Bản nộp nhóm)

> Làm chung 1 bản, mỗi thành viên copy vào repo cá nhân. Đi theo Phase 3 → 6 trong `01-worksheet.md`. Nhóm chỉ chọn **candidate problem** ở Phase 3, viết Problem Statement sau khi validate + vẽ workflow.

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm (VD: facilitator, workflow, research, writer) |
|-----|-----------|-------------|---------------------------------------------------------------|
| 1   | Phạm Văn Kiên | 2A202602590 | Tổng hợp candidates cá nhân, ghi nhận điểm nghẽn và metric |
| 2   | Phạm Đình Hải | 2A202602482 | Phân tích nhóm bài toán developer workflow, so sánh Rule/Workflow |
| 3   | Nguyễn Văn Bảo | 2A202602862 | Phân tích nhóm bài toán RAG/evaluation, kiểm tra metric và scope |
| 4   | Đàm Việt Hưng | 2A202602600 | Pitch RoadGuardian, owner chính của candidate nhóm chọn |

**Candidate problem nhóm chọn (1 câu):**

Tai nạn giao thông có thể đã xuất hiện trong vùng quan sát của camera nhưng không được phát hiện ngay vì không có người theo dõi liên tục, khiến việc xác minh và chuyển thông tin đến đúng đơn vị xử lý bị bắt đầu muộn.

---

## Phase 3 — Group Convergence: từ 9-12 candidates về 1

### 3.1. Trình bày top 3 mỗi người (mỗi candidate 1-2 phút)

| # | Người đưa ra | Candidate problem | Người gặp vấn đề | Điểm nghẽn | Cảm nhận nhanh của nhóm |
|---|---|---|---|---|---|
| 1 | Phạm Văn Kiên | Notebook/lab AI chạy lỗi nhưng log dài, khó xác định lỗi do code, data path, version thư viện hay runtime. | Sinh viên làm lab AI/ML/DL | Đọc log và khoanh vùng nguyên nhân lỗi, thường mất 20-45 phút/lỗi. | Workflow rõ, pain quen thuộc với nhóm, phù hợp mức Workflow có human review. |
| 2 | Phạm Văn Kiên | Project nhóm hay hỏi lại task, deadline và file mới nhất vì quyết định nằm rải rác trong chat/GitHub/Drive. | Nhóm sinh viên làm project AI | Tìm lại thông tin cũ hoặc hỏi lại nhóm, làm gián đoạn nhiều người. | Có thể chỉ cần Rule/bảng task; AI chưa chắc cần thiết. |
| 3 | Phạm Văn Kiên | Tổng hợp metric, biểu đồ và kết quả model từ notebook vào báo cáo lab/project mất thời gian. | Sinh viên phụ trách báo cáo kỹ thuật | Diễn giải kết quả thô thành nhận xét kỹ thuật rõ ràng. | Có workflow rõ, nhưng impact chủ yếu trong phạm vi bài nộp/report. |
| 4 | Phạm Đình Hải | Viết code mock và unit test boilerplate cho CRUD/API endpoints lặp đi lặp lại. | Fresher/Junior Backend Developer | Tạo mock data và nghĩ edge cases cho từng endpoint. | Rất thực tế với developer; metric thời gian/coverage rõ. |
| 5 | Phạm Đình Hải | Tổng hợp Git commits và Jira tickets để viết changelog/release notes mỗi sprint. | Junior Dev hoặc Release Engineer | Phân loại 25-30 commit thiếu chuẩn thành Features/Bugfix/Refactor. | Workflow tốt nhưng phụ thuộc quyền truy cập Git/Jira. |
| 6 | Phạm Đình Hải | Phân tích server log dài để tìm root cause lỗi HTTP 500/crash staging. | Fresher Dev trực debug | Đọc ngược stack trace qua nhiều tầng framework/thư viện. | Bài kỹ thuật mạnh, nhưng gần với problem debug log của Kiên. |
| 7 | Nguyễn Văn Bảo | Sau mỗi lần eval RAG, phải đọc thủ công câu trả lời sai để phân loại lỗi retrieval/generation/format. | Người xây pipeline RAG pháp luật tiếng Việt | Đọc câu sai, mở context retrieve và tự gắn nhãn nguyên nhân lỗi. | Rất đúng domain AI/RAG, nhưng số đo trong file còn nhiều placeholder cần validate. |
| 8 | Nguyễn Văn Bảo | Log score/config của từng lần chạy pipeline không có hệ thống nên khó so sánh phiên bản. | Người xây pipeline RAG và nhóm review | Quên log hoặc phải lục lại notebook cũ/chạy lại để lấy số. | Có thể giải bằng Rule/script trước, AI không phải phần chính. |
| 9 | Nguyễn Văn Bảo | Sửa system prompt theo kiểu thử-sai, không có checklist hoặc bộ test cố định. | Người thiết kế prompt cho RAG pipeline | Đánh giá cải thiện prompt bằng cảm giác trên vài câu mẫu. | Có liên quan AI rõ, nhưng metric “prompt tốt hơn” khó chốt trong Phase 3. |
| 10 | Đàm Việt Hưng | Tai nạn xuất hiện trên camera nhưng không được phát hiện ngay vì không có người giám sát liên tục. | Đơn vị giám sát, CSGT/cứu hộ, người gặp tai nạn | Khoảng trống “camera ghi được sự kiện” → “người có trách nhiệm biết có sự kiện cần kiểm tra”. | Pitch mạnh nhất: actor rộng nhưng rõ, impact xã hội cao, metric tốt, boundary human review rõ. |
| 11 | Đàm Việt Hưng | Sau khi biết có tai nạn, việc xác định chính xác camera/vị trí/timestamp còn thủ công. | Nhân viên tiếp nhận/điều hành sự cố giao thông | Mapping sự cố → camera → location → timestamp. | Có thể giải nhiều bằng metadata/rule, chưa chắc cần AI. |
| 12 | Đàm Việt Hưng | Sau tai nạn phải tìm đúng timestamp và trích xuất đoạn video trước/sau sự kiện để xác minh. | CSGT/quản trị camera/người xác minh sự cố | Tìm đúng đoạn recording và export clip. | Workflow rõ nhưng là bài toán sau khi tai nạn đã được biết, impact thấp hơn phát hiện sớm. |

### 3.2. Gom trùng / cluster (gom 9-12 ý thành 3-4 cụm)

| Cluster | Candidates included | Pattern chung | Ghi chú |
|---|---|---|---|
| A — Developer / coding workflow | #1, #4, #5, #6 | Giảm thời gian debug, viết test, xử lý log hoặc tổng hợp release notes trong công việc kỹ thuật. | Có metric rõ và nhóm hiểu domain, nhưng impact chủ yếu trong phạm vi developer/team nội bộ. |
| B — Project / học tập / báo cáo nhóm | #2, #3 | Giảm việc hỏi lại thông tin, tổng hợp kết quả notebook và viết báo cáo project. | Gần với trải nghiệm sinh viên, dễ validate trong lớp, nhưng một số bài có thể giải bằng template/rule đơn giản. |
| C — RAG / AI evaluation workflow | #7, #8, #9 | Cải thiện vòng lặp thử nghiệm pipeline RAG: phân loại lỗi, log score/config, quản lý prompt. | Domain AI sâu, nhưng vài ô còn thiếu số thật và có nguy cơ quá hẹp cho cả nhóm. |
| D — RoadGuardian / giao thông thông minh | #10, #11, #12 | Camera đã ghi dữ liệu nhưng workflow phát hiện, mapping vị trí và trích xuất bằng chứng còn chậm/thủ công. | Có câu chuyện problem-first tốt, tác động xã hội rõ, nhưng cần validate kỹ về dữ liệu, privacy và false alert. |

### 3.3. Shortlist (giữ 2-3 bài trả lời được 7 câu hỏi worksheet)

| Candidate | Vì sao vào shortlist (2-3 ý) | Rủi ro / điều chưa rõ |
|---|---|---|
| #10 — RoadGuardian: phát hiện sớm tai nạn từ camera không được giám sát liên tục | Actor và workflow rõ: camera ghi hình → chưa ai phát hiện → người có trách nhiệm nhận/xác minh. Impact cao vì detection latency ảnh hưởng thời điểm bắt đầu xử lý sự cố. Có metric tốt: Detection Latency, Recall, False Alert Rate, Human Verification Time. | Cần validate camera nào không được giám sát liên tục, baseline detection latency hiện tại và quyền truy cập dữ liệu camera. False alert cao có thể gây alert fatigue cho người vận hành. |
| #4 — Sinh unit test boilerplate và edge cases cho API | Workflow developer rõ, lặp lại thường xuyên, có metric thời gian/test case và coverage. Nhóm dễ hiểu cách Rule/Workflow/AI hỗ trợ mà vẫn có human review. | Impact xã hội thấp hơn RoadGuardian; rủi ro AI sinh test pass ảo hoặc dùng sai framework nếu thiếu context codebase. |
| #7 — Phân loại lỗi câu trả lời sai trong pipeline RAG | Rất đúng bối cảnh AI, có bottleneck rõ ở bước đọc câu sai và phân loại retrieval/generation. Nếu làm tốt sẽ tăng tốc vòng lặp cải thiện pipeline. | File cá nhân còn nhiều placeholder số liệu; scope pháp luật/RAG khá hẹp, cả nhóm chưa chắc có đủ shared domain để validate nhanh. |

### 3.4. Score để đồng thuận (chấm 1-5, ép nói rõ vì sao cho 5 / cho 3)

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| #10 RoadGuardian — phát hiện sớm tai nạn từ camera | 5 | 5 | 4 | 5 | 4 | 5 | 5 | 33 |
| #4 Sinh unit test boilerplate cho API | 5 | 5 | 4 | 4 | 5 | 5 | 4 | 32 |
| #7 Phân loại lỗi câu trả lời sai trong RAG | 4 | 5 | 2 | 4 | 4 | 4 | 3 | 26 |

**Candidate nhóm chọn (1 bài duy nhất):**

```text
RoadGuardian — Phát hiện sớm tai nạn giao thông từ camera không được giám sát liên tục.
```

**Vì sao chọn (4-5 câu):**

```text
Nhóm chọn candidate của Đàm Việt Hưng vì đây là problem có tác động lớn hơn phạm vi học tập/developer workflow: nếu phát hiện chậm, việc xác minh và phản ứng chính thức cũng bắt đầu chậm. Workflow hiện tại nhìn được rõ: tai nạn xảy ra → camera ghi hình → chờ người trực/người dân phát hiện → tiếp nhận → xác minh → chuyển thông tin xử lý. Bottleneck tập trung đúng một đoạn: camera đã có dữ liệu nhưng hệ thống/con người chưa biết có sự kiện cần kiểm tra. Bài này cũng có metric đủ rõ để validate như Detection Latency, Accident Recall, False Alert Rate và Human Verification Time. So với bài unit test, RoadGuardian khó prototype hơn một chút nhưng pitch có impact xã hội mạnh hơn và có boundary tốt: AI chỉ tạo suspected incident, con người vẫn xác minh trước mọi hành động chính thức.
```

**Vì sao KHÔNG chọn các candidate còn lại (mỗi bài 2-3 câu):**

```text
Không chọn #4 Sinh unit test boilerplate cho API làm candidate cuối vì đây là bài rất tốt về workflow kỹ thuật nhưng impact chủ yếu nằm trong team developer. Rủi ro chính là AI có thể sinh test pass ảo hoặc sai framework, nên nếu làm sâu cần codebase thật để validate; trong lab hôm nay nhóm muốn chọn bài có câu chuyện người dùng và tác động xã hội rõ hơn.

Không chọn #7 Phân loại lỗi RAG vì đây là bài đúng domain AI và có bottleneck rõ, nhưng số liệu trong file cá nhân còn nhiều placeholder cần đo lại. Ngoài ra scope RAG pháp luật khá chuyên sâu, không phải mọi thành viên đều có đủ domain context để challenge mạnh trong thời gian ngắn.

Không chọn các bài còn lại vì một số bài có thể giải phần lớn bằng Rule hoặc template trước, ví dụ bảng task nhóm, log score/config, mapping camera-location-timestamp. Một số bài khác là phần sau của workflow RoadGuardian, như trích xuất video sau tai nạn, nên phù hợp giữ làm sub-problem thay vì chọn làm candidate chính.
```

**Disagreement (nếu có — ai lo gì, chốt ra sao):**

```text
Nhóm có một điểm phân vân: bài #4 Sinh unit test boilerplate dễ làm prototype hơn và điểm chấm theo tiêu chí lab cao hơn ở phần “làm trong lab” và “nhóm hiểu domain”. Tuy nhiên, Đàm Việt Hưng bảo vệ RoadGuardian bằng cách thu hẹp scope: không xây agent tự xử lý tai nạn, chỉ xét lớp phát hiện suspected accident từ camera và bắt buộc human verification. Nhóm thống nhất chọn RoadGuardian với điều kiện Phase 4 phải validate ba điểm: problem có thật không, detection latency có phải bottleneck chính không, và false alert ở mức nào thì người vận hành còn chấp nhận được.
```

---

## Phase 4 — Quick Validation + Research

### 4.1. Quick validation (ít nhất 1 cách: interview 2-3 người hoặc survey 5-10 người)

| Nguồn | Số người / mẫu | Tín hiệu xác nhận (kèm quote nguyên văn) | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Interview | Chưa thực hiện | Chưa có quote nguyên văn để xác nhận detection latency hoặc số camera/người trực. | Chưa có dữ liệu phản bác. | Giữ đây là candidate problem, chưa kết luận production. Cần phỏng vấn 2-3 operator/nhân viên trực camera. |
| Survey / poll | Chưa thực hiện | Chưa có mẫu khảo sát. | Chưa biết mức độ phổ biến của việc camera ghi được sự cố nhưng không có người phát hiện. | Cần khảo sát 5-10 người thuộc nhóm vận hành hoặc tiếp nhận sự cố. |
| Log / ticket / review (nếu có) | Chưa có quyền truy cập | Chưa có log detection-to-review hoặc thời gian tìm clip. | Chưa có. | Không dùng số liệu công khai về tai nạn để suy ra bottleneck camera. |

**Insight sau validation (1-2 câu — pain thật nằm ở đâu):**

```text
Insight hiện tại là một giả thuyết cần kiểm chứng: pain có thể nằm ở khoảng thời gian từ “camera ghi được sự kiện” đến “người có trách nhiệm nhận được tín hiệu để review”. Các số liệu về mức độ nghiêm trọng của tai nạn chỉ cung cấp context, không chứng minh trực tiếp giả thuyết này.
```

Bằng chứng đính kèm (nếu có): `02-group-problem-statement-survey.png`, `...-interview-notes.md`

### 4.2. Research giải pháp đã có (ít nhất 2-3 tools/patterns + 1-2 link kiểm được)

| Nguồn / tool / case | Link | Họ giải quyết bước nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| WHO Road Traffic Injuries | https://www.who.int/news-room/fact-sheets/detail/road-traffic-injuries/ | Cung cấp context về mức độ nghiêm trọng của tai nạn giao thông | Nguồn chính thức, phạm vi toàn cầu | Không chứng minh camera không được giám sát là nguyên nhân gây chậm | Tách context khỏi evidence của workflow |
| NVIDIA DeepStream SDK | https://developer.nvidia.com/deepstream-sdk | Phân tích video stream và xây pipeline event detection | Có pattern xử lý video thời gian thực | Cần dữ liệu, phần cứng, quyền camera và kiểm tra độ chính xác | Prototype nên giới hạn vào camera/video được cấp quyền |
| OpenCV Background Subtraction | https://docs.opencv.org/4.x/d1/dc5/tutorial_background_subtraction.html | Làm baseline rule cho chuyển động/bất thường | Có thể thử nghiệm nhanh, không cần Agent | Dễ false positive, không hiểu ngữ cảnh tai nạn | Phải so sánh Rule với detector AI trước khi chọn AI |

**Research takeaway (2-3 câu — nên build gì / không build gì):**

```text
Không nên xây autonomous Agent hoặc tự điều động lực lượng. Hướng phù hợp là Workflow: camera được cấp quyền → Rule/AI tạo suspected incident → đính kèm metadata và clip → human review → chuyển workflow chính thức. Rule-based detection và quy trình hiện tại phải được giữ làm baseline/fallback.
```

> Lưu ý: không dùng số liệu AI đưa nếu không verify được link chính thức. Ghi rõ giả định chưa chắc.

---

## Phase 5 — Workflow + Problem Statement

### 5.1. Current workflow bản nhóm

Dán workflow hoặc link file: `02-group-problem-statement-workflow.png/pdf/md`

```text
[1 Tai nạn xảy ra] → [2 Camera ghi hình] → [3 Chờ người phát hiện: bottleneck]
→ [4 Tiếp nhận] → [5 Xác minh] → [6 Xác định vị trí] → [7 Chuyển thông tin]
```

**Before — trạng thái hiện tại:** 7 bước, tổng thời gian từ lúc tai nạn xảy ra đến lúc có người bắt đầu review **chưa có baseline thực tế**. Điểm nghẽn nằm ở bước 3: camera đã ghi hình nhưng không tạo cảnh báo, nên thời gian chờ phụ thuộc vào người trực, người đi đường hoặc người dân báo lại.

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú (handoff? bottleneck?) |
|---|---|---|---|---|---|
| 1 | Người tham gia giao thông | Sự kiện va chạm | Tai nạn xảy ra | Khi xảy ra; baseline cần validate | Điểm bắt đầu của workflow |
| 2 | Camera | Video stream | Recording | Liên tục | Camera có thể không có người xem |
| 3 | Người trực/người dân | Camera hoặc quan sát | Tín hiệu sự cố | Chưa đo | Bottleneck: camera đã ghi nhưng chưa ai biết |
| 4 | Đơn vị tiếp nhận | Tín hiệu sự cố | Incident record | Chưa đo | Handoff từ người phát hiện |
| 5 | Người xác minh | Incident và video | Confirm/reject | Chưa đo | Human review |
| 6 | Nhân viên xử lý | Incident + metadata | Vị trí chính xác | Chưa đo | Có thể dùng camera mapping |
| 7 | Đơn vị phụ trách | Incident đã xác minh | Hành động xử lý | Chưa đo | Ngoài scope tự động hóa |

**Bottleneck chính (2-3 câu):**

```text
Bottleneck chính là bước Camera ghi hình → Con người phát hiện sự cố. Camera có thể đã lưu video nhưng chưa tạo tín hiệu để người có trách nhiệm bắt đầu kiểm tra. Baseline detection latency và số camera/người trực phải được đo trước khi kết luận mức độ nghiêm trọng.
```

### 5.2. Future workflow bản nhóm

Phải nhìn ra 5 thứ: bước nào máy (Rule), bước nào AI, bước nào người, boundary ở đâu, fallback khi AI sai.

```text
[1 Camera được cấp quyền: máy] → [2 Rule/AI phân tích stream]
→ [3 Suspected Incident + metadata] → [4 Human review: boundary]
→ [5 Confirm và chuyển workflow chính thức]

Fallback: Reject thì bỏ alert và lưu feedback; detector sai, false alert cao hoặc thiếu quyền dữ liệu thì quay về workflow camera hiện tại.
```

**After — trạng thái kỳ vọng:** 5 bước chính, trong đó Rule/AI phát hiện và tạo alert; human vẫn xác minh trước khi chuyển thông tin chính thức. Mục tiêu prototype là median detection latency dưới 10 giây và giảm thời gian human verification nhờ có sẵn camera ID, location, timestamp và clip; các mục tiêu này phải được đo trên dataset được cấp quyền.

**Before/after impact:**

| Metric | Trước | Sau kỳ vọng | Cách đo |
|---|---:|---:|---|
| Detection latency | Chưa có baseline | Median < 10 giây trên dataset prototype | Timestamp tai nạn so với timestamp alert |
| Accident recall | Chưa có baseline | ≥ 90% trên dataset thử nghiệm | Số incident thật được phát hiện / tổng incident |
| False-alert rate | Chưa có baseline | Operator xác định ngưỡng chấp nhận | Alert sai / tổng alert |
| Human verification time | Chưa có baseline | Giảm nhờ metadata và clip | Alert xuất hiện đến confirm/reject |
| Số bước | 7 | 5-6 | Đếm bước current/future |
| Số bước thủ công | Chưa đo | Human review vẫn bắt buộc | Đếm bước do người thực hiện |
| Risk mới | Không có AI hallucination | Có false alert, miss và privacy risk | Review incident và audit quyền truy cập |

**Tóm tắt before/after:**

```text
BEFORE — 7 bước, thời gian chưa đo
Camera ghi hình → chờ người phát hiện → tiếp nhận → xác minh
→ xác định vị trí → chuyển thông tin
				  ^ bottleneck: không có alert tự động

AFTER — 5 bước chính, có human boundary
Camera được cấp quyền → Rule/AI phát hiện → suspected incident
→ human confirm/reject → chuyển workflow chính thức
				  ^ bottleneck mới: human review, nhưng đây là điểm kiểm soát chất lượng
```

### 5.3. Problem Statement v0 (mỗi field 2-3 câu)

| Field | Nội dung |
|---|---|
| **Actor** | Đơn vị hoặc nhân viên tiếp nhận, xác minh và chuyển thông tin sự cố giao thông; CSGT/cứu hộ là các bên nhận thông tin sau xác minh. |
| **Workflow** | Camera ghi hình; người trực hoặc người dân phát hiện; đơn vị tiếp nhận xác minh, xác định vị trí rồi chuyển thông tin cho đơn vị phụ trách. |
| **Bottleneck** | Camera đã ghi được sự kiện nhưng chưa tạo tín hiệu để người có trách nhiệm biết và bắt đầu review. |
| **Impact** | Detection chậm có thể kéo theo xác minh và chuyển thông tin chậm; mức impact thực tế chưa thể định lượng nếu chưa có baseline. |
| **Success Metric** | Đo detection latency, recall, false-alert rate và human verification time. Target prototype là median latency <10 giây và recall ≥90% trên dataset thử nghiệm, không coi đây là baseline production. |
| **Boundary** | Chỉ dùng camera được cấp quyền; AI tạo suspected incident và metadata. Không tự kết luận pháp lý, nhận dạng danh tính không cần thiết, phạt, hoặc điều động lực lượng; human phải confirm/reject trước hành động chính thức. |

**Câu hỏi AI phản biện v0 (nếu có):**
- Field nào mơ hồ: Baseline detection latency, số camera/người trực, độ phổ biến của problem và ngưỡng false alert còn chưa có dữ liệu.
- Tôi sửa gì: Đánh dấu target là prototype target, thêm non-AI baseline, giới hạn camera được cấp quyền và giữ human review làm boundary.

---

## Phase 6 — Rule / Workflow / Agent + Decision

### 6.0. Ma trận độ phù hợp (suy nghĩ nhanh, không thay quyết định cuối)

- Độ mơ hồ: [ ] Thấp (có đúng/sai rõ) / [x] Cao (nhiều cách trả lời vẫn OK) — Vì sao: nhiều tình huống trong video có thể giống tai nạn; ngưỡng cảnh báo cần người review.
- Độ phức tạp: [ ] Thấp (1-2 bước) / [x] Cao (3+ bước/nguồn, phụ thuộc nhau) — Vì sao: workflow nối camera stream, detector, metadata, alert queue và human review.

**Bài toán nhóm nằm ở ô nào:**

```text
Bài toán nằm ở ô độ mơ hồ cao + độ phức tạp cao, nhưng intervention được giới hạn trong flow cố định: phát hiện → tạo suspected incident → human review → chuyển thông tin.
```

**Vì sao (2-3 câu):**

```text
Rule có thể làm baseline cho tín hiệu đơn giản; Workflow phù hợp hơn vì cần nối nhiều bước và giữ điểm kiểm soát của con người. Agent chưa cần thiết vì hệ thống chưa phải tự lập kế hoạch hoặc tự gọi nhiều công cụ theo tình huống mở.
```

### 6.1. So sánh Rule / Workflow / Agent (so trên cùng 1 bài)

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? (Dùng cho bước nào?) |
|---|---|---|---|---|
| **Rule** | Ngưỡng chuyển động, dừng xe, va chạm hoặc bất thường | Camera cố định và case đơn giản | False positive, bỏ sót, khó hiểu ngữ cảnh | Dùng làm baseline detection |
| **Workflow** | Detector/Rule → suspected incident → metadata/clip → human review → chuyển thông tin | Flow nhiều bước nhưng vẫn xác định | Data access, integration, alert fatigue | **Chọn cho pilot** |
| **Agent** | Tự lập kế hoạch, gọi tool và tự điều phối xử lý | Chỉ khi cần xử lý nhánh phức tạp có owner rõ | Khó kiểm soát, rủi ro an toàn/pháp lý | Không chọn |

**5 câu hỏi chốt (trả lời câu đầy đủ):**
1. Rule có thể giải quyết một phần case đơn giản, nhưng chưa biết có đạt 70-80% vì chưa có dataset; nhóm phải đo thay vì giả định.
2. Flow chính đi khá thẳng từ phát hiện đến alert và review, chỉ rẽ ở Confirm/Reject.
3. Chưa cần Agent tự lập kế hoạch hoặc gọi tool vì các bước và boundary đã xác định.
4. Human reviewer phát hiện alert sai trước hành động chính thức; thời gian sửa và ngưỡng chấp nhận phải được đo trong pilot.
5. Có thể hạ từ Workflow xuống Rule hoặc quay về quy trình camera hiện tại nếu false alert, recall hoặc privacy không đạt.

**Mức chọn:**

```text
[Workflow — Rule làm baseline, Human Verification là bắt buộc]
```

**Vì sao chọn (3-4 câu):**

```text
Chọn Workflow vì bài toán cần nối detector, metadata, clip, hàng đợi cảnh báo và human review. Workflow vẫn giới hạn hành động của hệ thống và không tự kết luận pháp lý. Rule được giữ làm baseline; Agent chưa có lợi ích tương xứng với rủi ro.
```

**Vì sao không chọn mức đơn giản hơn (2-3 câu):**

```text
Không chọn chỉ Rule vì rule khó bao phủ các tình huống video khác nhau và không đủ để quản lý handoff, metadata, review và fallback. Không chọn Agent vì chưa cần lập kế hoạch động, chưa có quyền/tool integration và mọi hành động chính thức vẫn phải do người phụ trách xác nhận.
```

### 6.2. Problem Statement v1 (v0 sửa chặt hơn + 3 field cuối)

| Field | Nội dung |
|---|---|
| **Actor** | Đơn vị/nhân viên tiếp nhận và xác minh sự cố giao thông; owner pilot là người phụ trách review alert. |
| **Workflow** | Camera được cấp quyền ghi hình → Rule/AI phân tích → tạo suspected incident kèm metadata/clip → human confirm/reject → chuyển workflow chính thức hoặc bỏ alert. |
| **Bottleneck** | Khoảng trống từ camera ghi được sự kiện đến lúc người có trách nhiệm biết để review. |
| **Impact** | Có khả năng làm chậm thời điểm xác minh và chuyển thông tin; cần baseline detection latency và verification time để định lượng. |
| **Success Metric** | Prototype: median detection latency <10 giây, recall ≥90%; đồng thời false-alert rate và human verification time phải nằm trong ngưỡng operator chấp nhận. |
| **Boundary** (làm / không làm) | Làm: phân tích video được cấp quyền, tạo suspected incident, gắn camera ID/location/timestamp/clip/confidence. Không làm: tự kết luận trách nhiệm, nhận dạng không cần thiết, phạt, điều động lực lượng hoặc thu camera tư nhân khi chưa consent. |
| **AI intervention point** (can thiệp sau bước nào, trước bước nào) | Can thiệp sau bước camera ghi hình và trước bước người trực phát hiện; output chỉ là suspected incident để human review. |
| **Mức chọn** (Rule / Workflow / Agent + 1 câu vì sao) | Workflow, vì có chuỗi bước cố định cần metadata, alert queue và human handoff; Rule là baseline, Agent không cần thiết. |
| **Rủi ro & người thật kiểm tra** (rủi ro lớn nhất + ai kiểm tra bằng cách nào) | False alert, miss, privacy và alert fatigue; operator review từng alert trước khi confirm, audit camera consent, theo dõi recall/false-alert rate và rollback nếu không đạt. |

### 6.3. Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú (câu đầy đủ) |
|---|---|---|
| Actor + workflow rõ chưa? | Yes | Actor, 7 bước hiện tại, bottleneck và human boundary đã mô tả được. |
| Baseline + metric đo được chưa? | Not Yet | Metric đã định nghĩa nhưng chưa có số đo thực tế từ operator hoặc log camera. |
| Data/input đủ dùng chưa? | Not Yet | Chưa có dataset thử nghiệm được cấp quyền và chưa chốt quyền truy cập camera. |
| AI sai, hậu quả chấp nhận được không? | Not Yet | Chỉ chấp nhận trong pilot offline có human review; chưa đủ bằng chứng để triển khai thật. |
| Có người review/owner không? | Yes | Đơn vị/nhân viên tiếp nhận và xác minh là owner dự kiến. |
| Có cách non-AI đơn giản hơn không? | Yes | Rule, mapping metadata và quy trình camera hiện tại là alternative/baseline. |

**Decision:**

```text
[Not Yet]
```

**Lý do (3-4 câu dựa trên bằng chứng):**

```text
Problem đáng được kiểm chứng vì workflow và bottleneck đã rõ, nhưng nhóm chưa có interview/log, baseline detection latency, dataset, quyền camera và thỏa thuận privacy. Vì vậy chưa thể kết luận Go production hoặc khẳng định AI tốt hơn Rule. Nhóm chỉ nên tiến hành pilot offline quy mô nhỏ, có human review và so sánh với baseline Rule.
```

**Nếu Go — pilot nhỏ nhất (data nào, chạy tay ra sao, đo 3 số nào):**

```text
Chạy tay trên video giao thông được cấp quyền, không kết nối điều động thật. So sánh một baseline Rule với detector AI; đo detection latency, recall và false-alert rate, sau đó ghi thêm human verification time. Chỉ mở rộng khi operator xác nhận ngưỡng false alert và quyền sử dụng dữ liệu.
```

**Nếu Not Yet — cần validate gì trước:**

```text
Trước tiên cần phỏng vấn 2-3 người vận hành/tiếp nhận sự cố hoặc khảo sát 5-10 người; đo số camera/người trực, detection latency, thời gian review và false-alert tolerance; xin dataset/video có consent; kiểm tra privacy và xác nhận owner human review.
```

**Nếu No-Go — làm gì thay AI:**

```text
Nếu validation cho thấy detection không phải bottleneck hoặc Rule đã đủ tốt, dùng Rule + metadata mapping + workflow review thay cho AI.
```

**Exit / rollback (khi nào dừng AI, quay về cách cũ):**

```text
Dừng AI và quay về workflow camera hiện tại nếu false alert gây quá tải, recall không đạt target, dữ liệu thiếu consent, operator không thể review, hoặc AI không cải thiện đáng kể so với Rule. Không tự gửi cảnh báo chính thức khi human review hoặc camera permission không hợp lệ.
```

---

### Self-check nộp phần 02 (nhóm)
- [x] Có nhật ký hội tụ 9-12 → 1 (cluster + shortlist + score)
- [ ] Validation quote thật chưa có; cần thực hiện interview/survey trước khi nộp chính thức. Research đã có link kiểm được.
- [x] Có workflow trước/sau, handoff, bottleneck, boundary, fallback
- [x] Có PS v0 → v1, metric có trước/sau + cách đo, boundary có làm/không làm
- [x] Có so sánh Rule/Workflow/Agent + Decision Not Yet có lý do
