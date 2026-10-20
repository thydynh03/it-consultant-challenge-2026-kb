# 🏆 IT CONSULTANT CHALLENGE 2026 — CHAMPIONSHIP STRATEGY

*Tài liệu nội bộ cho team 3 người. Cập nhật: 05/10/2026 (còn 14 ngày đến khi nhận case).*

**Nhãn:** **FACT** = có nguồn chính thức · **INFERENCE** = suy luận chiến lược · **ASSUMPTION** = giả định · **UNKNOWN** = chưa công bố

**Nguồn FACT:** trang chủ `itconsultantchallenge.org/vi` và trang FAQ `itconsultantchallenge.org/vi/faq` (đã đọc trực tiếp ngày 05/10/2026). Mình **không tìm được** recap mùa 2024/2025, danh sách đội thắng trước đây hay bài đăng social của BTC qua tìm kiếm công khai → mọi nhận định về "đội thắng mùa trước" là **UNKNOWN**. Việc cần làm ngay: vào fanpage Code MeLy và Netcompany Vietnam xem tay các recap/video mùa trước (trang chủ có nhúng video Facebook).

---

## 0. ĐIỀU CHỈNH QUAN TRỌNG SO VỚI PROMPT GỐC

1. **Build không phải 24h mà là 7 ngày** (02/11–09/11). **FACT.** Các chiến lược 4h/8h/24h bên dưới được đổi thành "survival slice" trong tuần Build.
2. **Change request nằm ở vòng 3 (16/11–21/11)**, cùng với hoàn thiện và pitching. **FACT** (FAQ). Chỉ có \~5 ngày.
3. **Tiêu chí chấm sẽ được email trước mỗi vòng**, do BTC quyết định. **FACT.** → Bộ trọng số ở Phần 17 chỉ là **ASSUMPTION** và phải thay bằng bản chính thức ngay khi nhận.
4. **Học bổng trên web ghi "Top 200/100/50" nhưng bị dính số thứ tự (01/02/03)** → nhiều khả năng là Top 20 / 10 / 5. **INFERENCE.**
5. **Vòng 1 và 2 hoàn toàn online** (FACT) → chất lượng *tài liệu và sản phẩm tự giải thích được* quan trọng hơn khả năng thuyết phục trực tiếp.

---

## 1. COMPETITION INTELLIGENCE

### 1.1 Dữ kiện chính thức (FACT)

| Hạng mục | Nội dung |
| --- | --- |
| Đơn vị | Code MeLy + Netcompany; đối tác: EngineerPro, DevOi, DuaEdu |
| Đội | 3 thành viên (sinh viên/fresher), có thể đổi thành viên nếu báo BTC |
| Case | **Không công bố trước**, gửi qua email khi Vòng 1 bắt đầu |
| Vòng 1 – Discover / Idea Submission | 19/10–26/10, nộp proposal online. Kết quả 02/11 |
| Vòng 2 – Build / MVP Build-a-thon | 02/11–09/11, nộp MVP online. Kết quả 16/11 |
| Vòng 3 – Deliver / Pitching | 16/11–21/11: xử lý yêu cầu thay đổi, hoàn thiện, thuyết trình. Chung kết 21/11 tại Netcompany TP.HCM hoặc online |
| Số đội đi tiếp | BTC quyết định theo số đội và chất lượng bài |
| AI | Được khuyến khích; phải hiểu, kiểm chứng, chịu trách nhiệm; **nộp AI journal theo mẫu sau Vòng 2**; không nên dùng slide tạo 100% bằng AI |
| Công nghệ | Không giới hạn |
| Open source/template | Được, nếu đúng giấy phép và **nêu rõ phần nào do đội phát triển** |
| Sản phẩm | Không cần hệ thống hoàn chỉnh; cần MVP thể hiện chức năng cốt lõi, giá trị kinh doanh, tính khả thi |
| Sửa bài sau deadline | Không (trừ khi BTC thông báo) |
| Ngôn ngữ | Case, thông tin chính thức, slide bằng tiếng Anh (được cung cấp hoặc chuẩn bị bằng tiếng Anh) |
| Giải | 60 / 30 / 15 triệu VNĐ (e-voucher Got It, chia đều). Học bổng EngineerPro 30%, DuaEdu 50% và 70% |
| IP | Đội giữ quyền sở hữu; BTC được dùng tóm tắt, slide, video demo cho truyền thông |

### 1.2 "Prompt to Production" thực sự kiểm tra gì? (INFERENCE dựa trên mô tả chính thức)

Trang chủ nói Developer ngày nay cần: (1) hiểu nhu cầu kinh doanh, (2) làm việc hiệu quả với AI, (3) đưa ra lựa chọn kỹ thuật có cơ sở, (4) **tự tin giải thích và chịu trách nhiệm** về giải pháp. **FACT.**

→ Cuộc thi **không** chấm "ai code AI giỏi nhất". Nó chấm **judgment**: biết hỏi gì, biết tin gì, biết cắt gì, biết bảo vệ gì. Cụm "prompt" là phương tiện, "production" là *trách nhiệm*.

### 1.3 BTC muốn đội kiểu nào? Developer, Product Builder hay IT Consultant?

**INFERENCE:** Họ muốn **IT Consultant có khả năng build**. Tên cuộc thi, hành trình (tìm hiểu bài toán → thiết kế → xây dựng → điều chỉnh khi yêu cầu đổi → trình bày) và việc Netcompany là công ty tư vấn đều chỉ về một hướng: người dịch nhu cầu khách hàng thành giải pháp kỹ thuật đúng, rồi chịu trách nhiệm. Developer thuần mất điểm ở business; Product thuần mất điểm ở technical decision.

### 1.4 Vì sao nhấn mạnh từng yếu tố? (INFERENCE)

| Yếu tố | Lý do có khả năng cao |
| --- | --- |
| Business understanding | Consultant sai bài toán thì code đúng cũng vô nghĩa |
| AI-assisted dev | AI hạ rào cản code → phần phân biệt chuyển sang judgment |
| Responsible AI | Netcompany làm việc với khách hàng châu Âu/công, nơi compliance quan trọng; trang chủ ghi "giải pháp số có trách nhiệm" (FACT) |
| Technical decision | Mô phỏng việc consultant phải giải thích "vì sao chọn X" với khách |
| MVP | Kiểm tra khả năng cắt scope, không phải build nhiều |
| Change request | Dự án thật luôn đổi yêu cầu; đo khả năng thích ứng kiến trúc |
| Final pitching | Consultant phải bán và bảo vệ giải pháp trước khách |

### 1.5 Ba vòng

