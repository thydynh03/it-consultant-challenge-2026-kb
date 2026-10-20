# OrderFlow – Pitch deck nội bộ (để thống nhất với team)

> **Mục đích:** chốt câu chuyện và nội dung 10 slide với team *trước khi* dựng slide nộp.
> Mỗi slide có: **Tiêu đề (EN)** · **Nội dung trên slide (EN)** · **Nói gì (VN)**.
> Ký hiệu: **[A]** = giả định của team · **[V]** = số liệu vendor tự công bố.
> Hạn nộp Round 1: **22:00, 26/10/2026** · PDF · tối đa 10 slide · tiếng Anh. Slide nộp phải do team tự viết lại bằng lời của mình (FAQ cuộc thi).

---

## Câu chuyện trong 30 giây

Company A nên **tập trung trước vào Manual processes – cụ thể là khâu nhận đơn của nhà thầu (B2B)**. Hôm nay đơn đến qua email, điện thoại, PDF; nhân viên gõ lại tay vào ERP và hứa ngày giao không kiểm tồn. **OrderFlow** là một lớp AI mỏng đặt *trước* ERP hiện có: đọc đơn, khớp mã hàng, kiểm tồn, nhân viên duyệt trên một màn hình. **Cửa hàng pilot dùng được từ tuần 6, không cần sửa ERP.** Kịch bản cơ sở trả lại **≈55 FTE** thời gian cho bán hàng. Cùng một lõi được triển khai khác nhau ở Thụy Điển và Na Uy.

## Phạm vi – nói rõ để không bị bắt lỗi

| ✅ Trong phạm vi | ❌ Ngoài phạm vi (năm 2, chưa tính chi phí) |
|---|---|
| AI đọc đơn email/PDF/ảnh, khớp SKU | Live GPS tracking, khung giờ giao |
| Kiểm tồn Store + DC → ngày giao đáng tin | App tài xế, TMS, tối ưu tuyến |
| Màn hình duyệt (human-in-the-loop) | Portal/app tự đặt hàng cho nhà thầu |
| Adapter cho ERP từng nước | Thay hay hợp nhất ERP |
| Tin nhắn xác nhận + trạng thái tự động từ sự kiện ERP | AI gợi ý mua kèm, dự báo giao trễ |

---

## Slide 1 – Cover

**Tiêu đề:** One order flow. Three markets.
**Trên slide:** Fixing Company A’s contractor order handling with an AI order layer on top of the systems each country already runs. · Team ‹name› · ‹Member 1–3› · 26 October 2026
**Nói gì:** Mở bằng câu trả lời luôn: "Company A nên bắt đầu từ khâu nhận đơn của nhà thầu."

## Slide 2 – Executive summary

**Tiêu đề:** Start where three problems meet: contractor order intake
**Trên slide:**
| | |
|---|---|
| **We prioritise** | **Manual processes** in contractor (B2B) order handling |
| Why this | Orders arrive by email, phone and PDF, are re-typed by staff and promised without a stock check – where manual work, store inconsistency and late deliveries begin |
| Solution | **OrderFlow**: AI reads orders, matches products, checks store + DC stock; staff approve in one screen; posts to each country’s ERP |
| MVP | 12-week pilot, 5–10 Danish stores, email only – **first stores live in week 6, no ERP change** |
| Impact | ≈55 FTE-equivalents freed (base case [A]); faster, reliable confirmations |
| Decision | Fund the pilot (DKK 3.5–6m [A]); go/no-go at month 3 |

**Nói gì:** Đây là cả câu chuyện trên 1 slide. Nói thẳng câu "We prioritise Manual processes" để giám khảo thấy ngay ta chọn MỘT.

## Slide 3 – Problem understanding

**Tiêu đề:** Four challenges show up in one contractor order
**Trên slide:** 4 bước của một đơn hàng, mỗi bước gắn với một thách thức (giữ nguyên chữ "may" của đề):
1. **Order arrives** – email, phone, PDF lists, photos → *Fragmented systems*
2. **Re-typed by staff** → *Manual processes – may create the greatest impact in Denmark*
3. **Handled per store** → *Inconsistent operations – may be a more urgent priority in Norway*
4. **Promised & delivered** without a stock check → *Delivery & fulfilment – may have greater business impact in Sweden*

