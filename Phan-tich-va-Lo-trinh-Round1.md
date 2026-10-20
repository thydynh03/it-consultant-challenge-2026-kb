# Phân tích cuộc thi, review solution và lộ trình 6 ngày — Round 1

**IT Consultant Challenge 2026 (Netcompany × Code MeLy)** · Lập ngày 20/10/2026 · Nội bộ đội, không chia sẻ ra ngoài

> Tài liệu này **không lặp lại** các báo cáo đã có. Nó chốt quyết định, cập nhật những gì đã thay đổi từ 16/10, bổ sung bằng chứng mới tìm được trên web, và đưa ra lộ trình còn lại đến hạn nộp.
> Chi tiết từng lỗi theo slide: [Danh-gia-OrderFlow-Hoang-va-ATP-Thy.md](Danh-gia-OrderFlow-Hoang-va-ATP-Thy.md) (mã D1-xx, D2-xx, C-xx).

---

## 0. Tóm tắt trong 30 giây

1. **Giữ OrderFlow (Hoàng) làm bài nộp. Không chuyển sang ATP+ (Thy).** Chỉ tiếp thu 9 điểm đã kiểm chứng của ATP+.
2. **Deck chưa được sửa kể từ bản review 16/10.** Cả 21 phát hiện D1-01…D1-21 vẫn còn mở, và lộ trình cũ đã trễ khoảng 3 ngày.
3. **Điểm hiện tại khoảng 32,5/50. Nếu sửa đúng trọng tâm có thể đạt khoảng 40–42/50.** Phần lớn điểm cộng nằm ở slide 8 (Business Impact) và slide 5 (Prioritisation).
4. **Bằng chứng mới giúp đóng lỗ hổng lớn nhất là tiền thực:** với tỷ lệ lỗi nhập tay 1–3% mỗi đơn, mỗi lỗi tránh được chỉ cần tiết kiệm **≥ DKK 156** là dự án hòa vốn bằng tiền thật (mục 3.3).
5. **Round 1 chọn ý tưởng, nhưng Round 2 bắt đội phải build MVP chính ý tưởng đó trong 7 ngày.** OrderFlow đã có prototype, nên đây là lợi thế chiến lược. Cần nói rõ điều đó trên slide 7.

---

## 1. Đề bài thực sự kiểm tra gì

### 1.1 Dữ kiện chính thức

| Hạng mục | Nội dung | Nguồn |
|---|---|---|
| Case | Company A: chuỗi vật liệu xây dựng Đan Mạch, hàng trăm cửa hàng ở DK/NO/SE, phục vụ cả B2B (nhà thầu) và B2C | Đề |
| 4 thách thức | Manual processes · Inconsistent operations · Delivery & fulfilment · Fragmented systems | Đề |
| Gợi ý theo nước | DK *may* be manual processes · NO *may* be store operations · SE *may* be delivery/fulfilment | Đề (giữ nguyên chữ "may") |
| Nhiệm vụ | 01 Identify ONE opportunity → 02 Prioritise → 03 Solve (solution + MVP) → 04 Scale (rollout theo từng nước) | Đề |
| Nhấn mạnh | "Time to market is critical. Scope carefully. Focus on one problem." · "One strategic solution ≠ one identical implementation" | Đề |
| Tips | Được giả định nhưng phải nêu rõ và có lý do · không có đáp án "đúng" · AI tạo giá trị ở đâu | Đề |
| Nộp | PDF, **tối đa 10 slide**, tiếng Anh, upload form với **đúng tên đội**, hạn **22:00 26/10/2026** | Đề |
| 5 tiêu chí | Problem Understanding · Prioritisation & Critical Thinking · Business Impact · Feasible Solution · Structured Thinking & Innovation | Đề |

### 1.2 Bối cảnh cả cuộc thi (ảnh hưởng tới Round 1)

