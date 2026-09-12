# 01 — Individual Problem Scan

## Thông tin cá nhân

- **Họ và tên:** Đàm Việt Hưng
- **Mã học viên:** 2A202602600
- **Vai trò / bối cảnh:** Sinh viên năm cuối — Phenikaa University

---

# Phase 1 — Scan 5+ Problems

## Chủ đề quan tâm

**RoadGuardian – Phát hiện sớm tai nạn giao thông từ camera đường phố và hỗ trợ cảnh báo cơ quan chức năng**

### Bối cảnh

Hiện nay, nhiều tuyến đường, ngã tư, khu dân cư, cửa hàng và nhà dân đã có camera quan sát. Tuy nhiên, **camera đang ghi hình không đồng nghĩa với việc luôn có người theo dõi camera 24/7**.

Khi tai nạn xảy ra trong vùng quan sát của camera, video có thể đã ghi lại sự việc nhưng sự cố chưa chắc được phát hiện ngay. Việc phát hiện hiện có thể phụ thuộc vào người trực camera, người đi đường hoặc người dân chủ động báo sự cố.

Vì vậy, vấn đề được khảo sát không bắt đầu từ câu hỏi:

> “Làm thế nào để xây AI nhận diện tai nạn?”

Mà bắt đầu từ:

> **Làm thế nào để một sự cố giao thông xuất hiện trong camera được phát hiện và đưa đến đúng người xử lý nhanh hơn, đặc biệt với những camera không có người giám sát liên tục?**

---

## 1. Problem Scan

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu / bằng chứng cần kiểm chứng |
|---|---|---|---|---|
| 1 | Lặp lại | Phải theo dõi nhiều camera giao thông liên tục để tìm sự cố | Nhân viên trung tâm giám sát | Camera hoạt động liên tục; số camera/người trực cần validate |
| 2 | Tốn thời gian | Khi nhận thông tin sự cố phải tìm đúng camera hoặc vị trí xảy ra | Nhân viên điều hành / CSGT | Cần đo thời gian xác định camera/vị trí thực tế |
| 3 | AI có thể tốt hơn | Camera vẫn ghi hình nhưng không có người nhìn vào đúng thời điểm tai nạn xảy ra | Đơn vị giám sát, người gặp tai nạn | Candidate chính; detection latency thực tế cần validate |
| 4 | Tốn thời gian | Sau khi phát hiện sự cố phải xác định vị trí, camera và timestamp | Người tiếp nhận cảnh báo | Có thể tự động hóa nếu camera có metadata |
| 5 | Pain từ người khác | Người đi đường phải chủ động gọi điện/báo khi chứng kiến tai nạn | Người tham gia giao thông, cơ quan chức năng | Cần khảo sát mức phụ thuộc vào báo cáo của người dân |
| 6 | Lặp lại | Người trực phải phân biệt tai nạn thật với xe dừng, ùn tắc hoặc sự kiện bình thường | Người giám sát | Nhiều tình huống hình ảnh có thể giống tai nạn |
| 7 | AI có thể tốt hơn | Camera nhà dân/cửa hàng có thể ghi được tai nạn nhưng dữ liệu thường chỉ được xem lại sau sự kiện | Chủ camera, cơ quan chức năng | Cần validate khả năng hợp tác, quyền truy cập và privacy |
| 8 | Tốn thời gian | Sau tai nạn phải tìm và trích xuất đúng đoạn video trước/sau sự kiện | CSGT / quản trị camera | Cần đo thời gian tìm timestamp và xuất clip |
| 9 | Pain từ người khác | Người trực có thể bị quá tải khi số camera cần giám sát tăng | Trung tâm vận hành | Số camera/người trực cần validate |
| 10 | AI có thể tốt hơn | Camera chủ yếu ghi hình nhưng chưa tự nhận biết sự kiện bất thường cần xử lý | Đơn vị vận hành camera | Computer Vision có thể hỗ trợ anomaly/event detection |

### Pattern quan sát được