|  | **R1 Discover** | **R2 Build** | **R3 Deliver** |
| --- | --- | --- | --- |
| Objective | Được chọn: chứng minh hiểu bài toán và có hướng giải khả thi | Chứng minh ý tưởng chạy được | Được nhớ là đội thắng |
| Deliverable | Proposal (định dạng UNKNOWN, sẽ có email) | MVP + AI journal (FACT: nộp sau R2) | Bản hoàn thiện sau change request, demo, pitch |
| Hidden expectation (INF) | Proposal rõ, ngắn, có assumption và trade-off, không phải bài văn mẫu AI | Scope được cắt có lý do; MVP chạy end-to-end; có dấu vết tư duy | Bình tĩnh trước thay đổi, biết bảo vệ và biết nhận sai |
| Common mistakes (INF) | Giải pháp "mọi case đều dùng được"; chatbot hóa mọi thứ; không có KPI; slide/doc do AI viết giọng chung chung | Build quá rộng, demo vỡ, AI journal viết bù sau, không có evidence | Vá change request kiểu đắp thêm; ôm đồm pitch; không trả lời được "AI sai thì sao" |
| Winning behavior (INF) | Đặt lại vấn đề tốt hơn đề bài, nêu assumption rõ | Một luồng công việc cốt lõi hoàn hảo, có guardrail thấy được | Impact analysis trước khi sửa, giữ phần không đổi, kể chuyện bằng số |
| Tối đa điểm | Bám tiêu chí email; đọc case 3 lần; tự phản biện | Bám tiêu chí; nộp sớm 12h; kiểm thử trên máy sạch | Luyện Q\&A; có plan B cho demo |

---

## 2. JUDGE PSYCHOLOGY (toàn bộ là INFERENCE)

Mô phỏng judge xem 100 proposal, ngày xem 20–30 bài, mỗi bài vài phút.

**Sau 20 proposal đầu, mình loại:** đội không nêu được *ai* chịu đau và *đau bao nhiêu*; proposal mở đầu bằng công nghệ; AI bị thêm vào cho có; không có phạm vi MVP; văn phong giống nhau (AI-generated 100%); tính khả thi phi thực tế trong 1 tuần.

**Sau 20 MVP, mình nhớ đội nào:** đội có **một** workflow chạy trọn từ input đến outcome đo được; có guardrail thấy được trên giao diện; có README/AI journal cho thấy họ *từ chối* một số output AI; có số liệu trước/sau.

**Trong pitch, mình nghĩ "đây là đội thắng" khi:** họ trả lời câu khó mà không phòng thủ; thừa nhận giới hạn trước khi mình hỏi; thay đổi yêu cầu được xử lý trong vài phút, có lý lẽ; cả ba người đều nói được toàn bộ sản phẩm.

### 10 yếu tố khiến đội nổi bật

1. Problem framing sắc, có insight không hiển nhiên
2. Một persona cụ thể, một khoảnh khắc đau cụ thể
3. KPI đo được, có baseline giả định rõ
4. AI có lý do tồn tại (bỏ AI thì giá trị giảm rõ rệt, nhưng vẫn còn quy trình)
5. Human-in-the-loop hiển thị trong UI
6. MVP hẹp nhưng chạy thật
7. Quyết định kỹ thuật có trade-off nêu tên
8. Evidence trong sản phẩm (nguồn, độ tin cậy, audit)
9. Cả ba người bảo vệ được toàn bộ
10. Xử lý thay đổi bằng phân tích, không bằng hoảng loạn

### 10 lỗi khiến đội dễ bị loại

1. Hiểu sai bài toán nhưng build rất đẹp
2. Giải pháp chung chung (chatbot, dashboard) không gắn case
3. AI thêm vào để gây ấn tượng
4. Scope quá rộng, demo không chạy
5. Không có KPI/business value
6. Bỏ qua Responsible AI hoặc chỉ làm một slide
7. Slide/proposal rõ ràng do AI viết (FACT: BTC nói không nên 100% AI)
8. Không phân biệt phần tự làm với phần reuse (FACT: phải nêu rõ)
9. Nộp trễ/sai định dạng (FACT: không sửa sau deadline)
10. Không giải thích được code/quyết định của chính mình

### Judge Decision Matrix

| Factor | Judge wants | Weak team | Strong team | Champion team |
| --- | --- | --- | --- | --- |
| Problem | Hiểu đúng và sâu | Chép lại đề | Chọn đúng vấn đề | Tái định nghĩa vấn đề, nêu assumption và rủi ro hiểu sai |
| Value | Tiền/thời gian/rủi ro tiết kiệm | "Giúp hiệu quả hơn" | Con số ước lượng | Con số + cơ sở + cách đo trong demo |
| AI | Cần thiết và kiểm soát được | AI trang trí | AI giải quyết bước khó | AI + evidence + confidence + human approval + fallback |
| MVP | Chạy được, đúng trọng tâm | Nhiều tính năng dở | Luồng chính ổn | Luồng chính + một edge case + chứng minh bằng test |
| Tech | Lựa chọn có lý do | Stack thời thượng | Kiến trúc hợp lý | Quyết định + phương án bị loại + chi phí + đường mở rộng |
| Responsible AI | Có trong sản phẩm | Slide | Có checklist | Hiện trong demo: nguồn, tin cậy, duyệt, audit, chống injection |
| Change | Thích ứng | Sửa vội, vỡ chỗ khác | Sửa được | Impact analysis, regression test, giữ nguyên phần cốt lõi |
| Pitch | Rõ, thuyết phục | Đọc slide | Mạch lạc | Kể chuyện bằng số, Q&A thẳng thắn |

---

## 3. CHAMPION DNA (INFERENCE)

Chín mục trong prompt đều cần đạt chuẩn, nhưng **chênh lệch Good → Great → Champion nằm ở:**

| Mức | Dấu hiệu |
| --- | --- |
| **Good** | Hiểu đề, MVP chạy, slide ổn |
| **Great** | Thêm: business value định lượng, kiến trúc có lý do, AI có kiểm soát |
| **Champion** | Thêm: **(a)** độ chính xác của problem framing, **(b)** guardrail nằm trong sản phẩm thay vì slide, **(c)** bằng chứng tư duy (decision log, AI journal, test), **(d)** xử lý change request như cơ hội, **(e)** cả đội cùng bảo vệ được mọi thứ |

| Nhóm | Checklist DNA |
| --- | --- |
| Business | Problem framing, hiểu khách hàng, giá trị, ROI giả định có cơ sở, khả thi, mở rộng |
| Product | UX phục vụ một user journey, MVP scope gọn, khác biệt rõ |
| Technology | Kiến trúc đơn giản đủ dùng, AI đúng chỗ, dữ liệu, bảo mật, độ tin cậy, chi phí, khả năng giải thích |
| Consulting | Phân tích yêu cầu, quản lý assumption, trade-off, risk, stakeholder, change management |
| AI | Human-in-the-loop, validation, chống hallucination, privacy, explainability, minh bạch sử dụng AI |
| Presentation | Story, demo, narrative business, bảo vệ kỹ thuật, Q&A |

**Yếu tố tạo khác biệt nhất (INFERENCE):** *giải thích được tại sao* mọi thứ tồn tại. Đội thường thua không phải vì thiếu tính năng mà vì không bảo vệ được lựa chọn.

---

## 4. CASE STUDY RESPONSE FRAMEWORK

Quy trình: **CASE → DISCOVERY → PROBLEM → USER → ROOT CAUSE → SOLUTION → MVP → AI → ARCHITECTURE → VALUE → PITCH**

Lưu ý: Vòng 1 là 7 ngày (19–26/10). Các mốc dưới đây là *giờ làm việc tập trung đầu tiên*, không phải đồng hồ treo tường. **ASSUMPTION:** đội làm song song với học tập.

