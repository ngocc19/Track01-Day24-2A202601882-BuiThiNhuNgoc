# Track 1 — Day 24 · AI Product Financial Model Lab
**VinUni AI20k Program**

---

## **Thông Tin Bài Nộp**

| **Thông tin** | **Chi tiết** |
|---|---|
| **Họ và tên** | Bùi Thị Như Ngọc |
| **MSSV** | 2A202601882 |
| **Lớp** | AI20k Track 1 |
| **Tên dự án** | Enterprise AI Sales Enablement Platform |
| **Tên file Excel** | `BuiThiNhuNgoc_Day24.xlsx` |
| **Repo GitHub** | https://github.com/ngocc19/Track01-Day24-2A202601882-BuiThiNhuNgoc |
| **Ngày nộp** | 2026-08-26 |

---

## **00 — Mô hình Kinh doanh**

| **Hạng mục** | **Nội dung** |
|---|---|
| **Dự án** | **Enterprise AI Sales Enablement Platform** — Nền tảng SaaS B2B tự động hóa training, coaching, và performance analytics cho sales teams ở Enterprise. Giúp công ty lớn (500+ sales staff) standardize best practices, rút ngắn ramp-up time từ 6-9 tháng xuống 2-3 tháng, tăng sales productivity 20-30%, giảm turnover 15-20%. |
| **Target Persona (Người trả tiền)** | **Sales VP / Chief Revenue Officer** của công ty Enterprise (1,000+ nhân viên, 500+ sales) tại Việt Nam, chủ yếu trong ngành: CNTT, SaaS, Fintech, Telecom, BPO. **Nỗi đau:** (1) Onboarding dài (6-9 tháng) → chi phí idle 50-100 triệu/sales/tháng; (2) Thiếu consistency training → sales mới underperform 30-40% vs quota; (3) High turnover cost 10-20M/người; (4) **Ngân sách:** Enterprise chi 500-2,000M/năm cho sales training, sẵn sàng allocate nếu ROI clear. |
| **Revenue Model** | **HYBRID (Base Fee + Usage-based Overage).** Base fee 60M VNĐ/tháng cho 100 active users (max 200 concurrent trainers/learners), overage 500k/user/tháng nếu exceed 100 users. Optionally: Analytics add-on 20-30M/tháng. **Lý do HYBRID:** (1) Bảo vệ khỏi Power User trap (customer lớn 500 sales không gây lỗ); (2) Base fee bảo vệ cash flow, usage tạo incentive adopt; (3) Sticky model; (4) Easy expand vào API licensing, white-label. |
| **TAM (Total Addressable Market)** | **650 công ty** tại Việt Nam. **Chuỗi logic:** (1) Total Enterprise companies (1,000+ staff) VN: 3,500-4,500 (Statista 2024); (2) Lọc: ≥500 sales staff = ~1,000 companies (28%); (3) Lọc: ≥500M training budget/năm = ~650 companies (65% của bước 2). **Bottom-up check:** Mỗi company 500 sales, churn 20%/năm = 100 sales mới/năm. Training cost 5-10M/person/năm = 500-1,000M/năm → sẵn sàng chi 60-200M/tháng cho AI platform if ROI proven. |

---

## **Kết Quả Kiểm Tra Mô Hình (5 Gate Rubric)**

> **Lưu ý quan trọng:** toàn bộ số liệu dưới đây được xác minh lại bằng cách tái tạo chính
> xác công thức Excel trong Python và chạy mô phỏng 36 tháng — không phải số ước lượng tay.
> Bản nộp trước có 2 lỗi: (1) file Excel gốc có công thức Tab 2/Tab 3 trỏ sai dòng (do
> script sinh file dùng số dòng cứng thay vì tính động), khiến ARPU/COGS/Churn/CAC bị kéo
> nhầm ô; (2) kịch bản Pessimistic thực ra cạn tiền mặt từ **tháng 3**, không phải tháng
> 18-20 như báo cáo cũ. Cả hai đã được sửa: script sinh Excel viết lại theo row-map động,
> và giả định Fixed Costs/Initial Cash của Pessimistic được điều chỉnh theo đúng thứ tự ưu
> tiên của lab (cắt Fixed Cost trước, tăng Initial Cash sau) để Gate 3 đạt thật.

