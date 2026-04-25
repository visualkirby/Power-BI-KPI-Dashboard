# Power BI KPI Dashboard

**Power BI | DAX | Data Modeling | Interactive Reporting**

A multi-page Power BI report built to demonstrate how business and operational 
KPIs can be structured, calculated, and visualized across role-based views with 
interactive filtering and bookmark navigation.

This project demonstrates how organizations can use Power BI to track 
**performance metrics, operational health, and financial KPIs** across 
departments, teams, and time periods through a structured, decision-ready 
reporting system.

---

# Project Overview

Organizations collecting operational data often struggle to turn it into 
actionable visibility. Common problems include:

- KPIs that exist in spreadsheets but never reach decision-makers
- Reports that show numbers without context or comparison
- No role separation (everyone sees everything, or no one sees enough)
- Static exports that go stale the moment they're produced

This dashboard addresses those problems through a structured **two-page, 
seven-section Power BI report** with role-based views, a complete DAX 
measure library, and an interactive filter system that lets users slice 
data across multiple dimensions simultaneously.

---

# Dashboard Structure

## 👩‍🏫 Operational Staff View

Designed for front-line staff and team leads who need visibility into 
day-to-day performance metrics relevant to their role.

### Section 1 *Performance Overview*



![Academic Performance](./screenshots/Teacher_Academic_Performance.png)



High-level summary of core performance KPIs across the full dataset.

Key indicators include:

- Average Performance Rate
- Pass / Completion Rate
- At-Risk Count
- Average Score

Includes grade distribution, subject-level breakdowns, a scatter plot 
correlating two key performance dimensions, an assignment completion 
donut, and a behavior incidents heatmap by time period.

---

### Section 2 *Attendance & Availability*



![Attendance](./screenshots/Teacher_Attendance.png)



Tracks attendance patterns and flags chronic absence across segments.

Key indicators include:

- Average Attendance Rate
- Chronic Absenteeism Rate
- Attendance by Segment (bar charts)

---

### Section 3 *Behavior & Incidents*



![Behavior](./screenshots/Steadmark_Heatmap.png)



Monitors incident volume across time periods and segments to identify 
patterns that affect operational performance.

Key indicators include:

- Total Incidents
- Total Referrals
- Total Suspensions
- Incidents by Day and Period (heatmap)

---

### Section 4 *At-Risk Flagging*



![At Risk](./screenshots/Teacher_AtRisk.png)



Surfaces records flagged for immediate attention based on configurable 
threshold rules. Includes an alert banner, summary KPIs, and a 
drill-ready detail table.

---

## 🏢 Administrator View

Designed for administrators and managers who need cross-team visibility, 
staff performance data, and financial oversight.

### Section 5 *Staff Performance*



![Staff Performance](./screenshots/Admin_StaffPerformance.png)



Evaluates staff-level metrics across the full team.

Key indicators include:

- Average Class Pass Rate
- Average Staff Attendance
- Average PD Hours
- Total Records

Includes pass rate by staff member and professional development hours 
tracking with configurable targets.

---

### Section 6 *Operations*

Tracks operational health metrics across segments including enrollment, 
capacity, and suspension rates.

---

### Section 7 *Budget Utilization*



![Budget](./screenshots/Admin_Budget.png)



Evaluates spend against allocation across departments with gradient 
conditional formatting. Departments under budget display in blue, 
over-budget departments display in red.

Key indicators include:

- Total Allocated Budget
- Total Spent Budget
- Budget Utilization %
- Over-Budget Department Count

---

# Filter System

All sections are controlled by a right-side filter panel including:

- Segment-level color-coded button slicers
- School Year dropdown
- Term dropdown
- Grade Level dropdown
- Subject dropdown
- Minimum Attendance % range slider
- Show Only checkboxes (At-Risk, Chronically Absent, Below Passing, 
  Active Interventions)
- Apply All button

---

# DAX Measure Library

17 measures across 5 tables covering performance, attendance, behavior, 
staff, and budget KPIs.

| Table | Measures |
|---|---|
| **students_fact** | Total Students, Avg Attendance Rate, Chronic Absenteeism Rate, At Risk Count |
| **performance** | Avg Exam Score, Pass Rate, Avg Homework Completion |
| **behavior** | Total Incidents, Total Referrals, Total Suspensions |
| **teachers** | Avg Class Pass Rate, Avg PD Hours, Avg Teacher Attendance |
| **budget** | Total Allocated Budget, Total Spent Budget, Budget Utilization %, Over Budget Depts |

---

# Data Model

5-table star schema with the following structure:

- **students_fact** | core fact table (12,156 rows)
- **performance** | subject-level exam and completion data (36,468 rows)
- **behavior** | incident and referral records (12,156 rows)
- **teachers** | staff performance metrics (1,000 rows)
- **budget** | department-level financial data (6 rows)

Data engineered in R from Kaggle source datasets. Full dataset and 
engineering scripts will be added to this repo in a future update.

---

# Key Technical Features

| Feature | Detail |
|---|---|
| **Pages** | 2 (Staff View + Admin View) |
| **Bookmark Sections** | 7 |
| **DAX Measures** | 17 |
| **Filter Dimensions** | 7 |
| **Data Model** | 5-table star schema |
| **Role-Based Access** | Two-role RLS (Staff + Administrator) via USERPRINCIPALNAME() |
| **Settings Page** | Dedicated hidden page / thresholds, targets, user profile, active school year |
| **Canvas Size** | 1440 × 900 |

---

# Business Value

This dashboard enables organizations to:

- Surface at-risk records before they become critical issues
- Give front-line staff visibility into their own performance data
- Give administrators cross-team oversight without exposing individual 
  staff data to peers
- Track budget utilization with visual over/under alerts
- Configure alert thresholds and targets without rebuilding the report

---

# Tools Used

- Power BI Desktop
- DAX
- R (tidyverse) | data engineering
- Kaggle datasets | source data

---

# Author

**Sawandi Kirby**

Data Analytics | Dashboard Development | KPI Reporting  
Focused on building decision-ready reports that turn operational data 
into clear business visibility.

- GitHub: https://github.com/visualkirby
- LinkedIn: https://linkedin.com/in/sawandi-kirby
- Kaggle: https://kaggle.com/sawandikirby
