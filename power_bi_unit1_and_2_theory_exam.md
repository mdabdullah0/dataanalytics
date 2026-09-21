# Mid-Term Theory Examination: Unit I & Unit II
**Course Title:** Data Analytics Using Power BI  
**Course Code:** CSS03D201  
**Semester:** III | **Credits:** 4 (L-T-P: 3-0-1)  
**Time Allowed:** 2 Hours | **Maximum Marks:** 50 Marks  

---

## Instructions to Candidates
1. This question paper contains **Three Sections**: Section A (10 Marks), Section B (20 Marks), and Section C (20 Marks).
2. Answer **ALL** questions across all sections.
3. Read scenario descriptions carefully before answering applied questions in Section C.
4. Neatness, logical structuring, and clear technical explanations carry due weightage.

---

## Section A: Multiple Choice Questions (10 x 1 = 10 Marks)

**Q1.** Which data connection mode in Power BI Desktop loads a complete copy of the data into the in-memory xVelocity engine?
* (A) DirectQuery Mode
* (B) Import Mode
* (C) Live Connection Mode
* (D) Dual Mode

**Q2.** Which scale of measurement applies to variables that have categorical labels with a meaningful order, but lack uniform numerical distances between categories?
* (A) Nominal Scale
* (B) Ordinal Scale
* (C) Interval Scale
* (D) Ratio Scale

**Q3.** According to Edward Tufte's design principles, what is the primary goal when optimizing the "Data-to-Ink Ratio" in a dashboard?
* (A) Maximize background colors and gridlines to enhance visual depth.
* (B) Use 3D charts to display multi-dimensional data effectively.
* (C) Eliminate non-data ink (clutter, redundant borders, heavy gridlines) without losing information.
* (D) Ensure every visual element uses a unique color from the rainbow spectrum.

**Q4.** Which Gestalt principle explains why placing a light gray background box behind three related visual cards causes the human brain to perceive them as a single logical unit?
* (A) Principle of Proximity
* (B) Principle of Continuity
* (C) Principle of Enclosure
* (D) Principle of Similarity

**Q5.** In Power Query Editor, which operational feature allows you to combine rows from two tables with identical column structures into a single unified table?
* (A) Merge Queries
* (B) Append Queries
* (C) Transpose
* (D) Pivot Column

**Q6.** A retail analyst uses historical transaction data to answer the question: *"Why did net profit margin drop by 8% in Q3?"* Which category of data analytics does this represent?
* (A) Descriptive Analytics
* (B) Diagnostic Analytics
* (C) Predictive Analytics
* (D) Prescriptive Analytics

**Q7.** When connecting Power BI to an SQL database containing 50 million records where real-time accuracy is legally mandated, which connection mode should be selected?
* (A) Import Mode
* (B) DirectQuery Mode
* (C) Web Feed
* (D) Static File Mode

**Q8.** In Power Query Editor, what is the underlying functional language used to record all transformation steps in the "Applied Steps" pane?
* (A) DAX (Data Analysis Expressions)
* (B) M Code (Power Query Formula Language)
* (C) SQL (Structured Query Language)
* (D) Python

**Q9.** Which data profiling tool in Power Query Editor displays the percentage of Valid, Error, and Empty values present in a column?
* (A) Column Profile
* (B) Column Distribution
* (C) Column Quality
* (D) Monomorphic Profiler

**Q10.** Which visual chart type is best suited for showing the correlation between two continuous ratio variables (e.g., Marketing Spend vs. Units Sold)?
* (A) Stacked Bar Chart
* (B) Treemap
* (C) Scatter Plot
* (D) Donut Chart

---

## Section B: Short Answer Questions (5 x 4 = 20 Marks)

**Q11.** Compare **Import Mode** and **DirectQuery Mode** in Power BI. State **two advantages** and **two limitations** of using DirectQuery Mode. *(4 Marks)*

**Q12.** Explain the **Gestalt Principles of Visual Perception** (specifically *Proximity*, *Similarity*, and *Enclosure*). Briefly describe how an instructor or designer applies them to construct clean report page layouts. *(4 Marks)*

**Q13.** Differentiate between the four analytics pillars: **Descriptive**, **Diagnostic**, **Predictive**, and **Prescriptive Analytics**. Provide a single real-world business example for each. *(4 Marks)*

**Q14.** Explain the difference between **Merge Queries** and **Append Queries** in Power Query Editor. Describe a specific practical scenario where each transformation is required. *(4 Marks)*

**Q15.** What is **Exploratory Data Analysis (EDA)**? Explain the function of the three built-in data profiling views in Power Query Editor: *(a) Column Quality*, *(b) Column Distribution*, and *(c) Column Profile*. *(4 Marks)*

---

## Section C: Applied & Scenario-Based Questions (2 x 10 = 20 Marks)

### Q16. Scenario A: Dashboard Usability Audit & Redesign Layout (10 Marks)
A regional sales director complains that their current monthly performance dashboard is *"confusing, overwhelming, and impossible to interpret during executive meetings."* 

