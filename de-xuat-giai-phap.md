# IT Consultant Challenge 2026 – Round 1: Phân tích & đề xuất giải pháp

> Hạn nộp: **22:00, 26/10/2026** · PDF · tối đa 10 slide · tiếng Anh
> Ký hiệu: **[A]** = giả định của team (phải ghi rõ trên slide) · **[V]** = số liệu do vendor công bố (chưa kiểm chứng độc lập)

---

## 1. Chẩn đoán: gốc rễ của 4 vấn đề

4 vấn đề trong đề không độc lập — chúng là **4 triệu chứng của cùng một luồng bị gãy: B2B Order-to-Delivery** (nhà thầu đặt hàng → cửa hàng nhận/xử lý → kiểm kho → giao tới công trường).

| Triệu chứng (đề – giữ nguyên chữ "may") | Biểu hiện trong luồng order-to-delivery |
|---|---|
| Manual processes – *may create the greatest impact* in Denmark | Đơn của nhà thầu đến qua điện thoại / email / PDF danh sách vật tư / ảnh chụp → nhân viên **gõ lại thủ công** vào ERP |
| Inconsistent operations – *may be a more urgent priority* in Norway | Mỗi cửa hàng nhận và xử lý đơn một kiểu; nhân viên quầy bị kéo khỏi bán hàng để nhập đơn, gọi điện xác nhận |
| Delivery & fulfilment – *may have greater business impact* in Sweden | Hứa hẹn ngày giao khi **không kiểm tồn kho**; giao trễ/thiếu tới công trường; khách phải gọi hỏi đơn |
| Fragmented systems | Mỗi nước một ERP/quy trình → không có lớp dữ liệu đơn hàng chung để cải tiến một lần, dùng ba nơi |

> ✅ **Lựa chọn (ONE):** *"We prioritise **Manual processes** – specifically contractor order handling."* Đơn B2B được gõ lại thủ công và hứa ngày giao không kiểm tồn. Cải thiện điểm này **mở đường** cho 3 vấn đề kia (lợi ích lan tỏa), nhưng ta **không** tuyên bố "giải quyết cả 4".

**Vì sao không bắt đầu ở Thụy Điển?** Nỗi đau giao hàng ở Thụy Điển có thể lớn hơn, nhưng giao trễ thường bắt đầu từ lời hứa không kiểm tồn ở khâu nhận đơn. Ta sửa khâu nhận đơn ở nơi khối lượng thủ công cao nhất (Đan Mạch [A]) rồi tái dùng lõi ở Thụy Điển từ tháng 5.

**Vì sao không chọn B2C trước?** Khách lẻ mua qua quầy/web với giỏ hàng có sẵn SKU → ít nhập liệu thủ công; nhà thầu đặt qua email/điện thoại với danh sách vật tư tự do, đơn giá trị lớn, mua lặp lại và chịu thiệt hại nặng khi giao trễ → nơi đau và giá trị tập trung. *(Giả định — ghi rõ trên slide.)*

**Vì sao chọn khách B2B (nhà thầu)?** Họ là nhóm khách giá trị cao, mua lặp lại, nhạy cảm nhất với giao hàng đúng giờ (công trường dừng = mất tiền). Các merchant ở Anh (Travis Perkins, STARK UK – cùng tập đoàn với Beijer SE, Neumann Bygg NO) đã cho khách trade khung giờ giao 1–2h + live tracking → giao hàng minh bạch đang thành **chuẩn của ngành** (gọi là "UK peers", không phải đối thủ trực tiếp). Lợi ích cho B2C: mỗi giờ không phải gõ lại đơn là một giờ nhân viên quay lại sàn bán, phục vụ cả khách DIY. *(Đã bỏ trích dẫn "L.E.K. premium >5%" vì chưa xác minh được nguồn gốc — không đưa lên slide.)*

## 2. Ưu tiên: vì sao cơ hội này, không phải cái khác

So sánh 4 phương án (thang 1–5):

