# 🏥 Healthcare No-Show Analytics Dashboard

An advanced Excel-based Business Intelligence dashboard for analyzing patient appointment attendance behavior, uncovering the demographic, geographic, and clinical factors that drive medical appointment no-shows.

![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![Status](https://img.shields.io/badge/status-completed-brightgreen)
![Records](https://img.shields.io/badge/records-106%2C987-blue)

---

## 📌 Project Overview

Patient no-shows are one of the most persistent inefficiencies in healthcare systems — wasting clinical capacity, delaying care for other patients, and inflating operational costs. This project analyzes a real-world dataset of **106,987 medical appointments** to answer a core business question:

> **What patient, demographic, and clinical characteristics are most strongly associated with missed medical appointments — and how can healthcare providers use this insight to reduce no-show rates?**

The result is a fully interactive, single-workbook Excel dashboard that combines data cleaning, data modeling, pivot-table analysis, and dynamic visualizations into a decision-support tool suitable for clinic administrators and healthcare analysts.

---

## 🗂️ Dataset Description

| Attribute | Description |
|---|---|
| `PatientId` | Unique identifier for each patient |
| `AppointmentID` | Unique identifier for each appointment |
| `Age` | Patient age, grouped into decennial brackets (0–9, 10–19, ... 100+) |
| `Neighbourhood` | Geographic area of the clinic/patient |
| `Hipertension` | Binary indicator — chronic hypertension diagnosis |
| `Diabetes` | Binary indicator — diabetes diagnosis |
| `Scholarship` | Enrollment in the *Bolsa Família* social welfare program |
| `Alcoholism` | Binary indicator — history of alcoholism |
| `SMS_received` | Whether the patient received an SMS appointment reminder |
| `ScheduledDay` | Date/time the appointment was scheduled |
| `AppointmentDay` | Date of the actual appointment |
| `Attendance Status` | Target variable — Showed Up vs. No-Show |

**Dataset size:** 106,987 rows × 14 columns.

---

## 🛠️ Tools & Methodology

| Category | Tools / Techniques |
|---|---|
| **Data Cleaning & Prep** | Microsoft Excel — Power Query-style manual cleaning, boolean-to-label standardization |
| **Data Modeling** | Power Pivot, relational data modeling across multiple tables |
| **Analysis** | Pivot Tables, aggregation, % of Row Total / % of Grand Total calculations |
| **Visualization** | Pivot Charts — Line, Doughnut, Bar, Column charts |
| **Interactivity** | Slicers with multi-table Report Connections for synchronized, dynamic filtering |
| **Formatting** | Conditional formatting for at-a-glance risk highlighting |

**Methodology (ETL Workflow):**
1. **Extract** — raw appointment-level data ingested into Excel.
2. **Transform** — cleaned and standardized boolean fields into descriptive tags (e.g., `1/0` → `Has Hypertension` / `No Hypertension`), handled date fields for timeline analysis, and grouped continuous age values into readable brackets.
3. **Load** — structured the cleaned data into a Power Pivot data model to support cross-filtering across multiple pivot tables and charts from a single set of slicers.

---

## 📊 Key Insights & Visualizations

### 1. Appointments Timeline
A line chart tracking daily appointment volume, revealing scheduling patterns, peak booking periods, and volume fluctuations over the observed date range.

### 2. Overall Attendance vs. No-Show
A doughnut chart summarizing the macro-level compliance rate:
- **Attendance Rate:** ~20.26%
- **No-Show Rate:** ~79.74%

This headline figure frames the scale of the operational challenge the rest of the dashboard investigates.

### 3. No-Show Rate by Neighbourhood
A bar chart ranking geographic areas by non-attendance frequency, surfacing the specific neighbourhoods where outreach or scheduling interventions would have the greatest impact.

### 4. Attendance Distribution by Age Group
A column chart comparing attendance behavior across age brackets (0–9 through 100+), highlighting which age segments are most and least reliable in keeping appointments.

### 5. Impact of Chronic Conditions
Bar charts comparing attendance consistency between patients with and without **Hypertension** and **Diabetes**, testing whether chronic illness correlates with higher or lower no-show behavior.

### 6. Interactive Control Panel
A centralized bank of slicers — **Scholarship status**, **Alcoholism history**, and **SMS reminder receipt** — connected via Report Connections to every pivot table and chart in the workbook, enabling real-time, synchronized drill-down across all visuals simultaneously.

---

## 🏗️ Dashboard Architecture

```
Healthcare-NoShow-Analytics/
│
├── Raw Data Sheet        → Original, unmodified appointment records
├── Cleaned Data Sheet    → Standardized fields, descriptive labels, engineered columns
├── Data Model (Power Pivot) → Relationships linking fact/dimension tables
├── Pivot Tables          → Aggregated summaries feeding each chart
└── Dashboard Sheet       → Unified visual layer
    ├── KPI Cards (Attendance % / No-Show %)
    ├── Appointments Timeline (Line Chart)
    ├── Attendance vs. No-Show (Doughnut Chart)
    ├── No-Show by Neighbourhood (Bar Chart)
    ├── Attendance by Age Group (Column Chart)
    ├── Chronic Conditions Impact (Bar Charts)
    └── Slicer Panel (Scholarship / Alcoholism / SMS_received)
```

All visuals are pivot-chart-driven and connected to a single Power Pivot data model, ensuring that filtering any one slicer updates every chart on the dashboard in real time.

---

## 🚀 How to Use

1. **Download** the `.xlsx` file from this repository.
2. **Open** it in Microsoft Excel (2016 or later recommended for full Power Pivot / slicer support).
3. If prompted, click **Enable Editing** and **Enable Content** to activate data connections.
4. Navigate to the **Dashboard** sheet.
5. Use the **slicers** (Scholarship, Alcoholism, SMS Received) to filter the entire dashboard interactively.
6. Hover over chart elements to view detailed tooltips, or click into the underlying **Pivot Tables** sheet to inspect the raw aggregations behind any visual.
7. To modify or extend the analysis, use the **Cleaned Data** sheet as the single source of truth and refresh the Power Pivot data model after any changes.

---

## 💡 Key Business Takeaways

- Nearly **4 in 5 appointments** in this dataset ended in a no-show, indicating a systemic attendance issue rather than isolated cases.
- No-show rates vary meaningfully **by neighbourhood**, suggesting geography-targeted reminder or transportation-assistance programs could be more effective than blanket interventions.
- Age and chronic-condition status both show measurable relationships with attendance behavior, informing which patient segments may benefit most from proactive outreach (e.g., additional SMS reminders or phone confirmations).
- The interactive slicer design allows clinic administrators to test hypotheses live (e.g., "Do SMS reminders reduce no-shows among scholarship recipients?") without needing to rebuild any charts.

---

## 📬 Contact

**Author:** Hana
**Focus:** Machine Learning · Data Analysis · Computer Vision
**Portfolio:** Building toward internship / analyst-level opportunities in Egypt's tech sector

Feel free to open an issue or reach out with feedback or suggestions for extending this analysis.
