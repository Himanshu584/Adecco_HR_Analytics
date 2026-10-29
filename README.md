# HR Attrition Analytics | Excel Dashboard

An end-to-end **Excel HR analytics portfolio project** examining employee attrition patterns across departments, job roles, overtime, tenure, and job satisfaction, with a particular focus on **junior Sales employees**.

> **Headline finding:** 32 of 76 junior Sales employees are flagged as having left (**42.11%**). Within that group, the share flagged as having left is **72.73%** for employees with overtime versus **29.63%** without overtime. These are descriptive associations, **not causal findings or annualized turnover rates**.

## Project overview

- **Dataset:** IBM-style employee attrition snapshot; **1,470** unique employee records.
- **Tools:** Microsoft Excel, Power Query, PivotTables, slicers, calculated columns, charts, conditional formatting.
- **Deliverable:** Interactive executive dashboard and two accompanying Word reports.
- **Core question:** Where is attrition concentrated, and what should HR investigate first?

## Key results

| Segment / metric | Employees | Departures | Attrition share |
|---|---:|---:|---:|
| Overall | 1,470 | 237 | **16.12%** |
| Sales department | 446 | 92 | **20.63%** |
| Research & Development | 961 | 133 | 13.84% |
| Human Resources | 63 | 12 | 19.05% |
| Junior Sales | 76 | 32 | **42.11%** |
| All other employees | 1,394 | 205 | 14.71% |
| Junior Sales — overtime | 22 | 16 | **72.73%** |
| Junior Sales — no overtime | 54 | 16 | 29.63% |

**Junior Sales** is an analysis-specific definition: `Department = Sales` and `JobLevel = 1`.

Additional findings:
- **Sales Representatives** have the highest job-role attrition share: **33/83 (39.76%)**.
- **Laboratory Technicians** have the highest departure count: **62**.
- **31/32** junior Sales departures occur among employees with **five or fewer completed years of tenure**, but **69/76** junior Sales employees are also in these tenure groups.
- Overall junior Sales attrition share declines across satisfaction scores: **58.33%, 47.62%, 39.13%, 30.00%** for levels 1–4.
- Junior Sales overtime/satisfaction subgroups can be very small (as few as **n=1**); interpret cautiously.

## Dashboard contents

- Five KPI cards: total employees, employees left, overall attrition, junior Sales attrition, overtime attrition.
- Slicers: **Department**, **OverTime**, **Job Level**.
- Attrition by department — horizontal bar chart.
- Junior Sales overtime comparison — two doughnut charts.
- Junior Sales tenure vs attrition — combo chart.
- Job-role attrition risk — conditional-formatting heatmap.
- Junior Sales satisfaction × overtime — grouped horizontal bars.
- Junior Sales left vs retained — compact doughnut chart.


## Workbook structure

| Worksheet | Purpose |
|---|---|
| `HRData` | Cleaned employee data (Power Query output) and derived segmentation fields. |
| `Basis Analysis` | PivotTables and chart helper ranges for Basic Analysis. |
| `Advance Analysis` | PivotTables and chart helper ranges for Advance Analysis. |
| `Dashboard` | KPI cards, slicers, visualizations, and decision-support insights. |

### Preparation steps

1. Load the employee dataset into **Power Query** and validate data types, missingness and unique `EmployeeNumber`.
2. Remove constant columns `EmployeeCount`, `Over18`, and `StandardHours`.
3. Add `Attrition_Flag` (1 if `Attrition = Yes`, else 0) and `Junior_Sales_Flag` (Sales + JobLevel 1).
4. Create `Age_Group`, `Tenure_Group` and `Income_Band` segmentation columns.
5. Build PivotTables using employee counts, departure counts, and average `Attrition_Flag` as the attrition share.
6. Assemble the dashboard and selectively connect slicers to relevant PivotTables.

## Suggested repository layout

```text
HR-Attrition-Analytics/
├── HR_Attrition_Analysis.xlsx
├── HR_Attrition_Case_Study.docx
├── HR_Attrition_Solution_Guide.docx
├── README.md
└── dashboard.png  
```

![Dashboard Preview](https://github.com/Himanshu584/Adecco_HR_Analytics/blob/main/dashboard_screenshot.png)

## Recommendations

1. **Investigate overtime exposure** among junior Sales employees; validate actual hours, staffing and exit feedback before intervening.
2. **Test structured early-tenure support**, including 30/60/90-day onboarding and manager check-ins.
3. **Investigate satisfaction drivers** using confidential pulse surveys and manager-level process reviews.
4. **Monitor both attrition rate and departure volume** when prioritizing job roles.
5. **Measure pilots with dated HRIS data**, appropriate baselines, employee counts and comparison groups.

See [`HR_Attrition_Case_Study.docx`](HR_Attrition_Case_Study.docx) for the full analysis and [`HR_Attrition_Solution_Guide.docx`](HR_Attrition_Solution_Guide.docx) for a phased action plan.

## Important limitations

- This dataset is a **snapshot** with no specified observation period. “Attrition rate” in the analysis means **share of records flagged as departed**, not annualized employee turnover.
- The findings are **observational**, not causal; overtime and satisfaction may reflect other underlying factors.
- Small subgroups yield unstable percentages; show **sample sizes** alongside rates.
- Monthly income currency is **unspecified**; no currency symbol is assumed.
- This is a **portfolio/practice dataset**, not a verified analysis of a named real-world employer.

## How to use

1. Download or clone the repository.
2. Open `HR_Attrition_Analysis.xlsx` in desktop Microsoft Excel.
3. Navigate to `Dashboard` and explore the available slicers.
4. Review the two Word documents for interpretation and implementation guidance.
5. If the underlying dataset changes, refresh Power Query and PivotTables and verify chart/slicer connections.

