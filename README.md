Restaurant Inspection Dashboard (Power BI)

Dashboard Link: https://app.powerbi.com/view?r=eyJrIjoiNjg4ZmNhYjEtMTUzNC00ZDk2LWE4ZDAtODI1NDM4MmM1OTNjIiwidCI6IjIzODk2NDkwLTdlNzMtNGQ1Zi1hZjQ5LTBmMjUwMzQ5NWQ3NSJ9

Dashboard Overview

This project presents a **Restaurant Inspection Dashboard** built using **Power BI**, with a **CSV file as the data source**. The dashboard analyzes restaurant inspection performance, violations, and geographic trends using structured data modeling and advanced visualizations.

The report is designed with **two analytical pages**:

* **Inspections & Violations**
* **Zipcode Analysis**

The solution leverages **data modeling**, **DAX measures**, **KPI cards**, and **Azure Maps** to deliver actionable food safety insights.

---

Problem Statement

Restaurant inspection data contains critical information about compliance, violations, and regional risk patterns. This project aims to convert raw inspection data into an interactive dashboard that helps users:

* Monitor inspection outcomes
* Track violation counts and trends
* Analyze inspection data by zipcode
* Visualize geographic distribution using maps
* Quickly assess KPIs through summary cards

---

Tools & Technologies Used

* **Power BI Desktop**
* **CSV File (Data Source)**
* **DAX (Data Analysis Expressions)**
* **Data Modeling (Fact & Dimension tables)**
* **Azure Maps**
* **KPI Cards & Interactive Filters**

---

Data Model

* **Fact Table:** Restaurant Inspection Data
* **Dimension Tables:** Restaurant, Date, Zipcode (derived as needed)

The data model supports efficient filtering and aggregation across inspection results, violations, and geographic attributes.

---

Steps Followed

Data Preparation

* **Step 1:** Loaded restaurant inspection data from a **CSV file** into Power BI.
* **Step 2:** Created a **star-style data model** with inspection data as the fact table.
* **Step 3:** Cleaned and standardized inspection results and violation fields.
* **Step 4:** Established relationships between inspection, date, and zipcode fields.

Report Design

**Step 5:** Created **two report pages**:

  * **Inspections & Violations** – inspection results, violation metrics, KPIs
  * **Zipcode Analysis** – geographic analysis using Azure Maps
* **Step 6:** Added **two KPI cards** to highlight key inspection metrics.
* **Step 7:** Implemented **Azure Maps** to visualize inspection density and risk by zipcode.

---

DAX Measures Used

> This project uses **13 DAX measures**.
> Below are the **exact measures**, written in **Power BI-ready format** so they appear cleanly in the **Edit pane**.

---

Inspection Measures

```DAX
Total Inspections =
COUNT ( Inspection[Inspection_ID] )
```

```DAX
Passed Inspections =
CALCULATE (
    [Total Inspections],
    Inspection[Inspection_Result] = "Pass"
)
```

```DAX
Failed Inspections =
CALCULATE (
    [Total Inspections],
    Inspection[Inspection_Result] = "Fail"
)
```

```DAX
Pass Rate % =
DIVIDE ( [Passed Inspections], [Total Inspections], 0 )
```

---

Violation Measures

```DAX
Total Violations =
SUM ( Inspection[Violation_Count] )
```

```DAX
Average Violations per Inspection =
DIVIDE ( [Total Violations], [Total Inspections], 0 )
```

```DAX
Inspections with Violations =
CALCULATE (
    [Total Inspections],
    Inspection[Violation_Count] > 0
)
```

```DAX
Violation Rate % =
DIVIDE ( [Inspections with Violations], [Total Inspections], 0 )
```

---

Zipcode & Geographic Measures

```DAX
Distinct Zipcodes =
DISTINCTCOUNT ( Inspection[Zipcode] )
```

```DAX
Inspections by Zipcode =
[Total Inspections]
```

```DAX
Violations by Zipcode =
[Total Violations]
```

---

KPI Measures

```DAX
Failure Rate % =
DIVIDE ( [Failed Inspections], [Total Inspections], 0 )
```

```DAX
Average Inspection Score =
AVERAGE ( Inspection[Inspection_Score] )
```

---

Visualizations Used

* KPI Cards (Average Sanity Grade, Current Month Inspections)

Average Sanity Grade:

<img width="307" height="159" alt="Screenshot 2026-02-08 222952" src="https://github.com/user-attachments/assets/61f0688a-c811-420a-b437-aa6574407e19" />

Current Month Inspections:

<img width="299" height="164" alt="Screenshot 2026-02-08 223140" src="https://github.com/user-attachments/assets/180695c7-7193-4ee9-a0dc-34bca6c50df6" />

* Bar & column charts (violations and inspection trends)
* Azure Maps (zipcode-level inspection analysis)
* Slicers for dynamic filtering

---

Key Insights

* Certain zipcodes show higher violation density than others.
* Pass and failure rates help identify compliance trends.
* Average violation metrics highlight risk-prone establishments.
* Geographic visualization improves inspection planning and monitoring.

---
Conclusion

This project demonstrates strong expertise in **data modeling**, **DAX measure creation**, and **geospatial analysis using Azure Maps**. The dashboard converts inspection data into meaningful insights that support food safety monitoring and regulatory analysis.

