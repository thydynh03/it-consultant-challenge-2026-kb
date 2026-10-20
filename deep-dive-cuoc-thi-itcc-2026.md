# Deep dive: IT Consultant Challenge 2026 & kiểm tra lạc đề

## TL;DR
- ITCC 2026 (mùa 3, chủ đề **"Prompt to Production"**) **không chỉ là cuộc thi viết proposal**: 3 vòng loại trực tiếp — Proposal → **team tự build MVP trong 1 tuần** → xử lý change request + demo + pitch live.
- Vòng 1 chấm **"most creative, feasible and relevant ideas"** → ý tưởng phải *build được bởi 3 sinh viên trong 1 tuần*, không chỉ hay trên giấy.
- **OrderFlow không lạc đề** — trả lời đủ 4 bước Identify/Prioritise/Solve/Scale và câu hỏi "AI ở đâu". Đã sửa 3 điểm có nguy cơ lệch (xem mục 4) và bổ sung prototype cho vòng 2.
- AI được phép nhưng **slide không được hoàn toàn do AI viết**, team phải hiểu và bảo vệ mọi chi tiết; nộp **AI Journal** sau vòng 2.
- Netcompany đề cao: tái sử dụng (reuse, not reinvent), hiện đại hóa từng bước, chủ quyền dữ liệu châu Âu, AI có kiểm soát → OrderFlow khớp, cần làm rõ trên slide.

## 1. Cuộc thi (nguồn chính thức: itconsultantchallenge.org — đã tự kiểm tra trang Home & FAQ)

| Mục | Chi tiết |
|---|---|
| Tổ chức | Netcompany Vietnam & Code MeLy; mùa 2024, 2025 trước đó; 2026 là "brand-new format" |
| Đội | **3 người**, sinh viên/IT fresher; đăng ký **đã đóng** (đủ chỉ tiêu) |
| Vòng 1 – Discover | 19–26/10, online, nộp proposal. Kết quả 02/11 |
| Vòng 2 – Build | 02–09/11, online, **nộp MVP chạy được** + AI Journal. Chấm: product, technical capability, problem-solving approach. Kết quả 16/11 |
| Vòng 3 – Deliver | 16–21/11: **change request**, tinh chỉnh, demo + pitch live; chung kết 21/11 tại Netcompany HCM (online nếu ngoài HCM) |
| Tiêu chí | Gửi qua email trước mỗi vòng (Round 1 đã có trong đề: 5 tiêu chí) |
| AI | Được dùng như công cụ hỗ trợ; phải kiểm chứng, hiểu, bảo vệ được; tránh slide 100% AI |
| Tech stack | Không giới hạn; dùng open-source phải nêu rõ phần tự làm |
| Giải | Tổng >300 triệu: 60 / 30 / 15 triệu (Got It e-voucher) + học bổng Engineer Pro (top 20), DuaEdu (top 10, top 5) |
| Bài thắng/đề các năm trước | **Không tìm thấy** công khai (có thể có trên Facebook Code MeLy) |

## 2. Góc nhìn của giám khảo Netcompany
- Công ty IT Đan Mạch, mạnh ở khu vực công và ngành có quy định chặt; chiến lược 2026: **"sovereign and secure agentic AI"**, framework **Feniks AI** cho phát triển phần mềm có AI hỗ trợ.
- Cách làm: các module tái sử dụng, "Reuse, not Reinvent", governance & compliance trước.
- **Không tìm thấy** case bán lẻ/vật liệu xây dựng công khai của Netcompany → đừng tuyên bố "Netcompany đã làm X cho ngành này"; cũng không nên dựa giải pháp vào sản phẩm của họ.
- Netcompany VN tuyển developer/consultant làm dự án châu Âu: phân tích yêu cầu, làm việc với khách → giám khảo đánh giá cao tư duy BA + kỹ thuật vững.

## 3. Đối chiếu đề ↔ phương án