| Phương án | Business impact | Time-to-market | Khả thi | Tái sử dụng 3 nước | Đánh vào gốc rễ? |
|---|---|---|---|---|---|
| **A. OrderFlow – AI order intake (chọn)** | 5 | 4 | 4 | 5 | Có — gốc của manual processes |
| B. Cổng/app tự phục vụ cho nhà thầu | 4 | 2 (cần thời gian để khách chấp nhận) | 3 | 5 | Một phần — cần dữ liệu tồn kho/giá chuẩn trước |
| C. Chỉ delivery slots & tracking (như merchant Anh) | 4 | 3 | 3 | 4 | Một phần — chỉ SE; cần đội xe/TMS |
| D. App quản lý công việc cửa hàng (task mgmt) | 2 | 5 | 5 | 5 | Không — chữa triệu chứng NO |
| E. Hợp nhất/thay ERP | 5 | 1 (nhiều năm) | 2 | 5 | Có — nhưng loại vì time-to-market |

Lập luận then chốt: *"C can run without A, but its value is capped while dates are promised without a stock check – so A first, C later on the same order API."* B cũng hưởng lợi từ cùng Order API. E đúng gốc nhưng quá chậm.

## 3. Giải pháp: "OrderFlow" – lớp đơn hàng thông minh dùng chung

**Ý tưởng:** không thay ERP (big-bang, rủi ro, chậm). Đặt **một lớp tích hợp + AI** phía trước các ERP của từng nước (mô hình *strangler fig*).

```
Kênh vào (email, PDF, ảnh, điện thoại→ghi chú, sau này: portal)
        │
        ▼
[1] AI Intake  ── đọc đơn, trích xuất sản phẩm/số lượng/địa chỉ công trình/ngày cần
        │
[2] AI SKU Match ── khớp tên gọi dân dã ("tấm thạch cao 13 ly") → mã SKU, dựa trên catalogue + lịch sử mua của khách
        │
[3] Availability & Delivery-date Promise ── kiểm tồn kho cửa hàng/kho trung tâm (DC), đề xuất ngày giao khả thi; dòng tồn thấp → ngày theo DC hoặc kiểm tay
        │
[4] Staff Review (1 màn hình) ── nhân viên duyệt/sửa trong vài giây (human-in-the-loop)
        │
[5] Common Order API ──► Adapter ERP DK │ Adapter ERP NO │ Adapter ERP SE
        │
[6] Proactive updates cho nhà thầu: xác nhận đơn + ngày giao, cảnh báo thiếu hàng, tin nhắn trạng thái tự động từ sự kiện ERP (đã xuất kho, đã giao)
    (Live GPS tracking / khung giờ giao: KHÔNG thuộc phạm vi — tùy chọn năm 2, chưa tính chi phí)
```

**AI tạo giá trị ở đâu (trả lời thẳng câu hỏi của BTC):**
1. **Hiểu đơn phi cấu trúc** (LLM + document AI): email, PDF bản vẽ/danh sách vật tư, ảnh viết tay.
2. **Khớp sản phẩm** (embedding search + lịch sử mua): xử lý tên gọi khác nhau theo ngôn ngữ DK/NO/SE.
3. **Gợi ý bổ sung** (giai đoạn sau): "đơn có tấm thạch cao nhưng thiếu vít/băng keo".
4. **Dự báo ETA/rủi ro giao trễ** (giai đoạn sau, khi có dữ liệu).
— Luôn có người duyệt ở bước cuối → tuân thủ EU AI Act (rủi ro thấp), dữ liệu lưu trong EU/EEA (GDPR).

**Một giải pháp – ba cách triển khai** (đúng yêu cầu "not identical implementation"):

| Nước | Điểm đau chính | Module nhấn mạnh | Cách triển khai |
|---|---|---|---|
| 🇩🇰 Denmark | Manual processes | [1]+[2]+[4]: tự động hóa nhập đơn | Pilot đầu tiên — đo giờ công tiết kiệm |
| 🇸🇪 Sweden | Delivery & fulfilment | [3]+[6]: ngày giao kiểm theo tồn Store + DC + tin nhắn trạng thái tự động từ ERP | Wave 2 — đo % ngày hứa được giữ, số cuộc gọi "đơn tôi đâu". Live GPS tracking: tùy chọn năm 2 |
| 🇳🇴 Norway | Store operations | [4] **Counter mode** = cùng màn hình duyệt dùng cho đơn tại quầy và qua điện thoại → mọi cửa hàng Na Uy nhận, kiểm và xác nhận đơn **theo cùng một cách** | Wave 3 — đo thời gian xử lý tại quầy & độ đồng đều giữa cửa hàng. *(Ghi chú phụ, không phải lý do chính: luật e-invoicing B2B Na Uy bắt buộc từ 01/01/2027 — đơn có cấu trúc giúp tuân thủ dễ hơn.)* |

