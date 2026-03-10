# 🧑‍💼 HR Analytics: Employee Attrition & Retention Strategy

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-EDA-lightblue)
![scipy](https://img.shields.io/badge/scipy-Statistical%20Testing-orange)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Dataset](https://img.shields.io/badge/Dataset-IBM%20HR%20Analytics-blueviolet)

> **Exploratory Data Analysis · Statistical Validation · Prescriptive Recommendations**  
> A full end-to-end people analytics project profiling at-risk employees and delivering 8 segment-specific retention strategies backed by statistical evidence.

---

## 📌 Central Business Question

> *"Who are the employees most at risk of leaving — and what targeted interventions can the organisation implement to retain them?"*

This project is dual-purpose:
- **Who is leaving** → EDA profiling at-risk employees across demographic, organisational, and workplace experience variables
- **What to do about it** → Prescriptive retention strategies with KPIs and implementation timelines, grounded in statistically validated findings

---

## 📊 Dataset

| Property | Detail |
|---|---|
| **Source** | IBM HR Analytics Employee Attrition Dataset |
| **Rows** | 1,470 employees |
| **Columns** | 35 variables (reduced to 31 after cleaning) |
| **Target Variable** | Attrition (Yes / No) |
| **Attrition Rate** | 16.1% — 237 employees left, 1,233 stayed |

---

## 🔍 Methodology

The project follows a 4-stage analytical pipeline:

```
Univariate EDA → Bivariate Analysis → Statistical Validation → Prescriptive Recommendations
```

**Stage 1 — Data Cleaning & Preparation**
- Dropped 4 zero-variance / identifier columns
- Applied ordered categorical encoding to 8 ordinal variables

**Stage 2 — Exploratory Data Analysis**
- Univariate distributions for all 31 variables
- Bivariate attrition rate analysis across demographics, organisational factors, and workplace experience

**Stage 3 — Statistical Validation**
- Chi-square test of independence applied to all 10 categorical variables vs. Attrition
- Cramér's V effect size calculated for each significant association
- Variables with p > 0.05 explicitly ruled out from recommendations

**Stage 4 — Prescriptive Extension**
- 8 segment-specific retention recommendations
- Each recommendation linked to its EDA finding and statistical support
- KPIs and 30/60/90 day implementation timelines included

---

## 📈 Key Findings

### Scale of the Problem
| Metric | Value |
|---|---|
| Overall Attrition Rate | **16.1%** (237 / 1,470) |
| Median Monthly Income Gap (leavers vs. stayers) | **$2,002 less** per month |
| Average Age Difference | Leavers avg **4 years younger** |
| Estimated Replacement Cost | 50–200% of annual salary × 237 leavers |

### Top Risk Factors

| # | Risk Factor | Finding | Statistical Support |
|---|---|---|---|
| 1 | **OverTime** | 30.5% attrition (Yes) vs. 10.4% (No) | ✅ χ²=87.56, p<0.001, V=0.24 — **Moderate** |
| 2 | **Job Level** | Level 1 = 26.3% attrition | Numeric — pattern consistent & large |
| 3 | **Marital Status** | Single = 25.5% vs. Married = 12.5% | ✅ χ²=46.16, p<0.001, V=0.18 — **Weak** |
| 4 | **Stock Options** | Level 0 = 24.4% vs. Level 1 = 9.4% | Ordinal — monotonic drop across levels |
| 5 | **Job Involvement** | Low = 33.7% attrition | ✅ χ²=28.49, p<0.001, V=0.14 — **Weak** |
| 6 | **Env. Satisfaction** | Low = 25.4% attrition | ✅ χ²=22.50, p<0.001, V=0.12 — **Weak** |
| 7 | **Job Satisfaction** | Low = 22.8% attrition | ✅ χ²=17.51, p<0.001, V=0.11 — **Weak** |

### Variables Statistically Ruled Out
| Variable | p-value | Cramér's V | Verdict |
|---|---|---|---|
| Gender | 0.2906 | 0.03 — Negligible | ❌ Not significant |
| Education Level | 0.5455 | 0.05 — Negligible | ❌ Not significant |
| Relationship Satisfaction | 0.1550 | 0.06 — Negligible | ❌ Not significant |

> Ruling out non-significant variables is as important as identifying significant ones — it prevents wasted intervention budget.

---

## 🧍 The At-Risk Employee Profile

> *The employee most likely to leave is **under 35**, **single**, works as a **Sales Representative or Laboratory Technician** at **Job Level 1–2**, earns **below-median income**, works **overtime regularly**, has **no stock options**, scores **low on satisfaction**, and has gone **3+ years without a promotion**.*

This profile is immediately actionable — HR can query current employee records against these criteria and flag at-risk individuals for proactive check-ins today.

---

## 💡 Retention Recommendations

| # | Segment | Key Action | KPI |
|---|---|---|---|
| 1 | Entry-Level & Young | Structured onboarding + early career pathing | Attrition rate: <3 yrs tenure (quarterly) |
| 2 | Overtime Workers | Overtime cap (20hrs/month) + workload audit with 30/60/90 day plan | % workforce on overtime (monthly) |
| 3 | Sales Rep & Lab Tech | Compensation benchmarking — base + variable pay separately | Median income gap by role (annually) |
| 4 | Stagnating Careers | Promotion pipeline audit for 3+ years since last promotion | % employees at 3+ and 5+ yrs since promotion |
| 5 | Low Satisfaction | Quarterly pulse surveys + manager training + action threshold | Avg satisfaction scores vs. baseline |
| 6 | Single Employees | Flexible work + commuter benefits + social integration programmes | Attrition by marital status (semi-annually) |
| 7 | No Stock Options | Broaden Level 1 eligibility to high-risk roles | Attrition by stock option level (annually) |
| 8 | Manager Continuity | Team-level attrition dashboard by manager + effectiveness training | Team attrition rate by manager (quarterly) |

---

## 🛠️ Tools & Libraries

| Tool | Purpose |
|---|---|
| **Python 3** | Core analysis language |
| **pandas** | Data manipulation and cleaning |
| **NumPy** | Numerical operations |
| **matplotlib & seaborn** | Data visualisation |
| **scipy.stats** | Chi-square testing and Cramér's V |
| **Jupyter Notebook** | Interactive development environment |

---

## 📁 Repository Structure

```
hr-attrition-eda/
│
├── HR_Attrition_EDA.ipynb               ← Full analysis notebook
├── WA_Fn-UseC_-HR-Employee-Attrition.csv ← Dataset
├── HR_Attrition_Executive_Summary.docx  ← One-page summary for non-technical audience
└── README.md                            ← This file
```

---

## 🚀 How to Run

1. Clone the repository
```bash
git clone https://github.com/owolabiiyanuvictoria/hr-attrition-eda.git
cd hr-attrition-eda
```

2. Install required libraries
```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
```

3. Launch the notebook
```bash
jupyter notebook HR_Attrition_EDA.ipynb
```

> The dataset CSV must be in the same folder as the notebook.

---

## 👩‍💻 About

**Owolabi Victoria Iyanu**  
Data Analyst | B.Tech Food Engineering  
Tools: Python · SQL · Power BI · Excel

A technical engineering background applied to data analytics — building projects that go beyond description into statistical validation and business recommendations.

[![GitHub](https://img.shields.io/badge/GitHub-owolabiiyanuvictoria-black?logo=github)](https://github.com/owolabiiyanuvictoria)
