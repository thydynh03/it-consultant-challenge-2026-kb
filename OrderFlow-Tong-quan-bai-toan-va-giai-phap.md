# OrderFlow – Tổng quan bài toán và giải pháp

> Tài liệu nội bộ để cả team hiểu chung **context**, **giải pháp**, **điểm mạnh, điểm yếu, thiếu sót** và **lý do không chọn các hướng khác**.
> Ký hiệu: **[A]** = giả định của team, cần kiểm chứng · **[V]** = số liệu vendor tự công bố.
> Chi tiết số liệu và nguồn: `de-xuat-giai-phap.md`, `deep-dive-kiem-chung-orderflow.md`.

---

## 0. Trả lời nhanh: giải pháp phục vụ B2B hay cả B2C?

**Kết luận: OrderFlow được thiết kế cho B2B (nhà thầu, thợ). B2C (khách lẻ, DIY) chỉ hưởng lợi một phần và gián tiếp. B2C không có trong business case.**

| Thành phần của OrderFlow | B2B – nhà thầu | B2C – khách lẻ |
|---|---|---|
| AI đọc đơn từ email, PDF, ảnh | ✅ **Trọng tâm.** Nhà thầu gửi danh sách vật tư tự do | ⚠️ Rất ít. Chỉ khách lẻ làm dự án lớn (sửa cả nhà) mới gửi danh sách qua email [A] |
| AI khớp mã hàng dựa trên lịch sử mua | ✅ Nhà thầu có tài khoản và lịch sử mua → khớp chính xác hơn | ⚠️ Khách lẻ thường không có lịch sử → chỉ dựa vào catalogue, kém chính xác hơn |
| Kiểm tồn Store + DC → ngày giao đáng tin | ✅ Giao tới công trường, đội thợ chờ hàng | ⚠️ Chỉ khi đơn đi qua quầy hoặc điện thoại. **Webshop B2C chạy kênh riêng, không đi qua OrderFlow** |
| Counter mode (Na Uy): một quy trình nhận đơn chuẩn tại quầy và qua điện thoại | ✅ | ✅ **Trực tiếp.** Khách lẻ đặt tại quầy cũng được xử lý cùng một cách |
| Thời gian nhân viên được trả lại (≈300 giờ/cửa hàng/năm [A]) | ✅ | ✅ **Gián tiếp.** Nhân viên quay lại sàn bán, tư vấn cho khách DIY |
| Giá hợp đồng, tín dụng, mã dự án | ✅ Chỉ B2B | ❌ Không áp dụng |
| Webshop, click & collect, app cho khách lẻ | — | ❌ **Không giải quyết** |

**Về số liệu:** 100% business case (≈55 FTE, DKK 23m giá trị năng lực) tính trên **đơn B2B thủ công**. Lợi ích B2C không được định lượng.

**Như vậy có vi phạm đề không?** Không. Đề chỉ mô tả Company A *"serves both construction businesses and individual consumers"*. Đề không yêu cầu giải pháp phải phục vụ cả hai, mà yêu cầu *"Choose ONE key business opportunity… Focus on one problem"*. Tuy vậy giám khảo rất dễ hỏi câu này, nên team phải:
1. Nói rõ **B2B-first là lựa chọn có chủ ý**, kèm lý do (mục 6.4).
2. Nói được **lợi ích B2C cụ thể**: ≈300 giờ mỗi cửa hàng mỗi năm trả lại cho sàn bán, và counter mode ở Na Uy phục vụ cả khách lẻ.
3. Nói được **đường mở rộng sang B2C**: cùng pipeline có thể nhận đơn email hoặc điện thoại của khách lẻ làm dự án lớn, khớp mã theo catalogue. Đây là tùy chọn năm 2, chưa tính chi phí.

*Cách tính ≈300 giờ:* ≈55 FTE × 1.650 giờ ÷ 300 cửa hàng ≈ 300 giờ/cửa hàng/năm, tức khoảng 1,2 giờ mỗi ngày.

---

## 1. Bối cảnh cuộc thi

- **IT Consultant Challenge 2026** do Netcompany Vietnam và Code MeLy tổ chức, chủ đề *"Prompt to Production"*. Mỗi đội 3 người.
- Có 3 vòng loại trực tiếp:
  - **Vòng 1 (hạn 26/10):** nộp proposal PDF tối đa 10 slide.
  - **Vòng 2 (2–9/11):** **chính team build MVP** trong 1 tuần và nộp kèm AI Journal.
  - **Vòng 3 (16–21/11):** nhận change request, demo và pitch trực tiếp.
- Tiêu chí vòng 1 gồm: hiểu vấn đề, ưu tiên và tư duy phản biện, tác động kinh doanh, tính khả thi, tư duy cấu trúc và sáng tạo.
- **Hệ quả:** ý tưởng phải vừa hợp lý với khách hàng, vừa **build được bởi 3 người trong 1 tuần**.

## 2. Bài toán của Company A