**First 30 phút — Hiểu**

- Mỗi người đọc case độc lập, không dùng AI, gạch chân: ai, đau gì, ràng buộc, thuật ngữ lạ
- Mỗi người viết 5 dòng "case này thực chất là về gì"
- Đối chiếu 3 bản, ghi chỗ lệch → đây là chỗ cần hỏi/giả định
- Đọc email để lấy tiêu chí chấm và định dạng nộp; ghi deadline

**First 60 phút — Đóng khung**

- Chốt problem statement 1 câu, 1 persona chính, 1 pain chính
- Liệt kê assumption và UNKNOWN; gửi câu hỏi làm rõ cho BTC nếu có kênh (kiểm tra email)
- Dùng Case Breakdown Engine (Phần 5) để có bản nháp, rồi **team phản biện**

**First 2 giờ — Chọn hướng**

- 3 hướng giải pháp, chấm theo ma trận (Phần 7), chọn 1
- Root cause: vẽ cây 5-why
- Quyết định "AI làm gì / người làm gì"

**First 4 giờ — Khóa thiết kế**

- MVP scope (Must/Should/Nice/Never), KPI, kiến trúc 1 trang, risk register, demo scenario nháp
- **Chưa mở IDE** để build sản phẩm, chỉ có thể làm spike kỹ thuật nhỏ kiểm chứng rủi ro lớn nhất

**Final review (trước nộp)**

- Red Team 60 phút, đọc to proposal, kiểm tra tiêu chí email từng dòng, đối chiếu AI journal, kiểm tra định dạng/dung lượng/link, nộp sớm ≥ 6–12h

---

## 5. CASE BREAKDOWN ENGINE (prompt dán vào AI)

> **Cách dùng:** dán case vào chỗ `[CASE]`. Chạy ở 1–2 mô hình, sau đó team tự chỉnh. Không nộp nguyên văn AI.

```
Bạn là IT Consultant + Product Strategist + Solution Architect + Judge.
Dưới đây là case study của một cuộc thi tư vấn CNTT. Đừng bịa dữ kiện.
Mọi chi tiết không có trong case phải gắn nhãn [ASSUMPTION] hoặc [UNKNOWN].

[CASE]

Hãy trả về 23 mục:
1 Executive summary (5 dòng) 2 Business problem 3 Personas (tối đa 3, chọn 1 chính)
4 Pain points (kèm mức độ nghiêm trọng) 5 Current process (as-is)
6 Root causes (5-why) 7 Jobs-to-be-done 8 Functional requirements
9 Non-functional requirements 10 Constraints 11 Assumptions
12 Risks (xác suất x tác động) 13 Opportunity areas 14 AI opportunities
15 AI risks 16 MVP scope (Must/Should/Nice/Never) 17 Future scope
18 KPIs (baseline giả định + cách đo) 19 Business impact
20 Architecture (text diagram) 21 Tech stack (kèm 1 phương án bị loại và lý do)
22 Demo scenario (Before-Trigger-AI-Decision-Human-Action-Result-Proof)
23 Pitch storyline (13 ý)

Sau đó, tự phản biện, trả lời thẳng thắn từng câu:
A. Nếu tôi là khách hàng, tại sao tôi phải trả tiền?
B. Bỏ AI đi thì sản phẩm còn giá trị không? Phần nào mất?
C. AI thực sự giải quyết vấn đề hay chỉ để gây ấn tượng?
D. Có khả thi trong 7 ngày với 3 sinh viên không? Cắt gì?
E. Phần nào của case tôi có thể đã hiểu sai?
F. Cho 3 giải pháp thay thế khác biệt hẳn, và vì sao không chọn.
Kết thúc bằng danh sách "việc phải xác minh với con người".
```

**Quy tắc team:** AI cho bản nháp, team gạch bỏ ít nhất 30% và viết lại phần problem framing bằng lời của mình. Ghi lại vào AI journal.

---

## 6. WINNING SOLUTION PATTERNS (INFERENCE; điểm /10 là chủ quan)

Điểm = khả năng thành bài mạnh trong format *case thực tế + AI + MVP 7 ngày*.

| # | Pattern | Giải quyết | Judge thích | Dễ hỏng | MVP | Demo | Responsible AI | Điểm |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | **AI Decision Support** (gợi ý + bằng chứng) | Quyết định chậm/không nhất quán | Có HITL tự nhiên | Gợi ý không có evidence | Trung bình | Cao | Evidence, confidence, duyệt | **9** |
| 2 | **Document Intelligence** (trích xuất, phân loại, đối chiếu) | Khối lượng văn bản thủ công | Value đo được, dễ chứng minh | OCR/format hỗn loạn | Trung bình | Cao | PII, sai trích xuất | **8.5** |
| 3 | **Intelligent Triage** (phân loại + định tuyến + SLA) | Quá tải tiếp nhận | KPI rõ (thời gian xử lý) | Phân loại sai ở case biên | Thấp–TB | Cao | Fallback sang người | **8.5** |
| 4 | **Knowledge Assistant / RAG có trích dẫn** | Tri thức phân tán | Dễ hiểu, chống hallucination | Là chatbot "ai cũng làm" | Thấp | TB | Grounding, trích nguồn | 7 |
| 5 | **Human-in-the-loop Workflow Automation** | Quy trình nhiều bước thủ công | Gắn thẳng giá trị | Thiếu khác biệt | TB | Cao | Duyệt, audit | 8 |
| 6 | **Risk/Anomaly Detection** | Phát hiện sớm sai sót | Giá trị cao nếu dữ liệu đúng | Thiếu dữ liệu thật, giả lập yếu | TB–Cao | TB | Giải thích điểm rủi ro | 7 |
| 7 | **Predictive Analytics** | Dự báo nhu cầu/rủi ro | Business impact lớn | Dữ liệu giả → bị bắt bẻ | Cao | TB | Bias, độ tin cậy | 6 |
| 8 | **AI Copilot cho nhân viên tuyến đầu** | Công việc lặp, tri thức nằm trong đầu người | Hợp consulting | Quá giống chatbot | TB | Cao | Duyệt, nguồn | 7.5 |
| 9 | **Recommendation Engine** | Chọn lựa cá nhân hóa | Dễ demo | Cold-start, ít giá trị lõi | TB | Cao | Thiên lệch | 6 |
| 10 | **Process Mining/Optimization** | Điểm nghẽn quy trình | Rất "consultant" | Cần log dữ liệu | Cao | TB | Ít rủi ro AI | 6.5 |
| 11 | **Multi-agent Workflow** | Nhiệm vụ nhiều bước | Gây ấn tượng | Dễ phức tạp, khó kiểm soát | Cao | Cao | Phạm vi, audit | 5.5 |
| 12 | **Compliance/Policy Checker** | Đối chiếu quy định | Hợp bối cảnh châu Âu/doanh nghiệp | Quy tắc mơ hồ | TB | Cao | Giải thích, nguồn quy định | 8 |
| 13 | **Conversational Intake → Structured Data** | Thu thập thông tin hỗn độn | Giảm lỗi nhập liệu | Dễ thành form có chat | Thấp | TB | PII, xác nhận | 6.5 |
| 14 | **Simulation / What-if cho quyết định** | Chọn phương án | Wow cao | Mô hình giả định yếu | Cao | Cao | Minh bạch giả định | 6 |
| 15 | **Copilot + Dashboard KPI sống** | Thiếu đo lường kết quả | Chứng minh impact | Dashboard cho đẹp | Thấp | Cao | Thấp | 6.5 |