**Root cause:** no shared, structured, stock-aware order layer across three national ERPs.
**Nói gì:** Đây là "triệu chứng của cùng một luồng", nhưng ta chỉ giải **một** vấn đề: Manual processes ở khâu nhận đơn. Các lợi ích khác là lan tỏa, không phải mục tiêu chính.

## Slide 4 – Who experiences it

**Tiêu đề:** Contractors wait, staff re-type
**Trên slide:**
- **The contractor:** sends a material list from site, waits, calls “where is my order?”. A late or partial delivery stops the crew.
- **The store counter:** re-types lists into the ERP, guesses stock, calls back – time away from the shop floor.
- **Why B2B first:** larger repeat orders; most free-text manual orders come from trade customers [A]; UK peers (Travis Perkins, STARK UK) already give trade customers two-hour delivery windows.
- **B2C benefit:** every hour not spent re-typing goes back to the shop floor – for DIY customers too.

**Nói gì:** B2B trước là giả định, nói rõ. Gọi Travis Perkins và STARK UK là "UK peers", không phải "competitors".

## Slide 5 – Prioritisation

**Tiêu đề:** Why OrderFlow first
**Trên slide:**
| Option | Impact | Time to market | Feasibility | Reuse 3 markets | Root cause? |
|---|---|---|---|---|---|
| **A. OrderFlow – AI order intake** | High | **Weeks** | Medium-high | High | Yes |
| B. Contractor self-service portal | Medium-high | Slow (adoption) | Medium | High | Partly |
| C. Delivery slots & tracking only | Medium-high | Months (fleet/TMS) | Medium | Medium | Partly – Sweden only |
| D. Store task-management app | Low | Weeks | High | High | No |
| E. Consolidate ERPs | High | Years | Low | High | Yes – too slow |

- *C can run without A, but its value is capped while dates are promised without a stock check – so A first, C later on the same order API.*
- *D is fast but cosmetic. E fixes the root but fails time-to-market.*

**Nói gì:** A là phương án duy nhất vừa nhanh (vài tuần) vừa đánh vào gốc. Có thêm hàng E để chứng tỏ team đã cân nhắc phương án "thay ERP".

## Slide 6 – Solution

**Tiêu đề:** OrderFlow: AI does the typing, staff decide
**Trên slide (5 bước):**
1. **Read the order** (AI) – email, PDF or photo → items, quantities, site, date
2. **Match products** (AI) – trade slang → SKU, using catalogue and purchase history
3. **Check stock** (rules) – store + DC stock → a realistic delivery date; low stock → DC date or manual check
4. **Staff approve** (human) – one screen, low-confidence lines highlighted
5. **Post & confirm** (API) – adapter per country ERP; contractor gets date and automatic status messages

- **No ERP replacement:** a thin layer in front of today’s ERPs – they stay; old order screens can be retired step by step.
- **Built for trust:** EU-hosted models, no training on customer data, confidence scores, human sign-off, audit log.
- *Order extraction is not a high-risk use under the EU AI Act; we keep a human in the loop by design.*

**Nói gì:** AI nằm trong quy trình, không phải chatbot. AI tạo giá trị ở bước 1 và 2. Không có live tracking.

## Slide 7 – MVP scope

**Tiêu đề:** A 12-week, one-country pilot proves value before any rollout
**Trên slide:**
| Week | What | Result |
|---|---|---|
| 1 | ERP integration spike; 500 past orders as test set; check orders/day by store type | Know how orders reach the ERP |
| 2–5 | Order reading + SKU matching + review screen, back-tested offline | Accuracy measured before go-live |
| **6** | **Assistive mode live in 5–10 Danish stores** – staff approve, then enter as today | **Value from week 6, no ERP change** |
| 7–10 | Direct ERP write-back + confirmation with delivery date | No more copy-paste |
| 11–12 | Measure KPIs → **Gate 1: go/no-go** | Evidence before funding Sweden/Norway |