**Đóng khung theo cách Netcompany nghĩ** (từ nghiên cứu về Netcompany):
- **Reuse, not reinvent:** một lõi dùng chung (AI intake, SKU match, Order API) + cấu hình/adapter theo nước — không xây 3 hệ thống.
- **Incremental, không big-bang:** strangler-fig, giữ ERP hiện có, giảm rủi ro từng bước.
- **Chủ quyền & tin cậy** (khớp slide "European sovereignty", "secure, reliable, transparent"): hạ tầng & model chạy trong EU/EEA, dữ liệu theo từng nước, **không train trên dữ liệu khách**, mọi quyết định AI có điểm tin cậy + người duyệt + log kiểm toán; EU AI Act: rủi ro tối thiểu/hạn chế.
- **AI nhúng trong quy trình, không phải chatbot.**

## 4. Phạm vi MVP (≈ 12 tuần) [A]

**Trong phạm vi:**
- 1 nước (Đan Mạch), **5–10 cửa hàng pilot** có lượng đơn B2B lớn
- 1 kênh: **email + file đính kèm (PDF/ảnh)** gửi tới địa chỉ order chung
- AI trích xuất + SKU match + kiểm tồn kho cửa hàng
- Màn hình duyệt cho nhân viên
- Đẩy đơn vào ERP Đan Mạch qua 1 adapter
- Email xác nhận tự động cho nhà thầu kèm ngày giao dự kiến

**Ngoài phạm vi MVP:** portal khách hàng, tối ưu tuyến, tracking xe, upsell AI, NO/SE ERP.

**Lộ trình 12 tuần (2 nấc):**
| Tuần | Việc | Kết quả |
|---|---|---|
| 1 | Integration spike (API / import file / EDI của ERP DK) + 500 đơn lịch sử làm test set; kiểm giả định 20 đơn/ngày theo loại cửa hàng | Biết đường đưa đơn vào ERP |
| 2–5 | AI đọc đơn + SKU match + màn hình duyệt; back-test offline | Độ chính xác đo được trước khi go-live |
| **6** | **Assistive mode live ở 5–10 cửa hàng**: AI điền sẵn, nhân viên duyệt, đưa vào ERP như hiện nay (copy/import) | **Giá trị thật từ tuần 6, không cần sửa ERP** |
| 7–10 | Adapter ghi đơn thẳng vào ERP + xác nhận kèm ngày giao cho nhà thầu | Bỏ bước copy tay |
| 11–12 | Đo KPI → **Gate 1 (tháng 3): go/no-go** trước khi cấp vốn cho adapter SE/NO | Quyết định dựa trên số liệu thật |

> Rủi ro lớn nhất của time-to-market là **API của ERP chưa biết** → nấc assistive mode đưa rủi ro này ra khỏi đường găng. Câu chốt: *"First stores live in week 6 – no ERP change needed."*

**Team [A]:** ~6–8 người (PO, 2–3 dev, 1 ML/AI engineer, 1 integration engineer, UX, đại diện cửa hàng).

**KPI & ngưỡng thành công [A]:**
| KPI | Mục tiêu MVP |
|---|---|
| Tỷ lệ đơn "touchless" (duyệt không cần sửa) | ≥ 60% |
| AI khớp đúng **từng dòng hàng trước khi duyệt** (back-test 500 đơn) | ≥ 95% *(lưu ý: 90%/dòng → đơn 15 dòng chỉ đúng trọn 0,9¹⁵ ≈ 21%)* |
| Tỷ lệ lỗi đơn **sau khi duyệt** | ≤ 50% baseline hiện tại |
| Thời gian xử lý / đơn | −60% |
| Thời gian từ nhận đơn → xác nhận cho khách | < 15 phút |
| Ngày giao đã hứa được giữ | +10 điểm % so với baseline [A] |

> Pha chạy thật chỉ ~3–6 tuần (≈1.500–3.000 đơn) → KPI lỗi được **back-test thêm trên 500 đơn cũ**; tuần chạy thật xác nhận thời gian xử lý và mức độ nhân viên sử dụng.

