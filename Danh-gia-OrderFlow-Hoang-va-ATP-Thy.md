# BÁO CÁO ĐÁNH GIÁ ĐỘC LẬP

## Bản OrderFlow của Hoàng & Bản ATP+ của Thy

**IT Consultant Challenge 2026 – Round 1 (Netcompany × Code MeLy)**

---

### Thông tin tài liệu

| Hạng mục | Nội dung |
|---|---|
| Loại tài liệu | Báo cáo đánh giá độc lập (judge review) |
| Ngày lập | 16/10/2026 |
| Góc nhìn đánh giá | Chuyên gia ngành builders' merchant Bắc Âu · Solution architect · CFO |
| Hạn nộp bài thi | 22:00, 26/10/2026 (còn 10 ngày) |
| Phân loại | Nội bộ đội thi. Không chia sẻ ra ngoài |

### Tài liệu được đánh giá

| Mã | Tên gọi trong báo cáo | Người thực hiện | File gốc | Loại | Vai trò |
|---|---|---|---|---|---|
| **D1** | **Bản OrderFlow (Hoàng)** | Hoàng | `OrderFlow-Proposal-Draft.pdf` | Deck 10 slide (PDF) | Đối tượng đánh giá chính: bài dự thi của đội |
| **D2** | **Bản ATP+ (Thy)** | Thy | `IT_Consultant_Challenge_2026_Full_Report_VN.md` | Báo cáo phân tích (Markdown) | Ý kiến tham khảo: đánh giá D1 và đề xuất nâng cấp "OrderFlow ATP+" |

> Báo cáo đánh giá **nội dung tài liệu**, không đánh giá người thực hiện. Tên người chỉ dùng để nhận diện file.

**Thứ tự tin cậy khi có mâu thuẫn:** đề bài > D1 > D2.

---

### Mục lục