**INFERENCE:** pattern 1, 2, 3, 5, 12 thường là nền vững; kết hợp pattern 1 + (2 hoặc 3) + HITL cho độ sâu consulting tốt nhất.

---

## 7. TOP 5 CONCEPTS (generic, chưa có case — đều là ASSUMPTION khi áp vào case thật)

Mỗi concept là *khung* để thích ứng, không phải bài đã chọn.

1. **Evidence-first Decision Copilot:** AI đề xuất quyết định + trích dẫn bằng chứng + confidence → người duyệt → audit trail.
2. **Document-to-Decision Pipeline:** nhận tài liệu, trích xuất, đối chiếu quy tắc, gắn cờ, chuyển người duyệt.
3. **Smart Triage & Routing với SLA:** phân loại, ưu tiên, giao việc, giải thích vì sao.
4. **Compliance Guardian:** đối chiếu hồ sơ với quy định, chỉ ra điều khoản vi phạm có nguồn.
5. **Human-in-the-loop Workflow Orchestrator:** tự động phần dễ, đẩy phần mơ hồ cho người, đo thời gian tiết kiệm.

| Tiêu chí | C1 | C2 | C3 | C4 | C5 |
| --- | --- | --- | --- | --- | --- |
| Business value | 9 | 8 | 8 | 8 | 8 |
| Innovation | 7 | 7 | 6 | 7 | 6 |
| AI relevance | 9 | 9 | 8 | 9 | 7 |
| Feasibility | 8 | 7 | 8 | 7 | 8 |
| MVP feasibility | 8 | 7 | 9 | 7 | 8 |
| UX | 8 | 7 | 8 | 7 | 8 |
| Technical depth | 8 | 8 | 7 | 8 | 7 |
| Responsible AI | 9 | 8 | 8 | 9 | 8 |
| Demo wow | 8 | 8 | 8 | 7 | 8 |
| Scalability | 8 | 8 | 8 | 8 | 8 |
| Pitch potential | 9 | 8 | 8 | 8 | 7 |
| **Overall** | **8.3** | **7.7** | **7.9** | **7.7** | **7.5** |

**TOP 1 (khung): Concept 1, Evidence-first Decision Copilot.** Lý do: HITL, evidence, confidence, audit là Responsible AI *nằm trong luồng sản phẩm*; dễ tạo moment "AI đề xuất → bằng chứng → người duyệt → kết quả đo được"; thích ứng được với nhiều domain. **Cảnh báo:** nếu case không cần quyết định (ví dụ chỉ cần tự động hóa), đừng ép khung này. Case quyết định.

---

## 8. WOW MOMENT ENGINE

Mỗi wow phải mang giá trị kinh doanh.

| # | Khi nào | Thiết kế |
| --- | --- | --- |
| WOW 1 | 30 giây đầu | Hiện **một con số đau thật** (ví dụ "mỗi hồ sơ mất X phút, Y% sai") rồi chạy một ca thật cho thấy trước/sau |
| WOW 2 | Core workflow | Input hỗn độn → hệ thống ra quyết định kèm **evidence được highlight** trong tài liệu gốc |
| WOW 3 | Chứng minh giá trị AI | Chạy side-by-side: có AI vs không AI trên cùng 5 ca, hiện thời gian và độ chính xác |
| WOW 4 | Edge case | Đưa ca mơ hồ/cố tình độc hại (prompt injection, thiếu dữ liệu) → hệ thống **từ chối, hạ confidence, chuyển người** |
| WOW 5 | Trả lời câu khó | Mở sẵn **eval report / audit log / decision log** để trả lời bằng dữ liệu thật, không bằng lời |

---

## 9. RESPONSIBLE AI LAYER (hiện hữu trong MVP)

| Thành phần | Cách làm hiển thị trong demo |
| --- | --- |
| Input validation | Giới hạn loại/kích thước file, schema check, báo lỗi rõ |
| PII protection | Che/mask PII trước khi gửi mô hình; hiện badge "PII masked: n" |
| Prompt injection | Tách dữ liệu và lệnh; lọc nội dung; có một test case tấn công trong bộ demo |
| Grounded generation | Chỉ trả lời từ nguồn đã cho, **trích dẫn bắt buộc**; không nguồn → "không đủ căn cứ" |
| Confidence | Điểm tin cậy + ngưỡng: dưới ngưỡng bắt buộc người duyệt |
| Human approval | Nút Approve/Edit/Reject, ghi lại lý do |
| Audit log | Ai, khi nào, input, output, model/prompt version, quyết định |
| Explainability | "Vì sao" ở 1–2 câu + trích đoạn bằng chứng |
| Fallback | Mô hình lỗi/timeout → quy tắc đơn giản hoặc hàng đợi người |
| Monitoring & cost | Đếm token, chi phí/ca, độ trễ, tỷ lệ bị reject (chỉ số chất lượng) |

**Nguyên tắc:** đặt "Trust panel" bên phải mỗi kết quả AI. Judge nhìn thấy mà không cần bạn nói.

---

## 10. AI OPERATING SYSTEM CHO TEAM

**Nguyên tắc:** AI là *đồng nghiệp bị kiểm chứng*, không phải người ra quyết định (FACT: BTC yêu cầu không thay thế tư duy và trách nhiệm).

| Agent (vai trò prompt) | Dùng khi | Con người kiểm chứng |
| --- | --- | --- |
| Research | Hiểu domain, thuật ngữ, quy định | Đối chiếu ≥2 nguồn, ghi link |
| Product | Requirements, user story | PM của đội gạch bỏ/viết lại |
| Architect | Phương án kiến trúc | Architect phải *giải thích lại không cần AI* |
| Coding | Sinh code | Đọc từng dòng, chạy test, không merge thứ không hiểu |
| QA | Sinh test case | Bổ sung edge case riêng |
| Security | Rà lỗ hổng cơ bản | Kiểm tra thủ công, secrets, injection |
| Responsible AI | Rà rủi ro AI | Đối chiếu với Trust panel thực tế |
| Red Team | Tấn công giải pháp | Team xếp hạng và sửa |
| Pitch | Phản biện kịch bản | **Không** để AI viết slide 100% |
| Judge | Chấm thử theo tiêu chí email | So sánh với điểm tự chấm |

**Workflow:** Research → Analyze → Design → Build → Test → Red Team → Improve → Pitch. Mỗi bước có "cổng" do người ký: *không qua cổng nếu chưa giải thích được bằng lời*.

### AI Journal (mẫu chính thức sẽ do BTC cung cấp sau Vòng 2, FACT; ghi sẵn theo cấu trúc dưới để điền nhanh)

| Ngày | Bước | Công cụ | Prompt (tóm tắt + link) | Output của AI | Cách team kiểm chứng | Quyết định cuối | AI sai ở đâu | Team sửa gì | Người chịu trách nhiệm |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