| Vòng | Thời gian | Hệ quả cho bài Round 1 |
|---|---|---|
| R1 Discover | 19/10–26/10 | Proposal 10 slide |
| R2 Build | 02/11–09/11, online | **Phải build MVP của chính ý tưởng R1.** Ý tưởng không build được trong 7 ngày là tự bẫy mình |
| R3 Deliver | 16/11–21/11 | Có **change request**: kiến trúc phải đủ linh hoạt (adapter theo từng nước, API đơn hàng chung) |
| Quy định AI | Mọi vòng | Được dùng AI nhưng phải kiểm chứng và giải thích được. **Không khuyến khích slide 100% do AI tạo.** Nộp AI journal sau R2 |

Nguồn: [FAQ chính thức](https://itconsultantchallenge.org/vi/faq).

### 1.3 Đọc giữa các dòng: giám khảo Netcompany chấm gì

- **Người ra đề là người chấm.** Trích sai đề (lỗi D1-06) bị trừ điểm ngay ở Problem Understanding.
- **"Where should Company A focus first?"** là câu hỏi trung tâm. Bài phải trả lời được vì sao chọn vấn đề này **và vì sao không bắt đầu ở Thụy Điển**, dù đề gợi ý giao hàng ở đó có thể có tác động lớn nhất.
- **Netcompany làm hệ thống trong môi trường có quản lý chặt** (chính phủ, ngành trọng yếu). Họ sẽ đánh giá cao: không thay ERP kiểu big-bang, human-in-the-loop, EU hosting, audit log, có fallback. OrderFlow đã có đủ những điểm này.
- **Business Impact phải là "measurable value"**, tức con số có baseline, có chi phí và có cách đo. Đây đang là tiêu chí yếu nhất của bài.

---

## 2. Review solution của các thành viên

### 2.1 Bảng tổng hợp

| | **D1 – OrderFlow (Hoàng)** | **D2 – ATP+ (Thy)** |
|---|---|---|
| Dạng | Deck 10 slide PDF + prototype | Báo cáo phân tích Markdown |
| Ý tưởng | Lớp AI nhận đơn B2B: đọc email/PDF → khớp SKU → kiểm tồn → nhân viên duyệt trên một màn hình → đẩy vào ERP từng nước | Mở rộng OrderFlow thành ATP đa điểm, 3 chế độ vận hành theo nước, nhập bằng giọng nói, SMS, khóa giữ hàng, tách đơn |
| Điểm (/50) | **32,5** → ≈40–42 nếu sửa | Áp dụng nguyên văn vào D1: ≈33,5 |
| Mạnh nhất | Ghép 4 thách thức vào **một luồng đơn hàng**. MVP kỷ luật (1 nước, 1 kênh, 12 tuần). Kiến trúc lớp mỏng trên ERP. Footnote nguồn 9/9. **Đã có prototype** | Chẩn đoán đúng các lỗ hổng: KPI mơ hồ, thiếu chi phí vận hành, rủi ro tồn kho, Counter mode chưa định nghĩa, còn placeholder |
| Yếu nhất | **Business Impact**: con số 23m DKK là giá trị thời gian nhân viên nhưng trông như tiền thật. Không có chi phí vận hành, không tính giai đoạn triển khai dần, KPI chỉ đo nội bộ | **Gây lỗi mới**: 3 con số FTE mâu thuẫn (121 / 91 / 54,5). "19,8m DKK tiền thực" không có cơ sở và đếm trùng. Cặp KPI tự mâu thuẫn. Phình MVP. Mô tả sai sản phẩm Netcompany. Gán Company A = STARK |
| Kết luận | **Dùng làm nền** | **Chỉ tiếp thu 9 điểm** ở mục 2.3 |

### 2.2 Vì sao không chuyển sang ATP+

- **Trái hai yêu cầu cốt lõi của đề** là "focus on one problem" và "time to market". ATP+ tự nhận giải quyết cả 4 thách thức và thêm 6–7 mảng tính năng.
- **Không build được trong 7 ngày ở R2.** Giọng nói, SMS, tách đơn, khóa giữ hàng là những tích hợp riêng.
- **Rủi ro uy tín trước giám khảo.** Mô tả PULSE/AMPLIO vượt quá nguồn công khai, mà người chấm lại chính là nhân viên Netcompany.

### 2.3 Những gì lấy từ ATP+ (đã kiểm chứng)

| # | Điểm | Đưa vào slide |
|---|---|---|
| 1 | Tách KPI độ chính xác "trước duyệt" và "sau duyệt" | 7 |
| 2 | Có chi phí vận hành trong business case | 8 |
| 3 | Cổng go/no-go giữa các nước | 9 |
| 4 | Nút báo lệch kho để kích hoạt kiểm kê | 6, 10 |
| 5 | Định nghĩa Counter mode cho Na Uy (rút gọn) | 9 |
| 6 | Thụy Điển: bỏ live tracking, chỉ hứa ngày giao và báo trạng thái | 9 |
| 7 | Thêm phương án E "hợp nhất ERP" vào bảng so sánh | 5 |
| 8 | Tách luồng đọc và ghi ERP, fallback file/EDI | 6, 10 |
| 9 | Nói rõ lợi ích cho khách B2C | 4 |

### 2.4 Kiểm tra lại deck ngày 20/10

Mình đã trích lại text từ `OrderFlow-Proposal-Draft.pdf`. **Nội dung chưa đổi** so với bản được review: S1 vẫn còn `[Team name] · [Member 1]…`, S3 vẫn ghi "the urgent issue in Sweden", S7 vẫn "SKU accuracy after review 90%" và "Our Round 2 prototype", S8 vẫn "Payback 6 mo" và "run costs excluded".
→ **Toàn bộ danh mục sửa ở mục 7.1 của bản review vẫn còn nguyên giá trị.**

---

## 3. Bằng chứng mới (tra web ngày 20/10)

### 3.1 Củng cố giả định của slide 8

| Giả định trong deck | Bằng chứng mới | Cách dùng |
|---|---|---|
| 8 phút mỗi đơn nhập tay | Xử lý đơn B2B nhập tay mất **8–15 phút/đơn** (tài liệu Emporix, MACH Alliance trích, 06/2026). Một nhà bán sỉ vật liệu xây dựng báo cáo **10–15 phút mỗi yêu cầu** qua email (vendor tự công bố) | Footnote S8: "8 min is at the low end of the 8–15 min industry range" → giả định thận trọng |
| Mục tiêu tự động hóa | Benchmark của Esker: **tỷ lệ đơn touchless trung bình 67%**, nhóm dẫn đầu trên 90% | KPI 60% "approved without edits" nằm dưới mức trung bình ngành, nên khả thi |
| Lỗi đơn hiện tại | Nghiên cứu của Conexiom: **lỗi nhập tay 1–3% mỗi đơn** | Baseline cho KPI lỗi và lớp tiền thực (mục 3.3) |
| Tiền lệ cùng ngành | Koninklijke Dekker (nhà bán sỉ gỗ Hà Lan) dùng AI đọc PDF/email/bảng tính để nhận đơn (Lleverage) | Thêm vào footnote S7, gần ngành hơn ví dụ Topa |
| Tiền lệ có số liệu | Nhà cung cấp bánh B2B nhập lại email vào Dynamics NAV: lỗi giảm từ **12% xuống dưới 1%**, hơn 85% luồng đơn tự động (Beam AI, vendor tự công bố) | Chỉ dùng làm minh họa, ghi rõ "vendor-reported" |

> Mọi số liệu do vendor công bố phải ghi "vendor-reported" trên slide, như deck đang làm. Không gán danh tính Company A.

### 3.2 Lương

Theo DST, lương trung bình năm 2025 là **53.916 DKK/tháng** (đã gồm lương hưu, tính cho toàn bộ người lao động Đan Mạch). Nhân viên bán lẻ thấp hơn mức này, và Thụy Điển thấp hơn Đan Mạch. Vì vậy mức **425k DKK/FTE pha trộn ba nước là hợp lý**, nhưng footnote nên ghi rõ: *"blended fully-loaded cost, below DK all-employee average (DST 2025)"*.

### 3.3 Phép tính mới: điểm hòa vốn bằng tiền thực

Bản review đã chỉ ra: để hòa vốn bằng tiền thực trong 24 tháng cần **8,14m DKK/năm**, trong khi lớp tiền thực hiện có chỉ **5,8m**, tức **thiếu 2,34m/năm**. Phần thiếu này lấp được bằng giảm chi phí sai đơn:

| Bước | Phép tính | Kết quả |
|---|---|---|
| Số đơn B2B nhập tay mỗi năm | 300 cửa hàng × 20 đơn × 250 ngày | **1,5 triệu đơn** |
| Đơn có lỗi hôm nay (giả định 2%, giữa khoảng 1–3%) | 1,5m × 2% | **30.000 đơn** |
| Lỗi tránh được (KPI −50%) | 30.000 × 50% | **15.000 đơn/năm** |
| Chi phí tối thiểu mỗi lỗi để lấp phần thiếu | 2,34m ÷ 15.000 | **≈ DKK 156 mỗi đơn lỗi** |

**Câu dùng trên slide 8 (EN):**
> *"Cash break-even needs each avoided order error to save ≥ DKK 156 – less than one re-delivery trip [A]. With a 1–3% manual error rate (Conexiom), halving errors on 1.5m orders avoids ≈15,000 errors a year. The pilot measures the real cost per error from credit notes."*

Đây là câu trả lời mạnh cho câu hỏi của CFO: "tiền thật nằm ở đâu?". Nó dựa trên một ngưỡng nhỏ, dễ kiểm chứng, thay vì một con số lớn khó bảo vệ.

---

## 4. Định vị chiến thắng

**Thông điệp một câu (dùng ở slide 2):**
> *"Start where three problems meet: contractor order intake. Fix the promise at the order desk in Denmark, reuse the same core for Sweden's delivery promise and Norway's counter standard."*

Năm điểm khác biệt cần làm nổi bật, mỗi điểm gắn với một tiêu chí:

| Tiêu chí | Điểm khác biệt | Slide |
|---|---|---|
| Problem Understanding | Root cause là không có lớp đơn hàng chung; 4 thách thức là 4 bước của cùng một luồng | 3 |
| Prioritisation | Bảng có trọng số + kiểm tra độ nhạy; trả lời trực diện "Why not start in Sweden?" | 5 |
| Business Impact | Ba lớp: năng lực → tiền thực → tiền ròng; điểm hòa vốn DKK 156/lỗi; KPI khách hàng "promised date kept" | 7, 8 |
| Feasible Solution | Không thay ERP; adapter theo nước; spike tuần 1; fallback file/EDI; **prototype đang chạy** | 6, 7 |
| Structured Thinking & Innovation | Mạch SCQ; AI xử lý từ lóng nghề, đơn vị tính, lịch sử mua (chỗ mà công cụ đọc PO thông thường làm không được) | Toàn bài |

---

## 5. Lộ trình tối ưu 20/10 → 26/10

Nguyên tắc: **làm slide quyết định điểm trước** (8, 5, 7), **chốt số liệu một lần** rồi mới chỉnh hình thức, **nộp sớm 4 tiếng**.

Vai trò đề xuất (đội tự điều chỉnh):
- **Hoàng (chủ deck):** sửa slide, giữ giọng văn và thiết kế đồng nhất.
- **Thy (số liệu và business case):** slide 8, bảng trọng số slide 5, đối soát số liệu toàn bài.
- **Thành viên thứ 3 (prototype và rà soát):** backtest prototype, ảnh chụp màn hình, kiểm tra trích dẫn đề và tiếng Anh, chuẩn bị phần R2.

| Ngày | Mục tiêu | Hoàng | Thy | TV3 | Kết quả cuối ngày |
|---|---|---|---|---|---|
| **T2 20/10 (tối)** | Chốt hướng | Đọc tài liệu này; đồng ý giữ D1 | Đồng ý bỏ các số 19,8m / 91 / 121 FTE | Chuẩn bị bộ 30–50 đơn mẫu cho backtest | **Họp 30 phút, chốt C-01…C-04** |
| **T3 21/10** | Slide 8 (+2,5 điểm) | S1 tên đội; S3 trích đúng đề | Biểu đồ thác nước 23m → 5,8m → 3,6m; cấu phần chi phí vận hành; hoàn vốn hai lớp; dòng DKK 156 | Chạy backtest prototype, đo % dòng khớp | Slide 8 bản nháp có số liệu đã khóa |
| **T4 22/10** | Slide 5 + 7 | S7: bộ KPI nhất quán (95% dòng trước duyệt, lỗi ≤ 50% baseline, promised date kept +10 điểm %), "Working prototype" | S5: trọng số + độ nhạy, phương án E, hộp "Why not Sweden?" | Ảnh màn hình duyệt đơn cho S6/S7; kết quả backtest | S5, S7 xong |
| **T5 23/10** | Slide 2, 9, 6 | S2 action title + Impact ba lớp; S9 cổng tháng 3, phạm vi SE, Counter mode, dải "Across all three markets" | S6: quy tắc tồn thấp + nút báo lệch kho; câu EU AI Act | Rà footnote, đánh dấu [A] và "vendor-reported" | **Bản đủ 10 slide v1** |
| **T6 24/10** | Đồng bộ + đọc thử | S4, S10 (UK peers, B2C, Likelihood/Impact, "Decision needed") | Đối soát mọi con số giữa S2, S7, S8, S10 | **Mời 1–2 người ngoài đội đọc 5 phút**: họ có nhắc lại được vấn đề, giải pháp, con số chính không? | Danh sách góp ý |
| **T7 25/10** | Hoàn thiện | Sửa theo góp ý; rà tiếng Anh | Kiểm tra lại các phép tính lần cuối | Diễn tập 8 câu hỏi phản biện (mục 8 của bản review) | **Bản v2 đóng băng lúc 22:00** |
| **CN 26/10** | Nộp | Xuất PDF, mở xem từng trang, kiểm tra font và ảnh | Đối chiếu checklist mục 6 | Kiểm tra tên file và tên đội trên form | **Nộp trước 18:00** (dư 4 tiếng) |

**Nếu thiếu thời gian, cắt theo thứ tự này:** S4 → S10 cột Likelihood → kiểm tra độ nhạy ở S5. **Không cắt** S8, S7 KPI, S3 trích đề, S1 tên đội.

### Chuẩn bị song song cho Round 2 (không tốn thêm thời gian R1)

- Slide 7 ghi rõ phạm vi prototype: đọc đơn, khớp SKU trên catalogue mẫu, màn hình duyệt, adapter giả lập DK/SE/NO. Đây là lời hứa cho R2.
- Lưu kết quả backtest và ảnh chụp: dùng lại cho video demo R2 và AI journal.
- Bắt đầu ghi **AI journal** ngay từ bây giờ (prompt quan trọng, phần nào đã kiểm chứng). Mẫu bắt buộc nộp sau R2.
- Thiết kế adapter theo nước và API đơn hàng chung để sẵn sàng cho **change request ở R3** (ví dụ: "thêm kênh điện thoại" hoặc "Na Uy trước").

---

## 6. Checklist trước khi nộp

- [ ] ≤ 10 trang, PDF, tiếng Anh, tên file và tên trên form **đúng chính xác tên đội**
- [ ] S1 không còn placeholder; có tên đội, 3 thành viên, ngày 26/10/2026
- [ ] Mọi slide có action title (câu kết luận, không phải nhãn)
- [ ] S3 trích đúng gợi ý của đề, giữ chữ "may"
- [ ] Không có con số 19,8m, ~91 FTE hay ~121 FTE "unlocked"; chỉ dùng ≈55 FTE / 23m / 5,8m / 3,6m
- [ ] KPI nhất quán toán học (95% dòng ↔ ≈46% đơn 15 dòng không phải sửa)
- [ ] Có ít nhất một KPI phía khách hàng: "promised delivery date kept"
- [ ] Hoàn vốn ghi cả hai lớp, có giai đoạn triển khai dần và chi phí vận hành
- [ ] Trả lời được "Why not start in Sweden?"
- [ ] Không gán danh tính Company A; không mô tả PULSE/AMPLIO; STARK UK/Travis Perkins ghi là "UK peers"
- [ ] Mọi giả định có [A]; số liệu vendor ghi "vendor-reported"
- [ ] Có ảnh prototype
- [ ] Slide do đội tự dựng và tự viết lại (BTC không khuyến khích slide 100% AI)
- [ ] Mở PDF trên máy khác: font, ảnh, bảng hiển thị đúng

---

## 7. Rủi ro của đội

| Rủi ro | Dấu hiệu | Xử lý |
|---|---|---|
| Tiếp tục tranh luận D1 hay ATP+ | Đến tối 21/10 chưa chốt | Chốt theo tài liệu này; ghi ý kiến khác vào phụ lục để dùng ở R3 |
| Sửa số liệu ở một slide nhưng quên slide khác | S2, S7, S8 lệch nhau | Một người (Thy) giữ "bảng số liệu gốc"; các slide chỉ lấy số từ đó |
| Nộp sát giờ, lỗi form hoặc mạng | — | Nộp trước 18:00; nộp xong chụp màn hình xác nhận |
| Lộ tài liệu mật của BTC | Repo public, gửi file ra ngoài | Repo đang private; không chuyển sang public trước khi cuộc thi kết thúc |

---

## Nguồn tham khảo (tra ngày 20/10/2026)

- Đề bài: *IT Consultant Challenge 2026 – Round 1* (Netcompany, 16/10/2026), [Google Drive](https://drive.google.com/file/d/1Wdrtj0qMMcrHeXS2DS5eSZIYyDGtsR6-/view)
- [IT Consultant Challenge – FAQ](https://itconsultantchallenge.org/vi/faq): lịch các vòng, quy định AI, AI journal
- [MACH Alliance – From inbox to ERP (06/2026)](https://machalliance.org/insights-hub/from-inbox-to-erp): Esker touchless 67%, Conexiom lỗi 1–3%/đơn, Emporix 8–15 phút/đơn
- [Lleverage – Koninklijke Dekker](https://www.lleverage.ai/customer-stories/koninklijke-dekker): AI nhận đơn ở nhà bán sỉ gỗ (vendor-reported)
- [Beam AI – B2B bakery supplier](https://www.casestudies.com/company/beam-ai/case-study/transforming-order-management-with-ai-agents-for-a-leading-b2b-bakery-supplier): lỗi 12% → <1% (vendor-reported)
- [Apertia – B2B order agent](https://apertia.ai/en/b2b-objednavky-agent): nhà bán sỉ vật liệu xây dựng, 10–15 phút/yêu cầu (vendor-reported)
- [Danmarks Statistik – lương 2025](https://www.dst.dk/nyt/56703): trung bình 53.916 DKK/tháng
- [BCG – Digital and AI in Nordic Construction (2026)](https://web-assets.bcg.com/pdf-src/prod-live/digital-and-ai-in-nordic-construction.pdf): bối cảnh, chưa trích số liệu