**Company A** là chuỗi bán lẻ vật liệu xây dựng của Đan Mạch, có hàng trăm cửa hàng ở Đan Mạch, Na Uy và Thụy Điển, phục vụ cả nhà thầu (B2B) lẫn khách lẻ (B2C). Đề tóm lại là "một doanh nghiệp, ba thị trường, ba cách làm việc".

**4 thách thức** (mỗi nước tự xây hệ thống và quy trình riêng):

| Thách thức | Ý nghĩa | Đề gợi ý nước nào đau nhất |
|---|---|---|
| Manual processes | Nhiều việc làm tay, tốn công nhân viên | Đan Mạch: *may create the greatest impact* |
| Inconsistent operations | Mỗi cửa hàng làm một kiểu | Na Uy: *may be a more urgent priority* |
| Delivery & fulfilment | Đơn hàng và giao hàng kém hiệu quả, kém tin cậy | Thụy Điển: *may have greater business impact* |
| Fragmented systems | Hệ thống mỗi nước khác nhau, khó nhân rộng cải tiến | Cả ba |

**Ràng buộc của ban điều hành:**
- Chỉ đầu tư **một giải pháp số**, nhưng **không triển khai giống hệt** ở cả ba nước.
- Phải tính tới quy trình địa phương, hệ thống sẵn có, vận hành cửa hàng và kho, tác động lên nhân viên và khách hàng, và cách rollout.
- **Time to market là then chốt.** Khoanh phạm vi cẩn thận, tập trung một vấn đề.

**Nhiệm vụ của team:** Identify (chọn 1 cơ hội) → Prioritise (vì sao chọn) → Solve (giải pháp + MVP) → Scale (rollout có tính khác biệt địa phương). Ngoài ra phải trả lời *"AI tạo giá trị ở đâu?"*.

## 3. Chẩn đoán: gốc rễ nằm ở khâu nhận đơn

Đi theo một đơn hàng của nhà thầu, cả 4 thách thức đều xuất hiện:

```
1. Đơn đến       → email, điện thoại, PDF, ảnh; mỗi nước một kiểu    (Fragmented systems)
2. Gõ lại tay    → nhân viên nhập từng dòng vào ERP                  (Manual processes)
3. Xử lý         → mỗi cửa hàng xác nhận, gọi lại theo cách riêng    (Inconsistent operations)
4. Hứa & giao    → hứa ngày khi chưa kiểm tồn → giao trễ, thiếu      (Delivery & fulfilment)
```

**Gốc rễ:** Company A không có một lớp nhận đơn chung, có cấu trúc và có kiểm tồn, nằm trên ba hệ thống ERP quốc gia. Vì thế đơn nào cũng phải xử lý tay, và mọi cải tiến chỉ dừng ở cấp từng nước.

## 4. Lựa chọn: Manual processes ở khâu nhận đơn của nhà thầu

> **"We prioritise Manual processes – specifically contractor order handling."**

- **Một vấn đề duy nhất:** đơn B2B được gõ lại tay và được hứa ngày giao khi chưa kiểm tồn.
- Sửa được khâu này thì **mở đường** cho 3 thách thức kia, nhưng team **không** tuyên bố giải quyết cả 4.
- **Bắt đầu ở Đan Mạch:** đây là nơi đề gợi ý manual processes có tác động lớn nhất, và có thể là nơi khối lượng làm tay cao nhất [A].

## 5. Giải pháp: OrderFlow

### 5.1 Ý tưởng

Một **lớp phần mềm mỏng có AI**, đặt **trước** ERP hiện có của từng nước. **Không thay ERP.**

| Bước | Ai hoặc cái gì làm | Việc |
|---|---|---|
| 1. Đọc đơn | AI | Email, PDF hoặc ảnh → danh sách hàng, số lượng, công trình, ngày cần |
| 2. Khớp mã hàng | AI | Tên gọi kiểu dân trong nghề → mã SKU, dựa trên catalogue và lịch sử mua |
| 3. Kiểm tồn | Quy tắc | Tồn cửa hàng + kho trung tâm (DC) → ngày giao thực tế. Dòng tồn thấp → lấy ngày theo DC hoặc kiểm tay |
| 4. Duyệt | Nhân viên | Một màn hình; dòng AI không chắc được tô vàng |
| 5. Gửi & xác nhận | API | Adapter cho ERP từng nước; nhà thầu nhận ngày giao và tin nhắn trạng thái tự động |

### 5.2 AI tạo giá trị ở đâu

- **Hiểu đơn phi cấu trúc:** email, PDF, ảnh viết tay.
- **Khớp mã hàng:** xử lý tiếng lóng nghề và ba ngôn ngữ (Đan Mạch, Na Uy, Thụy Điển).
- **Sau này:** gợi ý mua kèm, dự báo rủi ro giao trễ.
- **Tin cậy:** model chạy trong EU, không train trên dữ liệu khách, có điểm tin cậy, người duyệt cuối và log kiểm toán. Theo EU AI Act, đây không phải ứng dụng rủi ro cao.

### 5.3 Timeline