| Yêu cầu trong đề | OrderFlow trả lời | Trạng thái |
|---|---|---|
| 01 Identify – chọn **MỘT** cơ hội | Xử lý đơn B2B thủ công & không đáng tin của nhà thầu | ✅ (đã sửa để không tuyên bố "giải cả 4") |
| 02 Prioritise – vì sao chọn | Gốc rễ chung, ma trận 4 phương án, là nền cho portal/delivery | ✅ |
| 03 Solve – giải pháp + MVP gọn | Lớp AI intake + review + adapter; pilot 12 tuần; prototype 1 tuần | ✅ (đã thêm prototype) |
| 04 Scale – khác biệt địa phương | DK intake → SE delivery promise → NO counter mode; lõi chung + adapter/config | ✅ (đã sửa NO bám "store operations") |
| "Where should Company A focus first?" | Đơn B2B nhà thầu, pilot Đan Mạch | ✅ — nên nói câu này thẳng ở slide 2 |
| Local processes, existing systems, operational needs, store & distribution ops, change impact, rollout | Có đủ trong mục 3, 6, 7 | ✅ |
| Time to market | Pilot 12 tuần, giữ phạm vi 1 nước/1 ERP/1 kênh | ✅ |
| AI tạo giá trị ở đâu | Extraction, SKU match, (sau) upsell/ETA; human-in-the-loop | ✅ |
| Được tự giả định, phải nêu rõ | Đánh dấu [A]/[V], bảng 3 kịch bản | ✅ |
| Max 10 slide, PDF, tiếng Anh, hạn 22h 26/10 | Dàn ý 10 slide | ✅ |

## 4. Đã sửa gì để tránh lạc đề
1. **Nói quá phạm vi** → định vị lại thành MỘT vấn đề gốc có lợi ích lan tỏa.
2. **Thiếu lý giải bỏ qua B2C** → thêm lập luận (giả định).
3. **Na Uy bị kéo sang e-invoicing** (ngoài đề) → quay về "store operations" (counter mode chuẩn hóa quy trình quầy); e-invoicing chỉ là ghi chú phụ.
4. **MVP chỉ ở góc độ khách hàng** → thêm "prototype vòng 2" team build được trong 1 tuần, thiết kế module để đón change request vòng 3.
5. **Thiếu góc nhìn Netcompany** → thêm reuse-first, incremental, sovereignty, responsible AI.

## 5. Lời khuyên thực tế
- **Viết lại slide bằng lời của team** — tài liệu hiện tại do AI soạn; FAQ ghi rõ giám khảo đánh giá việc team tự sở hữu nội dung. Giữ ghi chép quá trình dùng AI ngay từ bây giờ cho AI Journal.
- Chuẩn bị sớm cho vòng 2: chọn stack, dựng catalogue + đơn mẫu ngay sau 26/10 (vòng 2 chỉ có 7 ngày).
- Đoán trước change request vòng 3 (VD: thêm nước, thêm ảnh/điện thoại, thêm khung giờ giao, đổi ưu tiên sang B2C) → kiến trúc module.
- Kiểm tra email của tất cả thành viên — tiêu chí và template được gửi qua email.

## 6. Độ tin cậy & khoảng trống
- **Cao (nguồn chính thức, đã tự kiểm tra):** format, timeline, giải thưởng, quy định AI.
- **Trung bình:** chiến lược AI/Feniks của Netcompany (báo cáo Q1/2026 qua bản sao, báo chí).
- **Không tìm thấy:** đề, bài thắng, nhận xét giám khảo các mùa 2024–2025; trọng số chấm điểm.

## Nguồn
- Chính thức: https://itconsultantchallenge.org/en · https://itconsultantchallenge.org/en/faq
- Netcompany Q1 2026 (bản sao): https://www.placera.se/pressmeddelanden/netcompany-netcompany-interim-report-for-the-three-months-ended-31-march-2026-20260506
- Feniks AI: https://diginomica.com/node/30987
- Platforms/“Reuse, not Reinvent”: G-Cloud service definition (UK Digital Marketplace)
- Tuyển dụng Netcompany VN: https://topdev.vn/viec-lam/talented-it-graduates-netcompany-2029231