**Quy tắc:** ghi *ngay khi làm*, không viết bù. Mục "AI sai ở đâu" phải có ≥5 ví dụ thật; đây là bằng chứng mạnh nhất của "hiểu và chịu trách nhiệm".

---

## 11. TEAM OF 3

| Vai trò | Sở hữu | Backup | Quyền quyết định |
| --- | --- | --- | --- |
| **P1 Consultant/Product Lead** | Problem, requirement, KPI, storyline, pitch, tài liệu | Làm QA luồng nghiệp vụ, quản lý AI journal | Scope cuối, thông điệp |
| **P2 Architect/AI Lead** | Kiến trúc, pipeline AI, dữ liệu, bảo mật, Responsible AI, eval | Review code của P3 | Công nghệ, ranh giới AI |
| **P3 Delivery Lead** | MVP, tích hợp, deploy, demo environment, test | Làm UI cho P1, hỗ trợ eval | Cắt tính năng khi trễ, "go/no-go" demo |

**Nhịp làm việc không chặn nhau:**

- **Hợp đồng giao diện sớm:** P2 và P3 chốt API contract/mock trong 4 giờ đầu; P3 build UI trên mock trong khi P2 làm AI
- **Handoff:** P1 → P2/P3: scope + user story có acceptance criteria; P2 → P3: API/schema + prompt version; P3 → P1: bản chạy được để kiểm tra nghiệp vụ
- **Daily:** 15 phút đầu ngày (hôm qua / hôm nay / vướng), 15 phút cuối ngày (demo nhanh)
- **Decision log:** mọi quyết định > 30 phút bàn đều ghi (ai, lý do, phương án loại)
- **Quy tắc chéo:** cả ba phải *tự thuyết trình được toàn bộ* (Q&A thường chọn người bất kỳ)

---

## 12. MVP STRATEGY — *Build less, prove more*

| Nhóm | Nội dung |
| --- | --- |
| **Must prove** | Luồng chính end-to-end; giá trị cốt lõi đo được; 1 guardrail AI hiển thị; 1 KPI trong demo |
| **Should have** | Audit log; confidence + human approval; 1 edge case; dữ liệu giả hợp lý |
| **Nice to have** | Dashboard; đa ngôn ngữ; export |
| **Never build** | Đăng nhập phức tạp (dùng cho đủ); trang quản trị; tích hợp thật không cần thiết; microservices; tối ưu quy mô; hiệu ứng |

**Cắt scope khi trễ:** (1) bỏ Nice → (2) giảm Should về 1 → (3) đơn giản hóa AI (quy tắc + 1 lời gọi mô hình) → (4) cố định dữ liệu demo → (5) **không bao giờ** cắt Trust panel hoặc luồng chính.

**Chiến lược theo thời gian (đã chỉnh cho 7 ngày Build, ASSUMPTION: \~3–5 giờ/ngày/người):**

| Khung | Mục tiêu |
| --- | --- |
| **4-giờ survival** | Một luồng "happy path" chạy trên dữ liệu mẫu, deploy được URL, có 1 màn hình |
| **8-giờ** | + AI pipeline thật + Trust panel (nguồn, confidence, duyệt) + log |
| **24-giờ** | + 1 edge case + eval 10–20 ca + KPI hiển thị + README |
| **Tuần Build** | Ngày 1–2 thiết kế + spike rủi ro; 3–5 build; ngày 6 test/đóng băng; ngày 7 **nộp sớm** (không đợi phút chót) |
| **Final polish** | Đóng băng tính năng 24h trước deadline; chỉ sửa bug, làm demo mượt, quay video dự phòng |

---

## 13. CHANGE REQUEST WAR ROOM (R3, 5 ngày — FACT về thời gian)

**Quy trình:** Change request → Impact analysis → Priority → Risk → Architecture/UX/Data/AI impact → Implementation → Regression test → Demo.

**Chuẩn bị từ Build (INFERENCE):** kiến trúc theo module, cấu hình tách khỏi code, bộ test hồi quy, prompt có version → đổi yêu cầu rẻ.

**Mẫu phản hồi (nói 60–90 giây):**

1. "Chúng tôi hiểu yêu cầu là: …" (diễn đạt lại, xác nhận)
2. "Tác động kinh doanh: …"
3. "Về kỹ thuật thay đổi: …"
4. "Phần giữ nguyên: …"
5. "Đánh đổi: …"
6. "Chúng tôi đề xuất cách này vì …; phương án thay thế là …"

**Bảng impact (điền trong 30 phút đầu khi nhận):**

| Chiều | Câu hỏi |
| --- | --- |
| Business | Đổi mục tiêu hay phạm vi? KPI nào đổi? |
| Architecture | Module nào chạm? Có breaking change? |
| UX | Luồng nào đổi? |
| Data | Schema/dữ liệu mới? |
| AI | Prompt/mô hình/eval có đổi? Rủi ro mới? |
| Risk | Rủi ro regression? |
| Effort | Giờ công, ai làm? |

**Quy tắc vàng:** *phân tích trước, code sau; chạy lại bộ test trước khi demo.*

---

## 14. PITCH (7–10 phút; slide do đội tự viết, FACT: không nên 100% AI)

| # | Slide | Thời lượng | Script gợi ý (điền số thật) |
| --- | --- | --- | --- |
| 1 | Problem | 40s | "Mỗi \[đơn vị\] mất \[X\] và gây \[Y\]. Điều này tốn \[Z\]." |
| 2 | Vì sao giải pháp hiện tại thất bại | 30s | "Hiện nay họ làm \[as-is\]. Nó thất bại vì \[root cause\]." |
| 3 | User | 30s | "Gặp \[tên persona\], khoảnh khắc đau nhất là …" |
| 4 | Insight | 30s | "Điều chưa ai thấy: …" |
| 5 | Solution | 40s | "Chúng tôi xây \[X\] giúp \[user\] làm \[Y\] trong \[Z\]." |
| 6 | Why AI | 30s | "AI làm bước \[khó nhất\]; con người giữ quyết định." |
| 7 | **Live demo** | 3–4 phút | Theo Phần 15 |
| 8 | Business impact | 40s | "KPI: \[A→B\]. Ước tính: \[giả định công khai\]." |
| 9 | Responsible AI | 30s | "Bạn vừa thấy: nguồn, confidence, duyệt, audit. Đây là rủi ro còn lại và cách giảm." |
| 10 | Architecture | 30s | "Một hình. Ba quyết định, và vì sao." |
| 11 | Scalability | 20s | "100x: điểm nghẽn là …; chúng tôi sẽ …" |
| 12 | Future | 20s | "Hai bước tiếp theo." |
| 13 | Closing | 20s | Nhắc lại câu chuyện + 1 con số |

Quy tắc: tối đa 1 slide kiến trúc; không liệt kê tech stack; mỗi người nói ít nhất 2 phần.

---

## 15. DEMO SCRIPT

**Cấu trúc:** Before → Trigger → AI → Decision → Human → Action → Result → Proof