| Thời gian | Việc | Kết quả |
|---|---|---|
| Tuần 1 | Kiểm tra ERP Đan Mạch (API, file, EDI); lấy 500 đơn cũ làm bộ test | Biết cách đưa đơn vào ERP |
| Tuần 2–5 | Xây phần đọc đơn, khớp mã, màn hình duyệt; back-test | Đo độ chính xác trước khi go-live |
| **Tuần 6** | **Assistive mode** ở 5–10 cửa hàng: AI điền sẵn, nhân viên duyệt rồi nhập như hiện nay | **Có giá trị thật, chưa cần sửa ERP** |
| Tuần 7–10 | Ghi đơn thẳng vào ERP; xác nhận cho nhà thầu kèm ngày giao | Bỏ bước copy tay |
| Tuần 11–12 | Đo KPI → **Gate 1: go/no-go** | Quyết định dựa trên số liệu |
| Tháng 4–6 | Toàn bộ Đan Mạch | |
| Tháng 5–9 | Thụy Điển: adapter ERP + ngày giao kiểm theo tồn Store + DC + tin nhắn trạng thái | Đánh vào delivery & fulfilment |
| Tháng 8–12 | Na Uy: adapter ERP + **Counter mode** | Đánh vào inconsistent operations |
| Năm 2 (tùy chọn, chưa tính chi phí) | Live GPS tracking, khung giờ giao, portal nhà thầu, mở rộng B2C | |

### 5.4 Một giải pháp, ba cách triển khai

- **Dùng chung:** lõi AI, Order API, màn hình duyệt, mô hình dữ liệu.
- **Riêng từng nước:** adapter ERP, ngôn ngữ và thuật ngữ sản phẩm, quy tắc ngày giao, quy trình cửa hàng.
- **Con người:** tham vấn đại diện người lao động trước mỗi đợt triển khai, có "store champion" ở mỗi nước. **Không cắt giảm nhân sự.**

### 5.5 Business case (kịch bản cơ sở, toàn bộ là [A])

- 300 cửa hàng × 20 đơn B2B thủ công/ngày × 8 phút ≈ **121 FTE** đang làm việc gõ đơn.
- Giảm 60% thời gian × hiện thực hóa 75% → **≈55 FTE được giải phóng**, tương đương **DKK 23m/năm giá trị năng lực**. Đây không phải tiền mặt.
- Quy ra tiền mặt: ≈DKK 5,8m (bớt thuê thời vụ, giảm làm thêm giờ, không tuyển bù người nghỉ), trừ chi phí vận hành DKK 2,2m → **tiền mặt ròng ≈DKK 3,6m/năm**.
- Hoàn vốn tiền mặt: MVP (~DKK 4,5m) khoảng 15 tháng; toàn chương trình khoảng 3 năm.
- Chưa tính: giữ chân nhà thầu nhờ xác nhận nhanh và giao đúng hẹn, cùng lợi ích cho B2C.
- Độ nhạy: kịch bản bi quan ≈17 FTE (≈DKK 7m), lạc quan ≈109 FTE (≈DKK 49m).

## 6. Vì sao không chọn những hướng khác

### 6.1 Không chọn thách thức khác làm trọng tâm

| Thách thức | Vì sao không chọn làm trọng tâm |
|---|---|
| **Delivery & fulfilment** (Thụy Điển) | Giao trễ thường **bắt đầu từ lời hứa không kiểm tồn ở khâu nhận đơn**. Làm tracking trước thì chỉ cho khách *theo dõi* một lời hứa vốn đã sai. Tracking cũng cần đội xe, TMS, app tài xế, nên mất nhiều tháng. |
| **Inconsistent operations** (Na Uy) | Có thể sửa nhanh bằng app quản lý việc ở cửa hàng, nhưng đó chỉ là **chuẩn hóa bề mặt**, không chạm vào luồng gây tốn thời gian và mất khách. Na Uy vẫn được giải quyết ở wave 3 qua counter mode. |
| **Fragmented systems** | Sửa tận gốc nghĩa là hợp nhất hoặc thay ERP, mất **nhiều năm**, nên trượt yêu cầu time-to-market. OrderFlow làm "lớp chung" mà không cần thay ERP. |

### 6.2 Không chọn các phương án giải pháp khác

| Phương án | Tác động | Time to market | Vì sao loại |
|---|---|---|---|
| **A. OrderFlow (chọn)** | Cao | **Vài tuần** | Vừa nhanh vừa đánh vào gốc |
| B. Portal tự đặt hàng cho nhà thầu | Trung bình–cao | Chậm (phải chờ khách chấp nhận) | Cần giá và tồn kho chuẩn trước; nhà thầu vẫn quen gửi email. Để năm 2, dùng cùng Order API |
| C. Chỉ khung giờ giao + tracking | Trung bình–cao | Nhiều tháng | Chạy được mà không cần A, nhưng **giá trị bị giới hạn** khi ngày giao vẫn được hứa không kiểm tồn. Chỉ có ích cho Thụy Điển |
| D. App quản lý việc ở cửa hàng | Thấp | Vài tuần | Nhanh nhưng chỉ mang tính bề mặt |
| E. Hợp nhất hoặc thay ERP | Cao | Nhiều năm | Đúng gốc nhưng quá chậm và rủi ro |