### **✅ GATE 1: Assumptions Tab — 100% Điền Đủ**

| **Ràng buộc** | **Kết quả** | **Chứng minh** |
|---|---|---|
| 100% ô vàng có số (3 cột) | ✅ PASS | Tab 1 đầy đủ 18 ô nhập liệu (6 sections × 3 scenarios) |
| Hidden Costs ≥ 30% API Cost | ✅ PASS | Opt 93.3%, Base 100%, Pess 118.2% |
| Pess Churn ≥ 1.5x Base | ✅ PASS | 2.25% ÷ 1.5% = 1.50x (exact) |
| Pess CAC ≥ 1.5x Base | ✅ PASS | 225M ÷ 150M = 1.50x (exact) |

**Bóc tách AI Hidden Costs (Base scenario):**
- Data Labeling & QA: 1.3M/khách/tháng (sales training data labeling, feedback loop)
- Model Retraining: 1.2M/khách/tháng (monthly fine-tuning per customer cohort, ~20%/năm build cost)
- Human-in-the-loop QA: 1.0M/khách/tháng (AI coaching output review by sales trainers)
- Compliance & Security: 0.5M/khách/tháng (PDPA audit, data residency VN, SOC 2, encryption)
- **Tổng: 4.0M/khách/tháng = 100% API Cost 4M** ✅

---

### **✅ GATE 2: Unit Economics Tab — HEALTHY**

| **Chỉ số** | **Optimistic** | **Base** | **Pessimistic** | **Ngưỡng** | **Kết quả** |
|---|---|---|---|---|---|
| ARPU (M/tháng) | 100 | 80 | 50 | — | ✅ Base 80M (benchmark Salesforce Enterprise 50-150M) |
| Gross Margin % | 92.7% | 87.5% | 71% | ≥ 50–60% | ✅ ALL PASS |
| LTV (M/khách) | 9,270 | 4,667 | 1,577 | — | ✅ Tính trên Gross Margin |
| CAC (M/khách) | 120 | 150 | 225 | — | ✅ Enterprise 6-9 month sales cycle |
| **LTV / CAC** | **77.3x** | **31.1x** | **7.0x** | **> 3.0** | ✅ **Base 31.1x > 3.0 PASS** |
| **CAC Payback** | **1.29 tháng** | **2.14 tháng** | **6.34 tháng** | **< 12 tháng** | ✅ **Base 2.14 < 12 PASS** |
| **Status** | HEALTHY | **HEALTHY** | HEALTHY | — | ✅ **GATE 2 PASS** |

**Công thức tính LTV (chính xác):**
```
LTV = Gross Profit/khách/tháng × (1/Churn Rate)
    = (ARPU - COGS) × (1/Churn)
    = (80M - 10M) × (1/0.015)
    = 70M × 66.67
    = 4,667M VNĐ
```

---

### **✅ GATE 3: Stress-Test P&L & ROI — 36 Tháng**

(Số liệu dưới đây tái tạo chính xác công thức Tab 3: `New customers/tháng = TAM × Adoption`,
`Net CF = Gross Profit − S&M − Fixed Cost`, `Cash Positionₜ = Cash Positionₜ₋₁ + Net CFₜ`,
`NPV = NetCF₀ + NPV(lãi suất tháng, NetCF₁..₃₆)` với lãi suất tháng `= (1+lãi suất năm)^(1/12) − 1`.)

#### **Base Scenario KPI:**