| Bước | Nội dung demo |
| --- | --- |
| Before | Cho thấy user với tình huống khó (dữ liệu thật/giống thật) |
| Trigger | User đưa input |
| AI | Hệ thống phân tích, hiện nguồn |
| Decision | Đề xuất kèm confidence |
| Human | Người duyệt/sửa (có một lần **reject** để cho thấy kiểm soát) |
| Action | Hệ thống thực thi (cập nhật, thông báo) |
| Result | Thời gian/lỗi trước-sau |
| Proof | KPI, eval report, audit log |

| Phiên bản | Gồm |
| --- | --- |
| **3 phút** | Before → Trigger → AI+Decision → Human → Result |
| **5 phút** | + Edge case + Trust panel + KPI |
| **8 phút** | + Change request đã xử lý + Audit/monitoring + Proof |

**Dự phòng (bắt buộc):** video demo quay sẵn; dữ liệu cố định; chế độ offline/mock mô hình nếu API lỗi; một bản chạy local và một bản deploy.

---

## 16. JUDGE Q&A ATTACK

**Cách dùng:** Mỗi câu có "judge muốn kiểm tra" và công thức trả lời Champion. Câu trả lời mẫu dùng ngoặc `[...]` để điền số/thông tin thật của case.

### 16.1 Mười hai câu bắt buộc

| Câu hỏi | Judge kiểm tra | Yếu | **Champion** |
| --- | --- | --- | --- |
| Why AI? | AI có cần thật không | "AI đang hot" | "Bước \[X\] có dữ liệu phi cấu trúc/mơ hồ mà quy tắc không xử lý; chúng tôi đo được AI giảm \[A→B\] trên \[n\] ca. Con người giữ quyết định." |
| Why not normal software? | Khác biệt | "AI thông minh hơn" | "Phần xác định (quy tắc, workflow) vẫn là phần mềm thường. AI chỉ ở \[bước\]. Bỏ AI, vẫn có workflow nhưng mất \[X%\] tốc độ." |
| Why pay? | Giá trị | "Tiết kiệm thời gian" | "Mỗi \[đơn vị\] tiết kiệm \[phút × lương\] = \[số\]/tháng; chi phí vận hành \[số\]; hoàn vốn \[thời gian\] theo giả định \[A,B\] (công khai)." |
| What if AI is wrong? | Kiểm soát rủi ro | "AI ít khi sai" | "Ba lớp: grounding bắt buộc nguồn, confidence dưới ngưỡng → người duyệt, audit để truy vết. Đây là \[tỷ lệ\] sai trong eval; cách chúng tôi xử lý các ca đó: …" |
| Biggest technical risk? | Tự nhận thức | "Không có" | "\[Rủi ro cụ thể\], xác suất \[m\], đã giảm bằng \[cách\], còn lại \[phần\]." |
| Cắt gì nếu còn nửa thời gian? | Ưu tiên | "Cắt UI" | "Giữ luồng chính và Trust panel; cắt \[Nice\], thay \[AI phức tạp\] bằng \[đơn giản\]." |
| 100x người dùng? | Scalability | "Dùng cloud" | "Điểm nghẽn thứ nhất là \[gọi mô hình/DB\]; sẽ \[queue, cache, batch, mô hình nhỏ\]; chi phí/ca đi từ \[a\] đến \[b\]." |
| Bảo vệ dữ liệu thế nào? | Bảo mật | "Mã hóa" | "Tối thiểu hóa dữ liệu; mask PII trước khi gọi mô hình; phân quyền; log không chứa PII; xóa theo chính sách. Phần chưa làm trong MVP: \[..\]." |
| Vì sao kiến trúc này? | Quyết định | "Quen dùng" | "Chọn \[A\] vì \[tiêu chí\]; loại \[B\] vì \[lý do\]; sẽ đổi khi \[điều kiện\]." |
| AI sinh ra gì mà bạn từ chối? | Chịu trách nhiệm | "Không có" | Dẫn **một ví dụ thật** từ AI journal: AI đề xuất \[X\], bị loại vì \[Y\], thay bằng \[Z\]. |
| Phần nào là của team? | Sở hữu | "Cả hai" | "AI viết \[boilerplate\]; team thiết kế \[A, B, C\], viết \[module\], sửa \[lỗi\]. Open source dùng: \[liệt kê, giấy phép\]." |
| Có thêm 1 tháng sẽ làm gì? | Tầm nhìn | "Thêm tính năng" | "Pilot với \[n\] người dùng thật, đo \[KPI\], rồi \[bảo mật/tích hợp\]. Không thêm tính năng trước khi có bằng chứng." |

### 16.2 Bộ câu hỏi bổ sung (≥38 câu để đủ 50; trả lời theo công thức "nêu thẳng giới hạn → bằng chứng → bước tiếp theo")

**Business:** Khách hàng đầu tiên là ai và họ trả bao nhiêu? · KPI nào chứng minh thành công trong 3 tháng? · Giả định nào trong ROI yếu nhất? · Đối thủ/giải pháp hiện có là gì? · Ai trong tổ chức sẽ phản đối? **Product:** Persona chính là ai, vì sao không phải người khác? · Luồng nào bạn cố ý không làm? · Người dùng không tin AI thì sao? · Lúc nào người dùng nên bỏ qua đề xuất của AI? **AI:** Bạn đánh giá chất lượng AI thế nào (tập test, tiêu chí)? · Mô hình nào, vì sao, chi phí/ca? · Prompt injection xử lý ra sao? · Nếu nhà cung cấp mô hình đổi/ngừng? · Làm sao biết không hallucinate? **Architecture:** Điểm lỗi đơn lẻ ở đâu? · Dữ liệu chảy thế nào? · Vì sao không dùng \[công nghệ khác\]? · Làm sao đổi mô hình mà không viết lại? **Security:** Ai truy cập được dữ liệu nào? · Secrets quản lý thế nào? · Lỗi OWASP phổ biến đã kiểm tra chưa? **Cost:** Chi phí/giao dịch? · Điều gì làm hóa đơn tăng đột biến? · Cách giới hạn? **Scalability:** Sau 10x/100x cái gì vỡ đầu tiên? · Đa người thuê (multi-tenant) thế nào? **Data:** Dữ liệu từ đâu, ai sở hữu? · Chất lượng dữ liệu bẩn xử lý sao? · Giữ bao lâu? **Responsible AI:** Thiên lệch ở đâu? · Ai chịu trách nhiệm khi sai? · Người dùng biết khi đang tương tác với AI không? **Feasibility:** Triển khai thật mất mấy tháng, cần ai? · Tích hợp hệ thống hiện hữu thế nào? **Competition strategy:** Điều gì khiến bạn khác các đội còn lại? · Nếu một đội có cùng ý tưởng, bạn thắng ở đâu?

> **Cách luyện:** mỗi người chuẩn bị 10 câu thuộc phạm vi của mình, nhưng thi thử bắt chéo: người khác trả lời.

---

## 17. RED TEAM