```text
Camera nhìn thấy sự việc
        ≠
Hệ thống biết tai nạn vừa xảy ra
        ≠
Người có trách nhiệm đã nhận được cảnh báo
```

Khoảng trống đáng chú ý nằm giữa:

**“Camera ghi được sự kiện” → “Con người biết rằng có sự kiện cần xử lý”.**

---

## AI đã dùng ở Phase 1

- **Prompt đã hỏi:** Phân tích vấn đề phát hiện tai nạn giao thông từ camera và xác định liệu AI có thực sự cần thiết.
- **Ý dùng được:** AI có thể đóng vai trò lớp phát hiện sự kiện, thay vì thay thế toàn bộ hệ thống giám sát và xử lý.
- **Ý bỏ vì không phải pain thật:** “AI tự điều hành giao thông”, “AI tự xác định người gây tai nạn”, “AI tự động điều động lực lượng”. Các ý này vượt quá bottleneck đang khảo sát.

---

# Phase 2 — Top 3 Problem Cards

## 2.1. Chọn Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| **1** | Tai nạn xuất hiện trên camera nhưng không được phát hiện ngay vì không có người giám sát liên tục | Tác động trực tiếp tới detection latency; workflow rõ; có thể thử nghiệm bằng video | Detection latency thực tế? Camera nào không được giám sát liên tục? |
| **2** | Sau khi biết có tai nạn, việc xác định chính xác vị trí/camera/thời điểm còn thủ công | Workflow rõ; metadata camera có thể hỗ trợ mạnh | Đây có thực sự là bottleneck lớn không? |
| **3** | Tìm và trích xuất đoạn video liên quan sau tai nạn mất thời gian | Pain tiềm năng rõ; dễ đo thời gian | Impact có thể thấp hơn bài toán phát hiện sớm |

---

# 2.2. Problem Cards chi tiết

## Problem Card #1 — Phát hiện tai nạn từ camera không được giám sát 24/7

### Problem 1 câu

Một số camera giao thông hoặc camera dân cư có thể ghi được tai nạn nhưng không có người theo dõi liên tục, khiến sự kiện có nguy cơ chỉ được biết khi có người trực tiếp nhìn thấy hoặc chủ động báo lại.

### Actor

**Primary Actor:** Nhân viên/đơn vị chịu trách nhiệm tiếp nhận, xác minh và xử lý thông tin sự cố giao thông.

**Secondary Actors:**

- Cảnh sát giao thông.
- Đơn vị cứu hộ/cứu nạn.
- Người tham gia giao thông.
- Nạn nhân.
- Chủ camera tư nhân tự nguyện tham gia.

### Thời điểm / bối cảnh

Problem xảy ra khi:

- Camera đang hoạt động.
- Tai nạn xảy ra trong vùng quan sát.
- Không có người chú ý đúng camera tại đúng thời điểm.
- Hoặc camera thuộc nhà dân/cửa hàng và không có người theo dõi livestream.
- Chưa có nguồn khác báo sự cố.

### Current workflow

1. Tai nạn xảy ra.
2. Camera ghi lại sự kiện.
3. Chờ người trực/người dân/người đi đường phát hiện.
4. Đơn vị phụ trách tiếp nhận thông tin.
5. Xác minh sự cố.
6. Xác định vị trí.
7. Chuyển thông tin cho đơn vị có trách nhiệm.

### Bottleneck

```text
Camera đã ghi được tai nạn
        ↓
Nhưng hệ thống chưa biết rằng
có sự kiện cần người kiểm tra
```

**Bottleneck chính: bước Camera ghi hình → Con người phát hiện sự cố.**

### Impact

```text
Tai nạn xảy ra
      ↓
Phát hiện chậm
      ↓
Xác minh bắt đầu chậm
      ↓
Thông tin đến người xử lý chậm
      ↓
Khả năng phản ứng bắt đầu muộn hơn
```

### Success metric

**1. Detection Latency**

```text
Detection Latency =
Thời điểm phát hiện sự cố
-
Thời điểm tai nạn bắt đầu
```