| **Chỉ số** | **Giá trị** | **Ngưỡng** | **Kết quả** |
|---|---|---|---|
| **NPV 36 tháng** (Discount 25%/năm) | **8,537M VNĐ** | > 0 | ✅ **PASS** |
| **IRR (annualized)** | **134.3%/năm** | ≥ 20%/năm | ✅ **PASS** |
| **Break-even Month** | Tháng 9 | — | ✅ (Net CF dương lần đầu) |
| **Project Payback** | Tháng 20 | < 24 tháng | ✅ **PASS** |
| **Cash Position Month 12** | **+1,626M** | Không âm | ✅ **PASS** (dương suốt 36 tháng) |

**Dòng tiền Base Scenario (Adoption 0.15%/tháng × TAM 650 = 0.975 khách mới/tháng, Fixed Cost 430M/tháng):**

| **Month** | **Customers (cuối kỳ)** | **Revenue** | **Gross Profit** | **S&M** | **Fixed Cost** | **Net CF** | **Cash Position** |
|---|---|---|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 | 430M | -1,500M | +3,500M |
| 1 | 0.97 | 78M | 68M | 146M | 430M | -508M | +2,992M |
| 6 | 5.63 | 451M | 394M | 146M | 430M | -182M | +1,441M |
| 9 | 8.27 | 661M | 579M | 146M | 430M | +2M | +1,265M |
| 12 | 10.78 | 863M | 755M | 146M | 430M | +178M | **+1,626M** |
| 18 | 15.48 | 1,239M | 1,084M | 146M | 430M | +508M | +3,863M |
| 24 | 19.77 | 1,582M | 1,384M | 146M | 430M | +808M | +7,973M |
| 36 | 27.28 | 2,182M | 1,909M | 146M | 430M | +1,333M | +21,176M |

Base scenario không cần bridge funding: dòng tiền dương ngay từ Month 0 (buffer 3.500M) và tiếp tục dương suốt 36 tháng.

---

#### **Pessimistic Scenario — Runway:**

Kịch bản xấu nhất bị siết đồng thời 2 shock bắt buộc (Churn 2.25% = 1.5× Base, CAC 225M =
1.5× Base) **và** ARPU giảm còn 50M — với Fixed Cost và Initial Cash giữ nguyên như Base
(430M/tháng, 3.000M), mô hình **cạn tiền ngay từ tháng 3** (thất bại Gate 3). Để đạt gate mà
không nới lỏng 2 shock bắt buộc, đã áp dụng đúng thứ tự remedy của lab:

1. **Cắt Fixed Cost 42%** (430M → 250M/tháng): giữ Founder + 1 AE + 1 Eng + PM (150-170M),
   văn phòng chuyển remote-only (70M → 50M), Marketing cắt 50% (60M → 30M).
2. **Tăng Initial Cash lên 5.000M** (bằng Base): đây là số tiền đã huy động ở Month 0, không
   phụ thuộc vào kịch bản tương lai nào xảy ra — hợp lý hơn để 3 cột dùng cùng mức vốn ban đầu.

| **Checkpoint** | **Kết quả** | **Ngưỡng** | **Trạng thái** |
|---|---|---|---|
| **Cash Position thấp nhất, Month 0-12** | **+423.5M** | Không âm | ✅ **PASS** |
| **Runway** (tháng đầu tiên Cash Position âm) | **Tháng 15** | ≥ 12 tháng | ✅ **PASS** |
| NPV 36 tháng | -4,581M | (không yêu cầu > 0 cho Pessimistic) | — |
| Cash Position Month 36 | -109M | — | ⚠️ Cần funding bổ sung trước Month 15 |

**Dòng tiền Pessimistic (FC 250M/tháng, Initial Cash 5.000M):**

