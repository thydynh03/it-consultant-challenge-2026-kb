# Deep dive: Kiểm chứng phương án OrderFlow (Company A)

## TL;DR
- **Phương án vẫn đứng vững** — khả thi về kỹ thuật, có lý do quy định (Na Uy) và cạnh tranh; chưa thấy đối thủ Bắc Âu nào công bố AI order intake cho nhà thầu → còn tính khác biệt.
- **Số liệu cần sửa:** bỏ trích dẫn L.E.K. ">5% premium" và Esker "51% / 3,5 phút" (không xác minh được); FTE tính sai (1.200 h/ngày = 182 FTE, không phải 150); kịch bản cơ sở nên hạ xuống ~**DKK 23m/năm** thay vì 40m.
- **Điểm yếu lớn nhất:** không có benchmark độc lập nào của ngành builders' merchant — mọi số ROI đều là vendor tự công bố ở ngành lân cận.
- **Rủi ro khả thi lớn nhất:** API của ERP pilot chưa biết → 12 tuần là căng; cần integration spike tuần 1 và fallback.
- Đã cập nhật toàn bộ vào `de-xuat-giai-phap.md`.

## 1. Kiểm chứng benchmark (mở trang gốc)

| Trích dẫn cũ | Kết quả kiểm chứng | Được dùng? |
|---|---|---|
| Esker: 51% đơn qua fax/email, 3,5 phút, −84% | Trang chỉ có "84% faster"; khách **ẩn danh**, không có năm; 51%/3,5 phút không có | Chỉ "84%", kèm caveat |
| Topa: >90% vào thẳng ERP, 30s, ~4 FTE | "+90% automated"; 30s "cho một số khách"; ~3,8 FTE điều chuyển | Có, sửa câu chữ |
| OIKI (IBM): 30→12 phút | Đúng (−60%), khách có tên, phân phối thép | Có (vendor) |
| Biodeal: median 48s, ~7% cần kiểm | Đúng; không phải "accuracy" | Có (vendor) |
| L.E.K. 2016: nhà thầu trả >5% cho giao nhanh | **Không mở được PDF**, không xác minh | **Không** |
| KPMG DK | Không có số liệu | Chỉ định tính |

Không tìm thấy số độc lập (APQC/Gartner/McKinsey) về tỷ lệ touchless hay chi phí/đơn thủ công — các con số "$30–80/đơn" lưu hành trên blog vendor không truy được về nguồn gốc → **không dùng**.

## 2. Business case

| Giả định | Kết luận |
|---|---|
| 300 cửa hàng | Không chuỗi Bắc Âu nào có 300 cửa hàng riêng tại DK/NO/SE (Bygma ~60 ở DK, Beijer ~113, Byggmax ~210 ở 4 nước). Giữ 300 như giả định từ "hundreds" trong đề |
| 30 đơn thủ công/cửa hàng/ngày | Không có dữ liệu công khai; 30 là mức cao → **dùng 20 làm cơ sở** |
| 8 phút/đơn | Hợp lý (OIKI ghi 30 phút với đơn phức tạp) — giữ, bi quan 6 phút |
| DKK 450k/FTE | Đúng cho DK; NO/SE ~370k → **blend DKK 425k** |
| 1.200 h/ngày = 150 FTE | **Sai số học**: 1.200 × 250 ÷ 1.650 = **182 FTE** |
| Tiết kiệm DKK 40m | Thay bằng 3 kịch bản: **7m / 23m / 49m**, có hệ số hiện thực hóa |
| MVP DKK 4–6m | Hợp lý (6–8 người × 65 ngày × DKK 8–12k/ngày ≈ 3,1–6,2m) |
| Payback < 12 tháng | Chỉ đúng nếu tính riêng MVP; toàn chương trình (≈2,5× MVP) ~6 tháng (cơ sở), ~27 tháng (bi quan) |

Đã tự tính lại cả 3 kịch bản — khớp.

## 3. Khả thi kỹ thuật & quy định

| Thành phần | Đánh giá |
|---|---|
| Trích xuất đơn từ email/PDF bằng LLM | Khả thi (bài báo 2025 về trích xuất hóa đơn ~94% — chỉ tham khảo) |
| SKU matching tiếng Bắc Âu | Khả thi có điều kiện — ≥90% thực tế **sau khi duyệt**; hàng có kích thước/tiếng lóng ("45x95 C24") khó hơn; cần golden test set |
| Tồn kho & delivery promise | Có điều kiện — phụ thuộc API ERP và độ chính xác tồn kho |
| Màn hình duyệt | Khả thi |
| Adapter ERP trong 12 tuần | **Rủi ro** — không rõ các chuỗi dùng ERP gì (STARK chạy đơn vị quốc gia tự chủ → nhiều hệ thống khác nhau) |
| GDPR / LLM cloud | Có điều kiện — Azure OpenAI EU Data Zone, DPA, tối thiểu hóa dữ liệu cá nhân |
| EU AI Act | Rủi ro tối thiểu/hạn chế (không thuộc Annex III); nghĩa vụ AI literacy |
| E-invoicing Na Uy | **Xác nhận từ nguồn chính thức**: luật thông qua 06/2026, bắt buộc phát hành từ **01/01/2027** → wave Na Uy có động lực bắt buộc |
| Công đoàn/đồng quyết định | Có điều kiện — tham vấn sớm (NO AML ch.8, SE MBL §11, DK hợp tác) |

**Đối thủ:** Byggmax dùng AI nội bộ cho mua hàng/logistics, Beijer dùng RELEX cho chuỗi cung ứng; không thấy ai công bố AI order intake cho nhà thầu → **khác biệt trong ngắn hạn** (lưu ý: tìm kiếm chủ yếu bằng tiếng Anh, nên team nên kiểm tra newsroom bằng tiếng địa phương).

## 4. Top 5 rủi ro & giảm thiểu
1. **API ERP chưa biết** → canonical order model, spike tuần 1, fallback file/EDI.
2. **Phạm vi 12 tuần quá rộng** → giữ 1 nước / 1 ERP / chỉ email.
3. **SKU accuracy thấp với tiếng lóng nghề** → prior từ lịch sử mua, ngưỡng tin cậy, golden test set.
4. **Lo ngại GDPR/LLM** → EU Data Zone, DPA, không train trên dữ liệu khách.
5. **Kháng cự của nhân viên/công đoàn** → tham vấn sớm, định vị "trợ lý", người duyệt cuối.

## 5. Độ tin cậy & khoảng trống
- **Cao:** luật e-invoicing Na Uy, doanh thu STARK/Bygma/Byggmax, số liệu OIKI/Biodeal/Topa (như vendor công bố).
- **Trung bình:** lương & chi phí FTE (tỷ giá chưa kiểm), chi phí MVP.
- **Thấp/không có:** số đơn/cửa hàng, tỷ lệ đơn qua điện thoại/email, OTIF ngành, ERP của đối thủ, benchmark độc lập.
- Khuyến nghị: phỏng vấn 3–5 người trong ngành xây dựng/vật liệu để có insight thật — bù cho khoảng trống dữ liệu và ghi điểm "Problem Understanding".

## Nguồn
Primary: regjeringen.no (e-invoicing), stortinget.no (Prop. 44 L), báo cáo Byggmax (cision), IBM OIKI.
Secondary/vendor: esker.com, lleverage.ai, casestudies.com (Mirage), loen.dk, karrierestart.no, ledigajobb.se, interiordaily.com (Bygma), uni-mannheim.de (product matching), relexsolutions.com, mynewsdesk (Byggmax/Zimply), Microsoft Q&A (Azure EU Data Zone).