### 6.3 Vì sao bắt đầu ở Đan Mạch, không phải Thụy Điển hay Na Uy

- Đề gợi ý manual processes *có thể có tác động lớn nhất* ở Đan Mạch, đúng vấn đề team chọn.
- Đan Mạch là trụ sở của Company A: dễ tiếp cận stakeholder và dễ làm pilot [A].
- Thụy Điển cần dữ liệu đơn có cấu trúc và kiểm tồn **trước**, mà Đan Mạch sẽ tạo ra lõi đó. Thụy Điển bắt đầu từ tháng 5 trên cùng lõi.

### 6.4 Vì sao B2B trước, không phải B2C

- **Đơn thủ công tập trung ở B2B:** nhà thầu gửi danh sách vật tư tự do. Khách lẻ phần lớn mua ở quầy hoặc webshop với mã hàng có sẵn [A].
- **Giá trị mỗi khách lớn hơn:** đơn lớn, mua lặp lại, mất một nhà thầu là mất nhiều doanh thu.
- **Hậu quả khi hỏng nặng hơn:** đội thợ ngồi chờ thì nhà thầu chuyển sang đối thủ.
- **Ngành cũng đi theo hướng này:** STARK Group nói chiến lược của họ xoay quanh thợ và nhà thầu.
- **Không bỏ B2C:** khách lẻ hưởng lợi gián tiếp (≈300 giờ/cửa hàng/năm) và trực tiếp ở Na Uy (counter mode). Mở rộng B2C là tùy chọn năm 2.

## 7. Ưu điểm

1. **Đúng một vấn đề, có lý do rõ ràng.** Bám yêu cầu "Choose ONE".
2. **Time to market nhanh.** Có giá trị thật từ tuần 6 mà chưa cần sửa ERP.
3. **Rủi ro thấp.** Không thay ERP; triển khai từng bước, có Gate 1 trước khi tốn thêm tiền.
4. **Tái sử dụng cao.** Một lõi dùng cho ba nước, mỗi nước chỉ thêm adapter và module riêng, đúng tinh thần "reuse, not reinvent" của Netcompany.
5. **AI nằm trong quy trình và có kiểm soát.** Có người duyệt, chạy trong EU, có log, phù hợp tinh thần "European sovereignty".
6. **Trả lời được cả 4 thách thức** theo thứ tự hợp lý: DK manual → SE delivery → NO consistency, trên nền một lớp dữ liệu chung.
7. **Demo được ở vòng 2.** Luồng email → AI → màn hình duyệt → mock ERP build được trong 1 tuần.
8. **Thân thiện với người lao động.** Không cắt giảm nhân sự, có tham vấn công đoàn.

## 8. Nhược điểm và rủi ro

| Nhược điểm / rủi ro | Mức độ | Cách giảm |
|---|---|---|
| ERP không có API ghi đơn | Trung bình / Cao | Assistive mode không cần đụng ERP; spike tuần 1; dùng file hoặc EDI |
| AI khớp sai tiếng lóng nghề (VD "45x95 C24") | Trung bình / Trung bình | Người duyệt, ngưỡng tin cậy, back-test 500 đơn thật |
| Dữ liệu tồn kho không đúng | Cao / Trung bình | Dòng tồn thấp → lấy ngày theo DC hoặc kiểm tay; nhân viên báo lệch kho bằng 1 click → kích hoạt kiểm kê |
| Tiền mặt ròng khiêm tốn (≈DKK 3,6m/năm) | — | Nói thật: giá trị chính nằm ở năng lực bán hàng và giữ chân khách. Có Gate 1 để dừng sớm nếu không đạt |
| Nhân viên hoặc công đoàn phản đối | Trung bình / Cao | Đồng thiết kế với cửa hàng pilot; định vị là công cụ hỗ trợ |
| Lo ngại về dữ liệu (GDPR) | Thấp / Cao | Chạy trong EU, có hợp đồng xử lý dữ liệu, không train trên dữ liệu khách |
| **Chỉ phục vụ B2B là chính** | — | Nói rõ là lựa chọn có chủ ý; nêu lợi ích B2C và đường mở rộng |
| Không giải quyết vấn đề giao hàng ở khâu vận chuyển (xe, tuyến) | — | Ngoài phạm vi; để năm 2 |

## 9. Thiếu sót: những gì team chưa biết hoặc chưa có