| **Month** | **Customers** | **Net CF** | **Cash Position** |
|---|---|---|---|
| 0 | 0 | -1,500M | +3,500M |
| 6 | 2.95 | -262M | +1,671M |
| 12 | 5.52 | -171M | **+424M** |
| 14 | 6.31 | -143M | +124M |
| 15 | 6.68 | -130M | **-6M** ⚠️ (runway hết ở đây) |
| 27 | 10.61 | +10M | -620M (Net CF quay lại dương lần đầu) |
| 36 | 12.92 | +92M | -109M |

**Kết luận trung thực:** Pessimistic đạt Gate 3 (không âm trước Month 12, runway 15 tháng
≥ 12), nhưng đây là runway "vừa đủ", không phải dư dả — công ty cần chốt Series A hoặc bridge
funding **trước Month 14-15** để không rơi vào âm tiền kéo dài, vì hoạt động chỉ tự hoà vốn
dòng tiền trở lại từ Month 27.

---

### **✅ GATE 4: Decision Note**

#### **Đoạn 1 — Lý do chọn ARPU & CAC (Bảo vệ các con số)**

Mô hình định giá ARPU 80 triệu VNĐ/tháng (base fee 60M + overage 20M trung bình) dựa trên benchmark thực tế: Salesforce Einstein Enterprise 50-150M/tháng, HubSpot Sales Pro 60-200M/tháng, Docebo tại Việt Nam 70-150M/tháng. Khách hàng Enterprise (công ty 1,000+ nhân viên) chi sẵn 500-2,000M/năm cho sales training + tools, tương đương 40-170M/tháng per channel. ARPU 80M nằm giữa dải này, phản ánh được willingness-to-pay của personas. CAC 150M/khách phản ánh enterprise sales cycle 6-9 tháng với 2 Account Executives full-time, marketing support, proposal. Tỷ lệ CAC:MRR = 150M ÷ 80M = 1.875x, nằm trong benchmark SaaS Enterprise 1.5-2.5x (healthy). Chúng tôi neo kinh tế khách trên ROI rõ ràng: compress onboarding từ 6 tháng xuống 2-3 tháng = save 200M per sales staff (6 tháng × 30M idle/tháng) × 100+ new hires/năm = ~20 tỷ VNĐ revenue impact, hoàn toàn justify 1-1.5 tỷ initial investment to secure contract.

#### **Đoạn 2 — Bảo vệ AI Hidden Costs (4 phần)**

AI Hidden Costs 4.0M/khách/tháng (bằng 100% API cost 4M) không thể bỏ qua, vì đó là chi phí thực tế phát sinh hàng tháng để maintain product quality. Bóc tách 4 khoản: 
- **Data Labeling (1.3M):** Training data từ sales recordings cần được labeled, validated qua feedback loop hàng tháng. Enterprise domain phức tạp (regulations, jargon), labor-intensive.
- **Model Retraining (1.2M):** Every month, chúng tôi fine-tune LLM để improve accuracy cho specific industry/company. 20%/năm build cost recur = 100+ triệu/customer/năm.
- **Human QA (1.0M):** AI coaches output phải review bởi human sales trainers để ensure brand fit, accuracy, không harmful. Non-negotiable cho Enterprise.
- **Compliance (0.5M):** PDPA audit, Vietnam data residency requirement, SOC 2 certification, encryption maintenance.

**Nếu bỏ qua các chi phí này, Gross Margin sẽ tự động tăng lên 95% (thay vì 87.5%)** — dấu hiệu rõ ràng là model phi thực tế hoặc chất lượng product bị downgrade. Đối thủ sẽ phải bỏ ra chi phí này, nhưng nếu cut corner, product bị fail. Chi phí Hidden Costs cũng là competitive moat: khó competitors bắt chước nếu họ không sẵn sàng invest.

#### **Đoạn 3 — Kết luận Sức khỏe & Plan B**