Benchmark tham chiếu **[V]** — *"vendor-reported cases from adjacent distribution sectors"*, đã mở trang gốc kiểm chứng:
- OIKI Acciai (phân phối thép, Ý – IBM): **30 → 12 phút/đơn (−60%)**
- Topa Bathroom Products (wholesaler Hà Lan – Lleverage): **"+90% automated"**, ~3,8 FTE được điều chuyển
- Biodeal (phân phối sữa – Mirage Metrics): median 48 giây email→đơn, **~7% cần người kiểm**
- Esker – công ty vật liệu xây dựng **ẩn danh**: "84% faster" (không có năm, không trích 51%/3,5 phút vì không có trên trang)

→ **Chưa tìm thấy benchmark độc lập nào của ngành builders' merchant** — nói thẳng điều này trên slide; chính MVP là để tạo ra số liệu đó. Mục tiêu của ta **thận trọng hơn** vendor vì danh sách vật tư của nhà thầu (VD "45x95 C24", tiếng lóng nghề) khó hơn đơn công nghiệp.

### 4b. Prototype cho Vòng 2 cuộc thi (team 3 người tự build trong 1 tuần, 2–9/11)

Vòng 2 chấm "product, technical capability, problem-solving approach"; vòng 3 có **change request** + demo live. Vì vậy MVP trong proposal phải **build được bởi chính team trong 1 tuần**:

| Thành phần prototype | Cách làm gọn |
|---|---|
| Hộp thư đơn mẫu | 10–20 email/PDF/ảnh danh sách vật tư giả lập (tiếng Anh + Đan Mạch) |
| AI extraction | LLM API (vùng EU) trả JSON có cấu trúc: sản phẩm, số lượng, địa chỉ công trình, ngày cần |
| SKU match | Catalogue giả ~300–500 sản phẩm + embedding search + lịch sử mua mẫu, trả điểm tin cậy |
| Màn hình duyệt | Web app: đơn gốc bên trái, đơn đã parse bên phải, dòng tin cậy thấp tô vàng, sửa 1 click |
| Tồn kho & ETA | Bảng tồn kho giả theo cửa hàng → ngày giao dự kiến |
| ERP adapter | Mock ERP + **adapter theo nước (DK/SE/NO) qua config** → minh họa "one solution, different implementation" |
| Xác nhận cho khách | Email/tin nhắn xác nhận tự sinh, kèm ETA |
| Đo lường | Dashboard nhỏ: % touchless, thời gian xử lý, độ chính xác trên test set |

**Thiết kế sẵn cho change request vòng 3:** kiến trúc module + config theo nước, để thêm kênh (ảnh/điện thoại), thêm nước, hay thêm khung giờ giao chỉ là thêm module.
Stack gợi ý (không bị giới hạn): Next.js hoặc Streamlit + FastAPI + SQLite/Postgres + LLM API.

> Trong proposal: phân biệt rõ **"Client pilot (12 tuần, cửa hàng thật)"** và **"Our prototype (sẽ build ở Round 2)"** — cho giám khảo thấy ý tưởng vừa thực tế với khách, vừa build được ngay.

## 5. Business case (ước tính, cần ghi giả định) [A]

**Công thức:** cửa hàng × đơn thủ công/ngày × phút/đơn ÷ 60 × 250 ngày ÷ 1.650 giờ/FTE = FTE nhập đơn → × % giảm thời gian × chi phí/FTE × hệ số hiện thực hóa = tiết kiệm/năm

| | Bi quan | **Cơ sở** | Lạc quan |
|---|---|---|---|
| Cửa hàng [A] | 300 | 300 | 300 |
| Đơn B2B thủ công / cửa hàng / ngày [A] | 15 | **20** | 30 |
| Phút / đơn [A] | 6 | 8 | 8 |
| FTE đang nhập đơn | 68 | **121** | 182 |
| % giảm thời gian (vendor: 60–84%) | 50% | 60% | 60% |
| Chi phí đầy đủ / FTE (DK ~450k; NO/SE ~370k) | DKK 400k | DKK 425k | DKK 450k |
| Hệ số hiện thực hóa (điều chuyển/tiêu hao tự nhiên) | 50% | 75% | 100% |
| FTE được giải phóng (= FTE × % giảm × hệ số) | 17 | **≈55** | 109 |
| **Giá trị năng lực / năm** (value, không phải tiền mặt) | **~DKK 7m** | **~DKK 23m** | **~DKK 49m** |
| Chi phí MVP (6–8 người × ~65 ngày × DKK 8–12k/ngày) | 6m | 4,5m | 3,5m |

**Tách "giá trị" khỏi "tiền mặt" (kịch bản cơ sở)** — vì ta cam kết *không cắt người*:

| Bước | DKK/năm |
|---|---|
| Giá trị năng lực (≈55 FTE trả lại cho bán hàng) | 23m |
| Phần quy ra tiền mặt [A]: bớt thuê thời vụ, làm thêm giờ, không tuyển bù người nghỉ — thống nhất với đại diện người lao động | ≈5,8m |
| Chi phí vận hành (LLM, hạ tầng, hỗ trợ) [A] | −2,2m |
| **Tiền mặt ròng** | **≈3,6m** |

→ Hoàn vốn tiền mặt: MVP (~4,5m) ≈ 15 tháng; toàn chương trình (≈2,5× MVP ≈ 11m) ≈ 3 năm. Phần lớn giá trị nằm ở năng lực bán hàng và giữ chân nhà thầu (chưa tính) → đó là lý do có **Gate 1** sau pilot.

Ghi chú quan trọng:
- Tiết kiệm trải mỏng (~0,2 FTE/cửa hàng) → **không trình bày là cắt giảm nhân sự**, mà là "trả lại ≈55 FTE thời gian cho tư vấn bán hàng" (hiện ~121 FTE đang gõ đơn) — phù hợp văn hóa công đoàn Bắc Âu.
- Con số chính trên slide nên là **"≈55 FTE-equivalents freed"**, không phải "DKK 23m" (dễ bị hiểu là tiền thật).
- 20 đơn/ngày áp cho mọi cửa hàng, kể cả cửa hàng thiên DIY → kiểm theo loại cửa hàng ở tuần 1–2.
- Lương: DK sales assistant ~DKK 31k/tháng (Danmarks Statistik); NO ~NOK 457k/năm (SSB); SE ~SEK 34,6k/tháng (SCB) — quy đổi tỷ giá cần kiểm lại.
- 300 cửa hàng là giả định ("hundreds" trong đề); không chuỗi Bắc Âu nào công bố số đơn/cửa hàng → **20 đơn/ngày là giả định cần pilot xác nhận**. Sanity check: ~DKK 240k doanh thu/cửa hàng/ngày (ước từ Beijer) → 20 đơn × DKK 2–3k = 17–25% doanh thu, hợp lý.
- Giá trị doanh thu (giữ chân nhà thầu nhờ xác nhận nhanh, giao đúng hẹn) có thể lớn hơn tiết kiệm chi phí nhưng **chưa có số liệu** → trình bày định tính, đo trong pilot (NPS, tỷ lệ mua lặp lại).

> Trên slide: trình bày **công thức + bảng 3 kịch bản**, nhấn mạnh kịch bản cơ sở, nói rõ biến nào sẽ được MVP kiểm chứng.

## 6. Scale – rollout 3 nước (theo mẫu JYSK: 1 cửa hàng → cả nước → từng nước)

| Giai đoạn | Thời gian [A] | Nội dung |
|---|---|---|
| 0. MVP Denmark | Tháng 0–3 | 5–10 cửa hàng, email intake; assistive mode từ tuần 6 → **Gate 1 (tháng 3)** |
| 1. Denmark full | Tháng 4–6 | Toàn bộ cửa hàng DK, thêm kênh ảnh/ghi chú điện thoại |
| 2. Sweden | Tháng 5–9 | Adapter ERP SE + ngày giao kiểm theo tồn Store + DC + tin nhắn trạng thái tự động từ sự kiện ERP |
| 3. Norway | Tháng 8–12 | Adapter ERP NO + Counter mode (một cách nhận đơn chuẩn tại quầy/điện thoại). Ghi chú phụ: đơn có cấu trúc giúp e-invoicing B2B (bắt buộc 01/2027) |
| 4. Năm 2 (tùy chọn, chưa tính chi phí) | — | Live GPS tracking + khung giờ giao, portal nhà thầu, AI gợi ý mua kèm, dự báo rủi ro giao trễ — trên cùng Order API |

**Across all three markets – Phần dùng chung:** AI core, Order API, data model, UI duyệt. **Phần địa phương:** adapter ERP, ngôn ngữ/thuật ngữ sản phẩm, quy tắc ngày giao, quy trình cửa hàng.

**Change management:** tham vấn đại diện người lao động trước triển khai (DK samarbejdsudvalg, NO Arbeidsmiljøloven kap. 8, SE MBL); "store champions" mỗi nước; thông điệp "AI làm việc nhập liệu, nhân viên làm việc tư vấn".