**Go/no-go KPIs [A]:** orders approved without edits ≥ 60% · AI line match before review ≥ 95% (back-test) · order errors after review ≤ 50% of baseline · handling time −60% · order → confirmation < 15 min · promised dates kept +10 pp.
**Working prototype (Round 2):** order reading, SKU matching on a sample catalogue, review screen, mock DK/SE/NO adapters (+ ảnh màn hình duyệt đơn).
**Nói gì:** Tuần 6 là câu trả lời cho "time to market". KPI lỗi được back-test trên 500 đơn cũ vì pha chạy thật ngắn. Lưu ý vì sao đo theo dòng: 90%/dòng thì đơn 15 dòng chỉ đúng trọn khoảng 21%.

## Slide 8 – Business impact

**Tiêu đề:** ≈55 FTE of counter time back to customers
**Trên slide:**
- **Công thức:** stores × orders/day × minutes ÷ 60 × 250 days ÷ 1,650 h = staff on order entry → × time saved × share realised = FTE freed.

| Assumption [A] | Low | Base | High |
|---|---|---|---|
| Stores | 300 | 300 | 300 |
| Manual B2B orders / store / day | 15 | 20 | 30 |
| Minutes per order | 6 | 8 | 8 |
| Staff on order entry (FTE) | 68 | 121 | 182 |
| Time saved | 50% | 60% | 60% |
| Share realised | 50% | 75% | 100% |
| **FTE freed** | **17** | **≈55** | **109** |
| Capacity value / year (DKK) | 7m | 23m | 49m |

- **Value → cash (base):** capacity DKK 23m → cash-realisable ≈5.8m [A] (fewer temps, overtime, no backfill – agreed with employee reps) → run cost −2.2m [A] → **net ≈ DKK 3.6m a year**.
- Not counted: retaining contractors through faster, reliable confirmations – baselined in the pilot.
- Vendor benchmarks [V] (adjacent sectors): OIKI (IBM) 30 → 12 min/order; Topa (Lleverage) “+90% automated”.

**Nói gì:** Không nói "tiết kiệm 23 triệu" như tiền thật. 23m là giá trị năng lực, còn tiền mặt ròng khoảng 3,6m mỗi năm. Hoàn vốn tiền mặt cho MVP khoảng 15 tháng, cho cả chương trình khoảng 3 năm. Đó là lý do cần Gate 1.

## Slide 9 – Scale

**Tiêu đề:** One core, rolled out three ways
**Trên slide:**
| Months | Market | Pain | What we add |
|---|---|---|---|
| 0–6 | 🇩🇰 Denmark | Manual processes | Pilot → all stores; add photo and phone-note channels |
| 5–9 | 🇸🇪 Sweden | Delivery & fulfilment | Swedish ERP adapter + delivery date checked against store and DC stock + automatic status messages from ERP events |
| 8–12 | 🇳🇴 Norway | Store operations | Norwegian ERP adapter + **Counter mode**: the same review screen for walk-in and phone orders, so every store captures, checks and confirms orders the same way |

**Across all three markets:** shared once (AI core, order API, review screen, data model) · local per country (ERP adapter, language and product terms, delivery-date rules) · people first (employee reps consulted before each wave; store champions).
**Footer:** Gate 1 (month 3) before funding SE/NO adapters · Live GPS tracking and time slots: year-2 option, not costed.
**Nói gì:** Cùng một giải pháp, mỗi nước triển khai khác nhau, đúng yêu cầu của board. Thụy Điển chỉ nhận ngày giao đã kiểm tồn và tin nhắn trạng thái; **không** có tracking xe. Ghi chú phụ: đơn có cấu trúc giúp Na Uy đáp ứng e-invoicing B2B từ 01/2027.

## Slide 10 – Risks & next steps