Base scenario đạt **LTV/CAC 31.1x** (vượt 3.0x ngưỡng), **CAC Payback 2.14 tháng** (dưới 12 tháng), **NPV 8,537M VNĐ**, **IRR 134%/năm** (vượt 20%), **Project Payback 20 tháng** (dưới 24 tháng) — tất cả metrics chứng minh model sức khỏe, dòng tiền dương suốt 36 tháng không cần bridge funding. Pessimistic — nếu mọi giả định xấu xảy ra đồng thời (Churn 2.25%, CAC 225M, ARPU 50M) — đã bao gồm sẵn 2 hành động cắt giảm chi phí (Fixed Cost giảm 42% còn 250M/tháng, giữ Initial Cash ở mức 5.000M bằng Base) để đạt Runway 15 tháng, vượt ngưỡng 12 tháng nhưng không dư dả: dòng tiền chỉ tự cân bằng trở lại từ tháng 27.

**Plan B (hành động bổ sung nếu Pessimistic thực sự xảy ra, ngoài phần cắt chi phí đã đưa sẵn vào giả định):**
1. **Chốt Series A/bridge funding trước Month 14** (mục tiêu 3.000-4.000M VNĐ): vì Runway chỉ vừa đủ 15 tháng và công ty chưa tự hoà vốn dòng tiền cho tới tháng 27, cần vốn bổ sung trước khi cash chạm đáy ở tháng 15.
2. **Tăng Adoption Target 0.08% → 0.15%/tháng** (từ ~0.5 lên ~1 khách/tháng): geographic expansion (Hà Nội + HCMC + Đà Nẵng), partnership với sales training consultants, referral program. Impact: rút ngắn breakeven từ tháng 27 xuống dưới tháng 15.
3. **Tăng ARPU 50M → 70M** (add-on modules: AI coaching certification, API licensing cho consultants, white-label cho partners): impact trực tiếp lên Gross Profit/khách, giảm áp lực lên Fixed Cost đã cắt.

Ba hành động này, kết hợp với phần cắt Fixed Cost đã đưa vào giả định Pessimistic, là điều kiện để biến kịch bản xấu nhất từ "sống sót vừa đủ" (Runway 15 tháng) thành "viable dài hạn".

---

### **✅ GATE 5: Nộp Bài — Đủ File & Tên Repo**

| **Yêu cầu** | **Trạng thái** |
|---|---|
| File Excel 3 Tabs | ✅ `BuiThiNhuNgoc_Day24.xlsx` (Tab 1 Assumptions, Tab 2 Unit Economics, Tab 3 P&L & ROI) |
| File README.md | ✅ Đang nộp (file này) |
| Repo GitHub | ✅ https://github.com/ngocc19/Track01-Day24-2A202601882-BuiThiNhuNgoc |
| Tên repo đúng chuẩn | ✅ `Track01-Day24-2A202601882-BuiThiNhuNgoc` |

---

## **Tự Soi Lỗi Trước Khi Nộp (6 Checkbox)**

- [x] **1. Tab 1 có 100% ô vàng (3 cột)?** ✅ YES — 18/18 ô nhập liệu filled (6 sections × 3 scenarios)
- [x] **2. AI Hidden Costs ≥ 30% API Cost, khác 0?** ✅ YES — Opt 93.3%, Base 100%, Pess 118.2% (bóc tách 4 phần rõ ràng)
- [x] **3. LTV tính trên Gross Margin, không phải Revenue?** ✅ YES — LTV = (ARPU - COGS) × (1/Churn), công thức exact trong Tab 2
- [x] **4. Pess Churn & CAC ≥ 1.5x Base?** ✅ YES — Churn 2.25% ÷ 1.5% = 1.50x; CAC 225M ÷ 150M = 1.50x (đúng 1.5x)
- [x] **5. Base: LTV/CAC > 3.0 & Payback < 12 tháng?** ✅ YES — 31.1x > 3.0 ✅; 2.14 tháng < 12 ✅
- [x] **6. Base NPV > 0, IRR ≥ 20%, Pess Runway ≥ 12 tháng và không âm trước Month 12?** ✅ YES — NPV 8.537M ✅; IRR 134.3%/năm ✅; Payback 20 tháng ✅; Pess min cash Month 0-12 = +423.5M ✅; Pess runway = 15 tháng ✅