1. **Không có dữ liệu thật của Company A.** Số cửa hàng (300), số đơn/ngày (20), số phút/đơn (8) đều là giả định.
2. **Không có benchmark độc lập của ngành vật liệu xây dựng.** Các số "−60% thời gian xử lý", "90% tự động" đều do vendor công bố, và đến từ ngành lân cận (thép, sữa, thiết bị vệ sinh).
3. **Chưa biết Company A dùng ERP gì.** Đây là ẩn số lớn nhất về tính khả thi.
4. **Các số tiền mặt (DKK 5,8m quy đổi và 2,2m vận hành) là giả định**, chưa có cơ sở chi tiết.
5. **Lợi ích về doanh thu và B2C chưa được định lượng.**
6. **Chưa phỏng vấn người trong ngành** (nhà thầu hoặc nhân viên cửa hàng) để xác nhận nỗi đau.
7. **Chưa có ảnh prototype** để chứng minh ý tưởng build được.
8. **Tỷ giá và lương** lấy từ nguồn thứ cấp, cần kiểm lại.

→ Cách xử lý trong proposal: gắn **[A]** cho mọi giả định, nói rằng **pilot sinh ra để kiểm chứng chúng**, và nếu kịp thì phỏng vấn 3–5 người trong ngành.

## 10. Câu hỏi dễ bị hỏi và cách trả lời

> Mỗi câu gồm: **Vì sao bị hỏi** (giám khảo đang thử điều gì) · **Trả lời** (để team hiểu) · **EN** (câu nói gọn khi pitch).
> Nguyên tắc: trả lời thẳng trong 1 câu, sau đó mới giải thích. Nếu số liệu là giả định thì **nói luôn là giả định**.

### 10.1 Hiểu vấn đề (Problem Understanding)

**Q1. Giải pháp này chỉ phục vụ B2B à? Còn khách lẻ (B2C) thì sao?**
- *Vì sao bị hỏi:* đề nói Company A phục vụ cả hai nhóm khách.
- *Trả lời:* Đúng, trọng tâm là B2B, và đó là lựa chọn có chủ ý vì đơn làm tay tập trung ở nhà thầu. B2C vẫn hưởng lợi: khoảng 300 giờ mỗi cửa hàng mỗi năm được trả lại cho sàn bán, và counter mode ở Na Uy xử lý cả đơn tại quầy của khách lẻ. Mở rộng cho đơn email hoặc điện thoại của khách lẻ là tùy chọn năm 2.
- *EN:* "B2B is a deliberate choice – that’s where free-text, manual orders concentrate. Consumers gain about 300 staff hours per store per year on the shop floor, and Norway’s counter mode serves walk-in consumers too."

**Q2. Làm sao các bạn biết khâu nhận đơn là gốc rễ, khi chưa có dữ liệu của Company A?**
- *Vì sao bị hỏi:* thử xem đây là chẩn đoán hay đoán mò.
- *Trả lời:* Team suy ra từ đề: 4 thách thức đều xuất hiện trên đường đi của một đơn hàng (mục 3). Đây là giả thuyết, và tuần 1–2 của pilot dùng để kiểm chứng: đo số đơn làm tay, thời gian mỗi đơn, tỷ lệ ngày hứa bị trễ.
- *EN:* "It’s a hypothesis built from the brief – all four challenges show up in one order. Weeks 1–2 of the pilot measure it before we scale."

**Q3. Sao không làm khảo sát người dùng?**
- *Trả lời:* Thời gian vòng 1 có hạn và team không tiếp cận được Company A. Nếu kịp, team phỏng vấn 3–5 người làm xây dựng hoặc bán vật liệu. Trong pilot, việc đầu tiên là ngồi cùng nhân viên quầy để quan sát.
- *EN:* "Discovery with store staff is week 1 of the pilot; we validate before we build further."

**Q4. 4 thách thức đều được nói là "liên quan nhau", vậy các bạn đang giải 1 hay giải cả 4?**
- *Vì sao bị hỏi:* đề yêu cầu "Choose ONE".
- *Trả lời:* Giải **một**: Manual processes ở khâu nhận đơn của nhà thầu. 3 thách thức còn lại được cải thiện như hệ quả, theo từng wave, nhưng không phải mục tiêu chính và không nằm trong business case.
- *EN:* "One problem: manual contractor order handling. The other three benefit as a knock-on effect, not as our target."

### 10.2 Ưu tiên và tư duy phản biện (Prioritisation)

**Q5. Đề gợi ý Thụy Điển có thể có business impact lớn nhất. Sao không bắt đầu ở Thụy Điển?**
- *Trả lời:* Giao trễ ở Thụy Điển thường bắt đầu từ lời hứa không kiểm tồn ở khâu nhận đơn. Làm tracking trước thì chỉ giúp khách theo dõi một lời hứa vốn đã sai. Team sửa khâu nhận đơn ở Đan Mạch trước, nơi đề gợi ý manual processes có tác động lớn nhất, rồi dùng lại lõi đó ở Thụy Điển từ tháng 5.
- *EN:* "Late deliveries start with unchecked promises at intake. We fix intake first and reuse the core in Sweden from month 5."