**Tiêu đề:** Five risks, each with a week-1 test or a fallback
**Trên slide:**
| Risk | Likelihood / Impact | Mitigation |
|---|---|---|
| ERP has no usable order API | Medium / High | Week-1 spike; assistive mode needs no ERP change; file/EDI fallback |
| AI mismatches trade slang | Medium / Medium | Human review, confidence thresholds, back-test on 500 real orders |
| Stock data not accurate | High / Medium | Low-stock lines get a DC date or manual check; one-click mismatch flag triggers a cycle count |
| Staff or union resistance | Medium / High | Co-design with pilot stores; assistive tool; no headcount cuts |
| Data protection concerns | Low / High | EU hosting, data processing agreement, no training on customer data |

**Decision needed:** fund a 12-week pilot in 5–10 Danish stores (DKK 3.5–6m [A]) and nominate pilot stores and employee representatives.
**Nói gì:** Kết bằng lời đề nghị cụ thể. Nói thật là chưa có benchmark độc lập của ngành builders' merchant; chính pilot sẽ tạo ra số liệu đó.

---

## Q&A dự kiến (luyện trước)

| Câu hỏi | Trả lời gợi ý |
|---|---|
| Đề nói Thụy Điển có thể có business impact lớn nhất, sao không bắt đầu ở đó? | Giao trễ bắt đầu từ lời hứa không kiểm tồn ở khâu nhận đơn. Ta sửa khâu đó ở nơi khối lượng thủ công cao nhất, rồi tái dùng lõi ở Thụy Điển từ tháng 5. |
| Sao không làm tracking giao hàng như các merchant ở Anh? | Đó là một hệ thống khác (đội xe, TMS, app tài xế), lâu và tốn hơn. Ta để nó ở năm 2, chạy trên cùng Order API. |
| 23 triệu DKK có phải tiền thật không? | Không. Đó là giá trị năng lực (≈55 FTE). Tiền mặt ròng khoảng 3,6m/năm [A]. Phần còn lại là thời gian quay lại phục vụ khách. |
| Nếu ERP không có API thì sao? | Assistive mode chạy được từ tuần 6 mà không cần đụng ERP. Tuần 1 làm spike; nếu không có API thì dùng file hoặc EDI. |
| AI sai thì sao? | Nhân viên luôn duyệt trước khi đơn vào ERP. Dòng AI không chắc được tô vàng. KPI đo theo dòng và đã back-test. |
| Có cắt giảm nhân sự không? | Không. Thời gian được trả lại cho tư vấn bán hàng; đại diện người lao động được tham vấn trước mỗi đợt triển khai. |

## Đã sửa so với bản PDF nháp

1. Ghi rõ lựa chọn là **Manual processes** (slide 2, 3) và giữ nguyên chữ "may" của đề.
2. **Bỏ live tracking và khung giờ giao khỏi Thụy Điển**, chuyển sang năm 2, chưa tính chi phí (slide 9).
3. Slide 5: sửa mệnh đề "B and C both need A first", thêm phương án E (thay ERP), cột time-to-market ghi bằng thời gian.
4. MVP 2 nấc: **live từ tuần 6** ở assistive mode, thêm Gate 1 (slide 7, 9).
5. KPI: đo độ chính xác theo dòng trước khi duyệt (≥95%), thêm KPI ngày giao được giữ, back-test lỗi (slide 7).
6. Business case: con số chính là **≈55 FTE**; tách giá trị năng lực khỏi tiền mặt ròng (slide 8).
7. Định nghĩa **Counter mode** (slide 9); xử lý rủi ro tồn kho cụ thể hơn (slide 10).
8. "UK peers" thay cho "competitors"; thêm lợi ích cho B2C (slide 4).
9. Gộp 3 hộp dùng chung thành dải "Across all three markets" (slide 9); thêm cột Likelihood / Impact và quyết định cần phê duyệt (slide 10).

## Team cần chốt

- [ ] Tên team và 3 thành viên cho slide 1
- [ ] Đồng ý con số tiền mặt [A]: 5,8m quy ra tiền, 2,2m chi phí vận hành
- [ ] Ai làm ảnh màn hình duyệt đơn (prototype) cho slide 7
- [ ] Phân công: mỗi người tự viết lại 3–4 slide bằng lời của mình
