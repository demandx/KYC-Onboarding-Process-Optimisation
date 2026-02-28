# KYC-Onboarding-Process-Optimisation
Data-Led Process Re-Engineering | TAT Modelling | FTE Capacity Planning
**Project Overview**
This project applies data-led process re-engineering to a Retail KYC (Know Your Customer) onboarding operation at a bank. The bank was processing 500 new customer applications per day through a 12-step maker checker verification workflow, but was operating at 108% staff utilisation  meaning demand exceeded capacity every single day, creating backlogs and putting the 24-hour SLA at risk.
The project identifies the root causes, quantifies the problem, and designs a To-Be process that eliminates the backlog, stabilises the SLA, and frees up the equivalent of 10 full-time staff — without any new hires.

**Problem Statement**
The KYC process was experiencing:
High end-to-end TAT (approximately 90 minutes)
Team utilisation above 100 percent
Daily backlog formation
SLA breach risk
A data-driven approach was required to stabilise throughput and improve capacity.

**Excel Workbook — Sheet Guide**
1. SIPOC
A structured SIPOC table mapping the entire process from end to end.

Suppliers — Customer, RM, Upload System, APIs
Inputs — PAN, Aadhaar, Address Proof, Photo, Form
Process — All 12 steps, colour-coded by risk level
Outputs — Verified / Rejected / Pending
Customers — Ops, Compliance, Risk, Regulators

2. TAT_AsIs
Step-by-step touch time breakdown for the current process.

Each of the 12 steps with time, owner, and type (manual / API / automated)
Touch Time Total: 53 min | End-to-End TAT: 90 min
Step share analysis identifying Address Verification (10 min, 19% of total) as the bottleneck

3. Capacity_AsIs
FTE capacity model for the current state.

Blue cells = inputs you can change (volume, FTE, productivity)
Black cells = auto-calculated outputs
Shows Workload = 26,500 min/day vs Capacity = 24,480 min/day
Utilisation auto-turns red above 100%, green below
Includes a 7-scenario what-if table varying FTE from 50 to 65

4. TAT_ToBe
Revised touch time model after applying three targeted interventions.

Side-by-side comparison of every step (As-Is vs To-Be)
New T_touch = 45 min | New T_e2e = 75 min
Highlights which steps changed and why

5. Capacity_ToBe
New FTE requirement model after optimisation.

New workload = 22,500 min/day
FTE required drops from 65 → 55
Utilisation normalises to ~92–100%
Before/After impact table built in

6. MI_Dashboard
Management Information dashboard for daily monitoring.

Live KPI cards for both As-Is and To-Be (linked to source sheets)
What-if sensitivity table (FTE 50–65) with auto red/green formatting
SLA Risk Matrix showing threshold vs current vs target status

**Swimlane Diagram**

The HTML file contains an interactive swimlane diagram with two views:
🔴 As-Is View
Five swim lanes: Customer | Ops Analyst | Verification | Risk/Compliance | System
Shows the serial flow, handoffs, queue points, and bottleneck step highlighted in red.
🟢 To-Be View
Same five lanes with three interventions applied and visually marked:

✅ OCR badge on Data Entry
✅ API badge on Address Verification
∥ Parallel badge on PAN + Aadhaar
Full impact comparison table at the bottom

Open the .html file in any browser — no installation needed.

**Key Formulas Used**
Effective Minutes/FTE  (E)  =  Working_Mins × Productivity
                                480 × 0.85 = 408 min

Total Workload         (W)  =  Daily_Volume × T_touch
                                500 × 53 = 26,500 min

Available Capacity     (C)  =  FTE × E
                                60 × 408 = 24,480 min

Utilisation            (U)  =  W / C
                                26,500 / 24,480 = 108%

Backlog Cases/Day           =  MAX(0, (W − C) / T_touch)
                                MAX(0, 2,020 / 53) ≈ 38 cases

Throughput                  =  C / T_touch
FTE Required                =  ROUNDUP(W / E, 0)

**Assumptions & Data Sources**
All figures are based on industry-standard benchmarks for retail banking KYC operations:

500 cases/day — representative mid-sized retail bank daily intake
480 min/day — standard 8-hour operational shift
85% productivity — widely used workforce planning factor in banking ops
24-hour SLA — common regulatory and internal KYC completion target in India
Touch times — benchmarked against typical manual KYC processing times in Indian retail banking (maker–checker model)