| Vai | Tấn công |
| --- | --- |
| Skeptical judge | "Giá trị thật hay chỉ demo đẹp?" |
| CTO | "Kiến trúc có quá phức tạp? Ai bảo trì?" |
| CFO | "Chi phí tổng sở hữu? Hoàn vốn?" |
| Security | "Dữ liệu rò ở đâu? Injection?" |
| End user | "Mất bao nhiêu click? Tôi có tin được kết quả?" |
| Competitor | "Ý tưởng này ai cũng làm, đâu là moat?" |
| PM | "Ai dùng đầu tiên? Đo gì?" |

**Vòng lặp:** Solution → Attack → Fix → Attack → Fix. Dừng khi không còn điểm yếu *làm sụp luận điểm chính*. Ghi kết quả vào decision log. Sai lầm hay gặp cần săn: fake AI value, overengineering, demo phụ thuộc mạng, KPI không có cơ sở, thiếu fallback.

---

## 18. COMPETITOR SIMULATION (archetype, ASSUMPTION)

| Đội | Điểm mạnh | Điểm yếu | Cách thắng |
| --- | --- | --- | --- |
| A Technical monsters | Kiến trúc/độ hoàn thiện | Business nhạt, over-engineering | Làm business value và story rõ hơn; chứng minh "đơn giản đủ dùng" |
| B AI-heavy | Công nghệ AI nặng | Thiếu kiểm soát, khó giải thích | Responsible AI hiển thị, eval, chi phí |
| C Presentation | Kể chuyện hay | MVP mỏng, Q&A yếu | MVP chạy thật + trả lời bằng dữ liệu |
| D Business/Consulting | Phân tích tốt | Sản phẩm yếu | Demo end-to-end sắc nét |
| E Balanced | Cân bằng | Không có điểm nhớ | **Wow có ý nghĩa**: một insight + một moment chứng minh giá trị |

**Chiến lược "khó bị đánh bại":** không có điểm yếu nào bị khoét được (business, kỹ thuật, AI, trình bày) + một điểm nổi bật rõ (insight + evidence).

---

## 19. CHAMPION SCORE

**Quan trọng:** Trọng số chính thức **UNKNOWN** (BTC email trước mỗi vòng, FACT). Dùng thang của bạn làm **ASSUMPTION**, thay ngay khi có bản chính thức.

| Tiêu chí | Trọng số |
| --- | --- |
| Business Value | 20 |
| Problem Understanding | 15 |
| Innovation | 10 |
| AI Quality | 10 |
| Technical Feasibility | 10 |
| MVP Quality | 10 |
| Responsible AI | 10 |
| UX | 5 |
| Demo | 5 |
| Pitch & Q&A | 5 |

**Cách chấm:** mỗi tiêu chí 0–10, nhân trọng số. Chấm bởi cả 3 người độc lập (loại chênh lệch >2 bằng tranh luận), thêm bước "AI Judge" để đối chiếu. **Không thể chấm thật nếu chưa có case** (không bịa điểm). Ngưỡng ≥ 90 = Champion Candidate; nếu \< 90, liệt kê tiêu chí \< 8 và sửa theo thứ tự (trọng số × khoảng cách).

---

## 20. PLAYBOOK TỪNG VÒNG

### R1 — DISCOVER (19–26/10): *Get selected*

Checklist trước khi nộp:

- [ ] Đã đọc kỹ email tiêu chí và định dạng; đáp ứng từng dòng
- [ ] Problem statement 1 câu, persona chính, pain có số liệu/giả định công khai
- [ ] Giải pháp 1 câu + vì sao không chọn hướng khác
- [ ] Giá trị kinh doanh, KPI, baseline giả định
- [ ] Kiến trúc 1 hình, AI role rõ, human-in-the-loop
- [ ] Responsible AI cụ thể (không chỉ liệt kê)
- [ ] Khả thi: phạm vi MVP 7 ngày, rủi ro lớn nhất và cách giảm
- [ ] Assumption/UNKNOWN gắn nhãn
- [ ] Văn phong của đội, không "giọng AI"; ngôn ngữ đúng yêu cầu
- [ ] Red Team đã chạy; đọc to; nộp sớm ≥ 6–12h; kiểm tra file mở được

### R2 — BUILD (02–09/11): *Prove the idea is real*

Chiến lược: scope → kiến trúc → AI pipeline → test → deploy → demo → AI journal. Checklist:

- [ ] Luồng chính end-to-end chạy trên môi trường sạch
- [ ] Trust panel (nguồn, confidence, duyệt, audit)
- [ ] Eval 10–20 ca có kết quả ghi lại
- [ ] Bảo mật cơ bản: không lộ secrets, giới hạn input, mask PII
- [ ] README: cách chạy, kiến trúc, phần tự làm vs reuse (FACT: phải nêu rõ), giấy phép
- [ ] AI journal đầy đủ theo mẫu BTC
- [ ] Video demo dự phòng
- [ ] Nộp sớm; kiểm tra link/quyền truy cập

### R3 — DELIVER (16–21/11): *Make judges remember us*

Change request strategy (Phần 13) · Final polish (đóng băng sớm, chỉ sửa lỗi) · Demo 3/5/8 phút · Pitch (Phần 14) · Q&A (Phần 16) · Backup plan (video, bản local, dữ liệu cố định, người thay thế) · Failure recovery (câu nói: "đây là điều đang xảy ra, đây là phương án dự phòng" — không xin lỗi dài).

---

## 21. LEGAL UNFAIR ADVANTAGES (xếp theo tác động, INFERENCE)

| # | Lợi thế | Vì sao hiệu quả |
| --- | --- | --- |
| 1 | **Problem framing sắc, có assumption** | Đa số đội nhảy vào giải pháp |
| 2 | **Trust panel trong sản phẩm** | Responsible AI hiện hữu thay vì slide |
| 3 | **AI journal thật và trung thực (có chỗ AI sai)** | Chứng minh chịu trách nhiệm (FACT: BTC yêu cầu) |
| 4 | **Eval nhỏ nhưng có số** | Biến "AI tốt" thành bằng chứng |
| 5 | **KPI hiển thị ngay trong demo** | Business value không cần tin lời |
| 6 | **Kiến trúc module để đón change request** | Ghi điểm vòng 3 |
| 7 | **Demo có fallback và video dự phòng** | Không thua vì sự cố |
| 8 | **Nộp sớm, kiểm tra định dạng** | Tránh lỗi không sửa được (FACT) |
| 9 | **Cả ba người bảo vệ được toàn bộ** | Q&A là nơi phân định |
| 10 | **Tiếng Anh tốt** (FACT: là lợi thế) | Case và slide bằng tiếng Anh |

---

## 22. 🏆 THE CHAMPIONSHIP BLUEPRINT

1. **Winning philosophy:** *Hiểu đúng hơn, chứng minh rõ hơn, bảo vệ chắc hơn.* Không thắng bằng tính năng.
2. **Team structure:** P1 Consultant/Product, P2 Architect/AI, P3 Delivery; cả ba bảo vệ được tất cả.
3. **Technology strategy:** đơn giản đủ dùng, module hóa, ưu tiên công nghệ cả đội bảo vệ được; chọn stack theo case (FACT: không giới hạn).
4. **AI strategy:** AI ở bước khó nhất; mọi output có nguồn + confidence; người quyết định.
5. **Responsible AI:** Trust panel + audit + injection test trong demo.
6. **MVP:** một luồng chính hoàn hảo, một edge case, một KPI.
7. **Demo:** Before-Trigger-AI-Decision-Human-Action-Result-Proof; 3 phiên bản; dự phòng.
8. **Pitch:** câu chuyện kinh doanh, không phải tech stack; số liệu có giả định công khai.
9. **Q&A:** thẳng thắn, dẫn dữ liệu, thừa nhận giới hạn.
10. **Change request:** impact analysis trước, giữ phần cốt lõi, nói rõ trade-off.
11. **Risk:** risk register sống; spike rủi ro lớn sớm; Red Team mỗi vòng.
12. **Time management:** thiết kế trước, build sau; đóng băng sớm; nộp sớm.