Prototype target: **Median Detection Latency < 10 giây trên dataset thử nghiệm.**

**2. Accident Recall**

```text
Trong 100 tai nạn thực tế,
hệ thống phát hiện được bao nhiêu?
```

Prototype target: **Recall ≥ 90%.**

**3. False Alert Rate**

Đo số cảnh báo không phải tai nạn trong tổng số alert được tạo.

**4. Human Verification Time**

Đo thời gian:

```text
Alert xuất hiện
→
Human Confirm / Reject
```

### Non-AI alternative

- Tăng số nhân viên trực camera.
- Tiếp tục dựa vào người dân/người đi đường báo sự cố.
- Dùng rule-based detection như xe giảm tốc đột ngột hoặc đứng yên bất thường.

### AI hypothesis

Computer Vision có thể phân tích video từ những camera được cấp quyền, phát hiện pattern nghi ngờ tai nạn và chuyển thành **Suspected Incident**, để con người kiểm tra thay vì yêu cầu con người quan sát liên tục toàn bộ video stream.

### Quick gut

- [ ] No AI / process fix
- [ ] Rule
- [x] **Workflow**
- [ ] Agent
- [ ] Chưa biết

Candidate solution:

```text
Computer Vision
      +
Rule / Threshold
      +
Workflow
      +
Human Verification
```

### Draft workflow Card #1

```text
CURRENT STATE — thời gian chưa xác định

[1 Tai nạn]
      ↓
[2 Camera ghi hình]
      ↓
[3 Chờ con người phát hiện]  ← BOTTLENECK
      ↓
[4 Tiếp nhận]
      ↓
[5 Xác minh]
      ↓
[6 Xác định vị trí]
      ↓
[7 Chuyển thông tin]
      ↓
[8 Xử lý]


FUTURE STATE

[1 Tai nạn]
      ↓
[2 Camera ghi hình]
      ↓
[3 AI phân tích video]
      ↓
[4 Suspected Incident]
      ↓
[5 HUMAN REVIEW]  ← HUMAN BOUNDARY
      ↙       ↘
   Reject    Confirm
               ↓
[6 Chuyển thông tin]
               ↓
[7 Cơ quan chức năng xử lý]
```

**Fallback:** Nếu AI không đủ tin cậy hoặc false alert quá cao, tắt AI Detection Layer và quay lại workflow camera hiện tại. Hệ thống camera vẫn tiếp tục hoạt động bình thường.

---

# Problem Card #2 — Xác định camera/vị trí/thời điểm sự cố

### Problem 1 câu

Sau khi nhận được thông tin về một tai nạn, người tiếp nhận có thể phải xác định camera, vị trí và thời điểm xảy ra sự cố trước khi chuyển thông tin cho người xử lý.

### Actor

Nhân viên tiếp nhận/điều hành sự cố giao thông.

### Thời điểm / bối cảnh

Khi đã có thông tin rằng một sự cố xảy ra nhưng cần xác định chính xác camera và vị trí tương ứng.

### Current workflow

1. Nhận thông tin tai nạn.
2. Xác định khu vực.
3. Tìm camera liên quan.
4. Xác định timestamp.
5. Xác minh thông tin.
6. Chuyển cho đơn vị xử lý.

### Bottleneck

Việc mapping:

```text
Sự cố
→
Camera
→
Location
→
Timestamp
```

có thể còn thủ công.

### Impact

Làm tăng thời gian từ lúc tiếp nhận thông tin đến lúc incident có đủ dữ liệu để xử lý.

### Success metric

**Thời gian xác định camera + vị trí + timestamp.**

Baseline hiện tại: **[CẦN VALIDATE]**

### Non-AI alternative

Xây database mapping:

```text
Camera ID
→
GPS / Location
→
Khu vực
→
Đơn vị phụ trách
```

### AI hypothesis

AI không nhất thiết cần thiết. Metadata và workflow automation có thể giải quyết phần lớn problem.

### Quick gut

- [ ] No AI / process fix
- [x] **Rule**
- [x] **Workflow**
- [ ] Agent
- [ ] Chưa biết