**Q6. Sao không làm tracking giao hàng như Travis Perkins, STARK UK?**
- *Trả lời:* Tracking là một hệ thống khác hẳn (GPS xe, TMS, app tài xế), mất nhiều tháng và tốn tiền hơn. Nó chạy được mà không cần OrderFlow, nhưng giá trị bị giới hạn khi ngày giao vẫn được hứa không kiểm tồn. Team để tracking ở năm 2, chạy trên cùng Order API.
- *EN:* "Tracking needs fleet systems and months of work. Without a stock check, it only tracks a broken promise. It’s a year-2 option on the same order API."

**Q7. Sao không thay luôn ERP cho ba nước, để giải quyết tận gốc "fragmented systems"?**
- *Trả lời:* Thay ERP mất nhiều năm và rủi ro cao, nên trượt yêu cầu time-to-market. OrderFlow tạo một lớp dữ liệu đơn hàng chung **mà không cần thay ERP**. Sau này nếu Company A muốn hợp nhất ERP, lớp này giúp chuyển đổi dễ hơn.
- *EN:* "Replacing ERPs takes years. OrderFlow gives a shared order layer now, and makes a later consolidation easier."

**Q8. App quản lý việc ở cửa hàng nhanh và rẻ hơn. Sao không chọn?**
- *Trả lời:* Nhanh nhưng chỉ chuẩn hóa bề mặt (checklist, nhiệm vụ). Nó không chạm vào luồng gây tốn thời gian và mất khách. Na Uy vẫn được chuẩn hóa ở wave 3 qua counter mode, gắn với luồng đơn thật.
- *EN:* "It standardises tasks, not the flow that costs time and customers."

**Q9. Sao không làm portal cho nhà thầu tự đặt hàng? Như vậy khỏi cần AI đọc email.**
- *Trả lời:* Portal cần thời gian để khách chấp nhận, và nhà thầu vẫn quen gửi email hoặc gọi điện từ công trường. Đó là lý do tỷ lệ đặt hàng online trong ngành còn thấp. OrderFlow nhận đơn theo cách khách **đang** đặt. Portal để năm 2, dùng cùng Order API.
- *EN:* "We meet contractors where they already order – email and phone. A portal can come later on the same API."

**Q10. Bảng so sánh phương án do chính team chấm điểm. Có thiên vị không?**
- *Trả lời:* Có rủi ro đó, nên team mô tả mỗi phương án ở dạng mạnh nhất của nó (C là "slots & tracking" như merchant Anh, không phải một bộ TMS khổng lồ) và nêu rõ tiêu chí: tác động, time to market, khả thi, tái sử dụng, có đánh vào gốc không.
- *EN:* "We scored each option at its strongest, against the case criteria."

### 10.3 Tác động kinh doanh (Business Impact)

**Q11. DKK 23 triệu có phải tiền tiết kiệm thật không?**
- *Vì sao bị hỏi:* câu bẫy phổ biến nhất.
- *Trả lời:* Không. Đó là **giá trị năng lực**: khoảng 55 FTE được trả lại cho bán hàng. Vì team cam kết không cắt người, phần quy ra tiền mặt chỉ khoảng DKK 5,8 triệu (bớt thuê thời vụ, giảm làm thêm giờ, không tuyển bù người nghỉ). Trừ chi phí vận hành DKK 2,2 triệu còn **tiền mặt ròng khoảng 3,6 triệu/năm**. Tất cả là giả định.
- *EN:* "No – 23m is capacity value, about 55 FTE. Net cash is about 3.6m a year after run costs; the rest is time back with customers."

**Q12. Hoàn vốn tiền mặt cả chương trình mất 3 năm. Vậy có đáng làm không?**
- *Trả lời:* Phần tiền mặt chỉ là mức sàn. Giá trị lớn hơn nằm ở việc giữ chân nhà thầu (xác nhận nhanh, giao đúng hẹn) và năng lực bán hàng, nhưng team chưa định lượng vì chưa có dữ liệu. Vì thế mới có **Gate 1**: chỉ chi khoảng DKK 3,5–6 triệu cho pilot, đạt KPI thì mới mở rộng.
- *EN:* "Cash payback is the floor. The bigger upside is contractor retention – which the pilot measures before any further spend."

**Q13. Lấy đâu ra 300 cửa hàng, 20 đơn mỗi ngày, 8 phút mỗi đơn?**
- *Trả lời:* Đều là giả định. Đề chỉ nói "hundreds of stores", và không chuỗi nào công bố số đơn mỗi cửa hàng. Team đưa 3 kịch bản (17 / 55 / 109 FTE) để thấy độ nhạy. Tuần 1–2 của pilot đo số thật theo từng loại cửa hàng.
- *EN:* "They’re stated assumptions with a low–base–high range; week 1 measures the real numbers."

**Q14. Cửa hàng thiên về DIY đâu có 20 đơn B2B mỗi ngày?**
- *Trả lời:* Đúng, đó là điểm yếu của giả định. Team sẽ kiểm theo loại cửa hàng ở tuần 1–2. Pilot chọn các cửa hàng có nhiều đơn B2B, và kịch bản bi quan (15 đơn/ngày) đã tính tới điều này.
- *EN:* "Fair point – we validate by store type and pilot in trade-heavy stores first."