1. [Tóm tắt điều hành](#1-tóm-tắt-điều-hành)
2. [Phạm vi và phương pháp](#2-phạm-vi-và-phương-pháp)
3. [Đánh giá D1 – Bản OrderFlow (Hoàng)](#3-đánh-giá-d1--bản-orderflow-hoàng)
4. [Đánh giá D2 – Bản ATP+ (Thy)](#4-đánh-giá-d2--bản-atp-thy)
5. [Kiểm toán số liệu](#5-kiểm-toán-số-liệu)
6. [Đối chiếu D1 – D2 và khuyến nghị](#6-đối-chiếu-d1--d2-và-khuyến-nghị)
7. [Kế hoạch hành động](#7-kế-hoạch-hành-động)
8. [Chuẩn bị phản biện](#8-chuẩn-bị-phản-biện)
- [Phụ lục A – Thuật ngữ](#phụ-lục-a--thuật-ngữ)
- [Phụ lục B – Nguồn tham khảo](#phụ-lục-b--nguồn-tham-khảo)

---

## 1. Tóm tắt điều hành

### 1.1 Kết luận chính

1. **Bản OrderFlow của Hoàng (D1) đạt mức khá: 32,5/50.**
   - Mạnh: câu chuyện "một luồng nơi các thách thức gặp nhau", kiến trúc lớp mỏng trên ERP sẵn có, MVP hẹp, footnote nguồn đầy đủ, thiết kế chuyên nghiệp, có prototype.
   - Yếu nhất: **Business Impact**. Thời gian hoàn vốn 6 tháng được tính trên *giá trị thời gian nhân viên* thay vì tiền thực, chưa trừ chi phí vận hành, chưa tính giai đoạn triển khai dần, và chưa có KPI phía khách hàng.
2. **Bản ATP+ của Thy (D2) chẩn đoán đúng một phần, nhưng phương án sửa tạo ra lỗi mới.**
   - Chẩn đoán đúng: nhãn KPI mơ hồ, thiếu chi phí vận hành, xử lý rủi ro tồn kho yếu, Counter mode chưa định nghĩa, còn placeholder.
   - Lỗi mới:
     - Ba con số FTE không nhất quán.
     - Khoản "lợi ích tiền mặt 19,8m DKK" không có cơ sở.
     - Cặp KPI mới tự mâu thuẫn.
     - Mô tả sản phẩm Netcompany vượt quá nguồn.
     - Phương án đối chứng bị làm yếu đi để dễ bác (strawman).
3. **Không áp dụng nguyên văn D2.** Chỉ tiếp thu các điểm đã được kiểm chứng ở mục 4.5 và mục 6.

### 1.2 Điểm đánh giá

| Phương án | Điểm (/50) | Nhận định |
|---|---|---|
| D1 – bản của Hoàng, hiện tại | **32,5** | Nền tốt; Business Impact và Prioritisation kéo điểm xuống |
| D1 + áp dụng nguyên văn D2 (bản của Thy) | ≈ 33,5 | Lấp được vài lỗ hổng nhưng thêm lỗi số liệu và phình phạm vi |
| D1 + khuyến nghị của báo cáo này | **≈ 40** (39–42) | Sửa trọng tâm, giữ thế mạnh và prototype |

> Điểm là đánh giá chuyên môn độc lập theo 5 tiêu chí của BTC, không phải điểm chính thức.

### 1.3 Ba ưu tiên hành động

| # | Hành động | Slide | Tác động |
|---|---|---|---|
| 1 | Trình bày lại business case theo ba lớp: giá trị năng lực → tiền thực → tiền ròng. Có chi phí vận hành, giai đoạn triển khai dần, điểm hòa vốn | 8 | Business Impact +2,5 |
| 2 | Bộ KPI nhất quán, có baseline. Thêm KPI khách hàng "giao đúng ngày đã hứa". Chèn ảnh prototype | 7 | Business Impact, Feasibility |
| 3 | Trích đúng gợi ý của đề; trả lời "vì sao không bắt đầu ở Thụy Điển"; định nghĩa Counter mode; bỏ live tracking năm 1; thêm cổng go/no-go | 3, 5, 9 | Problem Understanding, Prioritisation |

Kèm theo: điền tên đội và thành viên ở slide 1 (5 phút, bắt buộc).

### 1.4 Khuyến nghị

**Giữ D1 làm nền và sửa theo mục 7.** Không chuyển sang phương án ATP+ đầy đủ. Lý do:
- D1 là tài liệu duy nhất đã thành deck và có prototype.
- Số học trong D1 đúng; chỉ phương pháp trình bày lợi ích cần sửa.
- Phương án ATP+ làm phình MVP, trái với yêu cầu "time to market" và "focus on one problem".

---

## 2. Phạm vi và phương pháp

### 2.1 Phạm vi

- **Có trong phạm vi:**
  - Toàn bộ 10 slide của D1.
  - Toàn bộ nội dung D2: phần tóm tắt D1, 7 "tử huyệt", 10 câu hỏi phản biện, phương án ATP+ và NordicFlow, nội dung 10 slide đề xuất.
- **Ngoài phạm vi:** đánh giá các bài thi khác; dự đoán thứ hạng.

### 2.2 Phương pháp

| Bước | Cách làm |
|---|---|
| Đọc D1 | Ba cách độc lập: (1) trích xuất văn bản; (2) phân tích cấu trúc PDF (cỡ chữ, số chữ, số ảnh); (3) render từng trang thành ảnh (Windows.Data.Pdf) và xem trực tiếp |
| Đối chiếu đề bài | So từng khẳng định của D1 và D2 với nguyên văn đề bài |
| Kiểm toán số liệu | Tính lại mọi con số, ghi rõ phép tính |
| Kiểm chứng nguồn | Tra cứu ngày 16/10/2026 cho benchmark, sản phẩm Netcompany, thông tin doanh nghiệp, số liệu ngành |
| Chấm điểm | Thang 10 cho mỗi tiêu chí trong 5 tiêu chí chính thức của BTC |

### 2.3 Quy ước

**Mức độ phát hiện**

| Mức | Định nghĩa |
|---|---|
| **Nghiêm trọng** | Giữ nguyên sẽ mất điểm lớn ở một tiêu chí hoặc vi phạm yêu cầu nộp bài |
| **Cao** | Ảnh hưởng rõ tới điểm hoặc độ tin cậy; nên sửa trước khi nộp |
| **Thấp** | Cải thiện chất lượng trình bày; sửa nếu còn thời gian |

**Nhãn nguồn**

| Nhãn | Định nghĩa |
|---|---|
| **[Đã kiểm]** | Đã đối chiếu với nguồn gốc hoặc nguồn độc lập (chủ yếu qua trích đoạn kết quả tìm kiếm) |
| **[Chưa kiểm]** | Có nguồn nhưng chưa đối chiếu được |
| **[Giả định của đội]** | Giả định do đội đặt (ký hiệu `[A]` trong D1) |
| **[Không có cơ sở]** | Không có nguồn, không có cách tính, hoặc tính sai |

**Ký hiệu và mức ưu tiên**
- Ký hiệu: `S3` = slide 3 của D1. `Phần 4 Q1` = câu hỏi 1, phần 4 của D2.
- Ưu tiên: **P0** bắt buộc · **P1** nên làm · **P2** nếu còn thời gian.
- Mã: `D1-xx` = phát hiện về D1 · `D2-xx` = phát hiện về D2 · `C-xx` = điểm đối chiếu · `Q-xx` = câu hỏi phản biện.

### 2.4 Giới hạn

- Điểm số mang tính chuyên môn và chủ quan. BTC không công bố thang điểm chi tiết.
- Phép tính xác suất theo đơn hàng giả định lỗi giữa các dòng độc lập nhau.
- Một số nguồn chính thức không truy cập được. Trường hợp đó gắn nhãn [Chưa kiểm].

---

## 3. Đánh giá D1 – Bản OrderFlow (Hoàng)

### 3.1 Điểm theo 5 tiêu chí

| Tiêu chí | Hiện tại | Bằng chứng | Điểm yếu chính | Hướng sửa | Sau sửa |
|---|---|---|---|---|---|
| **Problem Understanding** | **7,0** | S3 ghép 4 thách thức vào 4 bước của luồng đơn B2B và nêu nguyên nhân gốc. S4 có hai persona và lý do chọn B2B | S3 ghi sai gợi ý của đề (đề nói Na Uy *"more urgent"*, Thụy Điển *"greater business impact"*), bỏ chữ *may*. Chưa có con số nào về nỗi đau giao hàng | Trích nguyên văn đề; thêm một con số `[A]` về giao thất bại hoặc đơn sai | **8,0** |
| **Prioritisation & Critical Thinking** | **6,0** | S5 so sánh 4 phương án và nêu kết luận. S7 có danh sách ngoài phạm vi | Đánh giá định tính, không trọng số. Cột "Root cause?" trộn kiểu trả lời. Thiếu phương án hợp nhất ERP. Chưa trả lời "vì sao không bắt đầu ở Thụy Điển" | Thêm trọng số và kiểm tra độ nhạy; thêm phương án E; thêm hộp "Why not start in Sweden?" | **8,0** |
| **Business Impact** | **5,0** | S8 có công thức minh bạch, ba kịch bản, nguồn lương. S7 có KPI go/no-go | Hoàn vốn tính trên giá trị năng lực; loại chi phí vận hành; không tính giai đoạn triển khai dần. Con số "DKK 23m" nổi bật như tiền thực. KPI chỉ đo nội bộ | Trình bày ba lớp bằng biểu đồ thác nước; tính hoàn vốn hai lớp có triển khai dần; điểm hòa vốn; KPI "giao đúng ngày đã hứa" | **7,5** |
| **Feasible Solution** | **7,5** | S6 kiến trúc lớp mỏng, human-in-the-loop, EU hosting. S7 integration spike tuần 1, benchmark vendor. S10 fallback file/EDI | Rủi ro tồn kho xử lý chưa thuyết phục. S9 đưa live tracking vào năm 1. Counter mode chưa định nghĩa. Không có ảnh prototype | Quy tắc tồn thấp + nút báo lệch kho → kiểm kê; Thụy Điển dùng hứa ngày + báo trạng thái; định nghĩa Counter mode; ảnh prototype | **8,5** |
| **Structured Thinking & Innovation** | **7,0** | Mạch SCQ rõ; mỗi slide một thông điệp; footnote 9/9; thiết kế nhất quán | Còn placeholder; 3 slide chưa có action title; mức đổi mới vừa phải vì "AI đọc đơn" đã có sản phẩm thương mại | Action title cho mọi slide; nhấn phần khác biệt: từ lóng nghề + đơn vị tính + lịch sử mua + hứa ngày | **8,0** |
| **Tổng** | **32,5** | | | | **40,0** |

### 3.2 Hình thức và trình bày

| Hạng mục | Đánh giá | Ghi chú |
|---|---|---|
| Số slide ≤ 10 | **Đạt** | 10 trang |
| Placeholder | **Không đạt** | S1: `Team [Team name] · [Member 1] · [Member 2] · [Member 3]` |
| Action title | **6/9 đạt** | Chưa đạt: S2 "Executive summary", S7 "12 weeks, one country, one channel", S10 "What could go wrong – and how we de-risk it" |
| Footnote nguồn và giả định | **Đạt (9/9)** | Thế mạnh, cần giữ |
| Mật độ chữ | **Chấp nhận được** | 100–146 chữ mỗi slide nội dung (dày nhất S8); cỡ chữ nhỏ nhất 24pt trên canvas 1440×810pt |
| Tiếng Anh | **Tốt** | Cần sửa: "Our Round 2 prototype" (S7), "the urgent issue in Sweden" (S3) |
| Thiết kế | **Tốt** | Bảng màu navy/kem/cam nhất quán, bố cục gọn, không có chữ chồng |
| Khoảng trống | **Chưa tận dụng** | Khoảng 25–30% chiều cao phía dưới bỏ trống ở S4–S7, S9, S10. Đủ chỗ cho các bổ sung ở mục 7 mà không làm dày chữ |
| Hình ảnh, biểu đồ | **Không có** | 0 ảnh, 0 biểu đồ |

### 3.3 Điểm mạnh cần giữ

- **Cách đặt vấn đề:** ghép bốn thách thức vào một luồng đơn hàng B2B. Đây là cách trả lời tốt cho yêu cầu "one problem".
- **Kiến trúc thực dụng:** lớp mỏng phía trên ERP, adapter theo từng nước, không thay hệ thống lõi.
- **MVP kỷ luật:** một nước, một kênh, 12 tuần, có danh sách ngoài phạm vi.
- **Minh bạch giả định:** ký hiệu `[A]` và footnote nguồn ở mọi slide nội dung.
- **Bằng chứng ngoài ngành đã kiểm chứng:**
  - IBM/Oiki: thời gian xử lý giảm từ 30 xuống 12 phút/đơn.
  - Lleverage/Topa: hơn 90% đơn được nhận tự động.
  - Travis Perkins và STARK UK: khung giờ giao và tracking.
  - JYSK: triển khai POS theo đợt.
- **Yếu tố con người:** tham vấn đại diện người lao động, store champions.
- **Prototype đã xây dựng.** Đây là lợi thế lớn nhất, nhưng chưa được thể hiện bằng hình ảnh.

### 3.4 Phát hiện

#### Mức Nghiêm trọng

| Mã | Vị trí | Vấn đề | Bằng chứng / phép tính | Đề xuất (EN, dùng trên slide) |
|---|---|---|---|---|
| D1-01 | S1 | Còn placeholder tên đội và thành viên | Dòng cuối S1 | "Team ‹name› · ‹Member 1› · ‹Member 2› · ‹Member 3› · 26 October 2026" |
| D1-02 | S8, S2 | Hoàn vốn "6 mo" tính trên giá trị thời gian, trong khi cam kết "not headcount cuts"; chi phí vận hành bị loại; không tính triển khai dần | 300×20×8/60×250 = 200.000 giờ ÷ 1.650 = **121,2 FTE**; × 60% × 75% = **54,5 FTE**; × 425k = **23,18m DKK**. Hoàn vốn = 11,875m ÷ 23,18m × 12 = **6,1 tháng**, như thể 300 cửa hàng chạy đủ từ ngày đầu | "DKK 23m a year of counter capacity (≈55 FTE-equivalents) – value, not cash. Cash-realisable ≈DKK 5.8m a year [A] via avoided temps, overtime and attrition, agreed with employee reps." |

#### Mức Cao

| Mã | Vị trí | Vấn đề | Bằng chứng / phép tính | Đề xuất (EN) |
|---|---|---|---|---|
| D1-03 | S8 | Con số chính "DKK 23m" (màu cam, cỡ lớn nhất) khiến giá trị năng lực trông như tiền thực | Ảnh S8 | Con số chính: "≈55 FTE-equivalents freed". Thêm biểu đồ thác nước: "Capacity 23m → Cash 5.8m [A] → Run cost −2.2m [A] → Net ≈3.6m" |
| D1-04 | S7 | Nhãn "SKU accuracy after review ≥ 90%" đọc theo nghĩa đen là sau khi người duyệt | 90%/dòng → đơn 15 dòng đúng hoàn toàn = 0,9¹⁵ = **20,6%** (10 dòng: 34,9%) | "AI line match before review ≥ 95% (back-test on 500 past orders)" và "Order error rate after review ≤ 50% of today's baseline" |
| D1-05 | S7 so với S2–S3 | Câu chuyện nói lỗi nằm ở order-to-**delivery**, nhưng cả 5 KPI chỉ đo hiệu suất nội bộ | S7 không có KPI nào về ngày giao | "Promised delivery date kept: +10 pp vs. baseline [A]" |
| D1-06 | S3 | Ghi sai gợi ý của đề và bỏ chữ "may" | Đề: DK *"may create the greatest impact"* · NO *"may be a more urgent priority"* · SE *"may have greater business impact"* | "Manual processes – may have the greatest impact in Denmark" · "Inconsistent operations – may be the most urgent priority in Norway" · "Delivery & fulfilment – may have the biggest business impact in Sweden" |
| D1-07 | S5 | Không trọng số; cột "Root cause?" lẫn kiểu; thiếu phương án ERP; mệnh đề "B and C both need A first" dễ bị phản bác | Travis Perkins và STARK UK đã có khung giờ giao và tracking mà không cần AI nhận đơn [Đã kiểm] | "C can run without A, but its value is capped while dates are promised without a stock check – so A first, C on the same order API." Thêm hàng "E. Consolidate ERPs – very slow (years), rejected for time-to-market" |
| D1-08 | S2, S5 | Chưa trả lời "vì sao không bắt đầu ở Thụy Điển" | S9 đưa Thụy Điển vào tháng 5–9 nhưng không giải thích | "Why not start in Sweden? Its delivery pain may be bigger, but late deliveries start with unchecked promises at intake. We fix intake where manual volume is highest (Denmark [A]) and reuse the core in Sweden from month 5." |
| D1-09 | S9 | Thụy Điển: "time slots and live tracking" vượt phạm vi (cần dữ liệu đội xe / TMS); không có cổng giữa các nước | Live tracking ở các merchant Anh là dịch vụ gắn với đội xe [Đã kiểm] | "Sweden: ERP adapter + delivery-date promise from store and DC stock + automatic status messages from ERP events. Live GPS tracking: year-2 option." · "Gate 1 (month 3): go/no-go before funding SE/NO adapters." |
| D1-10 | S9 | "Counter mode" chưa được định nghĩa | Chỉ xuất hiện một dòng | "Counter mode: the same review screen for walk-in and phone orders – every Norwegian store captures, checks and confirms orders the same way." |
| D1-11 | S10 | Rủi ro tồn kho sai được xử lý bằng "the shared layer improves it over time" | Phần mềm không tự làm đúng tồn kho thực tế | "Low-stock lines get a DC-based date or a manual check; staff flag a stock mismatch in one click, which triggers a cycle count." |
| D1-12 | S7 | "Our Round 2 prototype" lạc vai; không có ảnh minh chứng | PDF có 0 ảnh | "Working prototype (built in one week): order reading, SKU matching on a sample catalogue, review screen, mock DK/SE/NO adapters." + ảnh màn hình duyệt đơn |

#### Mức Thấp

| Mã | Vị trí | Vấn đề | Đề xuất (EN) |
|---|---|---|---|
| D1-13 | S4 | Gọi STARK UK và Travis Perkins là "competitors": đây là thị trường Anh, và STARK UK cùng tập đoàn với Beijer (SE) và Neumann Bygg (NO) [Đã kiểm] | "UK peers (Travis Perkins, STARK UK) already give trade customers two-hour delivery windows and live tracking." |
| D1-14 | S2, S7, S10 | Chưa có action title | S2: "Start where three problems meet: contractor order intake" · S7: "A 12-week, one-country pilot proves value before any rollout" · S10: "Five risks, each with a week-1 test or a fallback" |
| D1-15 | S7 | Pha chạy thật chỉ 3 tuần (5–10 cửa hàng × 20 đơn × 15 ngày = **1.500–3.000 đơn**); có thể không đủ chứng minh "−50% wrong item/qty" | "Error KPIs are also back-tested on 500 past orders; live weeks confirm handling time and adoption." |
| D1-16 | S6 footnote | Gắn mức rủi ro EU AI Act với "human in the loop"; thực tế mức rủi ro do mục đích sử dụng quyết định | "Order extraction is not a high-risk use under the EU AI Act; we keep a human in the loop by design." |
| D1-17 | S6 | Hộp "No ERP replacement" lại viết "replaced step by step", tự mâu thuẫn | "No ERP replacement: a thin layer in front of today's ERPs – they stay; old order screens can be retired step by step." |
| D1-18 | S9 | Ba hộp "Shared once / Local per country / People first" nằm thẳng dưới ba cột quốc gia, dễ bị hiểu là thuộc từng nước | Gộp thành một dải ngang: "Across all three markets" |
| D1-19 | S10 | Rủi ro không có mức xác suất/tác động; phần Next steps thiếu quyết định cần phê duyệt | Thêm cột "Likelihood / Impact"; "Decision needed: fund a 12-week pilot in 5–10 Danish stores (DKK 3.5–6m [A]) and nominate pilot stores and employee representatives." |
| D1-20 | S4 | Lợi ích cho khách B2C chỉ được nói gián tiếp | "Every hour not spent re-typing goes back to the shop floor – for DIY and walk-in trade customers alike." |
| D1-21 | S8 | Giả định mọi cửa hàng, kể cả cửa hàng thiên về DIY, đều có 20 đơn B2B thủ công mỗi ngày | "…20 manual orders per store per day [A] – validated per store type in weeks 1–2." |

---

## 4. Đánh giá D2 – Bản ATP+ (Thy)

### 4.1 Độ chính xác khi tóm tắt D1

| Nội dung D2 về D1 | Kết luận | Lý do |
|---|---|---|
| Cấu trúc 10 slide và nội dung S1–S10 | **Đúng** | Khớp với D1 |
| Lỗi ghi sai gợi ý của đề ở S3 | **Không nêu** | D2 viết lại đúng nhưng không chỉ ra đây là lỗi |
| S7: dòng "Out of scope" và benchmark vendor (Oiki/IBM, Topa/Lleverage) | **Bỏ sót** | Hai chi tiết này làm yếu nhận định của D2 rằng D1 thiếu bằng chứng khả thi |
| S8: "Not counted: retaining contractors… measured in the pilot" | **Bỏ sót** | D1 đã chủ động loại doanh thu khỏi phép tính, tức là thận trọng |
| S9: footnote JYSK và "Year 2: contractor portal" | **Bỏ sót** | JYSK là tiền lệ có thật [Đã kiểm] |
| S5 "so sánh 4 công cụ ngẫu nhiên thay vì 4 bài toán" | **Phóng đại** | Các phương án tương ứng với các thách thức: B ↔ manual, C ↔ delivery (SE), D ↔ store ops (NO), A ↔ luồng đơn. Điểm thiếu thực sự là phương án ERP và trọng số |

### 4.2 Thẩm định bảy "tử huyệt"

| "Tử huyệt" theo D2 | Kết luận | Lý do |
|---|---|---|
| #1 KPI "after review ≥ 90%" | **Đúng về nhãn; phóng đại về mức độ** | Theo nghĩa đen thì sai thật (0,9¹⁵ = 20,6%). Nhưng câu "gần 80% chuyến xe giao sai" dựa trên giả định đơn 15 dòng, lỗi độc lập, mọi lỗi tới tay khách; con số "10–25 dòng/đơn" không có nguồn. Bản sửa của D2 lại mâu thuẫn (D2-03, D2-04) |
| #2 Lợi ích mềm thay cho tiền thực; bỏ chi phí vận hành; hoàn vốn ảo | **Đúng (lỗi cốt lõi)** | Câu "quỹ lương giảm 0 DKK" hơi tuyệt đối, vì thời gian giải phóng vẫn có thể giảm thuê thời vụ; chính D2 thừa nhận ở Phần 4 Q1 |
| #3 Nhảy cóc nhân quả về tồn kho | **Đúng một phần** | D1 đã kiểm tồn Store + DC (S6); vấn đề là chất lượng dữ liệu. Cách giảm thiểu ở S10 yếu thật, nhưng bản sửa của D2 làm phình phạm vi |
| #4 S5 mâu thuẫn với S9 | **Phóng đại** | S5 ghi "B and C both need A first", tức là sắp xếp thứ tự, không bác bỏ. Điểm đúng: live tracking ở tháng 5–9 vượt phạm vi |
| #5 Counter mode sơ sài | **Đúng** | — |
| #6a Bỏ sót B2C | **Phóng đại** | S4 có nhắc "customers on the shop floor", chỉ chưa nêu rõ là B2C |
| #6b "Round 2 prototype" | **Đúng** | Tuy nhiên tên thay thế "Validated" lại nói quá (D2-10) |
| #7 Placeholder; thiếu cổng kiểm soát | **Đúng / Đúng một phần** | S7 đã có go/no-go cho pilot; S9 thiếu cổng giữa các nước |
| Nhận định "bài thuộc nhóm 15–20% tốt nhất" | **Không có cơ sở** | Không có dữ liệu so sánh |

### 4.3 Khẳng định về Netcompany và danh tính Company A

| Khẳng định của D2 | Kết luận | Lý do |
|---|---|---|
| EASLEY là nền tảng GenAI độc lập mô hình, bảo mật | **Đúng** | Ra mắt 11/2023, kết nối nhiều LLM, không chia sẻ dữ liệu thô [Đã kiểm]. Vế "tích hợp RAG với danh mục sản phẩm": chưa kiểm được |
| PULSE là "sản phẩm chủ lực cho chuỗi cung ứng và bán lẻ", "control tower", "không nhân bản master data" | **Phóng đại** | Hồ sơ G-Cloud mô tả PULSE là nền tảng điều phối thời gian thực, hướng sự kiện, tích hợp hai chiều quanh một domain model thống nhất [Đã kiểm]. Không tìm thấy ca triển khai bán lẻ; vế master data chưa kiểm được |
| AMPLIO theo "triết lý human-in-the-loop" | **Phóng đại** | AMPLIO là nền tảng tự động hóa quy trình và quản lý hồ sơ [Đã kiểm]; không có nguồn cho "triết lý HITL" |
| Company A "lấy cảm hứng trực tiếp" từ STARK Group | **Không kiểm chứng được** | Đề bài ẩn danh. STARK Group có mặt ở DK/SE/NO nhưng còn ở FI/DE/UK và tập trung khách chuyên nghiệp [Đã kiểm] |
| Bygma hoạt động ở DK, SE, NO | **Sai (với NO)** | Nguồn tìm được: DK, SE, Iceland, Faroe, Ba Lan, Greenland [Chưa kiểm toàn văn] |
| XL-BYG hoạt động ở ba nước | **Đúng một phần** | Khoảng 270–340 cửa hàng ở NO/SE/DK tùy nguồn; là chuỗi liên kết nhà buôn độc lập [Chưa kiểm] |

**Rủi ro nếu đưa các khẳng định này lên slide:**
- Mô tả sai sản phẩm của chính Netcompany trước giám khảo Netcompany.
- Bài đọc như tài liệu bán hàng thay vì tư vấn.
- Gán danh tính cho một case ẩn danh là suy đoán, có thể vi phạm điều khoản bảo mật của đề.

### 4.4 Phương án ATP+ và thiên lệch đánh giá

| Nội dung | Kết luận | Lý do |
|---|---|---|
| ATP+ vẫn đảm bảo time to market | **Phóng đại** | Thêm ngưỡng an toàn, giờ cắt chuyến, tách đơn, gợi ý thay thế, nhập bằng giọng nói, SMS, khóa giữ hàng. Mỗi hạng mục là một mảng tích hợp hoặc quy trình mới |
| Phạm vi Thụy Điển của ATP+ | **Hợp lý** | Thay live tracking bằng "slot validation + status alerts" là thu hẹp phạm vi, nên tiếp thu |
| "3 Local Operating Modes" giải quyết cả 4 thách thức | **Rủi ro cao** | Dễ bị hiểu thành ba sản phẩm; trái yêu cầu "focus on one problem". Cách kể của D1 ("one flow where they meet") tốt hơn |
| Option C mới: "Standalone Fleet / Last-Mile TMS Suite" | **Strawman** | Bản gốc ở D1 là tính năng "slots & tracking", vốn đã được các merchant Anh triển khai [Đã kiểm] |
| Bảng so sánh tự chấm 10/10 | **Không có cơ sở** | Không có trọng số hay dữ liệu |
| Dự đoán điểm tăng từ 34,5 lên 45–47/50 | **Không có cơ sở** | Không có thang chấm; bản sửa vẫn mang lỗi D2-01 đến D2-04. Mức hợp lý khoảng 40/50 nếu sửa đúng |

### 4.5 Những điểm D2 làm đúng và nên tiếp thu

| Điểm | Áp dụng vào D1 |
|---|---|
| Tách KPI độ chính xác "trước duyệt" và "sau duyệt" | S7, với cặp đích nhất quán (C-04) |
| Bổ sung chi phí vận hành vào business case | S8, có cấu phần chi phí |
| Cổng go/no-go giữa các nước | S9 |
| Nút báo lệch kho để kích hoạt kiểm kê | S6, S10 |
| Định nghĩa Counter mode cho Na Uy | S9, dạng rút gọn |
| Thu hẹp phạm vi Thụy Điển (bỏ live tracking) | S9 |
| Thêm phương án hợp nhất ERP vào bảng so sánh | S5 |
| Tách luồng đọc và luồng ghi ERP, fallback file/EDI | S6, S10 |
| Nêu rõ lợi ích cho khách B2C | S4 |

### 4.6 Phát hiện

#### Mức Nghiêm trọng

| Mã | Vị trí trong D2 | Vấn đề | Bằng chứng / phép tính | Đề xuất |
|---|---|---|---|---|
| D2-01 | Phần 4 Q1; Phần 6 (Slide 2, Slide 8) | Ba con số FTE không nhất quán: "~121 FTEs unlocked", "~91 FTEs", và 54,5 FTE suy ra từ 23m | 121,2 là toàn bộ thời gian nhập đơn hiện nay. 121,2 × 75% = 90,9 (thiếu hệ số 60%). Đúng: 121,2 × 60% × 75% = **54,5**; kiểm ngược 23,18m ÷ 425k = 54,5 | "≈55 FTE-equivalents freed (121 FTE of order entry × 60% saved × 75% realised)" |
| D2-02 | Phần 5.1 (mục 4); Phần 6 (Slide 8) | "Hard P&L ≈ 19,8m DKK" không có cơ sở và đếm trùng | 9,8m ≈ 25% × **90,9** × 425k = 9,66m (sai nền FTE; đúng là 25% × 54,5 × 425k = **5,80m**). Khoản 6,0m và 6,2m không có baseline. Cùng một số giờ vừa dùng để giảm thời vụ vừa dùng để bán thêm | Chỉ đưa 5,8m vào lớp tiền thực; 6,0m và 6,2m ghi là "upside to be baselined in weeks 1–2" |

#### Mức Cao

| Mã | Vị trí trong D2 | Vấn đề | Bằng chứng / phép tính | Đề xuất |
|---|---|---|---|---|
| D2-03 | Phần 6 (Slide 7) | Cặp KPI tự mâu thuẫn: "≥85–90% line match" và "≥60% full orders zero-edit" | Để 60% đơn 15 dòng không phải sửa, mỗi dòng cần đúng ≥ 0,6^(1/15) = **96,7%** (đơn 10 dòng: 95,0%). Ở mức 90% chỉ đạt 20,6% | Cặp nhất quán: 95% dòng ↔ ≈46% đơn 15 dòng không sửa; 97% ↔ ≈63% |
| D2-04 | Phần 6 (Slide 7) | "Post-review ≥ 99,5%" và "−50% wrong item/qty" chỉ khớp nhau nếu baseline lỗi dòng đúng bằng 1% | 0,995¹⁵ = 92,8%, tức **7,2% đơn 15 dòng vẫn có lỗi** | Dùng một KPI duy nhất: "Order error rate after review ≤ 50% of the measured manual baseline" |
| D2-05 | Phần 1.3; Phần 5.1 | Mô tả PULSE và AMPLIO vượt quá nguồn công khai | Xem 4.3 | Không nhắc, hoặc một footnote đúng về EASLEY |
| D2-06 | Phần 5.1 | ATP+ làm phình MVP và rollout, đồng thời tự nhận giải quyết cả 4 thách thức | Trái yêu cầu "focus on one problem" và "time to market" | Giữ một vấn đề; chỉ đưa quy tắc tồn thấp và nút báo lệch kho vào MVP |
| D2-07 | Phần 6 (Slide 5) | Option C bị dựng thành bộ TMS 9–15 tháng; Feasibility của A bị nâng từ "Medium-high" lên "High" mà không có lý do | D1 gốc: C = "Delivery slots & tracking only"; A Feasibility = "Medium-high" | Giữ C như D1; không tự nâng điểm A |
| D2-08 | Phần 1.2; Phần 4 Q9 | Số liệu ngành không có nguồn: "80% hàng mua lặp lại", "B2B 65–75% doanh thu", "100.000–400.000+ SKU", "10–25 dòng/đơn" | Xem mục 5.2 | Loại bỏ, hoặc gắn `[A]` |
| D2-09 | Phần 1.2 | Gán Company A cho STARK / Bygma / XL-BYG | Xem 4.3 | Không gán danh tính; dùng "Nordic builders' merchants" |

#### Mức Thấp

| Mã | Vị trí trong D2 | Vấn đề | Đề xuất |
|---|---|---|---|
| D2-10 | Phần 6 (Slide 7) | "Validated Technical PoC" nói quá cho một prototype xây trong một tuần trên catalogue mẫu và adapter giả lập | "Working prototype" (xem D1-12) |
| D2-11 | Phần 4 Q7 | Khẳng định tuyệt đối "mọi ERP bán lẻ từ thập niên 1990 đều hỗ trợ EDI/CSV import" | "Most ERPs support file or EDI order import – confirmed in the week-1 spike." |

---

## 5. Kiểm toán số liệu

### 5.1 Số liệu trong D1

| Con số | Vị trí | Cách tính lại | Kết quả | Nhãn |
|---|---|---|---|---|
| 121 FTE nhập đơn | S8 | 300 × 20 × 8 / 60 × 250 = 200.000 giờ ÷ 1.650 | **121,2** ✓ | [Giả định của đội] |
| 68 / 182 FTE | S8 | 300×15×6/60×250 ÷ 1.650; 300×30×8/60×250 ÷ 1.650 | **68,2 / 181,8** ✓ | [Giả định của đội] |
| 23m DKK (Base) | S2, S8 | 121,2 × 0,6 × 425k × 0,75 | **23,18m** ✓ (giá trị năng lực) | [Giả định của đội] |
| 7m / 49m DKK | S8 | 68,2 × 0,5 × 400k × 0,5; 181,8 × 0,6 × 450k × 1,0 | **6,82m / 49,09m** ✓ | [Giả định của đội] |
| 1.650 giờ/FTE/năm | S8 | — | Hợp lý, không ghi nguồn | [Giả định của đội] |
| 425k DKK/FTE | S8 | — | Ghi Statistics Denmark/SSB/SCB, không ghi bảng hay năm | [Chưa kiểm] |
| MVP 3,5–6m; chương trình = 2,5 × MVP | S8 footnote | 2,5×3,5 = 8,75; 2,5×4,75 = 11,875; 2,5×6 = 15,0 | 8,75–15,0m | [Không có cơ sở] (không có cấu phần) |
| Hoàn vốn 6 / 27 / 2 tháng | S8 | 11,875÷23,18×12; 15÷6,82×12; 8,75÷49,09×12 | **6,1 / 26,4 / 2,1** ✓ | Số học đúng; phương pháp chưa đúng |
| Oiki (IBM): 30 → 12 phút/đơn | S7 footnote | −60% | ✓ khớp case study IBM | [Đã kiểm] (vendor công bố) |
| Topa (Lleverage): 90%+ tự động | S7 footnote | — | ✓ khớp câu chuyện khách hàng | [Đã kiểm] (vendor công bố; một blog của vendor mô tả là tự động hóa hóa đơn) |
| Travis Perkins, STARK UK: khung giờ + tracking | S4 | — | ✓ TP: khung 2 giờ, báo khi xe còn ~20 phút, POD. STARK UK: khung 2 giờ rồi 1 giờ, link theo dõi | [Đã kiểm] |
| JYSK triển khai theo đợt | S9 footnote | — | ✓ 110 cửa hàng Đan Mạch (10/2022–06/2023); Na Uy năm 2026 | [Đã kiểm] |

### 5.2 Số liệu trong D2

| Con số | Vị trí | Cách tính lại | Kết quả | Nhãn |
|---|---|---|---|---|
| ~91 FTE | Phần 4 Q1; Phần 6 Slide 2 | 121,2 × 0,75 = 90,9; đúng phải là 121,2 × 0,6 × 0,75 | **54,5** ✗ | [Không có cơ sở] |
| ~121 FTEs unlocked | Phần 6 Slide 8 | 121,2 là thời gian hiện tại, không phải phần giải phóng | ≈55 (thực hiện) hoặc 72,7 (gộp) ✗ | [Không có cơ sở] |
| ~400 giờ/cửa hàng/năm | Phần 4 Q6 | 200.000 × 60% ÷ 300 | **400** ✓ (gộp; sau hệ số 75% là 300) | [Giả định của đội] |
| ~2,5 giờ/cửa hàng/ngày | Phần 6 Slide 4 | 20 × 8 / 60 | **2,67** (nên ghi ~2,7) | [Giả định của đội] |
| OpEx 2,2m DKK/năm | Phần 5.1; Phần 6 Slide 8 | Không có cấu phần | Không kiểm được | [Không có cơ sở] |
| Net economic 21,0 / 4,8 / 46,5m | Phần 6 Slide 8 | 23,18−2,2; 6,82−2,2; 49,09−2,5 | **20,98 / 4,62 / 46,59** | Số học đúng; OpEx không cơ sở |
| 9,8m (giảm thời vụ, làm thêm giờ, không tuyển bù) | Phần 4 Q1; Phần 6 Slide 8 | 25% × 90,9 × 425k = 9,66m; đúng: 25% × 54,5 × 425k | **5,80m** ✗ | [Không có cơ sở] |
| 6,0m (giảm 50% chi phí trả hàng do sai mã) | Phần 4 Q1 | Suy ngược: baseline = 12,0m/năm = 8 DKK/đơn trên 1,5m đơn | Không có baseline | [Không có cơ sở] |
| 6,2m (+1 đơn B2B/cửa hàng/tuần) | Phần 4 Q1 | 6,2m ÷ (300 × 52) = 397 DKK lợi nhuận gộp/đơn | Không có giá trị đơn hay biên lợi nhuận; trùng giờ với khoản 9,8m | [Không có cơ sở] |
| Hard P&L 19,8m | Phần 6 Slide 2, 8 | 9,8 + 6,0 + 6,2 − 2,2 | 19,8 ✓ số học; **cơ sở không đứng**. Mức bảo vệ được: 5,80 − 2,2 = **3,6m** | [Không có cơ sở] |
| CapEx 11–12m | Phần 6 Slide 8 | 2,5 × (3,5 + 6) / 2 | **11,875m** ✓ | [Giả định của đội] |
| Hoàn vốn ~7 tháng | Phần 6 Slide 8 | 11,875 ÷ 19,8 × 12 | **7,2** ✓ (nếu dùng 21,0 thì 6,8) | Nền 19,8m không có cơ sở |
| Hoàn vốn ~13 tháng từ ngày đầu | Phần 6 Slide 8 | Không nêu phương pháp. Mô phỏng: lợi ích tăng tuyến tính từ tháng 3 đến tháng 12 | 19,8m → **tháng 15**; 21,0m → **tháng 14**; 3,6m → **tháng 47** | [Không có cơ sở] |
| "80% hàng mua lặp lại" | Phần 4 Q9 | — | Không tìm thấy nguồn | [Không có cơ sở] |
| "B2B chiếm 65–75% doanh thu" | Phần 1.2 | — | Không tìm thấy; STARK chỉ nêu chiến lược tập trung khách chuyên nghiệp | [Không có cơ sở] |
| "100.000–400.000+ SKU" | Phần 1.2 | — | STARK Deutschland: > 500.000 sản phẩm có thể đặt | Khoảng này [Không có cơ sở] |
| "10–25 dòng/đơn" | Phần 3, tử huyệt #1 | — | — | [Không có cơ sở] |
| "Shared core ~75% / local ~25%" | Phần 1.3; Phần 5.1 | — | — | [Không có cơ sở] |

### 5.3 Phép tính tham chiếu

| Chỉ số | Công thức | Kết quả |
|---|---|---|
| Xác suất đơn 15 dòng đúng hoàn toàn | p¹⁵ | 90% → **20,6%** · 95% → 46,3% · 99% → 86,0% · 99,5% → **92,8%** |
| Độ chính xác mỗi dòng cần để 60% đơn không phải sửa | 0,6^(1/n) | 15 dòng: **96,7%** · 10 dòng: **95,0%** |
| Điểm hòa vốn tiền mặt trong 24 tháng | 11,875 ÷ 2 + 2,2 | Cần **8,14m/năm** tiền thực; hiện có 5,80m → **thiếu 2,34m/năm**, pilot phải chứng minh phần này từ chi phí sai đơn giảm |

---

## 6. Đối chiếu D1 – D2 và khuyến nghị

| Mã | Chủ đề | D1 – OrderFlow (Hoàng) | D2 – ATP+ (Thy) | Khuyến nghị | Lý do |
|---|---|---|---|---|---|
| C-01 | Hướng giải | Lớp AI nhận đơn | ATP đa điểm, 3 chế độ địa phương, nhập bằng giọng nói, SMS | **Giữ D1, tiếp thu chọn lọc** (C-02 đến C-15) | Một vấn đề, MVP hẹp, prototype sẵn có |
| C-02 | Con số tác động | 23m DKK (giá trị) | 21m net; 19,8m hard; "~91" và "~121 FTE" | **Ba lớp: 23m (≈55 FTE) → 5,8m tiền thực [A] → ≈3,6m ròng sau chi phí vận hành [A]**; 6,0m và 6,2m là phần cần baseline | Số học đúng, có cơ sở, không đếm trùng |
| C-03 | Thời gian hoàn vốn | 6 tháng | ~7 tháng / ~13 tháng | **Hai lớp:** ≈14 tháng theo giá trị kinh tế (có triển khai dần); ≈4 năm nếu chỉ tính tiền thực. Nêu điểm hòa vốn 2,3m/năm | Minh bạch theo chuẩn CFO |
| C-04 | Bộ KPI | 5 KPI; nhãn "after review ≥ 90%" | Trước duyệt 85–90%, sau duyệt 99,5%, ≥60% không sửa | **95% dòng trước duyệt ↔ ≥45% đơn không sửa; lỗi theo đơn ≤ 50% baseline; giao đúng ngày đã hứa +10 điểm %** | Cả hai phiên bản đều mâu thuẫn hoặc thiếu |
| C-05 | Phương án C | "Delivery slots & tracking only" | "Standalone Fleet/TMS Suite, 9–15 tháng" | **Giữ cách mô tả của D1**, sửa mệnh đề "needs A first" (D1-07) | Tránh strawman |
| C-06 | Feasibility của A | Medium-high | High | **Giữ Medium-high** | Không tự nâng điểm phương án của mình |
| C-07 | Phạm vi Thụy Điển | Time slots + live tracking | Slot validation + SMS | **Hứa ngày + báo trạng thái**; live GPS để năm 2 | Time to market |
| C-08 | Counter mode (Na Uy) | Một dòng, chưa định nghĩa | SOP 4 bước + giọng nói + khóa giữ hàng | **Định nghĩa ngắn gọn** (D1-10); không đưa giọng nói | Rõ ràng, không phình |
| C-09 | Rủi ro tồn kho | "Improves it over time" | Ngưỡng an toàn + tách đơn + gợi ý thay thế + nút báo lệch | **Quy tắc tồn thấp → ngày DC hoặc kiểm tay; nút báo lệch → kiểm kê**; bỏ tách đơn và gợi ý thay thế khỏi MVP | Có cơ chế cụ thể, không phình |
| C-10 | Tên prototype | "Round 2 prototype" | "Validated Technical PoC" | **"Working prototype" + ảnh + kết quả backtest** | Đúng vai, không nói quá |
| C-11 | Vai trò của STARK | "Competitor" | Hình mẫu của Company A | **Không dùng cả hai**: ghi là "UK peers" | Đề ẩn danh; STARK UK cùng tập đoàn với Beijer và Neumann Bygg |
| C-12 | Sản phẩm Netcompany | Không nhắc | EASLEY + PULSE + AMPLIO | **Không nhắc**, hoặc một footnote đúng về EASLEY | Mô tả PULSE/AMPLIO vượt quá nguồn |
| C-13 | Lợi ích B2C | Gián tiếp | "~400 giờ/cửa hàng/năm" | **Một câu rõ ràng**; dùng 300 giờ (sau hệ số 75%) hoặc ghi rõ 400 là con số gộp | Nhất quán với hệ số thực hiện |
| C-14 | Gợi ý của đề theo từng nước | Ghi sai ("urgent issue in Sweden") | Viết lại đúng nhưng không chỉ ra lỗi | **Trích nguyên văn, giữ chữ "may"** (D1-06) | Giám khảo là người ra đề |
| C-15 | Vì sao không bắt đầu ở Thụy Điển | Không đề cập | Không đề cập | **Thêm hộp "Why not start in Sweden?"** (D1-08) | Câu hỏi gần như chắc chắn sẽ bị hỏi |

---

## 7. Kế hoạch hành động

### 7.1 Danh mục sửa theo slide (D1)

| Slide | Hạng mục | Tham chiếu | Ưu tiên | Thời gian |
|---|---|---|---|---|
| 1 | Điền tên đội và thành viên | D1-01 | P0 | 5 phút |
| 2 | Action title; dòng Impact theo ba lớp; thêm North Star "right-first-time contractor orders" | D1-14, C-02 | P0 | 45 phút |
| 3 | Trích nguyên văn gợi ý của đề; thêm một con số `[A]` về nỗi đau giao hàng | D1-06 | P0 | 30 phút |
| 4 | Đổi thành "UK peers"; thêm câu về B2C | D1-13, D1-20 | P1 | 20 phút |
| 5 | Trọng số + kiểm tra độ nhạy; cột Root cause dạng có/không; phương án E; sửa mệnh đề về C; hộp "Why not start in Sweden?" | D1-07, D1-08 | P0 | 2–3 giờ |
| 6 | Quy tắc tồn thấp + nút báo lệch; câu về EU AI Act; sửa "replaced step by step"; ảnh prototype | D1-11, D1-16, D1-17 | P1 | 1,5 giờ |
| 7 | Bộ KPI nhất quán có baseline; KPI giao đúng ngày; hộp prototype; câu về backtest; action title | D1-04, D1-05, D1-12, D1-15, C-04 | P0 | 2 giờ (+ nửa ngày backtest) |
| 8 | Biểu đồ thác nước ba lớp thay cho con số "DKK 23m"; chi phí vận hành có cấu phần; hoàn vốn hai lớp có triển khai dần; điểm hòa vốn; cấu phần chi phí MVP | D1-02, D1-03, C-02, C-03 | P0 | 4–6 giờ |
| 9 | Cổng go/no-go tháng 3; phạm vi Thụy Điển; định nghĩa Counter mode; dải "Across all three markets" | D1-09, D1-10, D1-18 | P0 | 2 giờ |
| 10 | Action title; cách xử lý rủi ro tồn kho; cột xác suất/tác động; "Decision needed" | D1-11, D1-19 | P1 | 1 giờ |
| Toàn bài | Đồng bộ số liệu giữa slide 2, 7, 8; rà soát tiếng Anh; xuất PDF và xem lại từng trang | — | P0 | 1,5 giờ |

### 7.2 Lộ trình đến hạn nộp

| Ngày | Công việc |
|---|---|
| 17/10 | Chốt C-01 đến C-04 trong đội |
| 18–19/10 | Slide 8; chạy backtest prototype trên đơn mẫu |
| 20/10 | Slide 5 và 7 |
| 21/10 | Slide 2, 3 và 9 |
| 22/10 | Slide 4, 6, 10; chụp ảnh prototype |
| 23/10 | Đồng bộ số liệu toàn bài |
| 24/10 | Người ngoài nhóm đọc thử trong 5 phút |
| 25/10 | Sửa theo góp ý |
| 26/10 | Xuất PDF, kiểm tra tên đội, **nộp trước 18:00** |

### 7.3 Nội dung mẫu

**Slide 8 – Business impact (EN):**
> *"≈55 FTE-equivalents of counter time freed – DKK 23m a year in capacity [A]. Cash-realisable ≈DKK 5.8m a year via avoided temps, overtime and attrition, agreed with employee reps [A]; net ≈DKK 3.6m after run costs [A]. Payback ≈14 months on economic value including ramp-up; on cash alone it needs ≥DKK 2.3m a year of avoided order-error costs – the pilot will measure exactly that."*

**Slide 10 – Decision (EN):**
> *"Decision needed: fund a 12-week pilot in 5–10 Danish stores (DKK 3.5–6m [A]) and nominate pilot stores and employee representatives."*

---

## 8. Chuẩn bị phản biện

Năm câu hỏi khó nhất giám khảo vẫn có thể đặt ra sau khi đã sửa:

| Mã | Câu hỏi | Gợi ý trả lời (EN) |
|---|---|---|
| Q-01 | "The brief says Sweden's delivery problem may have the greatest business impact. Is DKK 23m of staff time really the greatest impact?" | "We chose the root cause, not the loudest symptom. Most late or wrong deliveries start with an unchecked promise at intake. Fixing intake first makes Sweden's delivery promise possible from month 5 on the same core. Delivery and retention upside are baselined in the pilot, not assumed." |
| Q-02 | "If nobody loses their job, where does the cash come from – and have the unions agreed?" | "DKK 23m is capacity. About a quarter becomes cash through fewer seasonal temps, less overtime and not back-filling natural attrition [A] – agreed with employee reps before the pilot. We show payback on both value and cash." |
| Q-03 | "Your prototype was built in a week on a sample catalogue. What accuracy does it reach on real orders, and how do you know errors won't go up?" | "We don't know yet – that is weeks 1–2. We back-test on 500 real past orders, measure today's error rate from credit notes, and only go live if order-level errors after review are at most half of today's." |
| Q-04 | "Order-intake automation already exists (e.g. Esker, Lleverage). Why build?" | "Build-vs-buy is a week-1 decision. Generic tools read POs that already carry SKU codes. Our hard part is Nordic trade slang, units of measure, customer history and three ERPs. We buy extraction if it passes our back-test, and own the matching rules and integration layer." |
| Q-05 | "Your date promise reads stock from the ERP. If ERP stock is wrong, isn't the promise still wrong?" | "Yes, so we never promise blindly. Low-stock lines get a DC-based date or a manual check, and staff flag mismatches in one click to trigger a cycle count. We measure 'promised date kept' from day one." |

---

## Phụ lục A – Thuật ngữ

| Thuật ngữ | Nghĩa trong báo cáo |
|---|---|
| Giá trị năng lực (capacity value) | Giờ công được giải phóng quy ra tiền; **không phải** tiền thực trên P&L |
| Tiền thực (cash-realisable) | Chi phí thật giảm hoặc biên lợi nhuận thật tăng |
| Chi phí vận hành (run cost / OpEx) | Hosting, chi phí gọi mô hình, đội hỗ trợ, bảo trì adapter |
| Triển khai dần (ramp-up) | Giai đoạn rollout, lợi ích tăng dần theo số cửa hàng đã chạy |
| Điểm hòa vốn (break-even) | Mức lợi ích tối thiểu để hoàn vốn trong thời hạn đặt ra |
| Promise-kept rate | % đơn giao đúng ngày đã hứa khi xác nhận |
| Line accuracy / Order accuracy | Độ chính xác theo từng dòng hàng / theo cả đơn |
| Strawman | Phương án đối chứng bị làm yếu đi để dễ bác |
| Go/no-go gate | Điểm quyết định tiếp tục hay dừng trước khi cấp vốn cho đợt tiếp theo |
| Cycle count | Kiểm kê theo mã hàng, không cần đóng cửa hàng |

## Phụ lục B – Nguồn tham khảo

Tra cứu ngày 16/10/2026.

**Benchmark trong D1**
- [IBM – Oiki case study](https://www.ibm.com/case-studies/oiki)
- [Lleverage – Topa Bathroom Products](https://www.lleverage.ai/customer-stories/topa-bathroom-products)
- [Esker – Order management benchmarks](https://www.esker.com/blog/customer-service/how-order-management-benchmarks-can-guide-smarter-business-decisions/)
- [Builders Merchants News – Travis Perkins national delivery tracking](https://www.buildersmerchantsnews.co.uk/news/merchants/travis-perkins-launches-industry-national-delivery-tracking-service) · [Insight DIY](https://insightdiy.co.uk/news/travis-perkins-launches-industry-national-first-real-time-tracking/10902.htm)
- [Builders Merchants News – STARK UK real-time delivery updates](https://www.buildersmerchantsnews.co.uk/news/merchants/stark-uk-launches-real-delivery-update-service) · [Insight DIY](https://www.insightdiy.co.uk/news/stark-uk-launches-realtime-delivery-update-service/16466.htm)
- [JYSK – Unified commerce in all Danish stores](https://gojysk.com/en/news/unified-commerce-now-runs-all-danish-stores) · [Retail Tech Innovation Hub – JYSK in Norway](https://retailtechinnovationhub.com/home/2026/10/4/jysk-rolls-out-enactor-powered-unified-commerce-platform-in-norway-with-holland-and-belgium-next)

**Netcompany**
- [Netcompany launches AI solution EASLEY](https://netcompany-intrasoft.com/news/netcompany-launches-ai-solution-easley-private-and-public-customers) · [Business Chief – EASLEY](https://businesschief.eu/technology/netcompany-easley-ai-solution)
- [G-Cloud 15 service definition (PULSE, AMPLIO…)](https://assets.applytosupply.digitalmarketplace.service.gov.uk/g-cloud-15/documents/580285/106927894358168-service-definition-document-2026-01-30-1326.pdf) · [PULSE listing](https://www.applytosupply.digitalmarketplace.service.gov.uk/g-cloud/services/445066660195690)

**Doanh nghiệp trong ngành**
- STARK Group: [Business units](https://starkgroup.dk/our-business/business-units) · [STARK Deutschland](https://starkgroup.dk/our-business/business-units/stark-deutschland) · [Wikipedia](https://en.wikipedia.org/wiki/Stark_Group)
- Bygma: [Mynewsdesk](https://www.mynewsdesk.com/dk/bygma-gruppen) · [Interior Daily](https://www.interiordaily.com/article/9832326/bygma-revenue-reaches-new-high-as-profits-remain-under-pressure/)
- XL-BYGG: [Gule Sider](https://www.gulesider.no/xl/bedrifter) · [Finn.no](https://www.finn.no/butikk/xlbygg)
- [Builders Merchants News – Repeat sales](https://www.buildersmerchantsnews.co.uk/news/construction/construction-suppliers-unlock-120-repeat-sales-2025)