## 7. Rủi ro & giảm thiểu

| Rủi ro | Giảm thiểu |
|---|---|
| AI khớp sai SKU với danh sách vật tư tự do | Human-in-the-loop; học từ chỉnh sửa; đo accuracy offline trước khi go-live |
| ERP cũ khó tích hợp | Adapter/RPA tạm thời; bắt đầu với 1 ERP |
| Dữ liệu tồn kho không chính xác | Dòng tồn thấp → ngày theo DC hoặc kiểm tay; nhân viên báo lệch kho bằng 1 click → kích hoạt kiểm kê (cycle count) |
| Nhân viên kháng cự | Đồng thiết kế với cửa hàng pilot; không cắt giảm nhân sự |
| Vendor lock-in / chi phí LLM | Kiến trúc mở, có thể đổi model; xử lý trong EU |

## 8. Dàn ý 10 slide (tiếng Anh)

1. **Title** – "One order flow, three markets: fixing Company A's contractor order-to-delivery"
2. **Executive summary** – vấn đề, giải pháp, MVP, impact, ask (1 slide trả lời tất cả)
3. **Problem understanding** – 4 thách thức → 1 gốc rễ (sơ đồ luồng order-to-delivery với các điểm gãy)
4. **Who & why it matters** – persona nhà thầu + nhân viên quầy; chi phí của việc giao trễ; UK peers đã làm; lợi ích cho B2C
5. **Prioritisation** – ma trận impact × time-to-market của 4 phương án → chọn A
6. **Solution: OrderFlow** – kiến trúc 6 bước, AI ở đâu, responsible AI & sovereignty (EU hosting, human-in-the-loop, audit log)
7. **MVP scope** – client pilot 12 tuần + KPI go/no-go; và prototype team sẽ build ở Round 2 (mockup màn hình duyệt)
8. **Business impact** – ≈55 FTE trả lại; thác nước giá trị → tiền mặt ròng; độ nhạy + benchmark [V]
9. **Scale across markets** – roadmap 3 nước, phần chung vs địa phương, change management
10. **Risks, assumptions & next steps** – bảng rủi ro + danh sách giả định

## 9. Những gì team nên kiểm chứng thêm trước khi chốt slide

- Mở trực tiếp các nguồn vendor trước khi trích số (Esker, Topa/lleverage, IBM OIKI, Mirage/Biodéal).
- Báo cáo thường niên STARK Group 2025 (đối thủ/tương tự gần nhất) để lấy tỷ trọng B2B, digital.
- Số liệu lương bán lẻ: Statistics Denmark / SSB / SCB để làm business case chắc hơn.
- Có thể tự làm mini-survey/ phỏng vấn 3–5 người làm xây dựng để có "insight thật" — điểm cộng lớn cho tiêu chí Problem Understanding.

### Nguồn chính
- STARK Group FY2024/25: https://starkgroup.dk/newsroom/latest-news/stark-group-delivers-stable-net-sales-and-underlying-earnings-historically-challenging-market
- Travis Perkins tracking: https://www.buildersmerchantsnews.co.uk/Travis-Perkins-launches-industry-first-national-delivery-tracking-service-/52273
- STARK UK realtime delivery: https://www.insightdiy.co.uk/news/stark-uk-launches-realtime-delivery-update-service/16466.htm
- Esker building materials: https://www.esker.com/resources/case-studies/building-materials-company-case-study/
- Topa / lleverage: https://www.lleverage.ai/customer-stories/how-topa-bathroom-products-automated-order-intake-with-ai
- IBM OIKI: https://www.ibm.com/case-studies/oiki
- JYSK rollout: https://gojysk.com/en/news/unified-commerce-now-runs-all-danish-stores
- Norway e-invoicing 2027 (nguồn chính thức): https://www.regjeringen.no/no/aktuelt/nye-lovregler-om-e-fakturering-i-naringslivet-og-enkelte-andre-lovendringer-pa-finansmarkedsomradet-settes-i-kraft/id3166726/
- Mirage Metrics / Biodeal: https://www.casestudies.com/company/mirage-metrics/case-study/biodeal-enters-sap-orders-in-48s-with-mirage-metrics
- Lương DK: https://loen.dk/salgsassistent · NO: https://karrierestart.no/yrke/1047 · SE: https://ledigajobb.se/articles/lon-butikssaljare
- Chi tiết kiểm chứng: xem `deep-dive-kiem-chung-orderflow.md`