**Q15. Benchmark −60% thời gian lấy từ đâu? Có đáng tin không?**
- *Trả lời:* Từ case study do vendor công bố, ở ngành lân cận: OIKI (thép, IBM) giảm từ 30 xuống 12 phút mỗi đơn, Topa (thiết bị vệ sinh) tự động hơn 90%. Team chưa tìm thấy benchmark độc lập nào của ngành vật liệu xây dựng, và nói thẳng điều đó. Mục tiêu của team thận trọng hơn vendor, và pilot sẽ tạo ra số liệu riêng.
- *EN:* "Vendor-reported, adjacent sectors – we say so openly, set more conservative targets, and the pilot creates our own evidence."

### 10.4 Tính khả thi (Feasible Solution)

**Q16. Nếu ERP của Company A không có API thì sao?**
- *Trả lời:* Assistive mode chạy được từ tuần 6 **mà không cần đụng ERP**: nhân viên duyệt đơn rồi nhập như hiện nay. Tuần 1 team kiểm tra ERP. Nếu không có API thì dùng import file hoặc EDI. Rủi ro này đã được đưa ra khỏi đường găng.
- *EN:* "Assistive mode needs no ERP change, so week-6 value doesn’t depend on the API."

**Q17. AI đọc sai đơn thì sao? Ai chịu trách nhiệm?**
- *Trả lời:* Nhân viên luôn duyệt trước khi đơn vào ERP. Dòng nào AI không chắc thì được tô vàng. Mọi chỉnh sửa được ghi log, và AI học từ đó. Trách nhiệm cuối cùng vẫn thuộc về nhân viên, giống như hiện nay.
- *EN:* "A human approves every order; low-confidence lines are flagged and every edit is logged."

**Q18. AI hiểu tiếng lóng nghề và ba thứ tiếng thế nào (VD "45x95 C24")?**
- *Trả lời:* Kết hợp catalogue sản phẩm, lịch sử mua của chính nhà thầu đó, và tìm kiếm theo ngữ nghĩa. Team back-test trên 500 đơn thật trước khi go-live. Mục tiêu là ≥95% khớp đúng **theo từng dòng**, vì 90% mỗi dòng nghĩa là đơn 15 dòng chỉ đúng trọn khoảng 21%.
- *EN:* "Catalogue plus each contractor’s purchase history; we back-test on 500 real orders and target ≥95% per line."

**Q19. Tồn kho trên hệ thống không đúng thì ngày giao hứa vẫn sai?**
- *Trả lời:* Đúng, phần mềm không tự làm tồn kho đúng được. Vì vậy dòng nào tồn thấp thì lấy ngày theo kho trung tâm hoặc kiểm tay. Nhân viên báo lệch kho bằng 1 click, và việc đó kích hoạt kiểm kê.
- *EN:* "Low-stock lines get a DC-based date or a manual check, and a one-click mismatch flag triggers a cycle count."

**Q20. 12 tuần với 6–8 người có thực tế không?**
- *Trả lời:* Thực tế vì phạm vi rất hẹp: 1 nước, 1 ERP, 1 kênh (email), 5–10 cửa hàng. Tuần 6 đã có assistive mode, không phụ thuộc tích hợp. Các case vendor cũng cho thấy loại tự động hóa này thường làm được trong vài tháng.
- *EN:* "Yes – one country, one ERP, one channel, and value from week 6 without integration."

**Q21. Dữ liệu khách hàng (email nhà thầu) đưa qua AI có vi phạm GDPR không?**
- *Trả lời:* Không, nếu làm đúng: model chạy trong EU, có hợp đồng xử lý dữ liệu, không train trên dữ liệu khách, giảm tối thiểu dữ liệu cá nhân, có log kiểm toán. Theo EU AI Act, đọc đơn hàng không phải ứng dụng rủi ro cao.
- *EN:* "EU-hosted, under a data processing agreement, no training on customer data – and order extraction isn’t high-risk under the EU AI Act."

**Q22. Nhân viên và công đoàn có phản đối không?**
- *Trả lời:* Có thể, nhất là ở Bắc Âu, nơi luật yêu cầu tham vấn người lao động khi đưa công nghệ mới vào. Team cam kết không cắt người, đồng thiết kế với cửa hàng pilot, có "store champion", và tham vấn đại diện người lao động trước mỗi đợt.
- *EN:* "No headcount cuts, co-design with pilot stores, and employee reps consulted before each wave."

**Q23. Chi phí LLM khi chạy cho 300 cửa hàng có cao không?**
- *Trả lời:* Team ước chi phí vận hành khoảng DKK 2,2 triệu/năm [A], đã trừ vào tiền mặt ròng. Kiến trúc mở nên có thể đổi model để giảm chi phí, và chỉ gọi AI cho đơn phi cấu trúc.
- *EN:* "Run cost is in the case (about 2.2m a year [A]), and the architecture lets us switch models."