### 10 điều phải làm

1. Đọc email tiêu chí từng vòng ngay khi nhận
2. Tái định nghĩa vấn đề bằng lời của đội
3. Gắn nhãn assumption/UNKNOWN
4. Cắt scope dũng cảm
5. Hiển thị Responsible AI trong sản phẩm
6. Ghi AI journal ngay khi làm
7. Nêu rõ phần tự làm vs reuse, giấy phép (FACT)
8. Luyện Q&A bắt chéo
9. Có bản dự phòng cho demo
10. Nộp sớm

### 10 điều tuyệt đối không

1. Mở IDE trước khi hiểu bài toán
2. Chatbot hóa mọi thứ
3. Thêm AI chỉ để gây ấn tượng
4. Dùng slide/proposal do AI viết 100% (FACT)
5. Bịa số liệu không nêu giả định
6. Hứa vượt khả năng MVP
7. Dùng code/mẫu không rõ giấy phép hoặc không nêu nguồn
8. Chuẩn bị giải pháp cho một case đoán trước (không công bằng và rủi ro sai hướng)
9. Nộp sát deadline
10. Bỏ qua câu hỏi khó hoặc phòng thủ
11. **Sai lầm lớn nhất có thể mất chức vô địch:** hiểu sai bài toán, hoặc không bảo vệ được một phần của chính sản phẩm (thất bại ở Q&A khi bị hỏi chéo).
12. **Điểm khác biệt mạnh nhất:** *Evidence-first trust:* mọi khẳng định (giá trị, AI, an toàn) đi kèm bằng chứng nhìn thấy được trong demo.

---

## 23. ROADMAP CHUẨN BỊ (hôm nay 05/10 → 21/11)

### 23.1 Điều được phép / không được phép chuẩn bị trước

| Được phép (INFERENCE: an toàn) | Rủi ro vi phạm công bằng/quy tắc |
| --- | --- |
| Template tài liệu, checklist, prompt library tổng quát | Soạn sẵn giải pháp cho một case đoán trước |
| Boilerplate **chung** (auth, DB, logging, RAG skeleton) từ nguồn mở | Dùng code của người khác/đội khác không nêu nguồn |
| Pitch deck skeleton (cấu trúc, không nội dung case) | Slide hoàn chỉnh dựng sẵn rồi chỉ thay chữ |
| Luyện Q&A, mock competition | Nhờ người ngoài làm bài trong thời gian thi |
| Học công cụ, domain tổng quát | Tìm cách lấy case sớm hoặc dùng thông tin nội bộ |

**FACT liên quan:** được dùng thư viện/template mã nguồn mở nếu tuân thủ giấy phép và nêu rõ phần nào do đội phát triển. **UNKNOWN:** BTC có quy định riêng về *việc chuẩn bị boilerplate cá nhân trước ngày thi* hay không → **hành động:** email BTC ([code.mely@gmail.com](mailto:code.mely@gmail.com) / [EB.VN@netcompany.com](mailto:EB.VN@netcompany.com)) hỏi xác nhận bằng văn bản; trong README khai báo rõ phần boilerplate có sẵn.

### 23.2 Lịch

| Giai đoạn | Học | Chuẩn bị | Build trước (generic) | Ritual | Mock |
| --- | --- | --- | --- | --- | --- |
| **05/10 → 19/10** (14 ngày) | Case-framing, Responsible AI, eval cơ bản, tiếng Anh pitch | Starter Kit (bên dưới), email hỏi BTC, kiểm tra email thành viên | Skeleton RAG + auth + log + eval harness (nguồn mở, ghi giấy phép) | Daily 15', decision log, họp vai trò | **Mock 1:** case giả 48h; **Mock 2:** pitch 8 phút + Q&A |
| **19/10 → 26/10 (R1)** | — | Dùng Framework Phần 4–5 | Chỉ spike kỹ thuật cần thiết | Daily + Red Team trước nộp | Nộp sớm |
| **26/10 → 02/11** (chờ kết quả) | Học từ phản hồi (nếu có), kiến trúc cho đề đã chọn | Kế hoạch Build | Sửa starter kit theo bài học | Retro 1 giờ | Mock demo |
| **02/11 → 09/11 (R2)** | — | Theo Phần 12 | Build MVP | Daily + AI journal hằng ngày | Test trên máy sạch |
| **09/11 → 16/11** | Change-request drills | Bộ test hồi quy, khung impact analysis | Cải thiện độ ổn định, eval | Retro, phân vai pitch | **Mock change request** (nhờ người ngoài cho đề giả) |
| **16/11 → 21/11 (R3)** | — | Pitch/Q&A/demo | Đóng băng sớm, video | Luyện 3 lần/ngày | Mock chung kết, đúng thời lượng |

### 23.3 Competition Starter Kit (generic, được phép nếu khai báo)

Prompt library (Breakdown Engine, Red Team, Judge, Security, QA) · Architecture templates (C4 đơn giản) · UI components cơ bản · Auth boilerplate tối giản · DB boilerplate · AI/RAG skeleton có trích dẫn · Logging · Monitoring (token/cost/latency) · Eval harness (tập ca + chấm điểm) · Security checklist · Responsible AI checklist · Test framework · Deploy template · Pitch deck skeleton (cấu trúc 13 mục) · Demo script template · AI Journal template (Phần 10) · Decision log · Risk register · KPI framework.

---

# 🥇 IF WE WANT TO WIN, DO THIS

1. **Hỏi BTC** xác nhận chuẩn bị boilerplate và định dạng trước khi bắt đầu
2. **Đọc email tiêu chí** và đổi trọng số của mình ngay
3. **Dành 4 giờ đầu cho tư duy**, không code
4. **Tái định nghĩa vấn đề** bằng insight của đội
5. **Một luồng chính hoàn hảo** thay vì nhiều tính năng
6. **Trust panel** (nguồn, confidence, duyệt, audit) trong demo
7. **AI journal trung thực**, nêu rõ AI sai ở đâu
8. **Kiến trúc module** để đón change request
9. **Luyện Q&A chéo**: cả ba trả lời được mọi thứ
10. **Nộp sớm và có bản dự phòng**

---

*Phụ lục — Giới hạn của tài liệu:* chưa có case, tiêu chí chấm, định dạng nộp, mẫu AI journal, và dữ liệu mùa trước (UNKNOWN). Tất cả điểm số, danh sách pattern và mô phỏng judge là INFERENCE/ASSUMPTION và cần hiệu chỉnh khi có thông tin chính thức.