### Draft workflow Card #2

```text
CURRENT STATE

[Nhận tin]
    ↓
[Xác định khu vực]
    ↓
[Tìm camera]  ← BOTTLENECK
    ↓
[Xác định location/timestamp]
    ↓
[Chuyển thông tin]


FUTURE STATE

[Nhận incident]
      ↓
[Camera ID tự động mapping]
      ↓
[Location + Timestamp tự động]
      ↓
[Human Review]  ← HUMAN BOUNDARY
      ↓
[Chuyển thông tin]
```

**Fallback:** Nếu metadata thiếu hoặc mapping sai, người trực xác định camera/vị trí theo workflow hiện tại.

---

# Problem Card #3 — Tìm và trích xuất video sau tai nạn

### Problem 1 câu

Sau khi một tai nạn đã được biết, người quản lý camera có thể phải tìm đúng timestamp và trích xuất đoạn video trước/sau sự kiện để phục vụ xác minh.

### Actor

CSGT / nhân viên quản trị camera / người chịu trách nhiệm xác minh sự cố.

### Thời điểm / bối cảnh

Sau khi tai nạn đã được phát hiện và cần video liên quan để xác minh hoặc hậu kiểm.

### Current workflow

1. Nhận yêu cầu tìm video.
2. Xác định camera.
3. Xác định thời điểm tai nạn.
4. Tìm timestamp trong recording.
5. Xem lại video.
6. Trích xuất đoạn cần thiết.

### Bottleneck

```text
Recording dài
    ↓
Tìm đúng timestamp
    ↓
Xác định đoạn trước/sau sự kiện
    ↓
Export clip
```

### Impact

Tăng thời gian tìm kiếm và cung cấp bằng chứng video sau sự cố.

### Success metric

**Thời gian từ lúc nhận yêu cầu → xuất được đúng video clip.**

Baseline: **[CẦN VALIDATE]**

### Non-AI alternative

- Cho phép tìm recording theo timestamp.
- Chuẩn hóa Camera ID.
- Lưu metadata sự cố.
- Tạo bookmark khi có incident.

### AI hypothesis

Khi phát hiện một suspected incident, hệ thống có thể tự động lưu:

```text
X giây trước event
+
Event
+
Y giây sau event
```

và gắn Camera ID, timestamp, location để người dùng không phải tìm thủ công.

### Quick gut

- [ ] No AI / process fix
- [ ] Rule
- [x] **Workflow**
- [ ] Agent
- [ ] Chưa biết

### Draft workflow Card #3

```text
CURRENT STATE

[Nhận yêu cầu]
      ↓
[Tìm camera]
      ↓
[Tìm timestamp]  ← BOTTLENECK
      ↓
[Xem recording]
      ↓
[Export clip]


FUTURE STATE

[Incident xảy ra]
      ↓
[System bookmark timestamp]
      ↓
[Tự lưu pre/post-event clip]
      ↓
[Human Review]  ← HUMAN BOUNDARY
      ↓
[Export / sử dụng clip]
```

**Fallback:** Nếu hệ thống không tạo được clip tự động, recording gốc vẫn được giữ và người quản trị tìm video theo workflow hiện tại.

---

# 2.3. Card muốn pitch nhất

## Card tôi muốn pitch nhất

**Problem Card #1 — Phát hiện sớm tai nạn từ camera không được giám sát liên tục.**

### Vì sao?

Camera có thể đã ghi được tai nạn nhưng điều đó không đồng nghĩa có người biết sự việc vừa xảy ra. Bottleneck đáng chú ý nằm ở khoảng thời gian từ **“camera ghi được sự kiện” → “người có trách nhiệm biết có sự kiện cần kiểm tra”**.

Problem này có workflow rõ và có thể đo bằng các metric như:

- Detection Latency.
- Accident Recall.
- False Alert Rate.
- Human Verification Time.

Nếu hypothesis đúng, hệ thống có thể chuyển workflow từ:

```text
Con người phải quan sát rất nhiều camera
```

sang:

```text
Camera
   ↓
AI Detection
   ↓
Suspected Incident
   ↓
Human Verification
   ↓
Official Response
```

RoadGuardian vì vậy không được định nghĩa là một **autonomous Agent**, mà là một **AI-assisted Workflow** hỗ trợ con người phát hiện sự cố sớm hơn.

---

## Câu hỏi tôi muốn nhóm challenge

**1. Trong thực tế, việc “camera ghi được tai nạn nhưng không có người phát hiện ngay” có đủ thường xuyên và đủ nghiêm trọng để trở thành bottleneck đáng giải quyết không?**

**2. Nếu AI có recall cao nhưng tạo nhiều false alert, ngưỡng false-alert nào khiến người vận hành bắt đầu mất niềm tin hoặc gặp alert fatigue?**

---

## AI phản biện Card

### Điểm yếu AI chỉ ra

1. Chưa có dữ liệu thực tế về detection latency của hệ thống camera tại Việt Nam.
2. Chưa biết số camera mà một nhân viên thực tế phải giám sát.
3. Camera nhà dân tạo vấn đề về privacy, quyền truy cập và consent.
4. Accident detection ngoài thực tế khó hơn dataset vì góc camera, thời tiết, ban đêm, occlusion và chất lượng video.
5. Recall cao nhưng false positive cao có thể tạo **alert fatigue**.
6. Chưa chứng minh AI tốt hơn rule-based system đủ nhiều để đáng triển khai.

### Tôi sửa gì

- Không khẳng định RoadGuardian phải dùng AI trước validation.
- Thu hẹp AI Intervention vào đúng một bước: **phát hiện suspected accident**.
- Giữ **Human Verification** trước mọi hành động chính thức.
- Camera nhà dân chỉ là **optional data source**, phải có opt-in.
- Đo baseline trước khi đặt production target.
- Prototype trước trên dataset/video thử nghiệm.
- So sánh AI với Rule và workflow thông thường trước quyết định Go/No-Go.

---

# Human Boundary

RoadGuardian **được phép**:

- Phân tích video được cấp quyền.
- Phát hiện sự kiện nghi ngờ.
- Tạo Suspected Incident.
- Đính kèm Camera ID.
- Timestamp.
- Location đã đăng ký.
- Snapshot.
- Video clip.
- Confidence score.

RoadGuardian **không được phép**:

- Tự kết luận ai đúng/ai sai.
- Tự xác định trách nhiệm pháp lý.
- Tự phạt phương tiện.
- Tự nhận dạng danh tính người dân khi không cần thiết.
- Tự điều động lực lượng chỉ dựa trên prediction.
- Thu video camera tư nhân khi chưa được chủ sở hữu đồng ý.

```text
AI Detect
    ↓
Suspected Accident
    ↓
👤 HUMAN VERIFY
   ↙         ↘
Reject     Confirm
              ↓
       Official Workflow
```

---

# Preliminary Decision

Hiện tại:

**Chưa kết luận “phải dùng AI”.**

Cần kiểm chứng ba câu hỏi:

```text
1. Problem có thực sự tồn tại?
          ↓
2. Detection có thực sự là bottleneck?
          ↓
3. AI có tốt hơn Rule / Workflow thông thường
   đủ nhiều để đáng triển khai?
```

### NO-GO

Nếu problem không đủ lớn hoặc detection không phải bottleneck thực sự.

### NOT YET

Nếu problem tồn tại nhưng chưa có đủ dữ liệu, quyền truy cập camera hoặc điều kiện privacy/deployment.

### GO — Scope nhỏ

Nếu prototype chứng minh:

```text
Detection Latency ↓
Recall đủ cao
False Alert chấp nhận được
Human Review vẫn kiểm soát
```

thì RoadGuardian có thể được thử nghiệm ở phạm vi nhỏ như một:

> **AI-assisted Workflow hỗ trợ phát hiện sớm tai nạn giao thông từ camera, không phải autonomous Agent.**