### 10.5 Mở rộng và triển khai (Scale)

**Q24. "Một giải pháp, ba cách triển khai" cụ thể khác nhau ở đâu?**
- *Trả lời:* Lõi chung gồm AI, Order API và màn hình duyệt. Mỗi nước thêm phần riêng: Đan Mạch thêm kênh nhận đơn (ảnh, ghi chú điện thoại), Thụy Điển thêm ngày giao kiểm theo tồn và tin nhắn trạng thái, Na Uy thêm counter mode. Ngoài ra còn adapter ERP, ngôn ngữ và quy tắc ngày giao riêng của từng nước.
- *EN:* "Shared core; Denmark adds channels, Sweden adds checked delivery dates, Norway adds counter mode."

**Q25. Counter mode là gì? Sao nó giải quyết được vấn đề của Na Uy?**
- *Trả lời:* Counter mode là dùng cùng màn hình duyệt cho đơn tại quầy và qua điện thoại. Nhờ đó mọi cửa hàng Na Uy nhận, kiểm và xác nhận đơn **theo cùng một cách**, đúng vấn đề "inconsistent operations".
- *EN:* "The same review screen for walk-in and phone orders, so every Norwegian store works the same way."

**Q26. Nếu pilot ở Đan Mạch thất bại thì sao?**
- *Trả lời:* Có Gate 1 ở tháng 3: không đạt KPI thì dừng hoặc điều chỉnh trước khi chi tiền cho Thụy Điển và Na Uy. Số tiền rủi ro chỉ là chi phí pilot (khoảng DKK 3,5–6 triệu).
- *EN:* "Gate 1 at month 3 – we stop or adjust before funding Sweden and Norway."

**Q27. Sao Thụy Điển và Na Uy chạy gối đầu nhau mà không làm lần lượt?**
- *Trả lời:* Vì lõi chỉ xây một lần, mỗi nước chỉ thêm adapter và module riêng, nên có thể chạy song song phần nào. Rủi ro được kiểm soát bằng Gate 1 và việc mỗi nước có store champion riêng.
- *EN:* "The core is built once, so later waves only add an adapter and one module."

### 10.6 Về cuộc thi và quy trình làm việc

**Q28. Vòng 2 các bạn sẽ build gì trong 1 tuần?**
- *Trả lời:* Một prototype chạy được: hộp thư đơn mẫu, AI đọc đơn trả về JSON, khớp mã trên catalogue mẫu 300–500 sản phẩm, màn hình duyệt, bảng tồn kho giả, và mock ERP có adapter DK/SE/NO qua cấu hình. Kiến trúc module giúp đón change request ở vòng 3.
- *EN:* "Email inbox → AI extraction → SKU matching → review screen → mock ERP with per-country adapters."

**Q29. Các bạn dùng AI để làm bài thế nào? Phần nào là của team?**
- *Trả lời:* AI hỗ trợ nghiên cứu và soạn nháp. Team tự kiểm chứng nguồn (đã bỏ các số không xác minh được), tự quyết hướng giải pháp, và tự viết lại slide. Quá trình này được ghi vào AI Journal.
- *EN:* "AI helped research and draft; we verified every source, made the decisions, and wrote the deck ourselves."

**Q30. Điểm yếu lớn nhất của giải pháp là gì?**
- *Vì sao bị hỏi:* thử độ trung thực.
- *Trả lời:* Có ba điểm: (1) mọi số liệu đều là giả định, chưa có dữ liệu của Company A; (2) tiền mặt ròng khiêm tốn, giá trị chính nằm ở năng lực và giữ chân khách, mà phần này chưa định lượng; (3) chưa biết ERP thật. Pilot được thiết kế để kiểm chứng đúng ba điểm này trước khi tốn thêm tiền.
- *EN:* "Our numbers are assumptions, cash return is modest, and the ERP is unknown – the pilot is designed to test exactly these."

## 11. Thuật ngữ

| Thuật ngữ | Nghĩa |
|---|---|
| B2B / Pro | Khách doanh nghiệp: nhà thầu, thợ |
| B2C / DIY | Khách lẻ, người tự sửa nhà |
| ERP | Phần mềm quản lý lõi (đơn hàng, kho, hóa đơn) của từng nước |
| SKU | Mã hàng |
| DC | Kho trung tâm (distribution centre) |
| FTE | Một người làm toàn thời gian trong một năm |
| MVP / pilot | Bản tối thiểu chạy thử ở vài cửa hàng |
| Assistive mode | AI điền sẵn đơn, nhân viên duyệt rồi tự nhập vào ERP; chưa tích hợp ERP |
| Counter mode | Cùng màn hình duyệt dùng cho đơn tại quầy và qua điện thoại, để mọi cửa hàng làm giống nhau |
| Gate 1 | Điểm quyết định go/no-go sau 12 tuần pilot |
| TMS | Phần mềm quản lý vận tải (xe, tuyến, tài xế) |
| Live tracking | Theo dõi vị trí xe giao hàng theo thời gian thực; ngoài phạm vi |