An audit of the current report page reveals:
* A 3D Pie Chart containing 14 distinct category slices displaying sales breakdown.
* Bright rainbow background colors on every visual card.
* Y-axis baselines on bar charts starting at $50,000 instead of $0.
* Raw, unformatted database column names (e.g., `tbl_usr_cust_sales_net_amt_2025`) as chart titles.
* Random visual placement with no clear reading grid.

**Task Requirements:**
1. **Visual Critique:** Identify and explain **four distinct visual design rule violations** in this report using established visualization principles (e.g., Data-to-Ink Ratio, Cognitive Load, Pre-attentive Processing, Color Integrity). *(4 Marks)*
2. **Redesign Plan:** Propose a complete redesign strategy for this dashboard. Specify the **visual layout grid** (using the Z-pattern hierarchy), the **exact chart types** to replace the flawed visuals, and the **color/formatting guidelines** to make the dashboard executive-ready. *(6 Marks)*

---

### Q17. Scenario B: Power Query Data Preprocessing Pipeline (10 Marks)
You are assigned as the Lead BI Analyst for an e-commerce platform ("GlobalCart"). You receive monthly raw transaction logs from three regional warehouses exported as messy CSV files. 

An inspection of the raw data reveals the following data hygiene issues:
* **Inconsistent Dates:** The `OrderDate` field contains mixed formats (`2026-01-15`, `15/01/2026`, and text strings like `Jan 15, 2026`).
* **Text Noise:** The `CustomerName` column contains leading/trailing spaces and inconsistent casing (`JOHN smith`, `jane DOE  `).
* **Price Formatting:** The `UnitPrice` column contains embedded currency symbols (`$149.99`, `€120.00`).
* **Missing Values:** The `ReturnReason` field contains `null` entries for orders that were successfully delivered and never returned.
* **Non-Revenue Rows:** Transaction rows with `OrderStatus = 'Cancelled'` are mixed in with completed sales, artificially inflating order counts.

**Task Requirements:**
1. **ETL Pipeline Design:** Write a detailed, step-by-step transformation workflow in **Power Query Editor** to clean, shape, and standardize this dataset before loading it into the data model. List the specific menu options/functions applied at each step. *(6 Marks)*
2. **Applied Steps Order & Logic:** Explain why transformation sequence matters in Power Query. Specifically, why must **currency symbol removal** and **text trimming** occur *before* changing column data types to `Fixed Decimal Number` or `Date`? *(4 Marks)*

---

# Detailed Answer Key & Marking Scheme

## Section A: Multiple Choice Answer Key (10 Marks)
1. **(B) Import Mode** — Loads data into the xVelocity in-memory engine.
2. **(B) Ordinal Scale** — Ordered categories without equal numerical intervals.
3. **(C) Eliminate non-data ink** — Focuses visual attention purely on the data.
4. **(C) Principle of Enclosure** — Visual boundaries group items together.
5. **(B) Append Queries** — Stacks rows from tables with identical schemas.
6. **(B) Diagnostic Analytics** — Answers *why* something happened.
7. **(B) DirectQuery Mode** — Queries the source in real-time for live data accuracy.
8. **(B) M Code** — Power Query Formula Language recorded in Applied Steps.
9. **(C) Column Quality** — Displays Valid, Error, and Empty percentages.
10. **(C) Scatter Plot** — Ideal for relationship/correlation between two ratio variables.

---

## Section B: Model Answers & Marking Scheme (20 Marks)

### Q11. Import Mode vs. DirectQuery Mode (4 Marks)
* **Import Mode:** Data is extracted and stored in Power BI memory. Fast query performance.
* **DirectQuery Mode:** Data remains in the source database; queries are generated in real-time upon interaction.
* **Advantages of DirectQuery (1 Mark):**
  1. Handles massive datasets exceeding Power BI memory limits.
  2. Guarantees real-time data visibility without waiting for scheduled refreshes.
* **Limitations of DirectQuery (1 Mark):**
  1. Slower report response times as every visual interaction triggers live SQL queries.
  2. Limited DAX transformation functions and M-code capabilities compared to Import Mode.

### Q12. Gestalt Principles in Dashboard Design (4 Marks)
* **Proximity (1 Mark):** Elements placed near each other are seen as related. *Application:* Placing a KPI card directly next to its corresponding trend line chart.
* **Similarity (1 Mark):** Elements with similar visual traits (color, font, shape) are perceived as having similar functions. *Application:* Using blue headers for sales visuals and green headers for financial metrics.
* **Enclosure (1 Mark):** Placing a visual boundary (card/box) around elements binds them into a group. *Application:* Wrapping quarterly slicers and filters inside a shaded sidebar box.
* **Summary Impact (1 Mark):** Reduces visual clutter and helps users scan dashboards intuitively.