**Các lỗi đã phát hiện và sửa khi đối chiếu ngược Excel với README (tự soi bằng cách chạy lại công thức, không chỉ đọc số viết tay):**
- [x] **Lỗi công thức Excel (đã sửa):** bản sinh file trước dùng số dòng hard-code trong `generate_financial_model.py`, khiến Tab 2/Tab 3 trỏ nhầm ô (VD: ARPU trỏ vào dòng tiêu đề section, Total COGS trỏ vào dòng "Model Retraining"). Script đã viết lại theo row-map động — mọi công thức được xác minh lại bằng cách dump toàn bộ formula và đối chiếu tay.
- [x] **Lỗi Pessimistic Runway (đã sửa):** báo cáo cũ ghi "Runway 18-20 tháng" nhưng mô phỏng lại cho thấy với giả định gốc, tiền mặt âm ngay từ tháng 3. Đã cắt Fixed Cost Pessimistic 430M→250M/tháng và nâng Initial Cash Pessimistic lên bằng Base (5.000M) để Runway thực đạt 15 tháng (≥12).
- [x] Marketing budget (Fixed Costs) **không trùng** với S&M/CAC (Sales & Marketing): S&M trong Tab 3 = chỉ New customers × CAC; Marketing Budget trong Tab 1 là chi phí brand/content riêng.
- [x] Adoption 0.15% × TAM 650 = ~1 khách/tháng, **reasonable với 2 AE** (industry standard 0.5-2 deals/AE/tháng).
- [x] Gross Margin Base 87.5% **cao nhưng justified**: Enterprise segment (sticky, high-value), ARPU 80M, COGS chỉ 10M/khách.
- [x] LTV/CAC Base 31.1x **không extreme**: Churn 1.5% = 66.7-tháng lifetime, CAC 150M → 31x reasonable, không phi thực tế như 100x+.

---

## **Hệ Thống Tham Chiếu & Benchmark**

### **ARPU Benchmark (Enterprise Sales Platform, VN 2024)**
- Salesforce Einstein: 50-150M VNĐ/tháng
- HubSpot Sales Enterprise: 60-200M VNĐ/tháng
- Docebo (Learning Platform): 70-150M VNĐ/tháng
- **Chọn 80M Base:** Trung vị segment, phản ánh Enterprise 500+ sales staff chi 60-200M/tháng

### **Churn Rate Benchmark (B2B SaaS, Enterprise)**
- Enterprise SaaS churn: 1-3%/tháng
- AI product churn: 2-5%/tháng (newer category, more churn)
- **Chọn 1.5% Base:** Lower end (sticky product, long-term contracts)

### **CAC Benchmark (Enterprise Sales Cycle)**
- Enterprise deal = 6-9 tháng sales cycle
- 2 AE × 40-50M salary/month + marketing support = 150M CAC typical
- CAC:MRR ratio 1.5-2.5x (healthy Enterprise SaaS)
- **Chọn 150M Base:** Tỷ lệ 1.875x (healthy)

### **AI Hidden Costs Benchmark**
- LLM fine-tuning cost: 20% build cost/năm recur (industry standard)
- Data labeling: 1-2M/customer/tháng (domain-specific)
- Compliance: SOC 2 + PDPA audit 0.5-1M/tháng
- **Total: 30-120% API cost** (highly variable, 100% reasonable for Enterprise)

---

## **Tài Liệu Tham Khảo**

1. **Lab Handbook:** VinUni Day 24 — AI Product Financial Model (provided)
2. **Benchmark Sources:**
   - Gainsight SaaS Metrics Benchmark (2024)
   - Statista Vietnam Enterprise Companies (2024)
   - SaaS Academy CAC/LTV Ratios (2024)
