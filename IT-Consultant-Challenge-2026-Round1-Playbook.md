# IT Consultant Challenge 2026 – Round 1: Case Playbook

> Tài liệu chuẩn bị cho đội thi, gồm năm phần: tóm tắt đề, kiến thức nghiệp vụ ngành, bộ công cụ tư vấn chuyên nghiệp, cách làm business case như CFO, và một hướng giải mẫu để tham khảo.
>
> - **Nguồn chính:** đề bài *IT Consultant Challenge 2026 – Round 1* (Netcompany & Code Mely, 16/10/2026).
> - **Nguồn bổ sung:** tra cứu ngày 16/10/2026, xem [mục 12](#12-nguồn-tham-khảo).
> - **Bảo mật:** tài liệu gốc thuộc Netcompany, chỉ dùng cho cuộc thi. Không chia sẻ file này ra ngoài đội.

### Nhãn nguồn dùng trong tài liệu

| Nhãn | Nghĩa |
|---|---|
| **[Đã kiểm]** | Đã đối chiếu với nguồn gốc hoặc nguồn độc lập ngày 16/10/2026 |
| **[Chưa kiểm]** | Có nguồn nhưng chưa đối chiếu toàn văn |
| **[A]** | Giả định minh họa. Đội phải thay bằng giả định của mình và ghi rõ trên slide |
| **[Không nguồn]** | Kiến thức chung trong ngành, chưa tìm được nguồn. Không đưa lên slide như một sự thật |

---

## Mục lục

1. [Tóm tắt đề bài](#1-tóm-tắt-đề-bài-case-at-a-glance)
2. [Đọc giữa các dòng](#2-đọc-giữa-các-dòng-đề-thật-sự-kiểm-tra-gì)
3. [Kiến thức nghiệp vụ ngành](#3-kiến-thức-nghiệp-vụ-ngành-domain-knowledge)
4. [Bộ công cụ của consultant chuyên nghiệp](#4-bộ-công-cụ-của-consultant-chuyên-nghiệp)
5. [Phân tích phương án và ưu tiên](#5-phân-tích-phương-án-và-ưu-tiên)
6. [Hướng giải mẫu (tham khảo)](#6-hướng-giải-mẫu-tham-khảo-không-phải-đáp-án)
7. [Storyline 10 slide](#7-gợi-ý-storyline-10-slide)
8. [Checklist tự chấm](#8-checklist-tự-chấm-theo-tiêu-chí-của-btc)
9. [Lỗi thường gặp](#9-lỗi-thường-gặp-cần-tránh)
10. [Kế hoạch 10 ngày](#10-kế-hoạch-làm-việc-1610--2610)
11. [Thuật ngữ EN–VN](#11-thuật-ngữ-envn)
12. [Nguồn tham khảo](#12-nguồn-tham-khảo)

---

## 1. Tóm tắt đề bài (Case at a glance)

### 1.1 Thông tin nộp bài

| Hạng mục | Chi tiết |
|---|---|
| Ban tổ chức | Netcompany & Code Mely |
| Sản phẩm nộp | Proposal trình bày giải pháp của đội |
| Định dạng | **PDF, tối đa 10 slide** |
| Ngôn ngữ | Ưu tiên tiếng Anh |
| Hạn chót | **22:00 ngày 26/10/2026**. Nộp muộn không được chấp nhận |
| Cách nộp | Upload qua form của BTC, đặt tên **đúng chính xác tên đội** |
| Liên hệ | EB.VN@netcompany.com |

### 1.2 Về ban tổ chức: Netcompany

- Thành lập năm 2000 tại Copenhagen, hơn 10.000 nhân sự ở hơn 10 quốc gia, trong đó có Việt Nam (9.845 nhân viên cuối 2025, 28,7% nữ, hơn 50 quốc tịch – theo đề).
- Xây dựng và vận hành hạ tầng số cho chính phủ, ngành trọng yếu và doanh nghiệp trong môi trường **phức tạp, có quản lý chặt**.
- Thông điệp định vị: ***"Building European sovereignty for the age of AI"*** – *secure, reliable, transparent*.

**Các nền tảng của Netcompany.** Chỉ nhắc nếu mô tả đúng, và tối đa ở một footnote.

| Nền tảng | Mô tả theo nguồn công khai | Nhãn |
|---|---|---|
| **EASLEY** | Nền tảng GenAI độc lập mô hình (kết nối nhiều LLM), ra mắt 11/2023 cho khách hàng tư nhân và công; dữ liệu thô không chia sẻ cho bên thứ ba | [Đã kiểm] |
| **PULSE** | Nền tảng điều phối thời gian thực, hướng sự kiện; tích hợp hai chiều với hệ thống sẵn có quanh một domain model thống nhất | [Đã kiểm] (hồ sơ G-Cloud) |
| **AMPLIO** | Nền tảng điều phối tự động hóa quy trình và quản lý hồ sơ (case management) | [Đã kiểm] |
| AMI | Có trong danh sách nền tảng, chưa tìm được mô tả | [Chưa kiểm] |

> **Ý nghĩa cho bài thi:**
> - Giám khảo là người của Netcompany. Một giải pháp có AI **an toàn, minh bạch, dữ liệu lưu tại EU** và **giao nhanh, ít rủi ro** sẽ khớp với cách họ nhìn nhận dự án tốt.
> - Mô tả sai sản phẩm của chính họ là cách mất điểm nhanh nhất. Bài cũng không nên đọc như tài liệu bán hàng.

### 1.3 Company A

- Nhà bán lẻ vật liệu xây dựng hàng đầu Đan Mạch, **hàng trăm cửa hàng** tại Đan Mạch (DK), Na Uy (NO), Thụy Điển (SE).
- Phục vụ **cả doanh nghiệp xây dựng (B2B / "pro") lẫn người tiêu dùng (B2C / DIY)**.
- Bán vật liệu xây dựng, dụng cụ, sản phẩm cải tạo nhà.
- *"One business. Three markets. Different ways of working."*

> **Không gán Company A cho một công ty thật.**
> - Đề ẩn danh, nên gán danh tính là suy đoán và có thể đụng điều khoản bảo mật.
> - Ví dụ: có chuỗi khớp ba thị trường nhưng còn hoạt động ở nước khác; có chuỗi không có mặt ở Na Uy (xem 3.4).

### 1.4 Bốn thách thức kinh doanh

| Thách thức | Mô tả trong đề | Gợi ý của đề (nguyên văn có chữ *may*) |
|---|---|---|
| **Manual processes** | Kém hiệu quả, tốn công sức nhân viên | DK: *"may create the greatest impact"* |
| **Inconsistent operations** | Vận hành cửa hàng và trải nghiệm khách không đồng nhất | NO: store operations *"may be a more urgent priority"* |
| **Delivery & fulfilment** | Vấn đề đơn hàng và giao hàng làm giảm hiệu quả và độ tin cậy | SE: *"may have greater business impact"* |
| **Fragmented systems** | Hệ thống khác nhau giữa các nước, khó nhân rộng cải tiến | Cả 3 nước (nguyên nhân gốc / enabler) |

> **Trích đúng chữ của đề.** "Urgent" là của Na Uy; "greater business impact" là của Thụy Điển. Ghi nhầm hoặc bỏ chữ *may* sẽ bị giám khảo (người ra đề) nhận ra ngay.

Các thách thức **liên kết với nhau**, nhưng tác động và độ khẩn cấp **khác nhau theo thị trường**. Thị trường **cạnh tranh cao**.

### 1.5 Yêu cầu của Ban điều hành

Ban điều hành muốn đầu tư **MỘT giải pháp số** có tác động lớn nhất. Giải pháp đó **không triển khai y hệt** ở ba nước, và phải tính đến: quy trình địa phương, hệ thống sẵn có, nhu cầu vận hành, cửa hàng và phân phối, tác động lên nhân viên và khách hàng, cách rollout khác nhau.

> *"One strategic solution does not necessarily mean one identical implementation."*

### 1.6 Nhiệm vụ: Identify → Prioritise → Solve → Scale

| Bước | Yêu cầu |
|---|---|
| **01 Identify** | Chọn **MỘT** cơ hội kinh doanh then chốt |
| **02 Prioritise** | Giải thích vì sao ưu tiên hơn các thách thức khác |
| **03 Solve** | Giải pháp số + **phạm vi MVP tập trung**, chứng minh tác động |
| **04 Scale** | Rollout qua các thị trường, xét khác biệt địa phương và ràng buộc |

> **Time to market is critical. Scope carefully. Focus on one problem. Maximise the impact.**

### 1.7 Tips từ BTC

- Được giả định khi thiếu thông tin, nhưng phải **nêu rõ và giải thích**.
- Đề **cố ý để mở**. Điểm nằm ở việc chọn đúng và trình bày **logic, có cấu trúc**.
- Luôn nghĩ tới **time to market** khi xác định MVP.
- Câu hỏi gợi ý: vấn đề nào? ai chịu ảnh hưởng? vì sao quan trọng? giải pháp? phạm vi MVP? **AI tạo giá trị ở đâu?**

### 1.8 Tiêu chí chấm điểm

| Tiêu chí | Định nghĩa của BTC | Giám khảo sẽ tìm |
|---|---|---|
| **Problem Understanding** | Go beyond the surface and find the real problem | Nguyên nhân gốc; ai đau, đau bao nhiêu (có con số) |
| **Prioritisation & Critical Thinking** | Analyse, evaluate and choose what matters most | Tiêu chí có trọng số; phương án đối chứng công bằng; nói rõ **không làm gì** |
| **Business Impact** | Turn ideas into measurable value for the business | KPI có baseline; business case tách năng lực và tiền mặt |
| **Feasible Solution** | Practical, realistic IT solution | MVP hẹp, tích hợp được hệ thống cũ, có cổng go/no-go |
| **Structured Thinking & Innovation** | Combine creativity with a clear and logical approach | Storyline mạch lạc; con số khớp giữa các slide; AI có mục đích |

---

## 2. Đọc giữa các dòng: đề thật sự kiểm tra gì?

1. **"Chọn MỘT" là bẫy lớn nhất.** Đừng tuyên bố "giải cả 4 thách thức". Hãy nói "một vấn đề nằm ở nơi các thách thức gặp nhau".
2. **Gợi ý theo từng nước dùng chữ "may".** Có thể dùng hoặc thách thức, nhưng **phải trả lời thẳng**: vì sao bắt đầu ở nước X mà không phải ở nước mà đề gợi ý tác động lớn hơn.
3. **"One strategic solution ≠ one identical implementation"** gợi ý mô hình Global core + Local flex. Lưu ý: "ba chế độ cho ba nước" dễ bị hiểu thành ba sản phẩm.
4. **"Fragmented systems" là nguyên nhân gốc, nhưng thay ERP không phải MVP.** Hãy biến nó thành *enabler* (lớp tích hợp).
5. **"Time to market" xuất hiện hai lần.** MVP khoảng 12 tuần, một nước, một kênh, có go/no-go. Mọi tính năng cần hạ tầng khác (GPS xe, app tài xế) để sau.
6. **AI phải có mục đích:** gắn với điểm đau, có human-in-the-loop, đo được.
7. **Bảng giả định là bắt buộc.** Mọi con số trên slide cần nhãn nguồn hoặc `[A]`.
8. **Khớp định vị Netcompany:** bảo mật, minh bạch, dữ liệu tại EU, giao hàng ít rủi ro.

---

## 3. Kiến thức nghiệp vụ ngành (Domain knowledge)

Company A thuộc ngành **builders' merchant / DIY retail** (bán lẻ và phân phối vật liệu xây dựng).

### 3.1 Hai phân khúc khách hàng: Pro (B2B) và DIY (B2C)

| Khía cạnh | **Pro / B2B** (nhà thầu, thợ) | **DIY / B2C** (chủ nhà) |
|---|---|---|
| Ai | Nhà thầu, thợ (DK *håndværker*, NO *håndverker*, SE *hantverkare*), chỉ huy công trường | Chủ nhà, người tự sửa nhà |
| Hành vi mua | Lặp lại, theo dự án, giỏ hàng lớn, mua sớm trong ngày [Không nguồn] | Theo mùa, cần cảm hứng, nghiên cứu online trước |
| Kênh đặt hàng | Điện thoại, email kèm PDF/ảnh danh sách vật tư, quầy, webshop/app | Cửa hàng, webshop, click & collect |
| Giá | **Giá riêng theo hợp đồng**, báo giá theo dự án | Giá niêm yết, khuyến mãi |
| Thanh toán | Tài khoản tín dụng, hóa đơn tháng, e-invoice, mã dự án / PO | Thẻ, ví di động, BNPL |
| Fulfilment | **Giao tới công trường** (thường xe cẩu), drive-in kho gỗ, lấy hàng sớm | Mang về, click & collect, giao tận nhà |
| Coi trọng | **Có hàng, giao đúng ngày đã hứa, đủ hàng**, giá, tín dụng | Cảm hứng, tư vấn, giá, tiện lợi |
| Hậu quả khi hỏng | **Đội thợ ngồi chờ**, dự án trễ, chuyển sang đối thủ | Không hài lòng, trả hàng |

> **Insight:** chuỗi lớn trong ngành tập trung vào khách Pro.
> - STARK Group nói chiến lược xoay quanh thợ và nhà thầu nhỏ, vừa, và phục vụ hơn 450.000 thợ [Đã kiểm].
> - Chưa tìm được nguồn công khai cho **tỷ trọng doanh thu B2B** của các chuỗi Bắc Âu. Nếu dùng, gắn `[A]`.

### 3.2 Chuỗi giá trị và quy trình cốt lõi

```
Nhà cung cấp → Thu mua → Kho trung tâm (DC) / cross-dock → Cửa hàng & bãi gỗ
      → Fulfilment: cash & carry | click & collect | drive-in | giao tới công trường | drop-ship
      → Hóa đơn & thanh toán → Hậu mãi (trả hàng, khiếu nại)
```

| Quy trình | Mô tả | Điểm đau thủ công điển hình | KPI chính |
|---|---|---|---|
| **Quote-to-Order** | Nhận yêu cầu, báo giá, chốt đơn | Đọc danh sách vật tư từ PDF/ảnh, tra giá hợp đồng, gõ tay | Quote turnaround, hit rate |
| **Order-to-Delivery** | Nhận đơn, hứa ngày giao, soạn, xếp xe, giao | Nhập lại đơn, hứa ngày không kiểm tồn Store + DC, không báo trạng thái | Promise-kept rate, OTIF, failed delivery rate |
| **Order-to-Cash** | Hóa đơn, thu tiền | Sai hóa đơn, credit note | DSO, credit note rate |
| **Procure-to-Pay** | Đặt NCC, nhận hàng, trả tiền | Đối chiếu PO, phiếu nhận, hóa đơn | Cost per invoice |
| **Inventory & Replenishment** | Dự báo, bổ sung, kiểm kê | Tồn kho hệ thống lệch thực tế ("ghost stock") | Availability, stock accuracy |
| **Store operations** | Mở cửa, nhận hàng, kiểm kê, quầy | Mỗi cửa hàng một cách làm | Task compliance |
| **Customer service** | Tư vấn, trạng thái đơn, khiếu nại | Cuộc gọi "hàng đâu?" (WISMO) | Contact rate |

**Available-to-Promise (ATP):** lượng hàng *thực sự* có thể hứa giao, bằng tồn kho trừ hàng đã giữ cho đơn khác, xét cả cửa hàng và DC. Hứa ngày giao mà không kiểm ATP là nguyên nhân phổ biến của giao trễ hoặc giao thiếu. Tuy vậy, ATP chỉ đúng khi dữ liệu tồn kho đúng, nên cần thêm cơ chế phát hiện lệch kho (xem 6.3).

### 3.3 Vì sao ngành này khó số hóa

- **Hàng nặng, cồng kềnh, dài:** cần xe chuyên dụng, cẩu, khung giờ và điều kiện tiếp cận công trường.
- **Danh mục rất lớn**, nhiều hàng đặt riêng. Ví dụ: STARK Deutschland cho khách tiếp cận hơn 500.000 sản phẩm, phần lớn đặt theo yêu cầu [Đã kiểm].
- **Đơn phức tạp:** giao từng phần, theo giai đoạn thi công, thay đổi phút chót.
- **Đơn không cấu trúc:** email, PDF, Excel, ảnh chụp; **từ lóng nghề** và **đơn vị tính** khác nhau (thanh, mét dài, m², kiện).
- **Mùa vụ và thời tiết:** cao điểm xuân–hè.
- **Chi phí lao động Bắc Âu cao**, nên tự động hóa có giá trị rõ, nhưng phải tính đúng (mục 4.6).

### 3.4 Bối cảnh ba thị trường

| Khía cạnh | Đan Mạch (DK) | Na Uy (NO) | Thụy Điển (SE) |
|---|---|---|---|
| Tiền tệ | DKK (neo EUR, ~7,46 DKK/EUR) | NOK | SEK |
| Ngôn ngữ | Tiếng Đan Mạch | Tiếng Na Uy (Bokmål/Nynorsk) | Tiếng Thụy Điển |
| Quan hệ với EU | Thành viên EU | **Ngoài EU, thuộc EEA**: GDPR áp dụng qua EEA; luật số EU thường áp dụng chậm hơn | Thành viên EU |
| Ví di động | MobilePay | Vipps (cùng tập đoàn Vipps MobilePay) | Swish |
| E-invoicing | B2G bắt buộc qua NemHandel; B2B chưa bắt buộc | B2G bắt buộc (EHF/Peppol). **B2B: đã luật hóa 06/2026** (Prop. 44 L (2025–2026)). **Gửi** e-invoice từ **01/01/2027**; **nhận** và kế toán số từ **01/01/2030**; B2C ngoài phạm vi [Đã kiểm, nguồn thứ cấp] | B2G qua Peppol; B2B tự nguyện; ủy ban điều tra báo cáo trước 30/11/2027 [Chưa kiểm] |
| Triển vọng xây dựng | Phục hồi chậm hơn SE | Phục hồi chậm hơn SE | **Phục hồi mạnh nhất** [Chưa kiểm toàn văn] |

**Các chuỗi tham khảo** (danh sách chưa kiểm từng tên, trừ chỗ có ghi chú):

| Chuỗi / tập đoàn | Có mặt | Ghi chú |
|---|---|---|
| **STARK Group** | DK (STARK Danmark), SE (Beijer Byggmaterial), NO (Neumann Bygg), cùng FI, DE, UK | Ba chuỗi Bắc Âu này **cùng một tập đoàn**, không phải ba đối thủ riêng [Đã kiểm] |
| **Bygma** | DK, SE (cùng Iceland, Faroe, Ba Lan, Greenland) | Không thấy hoạt động ở Na Uy [Chưa kiểm toàn văn] |
| **XL-BYG / XL-Bygg** | DK, SE, NO | Chuỗi liên kết các nhà buôn độc lập; khoảng 270–340 cửa hàng, số liệu lệch theo nguồn [Chưa kiểm] |
| Khác | DK: Davidsen, Silvan, jem & fix, Bauhaus · NO: Byggmakker, Optimera/Montér, Maxbo, Obs Bygg · SE: Byggmax, Bauhaus, Hornbach | [Chưa kiểm] |

**Benchmark quốc tế** (thị trường Anh, dùng như "peers", không gọi là đối thủ):
- **Travis Perkins** báo khung giờ giao 2 tiếng qua SMS trong ngày, báo khi xe còn khoảng 20 phút, gửi email bằng chứng giao hàng (POD) [Đã kiểm].
- **STARK UK** báo khung 2 tiếng, sau đó thu hẹp còn 1 tiếng, kèm link theo dõi lộ trình xe [Đã kiểm].

**Văn hóa và thay đổi:**
- Tổ chức phẳng, đồng thuận, **đại diện người lao động tham gia** vào thay đổi lớn [Không nguồn – kiến thức chung].
- Minh bạch về AI ("hỗ trợ, không thay thế").
- Dữ liệu vị trí tài xế cần cơ sở pháp lý và DPIA theo GDPR.

### 3.5 Số liệu thị trường và benchmark

| Số liệu | Nguồn | Nhãn | Cách dùng |
|---|---|---|---|
| 83% doanh nghiệp B2B Bắc Âu dùng kênh số; 28% giao dịch qua kênh số; 21% đã dùng AI (năm trước 15%) | Litium, *Nordic Digital Commerce in B2B 2025* (920 người ra quyết định) | [Đã kiểm] | Bối cảnh: B2B còn nhiều đơn ngoài kênh số |
| Nhận đơn bằng AI: thời gian xử lý từ 30 xuống 12 phút/đơn (−60%) | IBM, case Oiki (thép không gỉ) | [Đã kiểm] (vendor tự công bố) | Benchmark khả thi, ngành lân cận |
| Hơn 90% đơn nhận tự động; khoảng 4 FTE chuyển sang việc khác | Lleverage, case Topa (bán buôn thiết bị phòng tắm, Hà Lan) | [Đã kiểm] (vendor tự công bố) | Như trên |
| Nhập đơn thủ công trung vị khoảng 11 phút, so với 3 phút khi có AI | Esker, benchmark | [Chưa kiểm] (vendor) | Đối chiếu giả định "phút/đơn" |
| 80% thợ dùng smartphone cho công việc; 35–40% đơn có kế hoạch đặt qua web/app | L.E.K. (Anh, 2019) | [Chưa kiểm] | Xu hướng, không phải Bắc Âu |
| Người mua cần reorder thông minh, giao diện mobile-first | Simon-Kucher | [Chưa kiểm] | Định tính |
| JYSK chuyển 110 cửa hàng Đan Mạch sang POS mới theo đợt (10/2022 – 06/2023), sau đó tới các nước Bắc Âu khác | JYSK; báo ngành | [Đã kiểm] | Tiền lệ cho rollout theo đợt |
| Hoạt động xây dựng Scandinavia khoảng +6% năm 2026, Thụy Điển mạnh nhất | Veidekke | [Chưa kiểm toàn văn] | Lập luận chọn thị trường |

> Số liệu vendor và ngoài Bắc Âu chỉ dùng như **chỉ báo**. Ghi nguồn ở footnote, không coi là số liệu của Company A.

### 3.6 Từ điển KPI

| KPI | Định nghĩa | Dùng để đo |
|---|---|---|
| **Promise-kept rate** | % đơn giao **đúng ngày đã hứa** khi xác nhận | Độ tin cậy lời hứa (gắn trực tiếp với nhận đơn) |
| **OTIF** (On-Time In-Full) | % đơn giao đúng hẹn **và** đủ hàng | Độ tin cậy giao hàng |
| **Right-first-time order** | % đơn xác nhận nhanh (vd. < 15 phút), đúng dòng hàng, giao đúng ngày hứa và đủ | North Star gộp cho luồng order-to-delivery |
| Perfect order rate | Đơn không lỗi ở mọi khâu, kể cả hóa đơn | Chất lượng end-to-end |
| Failed / re-delivery rate | % chuyến giao thất bại phải giao lại | Chi phí logistics (tiền thật) |
| Line accuracy | % **dòng hàng** đúng SKU và số lượng | Chất lượng AI / nhập liệu |
| Order accuracy | % **đơn** không có dòng nào sai | Thứ khách thực sự cảm nhận (xem 4.13) |
| Edit-free rate | % đơn AI đề xuất được duyệt không cần sửa | Mức tự động hóa |
| Handling time / order | Phút nhân viên xử lý một đơn | Năng lực giải phóng |
| Order-to-confirmation time | Từ lúc nhận đơn tới khi khách nhận xác nhận | Tốc độ phục vụ |
| WISMO contacts | Số liên hệ "Where is my order?" | Minh bạch với khách |
| **Fill rate** | % **nhu cầu** (dòng hoặc số lượng) đáp ứng được ngay từ tồn kho | Tồn kho theo góc khách |
| **Availability** | % **SKU** đang có hàng tại thời điểm đo | Tồn kho theo góc danh mục |
| Stock accuracy | % khớp giữa tồn hệ thống và thực tế | Chất lượng dữ liệu tồn |
| Cost-to-serve | Chi phí phục vụ một đơn hoặc một khách | Hiệu quả |
| Adoption rate | % đơn đủ điều kiện đi qua công cụ mới | Thành công thay đổi |

---

## 4. Bộ công cụ của consultant chuyên nghiệp

### 4.1 Quy trình làm case theo giả thuyết

```
Understand → Structure → Prioritise → Solve → Quantify → Plan → Communicate
```

- **Đưa giả thuyết sớm**, dùng dữ kiện để xác nhận hoặc bác bỏ.
- **80/20.**
- **"So what?"** cho mọi phân tích.

### 4.2 SCQ và Pyramid Principle

| | Áp dụng cho case |
|---|---|
| **Situation** | Company A dẫn đầu thị trường vật liệu xây dựng Bắc Âu, hàng trăm cửa hàng ở DK/NO/SE, phục vụ Pro và DIY |
| **Complication** | Mỗi nước tự phát triển hệ thống và quy trình, gây việc thủ công, vận hành thiếu đồng nhất, giao hàng kém tin cậy, trong thị trường cạnh tranh |
| **Question** | Tập trung vào **một** cơ hội số nào trước để có tác động lớn nhất và nhanh nhất? |

Slide 2 nêu **câu trả lời** ngay. Các slide sau là luận điểm hỗ trợ.

### 4.3 MECE issue tree và 5 Whys

```
Vì sao Company A có nguy cơ mất năng lực cạnh tranh?
├── Doanh thu bị đe dọa
│   ├── Khách Pro rời bỏ vì giao trễ/thiếu, không biết trạng thái
│   ├── Trải nghiệm không đồng nhất giữa cửa hàng/nước
│   └── Báo giá chậm nên mất đơn dự án
├── Chi phí cao
│   ├── Nhập liệu thủ công
│   ├── Giao lại, xe chạy không tối ưu
│   └── Tồn kho sai
└── Không nhân rộng được cải tiến
    ├── Hệ thống phân mảnh
    ├── Dữ liệu không thống nhất
    └── Không có quy trình chuẩn chung
```

**5 Whys (giao trễ/thiếu):**
1. Vì sao khách Pro nhận hàng trễ hoặc thiếu? Ngày giao được hứa mà không kiểm tồn khả dụng; đơn có dòng sai.
2. Vì sao? Đơn nhập tay từ email/điện thoại, kiểm tồn Store và DC ở các màn hình khác nhau.
3. Vì sao? Không có lớp đơn hàng có cấu trúc dùng chung; mỗi cửa hàng làm một kiểu.
4. Vì sao? Mỗi nước một hệ thống, không chia sẻ dữ liệu đơn và tồn.
5. **Gốc:** không có luồng order-to-delivery chuẩn hóa, có kiểm tồn, xuyên suốt các hệ thống.

### 4.4 Ma trận ưu tiên và phương án đối chứng công bằng

- Dùng **weighted scoring** (gợi ý trọng số: Impact 30%, TTM 20%, Urgency 15%, Feasibility 15%, Scale 10%, AI 10%). Nêu lý do trọng số và chạy **sensitivity**.
- Cột đánh giá phải **cùng kiểu câu trả lời**. Ví dụ cột "Root cause?" chỉ trả lời Có / Một phần / Không; ghi chú để cột riêng.
- **Phương án đối chứng phải công bằng.** Mô tả mỗi phương án ở dạng mạnh nhất của nó, đúng như ngoài thực tế (dịch vụ "khung giờ + tracking" là một tính năng, không phải "bộ TMS 15 tháng"). Không tự nâng điểm phương án của mình so với phiên bản trước mà không có lý do.
- Luôn có phương án **"hợp nhất ERP"** để cho thấy đã cân nhắc và loại vì time-to-market.
- Nếu cho rằng "B cần A trước", kiểm tra xem ngoài thực tế B có chạy độc lập không. Nếu có, nói chính xác hơn: "B chạy được, nhưng giá trị bị giới hạn khi…".

### 4.5 Định nghĩa MVP đúng cách

- MVP là phiên bản **nhỏ nhất** kiểm chứng được giả thuyết giá trị và có tác động đo được.
- **Lát cắt mỏng end-to-end**: một nước, một kênh, vài cửa hàng, một nhóm khách.
- **MoSCoW** + bảng **In / Out of scope**. Tính năng cần hạ tầng mới (GPS, app tài xế, TMS) xếp vào *Won't (MVP)*.
- **Tiêu chí go/no-go** có baseline đo ở tuần 1–2.
- **Prototype là bằng chứng mạnh nhất:**
  - Gọi đúng tên ("working prototype").
  - Có **ảnh chụp màn hình**.
  - Có kết quả **backtest** trên dữ liệu mẫu.
  - Không gọi là "validated" khi chưa chạy với dữ liệu thật.

### 4.6 Business case như CFO

**Nguyên tắc 1 – Ba lớp, không trộn:**

| Lớp | Là gì | Ví dụ | Dùng để tính payback? |
|---|---|---|---|
| **1. Năng lực (capacity)** | Giờ công được giải phóng × chi phí giờ | "≈57 FTE thời gian quầy" | **Không**, trừ khi ghi rõ là "payback trên giá trị kinh tế" |
| **2. Tiền mặt (cash)** | Chi phí thật giảm hoặc biên lợi nhuận thật tăng | Giảm giao lại; bớt thuê thời vụ/làm thêm; không tuyển bù khi nghỉ tự nhiên (đã thỏa thuận với đại diện người lao động) | **Có** |
| **3. Upside** | Có thể có nhưng chưa có baseline | Giữ chân khách Pro, tăng tỷ lệ chốt đơn | Không. Dùng **break-even**: "cần cải thiện bao nhiêu để đạt payback X" |

**Nguyên tắc 2 – Không đếm trùng.** Một giờ công chỉ được dùng **một lần**: hoặc chuyển thành tiền (bớt thời vụ), hoặc để bán thêm, hoặc để nguyên là năng lực. Ghi rõ tỷ lệ phân bổ.

**Nguyên tắc 3 – Trừ run cost và tính ramp-up:**
- Run cost cần có cấu phần: hosting, chi phí gọi model, đội hỗ trợ, bảo trì adapter.
- Payback phải tính theo **tiến độ rollout thực tế**, không giả định 100% cửa hàng chạy từ ngày 1.
- Nêu cả **steady-state** lẫn **kể cả ramp-up**.

**Nguyên tắc 4 – Ba kịch bản và nhãn nguồn.**
- Low / Base / High.
- Mỗi con số gắn `[A]` hoặc nguồn.
- Kiểm **mọi con số khớp nhau** giữa slide tóm tắt, slide KPI và slide business case.

**Công thức:**

```
Năng lực/năm      = Khối lượng × phút tiết kiệm ÷ 60 × chi phí giờ × tỷ lệ thực hiện
Tiền mặt/năm      = Chi phí lỗi tránh được + (năng lực × tỷ lệ chuyển thành tiền)
Net cash/năm      = Tiền mặt − run cost
Payback steady    = Tổng đầu tư ÷ Net cash × 12 (tháng)
Break-even        = Tiền mặt gộp cần có để payback trong N tháng = Đầu tư ÷ (N/12) + run cost
```

### 4.7 Global core + Local flex

| Global core (dùng chung) | Local flex (theo nước) |
|---|---|
| Mô hình dữ liệu đơn/khách/sản phẩm | Ngôn ngữ, thuật ngữ nghề, đơn vị tính |
| Workflow lõi (nhận đơn, kiểm tồn, hứa ngày, xác nhận) | Tiền tệ, VAT, định dạng e-invoice (do ERP xử lý) |
| Dịch vụ AI dùng chung (trích xuất, khớp SKU) | Adapter vào ERP/POS/WMS hiện có |
| Bảo mật, IAM, log, hosting tại EU | Quy tắc giao hàng (giờ cắt chuyến, xe cẩu, vùng) |
| Bộ KPI và dashboard chung | **Module dẫn dắt, thứ tự rollout, đào tạo** |

> Trình bày là **một sản phẩm, cấu hình khác nhau**, không phải "ba chế độ" như ba sản phẩm.

### 4.8 Chiến lược rollout

| Cách | Khi nào | Rủi ro |
|---|---|---|
| **Pilot / lighthouse** | Kiểm chứng giá trị | Pilot "đẹp" quá; chọn cửa hàng đại diện |
| **Wave rollout** (theo vùng/nước) | Mặc định cho chuỗi nhiều chi nhánh; tiền lệ: JYSK chuyển POS theo đợt | Chạy song song hai cách làm |
| **Big bang** | Phạm vi nhỏ | Sự cố lan rộng |
| **Module-by-market** | Mỗi nước bắt đầu bằng module giải điểm đau lớn nhất | Cần kiến trúc module hóa |

Luôn đặt **cổng go/no-go giữa các đợt**: chỉ cấp vốn cho adapter của nước tiếp theo khi đợt trước đạt KPI.

### 4.9 Change management: ADKAR và stakeholder map

**ADKAR:** Awareness → Desire → Knowledge → Ability → Reinforcement.

| Stakeholder | Quan tâm | Cần gì |
|---|---|---|
| Ban điều hành | ROI, cạnh tranh, rủi ro | Business case ba lớp, roadmap có cổng |
| Country MD | Tự chủ địa phương | Local flex, đồng thiết kế |
| Quản lý cửa hàng | Không gián đoạn | Pilot an toàn, champion |
| Nhân viên quầy, kho | Việc dễ hơn, không bị thay thế | UX đơn giản; cam kết không sa thải; minh bạch cách dùng thời gian giải phóng |
| Tài xế | Không bị giám sát quá mức | Không dùng dữ liệu để đánh giá cá nhân |
| Đại diện người lao động | Điều kiện làm việc, quyền riêng tư | Tham vấn **trước** pilot, nhất là về việc không tuyển bù |
| IT từng nước | Tích hợp, bảo trì | Kiến trúc API, không phá hệ thống cũ |
| Khách Pro | Giao đúng, minh bạch | Ngày hứa đáng tin, báo trạng thái |

### 4.10 Kiến trúc thực dụng: integrate, don't replace

- **Không thay ERP trong MVP.** Lớp tích hợp phía trên (strangler fig pattern).
- Tách **luồng đọc** (danh mục, giá, tồn kho đồng bộ định kỳ) và **luồng ghi** (đẩy đơn đã duyệt). Nếu ERP không có API: **import file / EDI làm cầu nối**, xác nhận trong integration spike tuần 1. Không khẳng định "mọi ERP đều hỗ trợ".
- **Buy vs build:** mua phần phổ thông (OCR/trích xuất nếu đạt backtest, SMS, tối ưu tuyến); tự làm phần khác biệt (khớp từ lóng nghề và đơn vị tính, lịch sử mua của khách, quy tắc hứa ngày).
- **Cloud tại EU**, dữ liệu trong EU/EEA.

### 4.11 Responsible AI

- **Human-in-the-loop** và **ngưỡng tin cậy**: dòng có độ tin cậy thấp hoặc có quy đổi đơn vị tính bắt buộc người xác nhận. Không để LLM "tự sáng tạo" mã SKU; chỉ chọn trong danh mục.
- **GDPR:** tối thiểu hóa dữ liệu; DPIA cho dữ liệu vị trí tài xế.
- **EU AI Act** [Đã kiểm, nhiều nguồn thứ cấp]:
  - Gói **Digital Omnibus** đã thông qua và có hiệu lực tháng 07/2026.
  - Nghĩa vụ high-risk **Annex III** dời từ 02/08/2026 sang **02/12/2027**; **Annex I** sang **02/08/2028**.
  - Nghĩa vụ **minh bạch (Điều 50)** phần lớn vẫn áp dụng từ **02/08/2026**.
  - Mức rủi ro do **mục đích sử dụng** quyết định, không do có người duyệt hay không. Trích xuất đơn hàng không thuộc nhóm high-risk.
  - **Tránh** dùng AI để đánh giá hiệu suất hoặc phân việc theo hành vi cá nhân của nhân viên (Annex III).
  - Chatbot phải cho người dùng biết đó là AI.
- **Data residency:** mô hình và dữ liệu chạy trong EU.

### 4.12 Kỹ năng làm slide

- **Action title** cho *mọi* slide nội dung, kể cả slide tóm tắt và slide rủi ro.
- **Một thông điệp mỗi slide**; thử "3 giây".
- **Con số lớn nhất trên slide phải là con số đúng bản chất.** Đừng để giá trị năng lực nổi bật như thể là tiền.
- **Dùng khoảng trống**: thêm một hộp "Why not X?" hoặc ảnh prototype thay vì thêm chữ.
- **Footnote** nguồn và giả định ở mỗi slide.
- Kiểm tra sau khi xuất PDF: xem lại từng trang, chữ không chồng, các khối không bị đọc nhầm nhóm (ví dụ hàng hộp dưới ba cột nước sẽ bị hiểu là thuộc từng nước).

### 4.13 KPI nhất quán: độ chính xác theo dòng và theo đơn

Một đơn của nhà thầu thường có nhiều dòng. Số dòng thực tế phải đo; 10 và 15 dòng dưới đây chỉ là ví dụ. Giả sử lỗi giữa các dòng độc lập, xác suất **cả đơn đúng** = (độ chính xác mỗi dòng)^(số dòng):

| Độ chính xác mỗi dòng | Đơn 10 dòng đúng hết | Đơn 15 dòng đúng hết |
|---|---|---|
| 90% | 34,9% | 20,6% |
| 95% | 59,9% | 46,3% |
| 97% | 73,7% | 63,3% |
| 99% | 90,4% | 86,0% |
| 99,5% | 95,1% | 92,8% |
| 99,9% | 99,0% | 98,5% |

**Muốn X% đơn không cần sửa thì cần độ chính xác mỗi dòng bao nhiêu?**

| X% đơn edit-free | 10 dòng | 15 dòng |
|---|---|---|
| 50% | 93,3% | 95,5% |
| 60% | 95,0% | 96,7% |
| 80% | 97,8% | 98,5% |

**Quy tắc:**
1. Đặt **cặp đích nhất quán**. Ví dụ "95% dòng" đi với "≈45% đơn 15 dòng không sửa", không phải "≥60%".
2. Ghi nhãn rõ **trước khi duyệt** (AI) hay **sau khi duyệt** (sau người). Tránh nhãn mơ hồ như "accuracy after review ≥ 90%".
3. KPI chất lượng cuối cùng nên là **lỗi theo đơn so với baseline thủ công**, ví dụ "≤ 50% baseline". Một đích tuyệt đối không có baseline (như 99,5% dòng) vẫn có thể để lọt khoảng 7% đơn 15 dòng có lỗi.
4. Đo baseline ở tuần 1–2: credit note, hàng trả, nhật ký giao hàng; backtest trên vài trăm đơn cũ.

### 4.14 Những gì không nên đưa lên slide

| Không nên | Vì sao | Thay bằng |
|---|---|---|
| Gán Company A cho công ty thật | Suy đoán, có thể sai, đụng bảo mật | "Nordic builders' merchants" |
| Gọi một chuỗi là "đối thủ" khi có thể cùng tập đoàn với hình mẫu của case | Sai bối cảnh | "UK peers" / "industry benchmarks" |
| Mô tả sản phẩm Netcompany vượt quá nguồn công khai | Giám khảo biết rõ sản phẩm của họ | Bỏ, hoặc một footnote đúng (1.2) |
| Số liệu ngành không nguồn ("80% hàng mua lặp lại", "B2B 65–75%"…) | Không kiểm được | Bỏ, hoặc gắn `[A]` |
| "Validated" cho prototype một tuần | Nói quá | "Working prototype" + ảnh + kết quả backtest |
| "Giải quyết cả 4 thách thức" | Trái "focus on one problem" | "One problem where the challenges meet" |

---

## 5. Phân tích phương án và ưu tiên

### 5.1 Danh sách cơ hội

| # | Cơ hội | Thách thức | Thị trường liên quan nhất | Ví dụ giải pháp | Góc AI |
|---|---|---|---|---|---|
| 1 | AI order intake | Manual | DK | Đọc email/PDF/ảnh, tạo đơn nháp, người duyệt | Trích xuất, khớp SKU |
| 2 | Store operations app | Inconsistent ops | NO | Checklist, quy trình chuẩn tại quầy | Thấp–vừa |
| 3 | Delivery promise & status | Delivery | SE | Hứa ngày dựa trên tồn Store + DC, báo trạng thái tự động | Dự đoán ngày giao |
| 4 | Contractor portal/app | Manual + delivery | Cả 3 | Tự đặt, reorder | Gợi ý reorder |
| 5 | Inventory visibility & forecasting | Delivery + stores | Cả 3 | Tồn kho thời gian thực | Forecasting |
| 6 | Hợp nhất ERP | Fragmented | Cả 3 | Một ERP chung | Thấp |

### 5.2 Chấm điểm (minh họa, đội tự hiệu chỉnh)

| Phương án | Impact (30%) | TTM (20%) | Urgency (15%) | Feasibility (15%) | Scale (10%) | AI (10%) | **Tổng** |
|---|---|---|---|---|---|---|---|
| **A. Pro order-to-promise** (nhận đơn AI + hứa ngày + báo trạng thái) | 5 | 3 | 5 | 3 | 5 | 4 | **4,20** |
| B. Chỉ AI order intake | 3 | 4 | 3 | 4 | 4 | 5 | 3,65 |
| C. Chỉ delivery slots & tracking (như các merchant Anh) | 4 | 3 | 4 | 3 | 3 | 3 | 3,45 |
| D. Store operations app | 3 | 4 | 3 | 4 | 3 | 2 | 3,25 |
| E. Hợp nhất ERP | 4 | 1 | 2 | 1 | 5 | 2 | 2,55 |

Cách tính, lấy A làm ví dụ: 0,3×5 + 0,2×3 + 0,15×5 + 0,15×3 + 0,1×5 + 0,1×4 = 4,20.

> **Sensitivity:** tăng trọng số TTM lên 35% (giảm Impact còn 15%). A = 0,15×5 + 0,35×3 + 0,15×5 + 0,15×3 + 0,1×5 + 0,1×4 = **3,90**; B = 0,15×3 + 0,35×4 + 0,15×3 + 0,15×4 + 0,1×4 + 0,1×5 = **3,80**. A vẫn dẫn nhưng sát nút. **Nói thẳng điều đó trên slide**: đó là tư duy phản biện.

### 5.3 Insight: ba triệu chứng, một chuỗi giá trị

```
Thợ gửi email kèm ảnh danh sách vật tư
   → Nhân viên gõ tay vào hệ thống địa phương        ← manual processes (gợi ý DK)
   → Mỗi cửa hàng kiểm tồn, hứa ngày một kiểu        ← inconsistent operations (gợi ý NO)
   → Ngày hứa không dựa trên tồn khả dụng, không báo trạng thái → giao trễ/thiếu
                                                     ← delivery & fulfilment (gợi ý SE)
   (bên dưới: hệ thống phân mảnh không chia sẻ dữ liệu đơn và tồn)
```

- **MỘT vấn đề:** khách Pro không tin được rằng vật tư đúng sẽ tới đúng ngày đã hứa.
- **MỘT North Star:** *right-first-time pro orders* (xem 3.6).
- **MỘT giải pháp:** lớp order-to-promise dùng chung, cấu hình khác nhau theo nước.

---

## 6. Hướng giải mẫu (tham khảo, không phải đáp án)

### 6.1 Problem statement

> *"Professional customers – Company A's most valuable segment – cannot rely on getting the right materials on the promised day. Orders are re-keyed by hand and dates are promised without checking available stock, causing idle crews, costly failed deliveries and churn."*

### 6.2 Persona

| Persona | Bối cảnh | Nỗi đau | Mong muốn |
|---|---|---|---|
| **Site manager**, nhà thầu vừa (SE) | Đặt hàng qua email/điện thoại sáng sớm | Hàng tới trễ/thiếu, không biết trạng thái, đội thợ chờ | Ngày hứa đáng tin, được báo khi hàng xuất kho |
| **Nhân viên quầy Pro** (DK) | Hàng chục email đơn mỗi sáng | Gõ tay, tra tồn ở nhiều màn hình, bị gọi hỏi liên tục | Ít nhập liệu, thời gian tư vấn |
| **Quản lý cửa hàng** (NO) | Mỗi cửa hàng một quy trình | Khó chuẩn hóa, khó đào tạo | Một cách làm chuẩn cho mọi cửa hàng |

### 6.3 Giải pháp: "SiteReady – Pro Order-to-Promise Layer"

| Thành phần | Chức năng | MVP? |
|---|---|---|
| **1. AI Order Intake** | Đọc email/PDF; khớp từ lóng nghề và đơn vị tính sang SKU trong danh mục (ưu tiên lịch sử mua của khách); màn hình duyệt, dòng độ tin cậy thấp tô màu | **Có** |
| **2. Delivery-date promise** | Kiểm tồn Store + DC đồng bộ định kỳ, giờ cắt chuyến. Dòng tồn thấp → hứa theo ngày DC hoặc yêu cầu kiểm tay. Nút **"flag stock mismatch"** tạo lệnh kiểm kê (cycle count) | **Có** |
| **3. Status messages** | SMS/email tự động khi trạng thái đơn trong ERP đổi (đã xác nhận → đã soạn → đang giao) | **Có** |
| **4. Integration layer** | Adapter đọc/ghi vào ERP hiện có; fallback import file/EDI | **Có** (một ERP) |
| **5. Dashboard** | Promise-kept, handling time, adoption theo cửa hàng | **Có** |
| 6. Store standard workflow | Cùng màn hình duyệt dùng cho đơn tại quầy và qua điện thoại, nên mọi cửa hàng nhận, kiểm, xác nhận đơn một cách | Đợt NO |
| 7. App tài xế, POD, live GPS, tối ưu tuyến | Cần dữ liệu đội xe / TMS | Năm 2 |

**AI tạo giá trị ở đâu:**

| Use case | Kỹ thuật | Giá trị | Kiểm soát |
|---|---|---|---|
| Trích xuất dòng hàng | Document AI + LLM | Giảm thời gian nhập | Human-in-the-loop, ngưỡng tin cậy |
| Khớp từ lóng nghề sang SKU (ba ngôn ngữ) | Tìm kiếm từ khóa (kích thước như 45x195) + tìm kiếm ngữ nghĩa + lịch sử mua | Giảm sai đơn | Chỉ chọn trong danh mục; top-3 gợi ý |
| Kiểm tra đơn vị tính | Quy tắc quy đổi (mét dài ↔ thanh) | Tránh sai số lượng | Bắt buộc xác nhận khi có quy đổi |
| *(Năm 2)* Dự đoán ngày giao, trợ lý WISMO, dự báo nhu cầu | ML / GenAI | Minh bạch, giảm tải | Ghi rõ là AI |

### 6.4 Phạm vi MVP

**Pilot:** Thụy Điển, một vùng, 3–5 cửa hàng có đội xe giao hàng, khoảng 50 khách Pro lớn `[A]`.

> **Why not start in Denmark?** *"Denmark's manual workload may be the largest, but Sweden is where delivery failures may have the biggest business impact and where construction is recovering fastest. The MVP already includes AI order intake, so Denmark reuses the same core in wave 2."*
>
> Nếu đội giả định IT trung tâm và khối lượng đơn email lớn nhất ở Đan Mạch, pilot ở Đan Mạch cũng bảo vệ được. Khi đó viết hộp ngược lại: "Why not start in Sweden?".

| MoSCoW | Hạng mục |
|---|---|
| **Must** | AI đọc đơn email/PDF + màn hình duyệt; hứa ngày theo tồn Store + DC với quy tắc tồn thấp và nút flag mismatch; SMS trạng thái từ sự kiện ERP; tích hợp ERP Thụy Điển (đọc danh mục/tồn, ghi đơn; fallback file); dashboard |
| **Should** | Mã lý do khi giao thất bại (do điều phối viên nhập) |
| **Could** | Gợi ý phụ kiện còn thiếu ("complete-the-job") |
| **Won't (MVP)** | App tài xế, POD, live GPS, tối ưu tuyến, portal, B2C, thay ERP, dự báo nhu cầu, rollout DK/NO |

**Timeline 12 tuần:**

```
Tuần 1–2   Integration spike ERP; đo baseline (credit note, nhật ký giao, time-motion 100 đơn); backtest 500 đơn cũ
Tuần 3–8   Build: 3 sprint × 2 tuần, demo với store champions
Tuần 9–12  Live tại 3–5 cửa hàng (khoảng 1.200–2.000 đơn), đo KPI hằng tuần
Tuần 12    Gate 1: go/no-go
```

**Đội ngũ `[A]`:** PO (phía Company A), BA/consultant, UX, 3 developer, 1 data/AI engineer, 1 QA, cùng 1 store champion mỗi cửa hàng.

**North Star:** *Right-first-time pro orders*, tức % đơn Pro xác nhận < 15 phút, đúng dòng hàng, giao đúng ngày đã hứa và đủ hàng.

**KPI go/no-go** (đích nhất quán theo 4.13):

| KPI | Baseline đo bằng | Đích tuần 12 `[A]` |
|---|---|---|
| Promise-kept rate | Nhật ký giao 3 tháng gần nhất | +10 điểm % so với baseline |
| Failed / re-delivery rate | Nhật ký vận tải | −20% |
| AI line match **trước** duyệt | Backtest 500 đơn | ≥ 95% |
| Edit-free orders | Backtest + live | ≥ 45% (nhất quán với 95% dòng, đơn khoảng 15 dòng) |
| Lỗi theo **đơn sau** duyệt | Credit note / hàng trả 6 tháng | ≤ 50% baseline thủ công |
| Handling time / order | Time-motion 100 đơn | 8 → ≤ 3 phút |
| Order → confirmation | Timestamp email vs. ERP | < 15 phút trong giờ làm việc |
| Adoption | — | ≥ 80% đơn đủ điều kiện |

### 6.5 Business case minh họa (toàn tập đoàn sau rollout; DKK, EUR trong ngoặc)

> Mọi con số dưới đây là **`[A]`** để minh họa phương pháp ở 4.6. Đội phải thay bằng giả định của mình. 1 EUR ≈ 7,46 DKK.

**Giả định:**

| Biến | Base | Low / High | Ghi chú |
|---|---|---|---|
| Cửa hàng; cửa hàng có giao hàng Pro | 300; 200 | — | Đề nói "hàng trăm" |
| Chuyến giao / cửa hàng / ngày; ngày / năm | 12; 250 | — | Tổng 600.000 chuyến/năm |
| Tỷ lệ giao thất bại (baseline) | 8% | — | Đo lại ở tuần 1–2 |
| Chi phí một lần giao lại | DKK 900 (≈EUR 120) | — | Xe, tài xế, cẩu, xử lý |
| Mức giảm giao thất bại | 20% | 10% / 30% | Nhờ hứa ngày có kiểm tồn và báo trạng thái |
| Đơn thủ công / cửa hàng / ngày | 20 | — | Tổng 1,5 triệu đơn/năm |
| Phút tiết kiệm / đơn | 5 (8 → 3) | — | Đối chiếu benchmark: −60% (IBM/Oiki) |
| Chi phí giờ đầy đủ | DKK 336 (≈EUR 45) | — | Lấy lại từ Statistics Denmark / SCB / SSB |
| Tỷ lệ năng lực thực hiện được | 75% | 50% / 90% | |
| Phần năng lực chuyển thành tiền | 25% | 15% / 35% | Bớt thời vụ/làm thêm, không tuyển bù; thỏa thuận với đại diện người lao động |
| Run cost / năm | DKK 3,2m | — | Hosting + model 0,8m; 2 FTE hỗ trợ × 0,9m; bảo trì 3 adapter × 0,2m |
| Đầu tư | MVP DKK 4,8m; rollout DKK 17,2m; **tổng DKK 22,0m (≈EUR 2,9m)** | — | MVP: 8 người × 12 tuần × 37 giờ × DKK 1.200 + 0,5m hạ tầng. Rollout: 8 người × 40 tuần × 37 × 1.200 + đào tạo DKK 10k/cửa hàng |

**Ba lớp (Base):**

| Lớp | Phép tính | Kết quả/năm |
|---|---|---|
| **1. Năng lực** | 1,5m đơn × 5 phút = 125.000 giờ (≈76 FTE); × 75% = 93.750 giờ (**≈57 FTE**); × DKK 336 | **DKK 31,5m** (giá trị, không phải tiền) |
| **2a. Tiền: giảm giao lại** | 600.000 × 8% = 48.000 lần thất bại; × 20% = 9.600 lần tránh được; × DKK 900 | **DKK 8,6m** |
| **2b. Tiền: từ năng lực** | 25% × 31,5m | **DKK 7,9m** |
| **Tiền mặt gộp** | 8,6 + 7,9 | **DKK 16,5m** |
| **Net cash** | 16,5 − 3,2 run cost | **DKK 13,3m (≈EUR 1,8m)** |
| Năng lực còn lại (dùng cho bán hàng, tư vấn) | 31,5 − 7,9 | DKK 23,6m (không cộng vào tiền) |
| **3. Upside chưa tính** | Mỗi 0,1 điểm % churn khách Pro giảm ≈ DKK 2,2m lợi nhuận gộp (doanh thu Pro giả định ≈ DKK 9bn × 25% biên) | Đo trong pilot |

**Ba kịch bản và payback:**

| | Low | Base | High |
|---|---|---|---|
| Tiền mặt gộp / năm | DKK 7,5m | DKK 16,5m | DKK 26,2m |
| Net cash / năm (sau run cost) | DKK 4,3m | DKK 13,3m | DKK 23,0m |
| Payback trên tiền mặt, steady-state | 62 tháng | 20 tháng | 12 tháng |
| **Payback trên tiền mặt, kể cả ramp-up** | 72 tháng | **30 tháng** | 22 tháng |
| Payback trên giá trị kinh tế (tiền + năng lực còn lại), kể cả ramp-up | 22 tháng | 17 tháng | 14 tháng |

*Ramp-up:* MVP tháng 1–3, chưa có lợi ích. Rollout tháng 4–18, lợi ích và run cost tăng tuyến tính tới 100% ở tháng 18.

**Break-even:**
- Để hoàn vốn tiền mặt trong 24 tháng (steady-state) cần tiền mặt gộp ≥ 22,0 ÷ 2 + 3,2 = **DKK 14,2m/năm**. Base (16,5m) đạt; Low (7,5m) thiếu 6,7m.
- Low đạt được nếu churn khách Pro giảm thêm khoảng **0,3 điểm %** (6,7 ÷ 22,4 ≈ 0,3).
- Đây là điều pilot phải đo.

**Câu mẫu cho slide 8 (EN):**
> *"≈57 FTE of counter time freed (DKK 31.5m of capacity) and ≈DKK 13m net cash a year at full run-rate [A]. Cash payback ≈30 months including ramp-up; each 0.1 pp of contractor churn avoided adds ≈DKK 2m – measured in the pilot."*

### 6.6 Scale: rollout có cổng go/no-go

| | **Thụy Điển (Wave 1)** | **Đan Mạch (Wave 2)** | **Na Uy (Wave 3)** |
|---|---|---|---|
| Gợi ý của đề | Delivery: *may have greater business impact* | Manual: *may create the greatest impact* | Store ops: *may be more urgent* |
| Module dẫn dắt | Hứa ngày + báo trạng thái + AI intake | **AI intake** (khối lượng email lớn) | **Store standard workflow** (cùng màn hình cho quầy và điện thoại) |
| Local flex | Tiếng Thụy Điển, SEK, adapter ERP SE | Tiếng Đan Mạch, DKK, adapter ERP DK | Tiếng Na Uy, NOK, adapter ERP NO. Phụ thuộc: ERP Na Uy phải sẵn sàng **gửi e-invoice B2B từ 01/01/2027** (việc của ERP, ngoài phạm vi) |
| Thời gian `[A]` | Tháng 0–3 pilot; 4–9 toàn quốc | Tháng 7–12 | Tháng 10–18 |
| Cổng | **Gate 1** (tháng 3): KPI pilot | **Gate 2** (tháng 6): kết quả vùng SE | **Gate 3** (tháng 9): kết quả DK sớm |

**Roadmap:**
- **Now (0–3):** MVP và pilot SE; đo baseline cả ba nước.
- **Next (4–18):** ba đợt có cổng; dùng chung lõi.
- **Later (năm 2):** app tài xế và POD, live tracking, portal tự đặt hàng, dự báo nhu cầu; dần chuẩn hóa dữ liệu và hệ thống.

### 6.7 Rủi ro và giảm thiểu

| Rủi ro | Xác suất / Tác động | Giảm thiểu |
|---|---|---|
| ERP không có API ghi đơn | Cao / Cao | Spike tuần 1; fallback import file/EDI; dừng ở Gate 1 nếu không khả thi |
| Dữ liệu tồn kho sai ("ghost stock") | Cao / Cao | Quy tắc tồn thấp (ngày DC hoặc kiểm tay); nút flag mismatch tạo lệnh cycle count; đo promise-kept từ ngày 1 |
| AI khớp sai từ lóng / đơn vị tính | Trung bình / Cao | Chỉ chọn trong danh mục; ngưỡng tin cậy; bắt buộc xác nhận khi quy đổi; backtest |
| Nhân viên không dùng | Trung bình / Trung bình | Store champions, đồng thiết kế, phím tắt, không phải mở lại ERP |
| Lo ngại việc làm, quyền riêng tư | Trung bình / Trung bình | Cam kết không sa thải; thỏa thuận trước về không tuyển bù; DPIA |
| Phạm vi phình | Cao / Cao | MoSCoW cứng; tính năng cần hạ tầng mới để năm 2 |

---

## 7. Gợi ý storyline 10 slide

| # | Action title (EN, gợi ý) | Nội dung chính | Tiêu chí |
|---|---|---|---|
| 1 | *SiteReady: the right materials, on the promised day* | Tên đội và thành viên (điền đủ), một câu tóm tắt | — |
| 2 | *Fix the contractor order-to-promise flow first* | SCQ + câu trả lời + 3 con số (≈57 FTE, ≈DKK 13m net cash, +10 pp promise kept) | Structured |
| 3 | *Three symptoms, one broken flow* | Luồng đơn Pro, ba nút thắt **trích đúng chữ đề (có "may")**, 5 Whys | Problem |
| 4 | *Idle crews and failed deliveries: the cost of broken promises* | Persona, con số `[A]` về giao thất bại; UK peers đã có khung giờ và tracking; một câu về lợi ích cho B2C | Problem, Impact |
| 5 | *Why this opportunity first – and why Sweden first* | Bảng có trọng số + sensitivity; phương án đối chứng công bằng gồm ERP; hộp "Why not Denmark?" | Prioritisation |
| 6 | *One layer from email to a promise we can keep* | 5 thành phần, luồng đọc/ghi, AI value map, **ảnh prototype** | Feasible, Innovation |
| 7 | *A 12-week pilot in 3–5 Swedish stores, with go/no-go gates* | MoSCoW, timeline, KPI nhất quán có baseline | Feasible |
| 8 | *≈DKK 13m net cash a year, plus ≈57 FTE of counter time* | Waterfall ba lớp, ba kịch bản, payback có ramp, break-even | Impact |
| 9 | *One core, three waves, three gates* | Global core + local flex (dải ngang "across all three"), wave plan, phụ thuộc NO | Scale |
| 10 | *Six risks, each with a week-1 test or a fallback – decision needed* | Rủi ro có xác suất/tác động; change management; "Decision needed: fund the 12-week pilot" | Feasible, Critical thinking |

> Giới hạn 10 slide: coi slide bìa nằm trong 10, không thêm appendix.

---

## 8. Checklist tự chấm theo tiêu chí của BTC

**Problem Understanding**
- [ ] Nguyên nhân gốc, không chỉ triệu chứng
- [ ] Trích đúng chữ của đề (ưu tiên từng nước, chữ "may")
- [ ] Có ít nhất một con số về nỗi đau (dù là `[A]`)

**Prioritisation & Critical Thinking**
- [ ] Đúng một cơ hội; nói rõ không làm gì
- [ ] Trọng số + sensitivity; phương án đối chứng công bằng; có phương án ERP
- [ ] Trả lời "vì sao không bắt đầu ở nước khác"

**Business Impact**
- [ ] Ba lớp: năng lực / tiền mặt / upside; không đếm trùng giờ công
- [ ] Run cost có cấu phần; payback có ramp-up; break-even
- [ ] KPI phía khách hàng (promise-kept / OTIF), không chỉ hiệu suất nội bộ

**Feasible Solution**
- [ ] MVP một nước, một kênh, khoảng 12 tuần; tính năng cần hạ tầng mới để năm 2
- [ ] Luồng đọc/ghi ERP + fallback; cơ chế xử lý tồn kho sai
- [ ] Cổng go/no-go giữa các đợt

**Structured Thinking & Innovation**
- [ ] Action title cho mọi slide nội dung
- [ ] **Mọi con số khớp nhau** giữa slide 2, 7, 8
- [ ] Cặp KPI nhất quán (bảng 4.13)
- [ ] Ảnh prototype + kết quả backtest

**Hình thức**
- [ ] ≤ 10 slide, PDF, tiếng Anh; **không còn placeholder**
- [ ] Tên nộp đúng tên đội; nộp trước 22:00 ngày 26/10/2026 (nên trước 18:00)
- [ ] Footnote nguồn và giả định; xem lại từng trang PDF sau khi xuất

---

## 9. Lỗi thường gặp cần tránh

1. **Tính payback trên giá trị thời gian nhân viên** rồi trình bày như tiền; quên run cost; quên ramp-up.
2. **Đếm trùng giờ công:** cùng một giờ vừa "bớt thời vụ" vừa "bán thêm".
3. **Con số không khớp giữa các slide** (ví dụ số FTE ở slide tóm tắt khác slide business case).
4. **Cặp KPI mâu thuẫn** (95% dòng nhưng đòi 60% đơn 15 dòng không sửa) hoặc **nhãn KPI mơ hồ** ("accuracy after review").
5. **Không có KPI cho khách hàng**, dù câu chuyện nói giải quyết giao hàng.
6. **Ghi sai gợi ý của đề** hoặc bỏ chữ "may".
7. **Dựng phương án đối chứng yếu (strawman)** hoặc tự nâng điểm phương án của mình.
8. **Tuyên bố giải quyết cả 4 thách thức**, hoặc trình bày ba "chế độ" như ba sản phẩm.
9. **Đưa vào năm 1 tính năng cần hạ tầng khác** (live GPS, app tài xế) mà không ghi phụ thuộc.
10. **Gán Company A cho công ty thật; mô tả sai sản phẩm Netcompany; dùng số liệu ngành không nguồn.**
11. **Gọi prototype là "validated"** khi chưa chạy dữ liệu thật; không có ảnh.
12. **Giải pháp cho tồn kho sai kiểu "hệ thống sẽ tự cải thiện"**, không có cơ chế cụ thể.
13. **Quên người:** không nhắc đại diện người lao động, đào tạo, champions.
14. **Còn placeholder, nộp sát giờ, sai tên đội.**

---

## 10. Kế hoạch làm việc (16/10 → 26/10)

| Ngày | Việc chính | Đầu ra |
|---|---|---|
| 16–17/10 | Đọc đề, long-list, giả thuyết | Long-list |
| 18/10 | Issue tree, chấm điểm có trọng số + sensitivity | **Chốt MỘT cơ hội và thị trường pilot** |
| 19/10 | Ghost deck 10 action title | Ghost deck |
| 20–21/10 | Giải pháp, MVP, KPI nhất quán; chụp ảnh prototype, chạy backtest | Slide 5–7 |
| 22/10 | Business case ba lớp + ramp-up + break-even | Slide 8 |
| 23/10 | Rollout có cổng, rủi ro, change | Slide 9–10 |
| 24/10 | Thiết kế, footnote, kiểm số khớp giữa các slide | Bản gần hoàn chỉnh |
| 25/10 | Red-team theo checklist mục 8 | Danh sách sửa |
| 26/10 | Sửa, xuất PDF, xem lại từng trang, kiểm tên đội, **nộp trước 18:00** | Nộp |

---

## 11. Thuật ngữ EN–VN

| Thuật ngữ | Nghĩa |
|---|---|
| Builders' merchant | Nhà phân phối/bán lẻ vật liệu xây dựng (chủ yếu cho thợ, nhà thầu) |
| Pro / trade customer | Khách chuyên nghiệp |
| DIY | Khách tự làm |
| ATP (Available-to-Promise) | Lượng hàng thực sự hứa giao được |
| Ghost stock | Tồn trên hệ thống nhưng không có thật |
| Cycle count | Kiểm kê theo mã hàng, không đóng cửa hàng |
| OTIF / Promise-kept rate | Giao đúng hẹn và đủ / giao đúng ngày đã hứa |
| Right-first-time order | Đơn đúng ngay từ đầu, đúng hẹn |
| POD | Bằng chứng giao hàng |
| WISMO | "Where is my order?" |
| Capacity value vs. cash | Giá trị thời gian giải phóng vs. tiền thật |
| Ramp-up | Giai đoạn triển khai dần, lợi ích tăng dần |
| Break-even | Mức cải thiện tối thiểu để hoàn vốn trong thời hạn đặt ra |
| Strawman | Phương án đối chứng bị làm yếu đi để dễ bác |
| MVP / MoSCoW / Go-no-go gate | Sản phẩm tối thiểu / phân loại ưu tiên / cổng quyết định |
| Human-in-the-loop | Con người duyệt kết quả AI |
| Strangler fig pattern | Thay hệ thống cũ dần bằng lớp mới bao quanh |
| Peppol / EHF / OIOUBL | Chuẩn và mạng hóa đơn điện tử (châu Âu / Na Uy / Đan Mạch) |
| DPIA | Đánh giá tác động bảo vệ dữ liệu |
| EEA | Khu vực Kinh tế châu Âu (Na Uy thuộc EEA) |

---

## 12. Nguồn tham khảo

**Đề bài:** *IT Consultant Challenge 2026 – Round 1*, Netcompany & Code Mely, 16/10/2026.

**Netcompany**
- [Netcompany launches AI solution EASLEY](https://netcompany-intrasoft.com/news/netcompany-launches-ai-solution-easley-private-and-public-customers) · [Business Chief – EASLEY](https://businesschief.eu/technology/netcompany-easley-ai-solution)
- [G-Cloud 15 service definition (PULSE, AMPLIO, EASLEY…)](https://assets.applytosupply.digitalmarketplace.service.gov.uk/g-cloud-15/documents/580285/106927894358168-service-definition-document-2026-01-30-1326.pdf) · [PULSE listing](https://www.applytosupply.digitalmarketplace.service.gov.uk/g-cloud/services/445066660195690)

**Ngành và benchmark**
- STARK Group: [Business units](https://starkgroup.dk/our-business/business-units) · [STARK Deutschland](https://starkgroup.dk/our-business/business-units/stark-deutschland) · [Expanding in Sweden](https://starkgroup.dk/newsroom/latest-news/stark-group-expand-its-footprint-sweden) · [Company presentation](https://starkgroup.dk/application/files/2617/1291/4546/STARK_Group_Company_Presentation.pdf) · [Wikipedia](https://en.wikipedia.org/wiki/Stark_Group)
- Bygma: [Mynewsdesk](https://www.mynewsdesk.com/dk/bygma-gruppen) · [Interior Daily](https://www.interiordaily.com/article/9832326/bygma-revenue-reaches-new-high-as-profits-remain-under-pressure/)
- XL-BYGG: [Gule Sider](https://www.gulesider.no/xl/bedrifter) · [Finn.no](https://www.finn.no/butikk/xlbygg)
- [Travis Perkins – national delivery tracking (Builders Merchants News)](https://www.buildersmerchantsnews.co.uk/news/merchants/travis-perkins-launches-industry-national-delivery-tracking-service) · [Insight DIY](https://insightdiy.co.uk/news/travis-perkins-launches-industry-national-first-real-time-tracking/10902.htm)
- [STARK UK – real-time delivery updates (Builders Merchants News)](https://www.buildersmerchantsnews.co.uk/news/merchants/stark-uk-launches-real-delivery-update-service) · [Insight DIY](https://www.insightdiy.co.uk/news/stark-uk-launches-realtime-delivery-update-service/16466.htm)
- [IBM – Oiki case study](https://www.ibm.com/case-studies/oiki) · [Lleverage – Topa Bathroom Products](https://www.lleverage.ai/customer-stories/topa-bathroom-products) · [Esker – order management benchmarks](https://www.esker.com/blog/customer-service/how-order-management-benchmarks-can-guide-smarter-business-decisions/)
- [JYSK – unified commerce in all Danish stores](https://gojysk.com/en/news/unified-commerce-now-runs-all-danish-stores) · [JYSK rolls out in Norway](https://retailtechinnovationhub.com/home/2026/10/4/jysk-rolls-out-enactor-powered-unified-commerce-platform-in-norway-with-holland-and-belgium-next)
- [Litium – Nordic B2B report 2025](https://www.litium.com/blog/new-report-nordic-b2b-companies-level-up-digital-commerce-with-customer-service-and-ai) · [Litium – Nordic B2B 2026 (PDF)](https://content.litium.com/hubfs/IR/Rapporter/Nordic%20Digital%20Commerce%20in%20B2B%202026.pdf)
- [L.E.K. – Online opportunities (PDF)](https://www.lek.com/sites/default/files/insights/pdf-attachments/1966-Online_Opportunities_and_the_Arrival_of_Amazon.pdf) · [Simon-Kucher](https://www.simon-kucher.com/ja/node/8377)
- [Veidekke – market outlook](https://www.veidekke.com/investor-relations/company-disclosures/veidekke-expecting-seven-percent-growth-in-2026-and-2027/) · [Bain – European construction](https://www.bain.com/about/media-center/press-releases/20252/europes-construction-industry-is-turning-a-corner-as-early-signs-of-recovery-point-to-strengthening-medium-term-prospects--bain--company/)

**Pháp lý**
- Na Uy: [Sovos – Parliament approves mandatory B2B e-invoicing](https://sovos.com/regulatory-updates/vat/norway-parliament-approves-mandatory-b2b-e-invoicing-and-digital-bookkeeping-law/) · [PwC Norge](https://www.pwc.no/no/innsikt/skattenytt/obligatorisk-b2b-e-fakturering-i-norge-fremskyndes.html) · [SEEBURGER](https://blog.seeburger.com/e-invoicing-in-norway-how-the-b2b-mandate-is-taking-shape/) · [Regjeringen – lovforslag](https://www.regjeringen.no/no/aktuelt/lovforslag-om-e-fakturering-i-naringslivet-og-andre-endringer-pa-finansmarkedsomradet/id3153196/)
- Đan Mạch / Thụy Điển: [TrueCommerce – Denmark](https://www.truecommerce.com/blog/e-invoicing-in-denmark-current-requirements-and-future-changes/) · [LookupTax – Sweden](https://lookuptax.com/docs/einvoicing/peppol-einvoicing-sweden)
- EU AI Act: [Orrick – Digital Omnibus finalizes changes](https://www.orrick.com/en/Insights/2026/07/EU-AI-Act-Update-Digital-Omnibus-Finalizes-8-Compliance-Changes) · [White & Case – AI Omnibus enters into force](https://www.whitecase.com/insight-alert/eu-ai-omnibus-enters-force-amending-ai-act) · [Jones Walker – August 2 still matters](https://www.joneswalker.com/en/insights/blogs/ai-law-blog/yes-august-2-still-matters-the-eu-approved-a-high-risk-ai-delay-but-most-trans.html)

**Thanh toán Bắc Âu:** [Checkout.com](https://www.checkout.com/blog/how-to-master-payments-in-the-nordics)