### Q13. Four Pillars of Analytics (4 Marks)
* **Descriptive (1 Mark):** *What happened?* Example: A monthly report showing $1.2M in gross sales.
* **Diagnostic (1 Mark):** *Why did it happen?* Example: Drill-down analysis showing sales dropped due to a supply chain bottleneck in Europe.
* **Predictive (1 Mark):** *What will happen?* Example: Forecasting Q4 demand using statistical time-series models.
* **Prescriptive (1 Mark):** *What should we do?* Example: Automated recommendation system advising inventory managers to reorder 500 units of Product X.

### Q14. Merge vs. Append Queries (4 Marks)
* **Merge Queries (2 Marks):** Relational join (horizontal combination) based on a common matching column (Primary/Foreign key). *Scenario:* Joining a `Sales Transactions` table with a `Product Lookup` table using `ProductID`.
* **Append Queries (2 Marks):** Union operation (vertical combination) stacking rows from tables with matching schemas. *Scenario:* Combining separate monthly CSV files (`January_Sales.csv`, `February_Sales.csv`) into a single master sales table.

### Q15. Exploratory Data Analysis & Profiling (4 Marks)
* **EDA Definition (1 Mark):** Initial investigation of datasets to spot anomalies, test hypotheses, and verify data quality before modeling.
* **Data Profiling Tools (3 Marks):**
  * *(a) Column Quality:* Displays bar summary of Valid %, Error %, and Empty %.
  * *(b) Column Distribution:* Shows a mini histogram of value distributions and counts of Unique vs. Distinct values.
  * *(c) Column Profile:* Provides detailed column statistics (Min, Max, Mean, Standard Deviation, Null counts, Value distribution).

---

## Section C: Scenario Solutions & Rubric (20 Marks)

### Q16. Scenario A: Usability Audit & Redesign (10 Marks)

#### Part 1: Visual Critique (4 Marks — 1 Mark per valid violation explained)
1. **3D Pie Chart with 14 Slices:** Violates cognitive load and perception limits. Human angle estimation is poor; pie charts should never exceed 5 slices and must never be 3D.
2. **Rainbow Background Colors:** Violates color integrity and causes visual fatigue. Colors should be neutral with purposeful accent colors.
3. **Non-Zero Baseline on Bar Charts:** Distorts quantitative ratios, misleading viewers regarding relative growth.
4. **Raw Database Column Names:** Violates clarity and domain accessibility; headers must be business-friendly (e.g., `Net Sales Amount ($)`).

#### Part 2: Dashboard Redesign Plan (6 Marks)
* **Layout Hierarchy (Z-Pattern) (2 Marks):**
  * **Top Row:** 3–4 summary KPI Cards (Total Sales, Total Profit, Orders, Return Rate) for immediate executive overview.
  * **Middle Section:** Main trend Line Chart (Monthly Sales Performance) on the left; Horizontal Bar Chart (Sales by Category) on the right.
  * **Bottom Section:** Detailed Data Matrix table for granular inspection.
  * **Left Sidebar:** Slicers for Region and Date Range enclosed in a shaded box.
* **Chart Selection Alternatives (2 Marks):** Replace 14-slice pie chart with a Horizontal Bar Chart or Treemap.
* **Formatting & Color Strategy (2 Marks):** Use soft gray/slate backgrounds (`#F8F9FA`), dark gray text for high contrast, neutral blue for standard bars, and red callouts only for negative performance alerts.

---

### Q17. Scenario B: Power Query ETL Pipeline (10 Marks)

#### Part 1: Step-by-Step Transformation Workflow (6 Marks — 1 Mark per clean step)
1. **Filter Non-Revenue Rows:** Apply filter on `OrderStatus` column to exclude `'Cancelled'` orders (`OrderStatus <> 'Cancelled'`).
2. **Text Standardization:** Select `CustomerName` column $\rightarrow$ apply `Transform -> Format -> Trim` (removes trailing spaces) and `Format -> Capitalize Each Word`.
3. **Currency Symbol & Text Removal:** Select `UnitPrice` column $\rightarrow$ apply `Replace Values` (replace `$` with `""`, `€` with `""`) or use `Extract Text After Delimiter`.
4. **Data Type Casting:** Cast `UnitPrice` to `Fixed Decimal Number` (`Currency`), `OrderDate` to `Date` (using Locale if needed), and `OrderID` to `Text`.
5. **Handling Nulls:** Select `ReturnReason` column $\rightarrow$ apply `Replace Values` (replace `null` with `"Not Applicable / Delivered"`).
6. **Combine Files (if multi-warehouse):** Load files into Power Query folder ingestion, combine binaries, and remove source filename clutter.

#### Part 2: Applied Steps Order Logic (4 Marks)
* **Applied Steps Dependencies (2 Marks):** Power Query executes transformations sequentially. Changing a column type to numeric (`Fixed Decimal`) while it still contains text symbols (`$`, `€`) causes type conversion errors (`DataFormat.Error`), turning valid cells into `Error` or `null`.
* **Execution Strategy (2 Marks):** Data hygiene (trimming, symbol replacement, null handling) MUST occur while the field is still in `Text` mode. Data type casting must always be the *final step* in a transformation sequence to guarantee zero conversion errors.