3. **Excel Model:** Generated using openpyxl (Python 3.10+), formula-based (not hardcoded values)

---

## **Hướng Dẫn Sử Dụng File Excel**

### **Tab 1 — Assumptions:**
- **Ô vàng:** Nhập liệu các giả định (chỉ cần fill 18 ô, 6 sections × 3 scenarios)
- **Ô trắng:** Công thức tự động (total COGS, total FC, checks)
- **Kiểm tra:** 3 dòng check ở cuối (Hidden%, Churn ratio, CAC ratio) phải pass threshold

### **Tab 2 — Unit Economics:**
- **Link tự động:** Toàn bộ metrics link sang Tab 1 (không cần copy-paste)
- **LTV công thức:** LTV = Gross Profit × (1/Churn) — **TUYỆT ĐỐI** tính trên Gross Margin
- **Status conditional:** HEALTHY nếu LTV/CAC > 3 AND Payback < 12

### **Tab 3 — P&L & ROI:**
- **Scenario selector (ô B1):** Dropdown chọn Optimistic / Base / Pessimistic
- **36-month projection:** Tự động recalculate khi đổi scenario (Month 0 = đầu tư ban đầu, Month 1-36 = vòng lặp customer/revenue/cash)
- **KPI Summary:** Break-even Month, NPV, IRR (tháng & năm), Project Payback, Min Cash (Month 0-12), Cash tại Month 12, Runway — tất cả formula-based, tham chiếu đúng dải Month 0-36 (3 công thức Break-even/Payback/Runway dùng `INDEX+MATCH(TRUE,...)`, cần bấm **Ctrl+Shift+Enter** nếu mở bằng Excel bản cũ hơn 2021; Excel 365/Google Sheets tự nhận dynamic array)

---

## **Câu Hỏi Thường Gặp**

**Q: Tại sao model chuyển sang Enterprise thay vì SMB?**
A: SMB segment (ARPU 6M, FC 240M) never break-even vì Gross Profit không đủ cover Fixed Costs. Enterprise (ARPU 80M, FC 430M) achieves profitability + strong NPV. Realistic for AI startups: focus enterprise trước (ACV cao, churn thấp, contract dài), rồi expand SMB sau.

**Q: Giá Initial Cash 5 tỷ VNĐ có thực tế không?**
A: Có. Series Seed VN 2024: các case tương tự huy động 4-7B VNĐ cho deep-tech AI platform. Base và Pessimistic dùng cùng mức 5.000M vì đây là số tiền đã huy động ở Month 0 — không phụ thuộc kịch bản tương lai nào xảy ra; Optimistic dùng 4.000M vì ít cần buffer hơn.

**Q: Vì sao Pessimistic Runway chỉ 15 tháng, không phải 18-20 tháng như bản nháp đầu?**
A: Bản nháp đầu tính tay và ước lượng sai. Khi mô phỏng lại đúng công thức (New customers = TAM × Adoption, Cash tích luỹ từng tháng), với Fixed Cost giữ nguyên 430M/tháng như Base, Pessimistic thực ra cạn tiền từ tháng 3 — KHÔNG đạt Gate 3. Để đạt gate mà không nới lỏng shock Churn/CAC 1.5x, đã cắt Fixed Cost Pessimistic xuống 250M/tháng (giảm 42%, mô phỏng đội ngũ tinh gọn khi khủng hoảng) — kết quả Runway thực là 15 tháng, vượt ngưỡng 12 nhưng không dư dả, nên Decision Note khuyến nghị chốt funding bổ sung trước tháng 14.

---

**Document generated:** 2026-08-26  
**Status:** ✅ Ready for submission  
**Gate Checklist:** ✅ 1, ✅ 2, ✅ 3, ✅ 4, ✅ 5 — **ALL PASS**

