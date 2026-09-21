# Week 1 Day-Wise Teaching Plan & Lesson Guide
**Course Title:** Data Analytics Using Power BI  
**Course Code:** CSS03D201 | **Semester:** III | **Credits:** 4 (L-T-P: 3-0-1)  
**Week 1 Focus:** Business Intelligence Principles, Measurement Scales, Visual Perception, Chart Selection & Low-Fidelity Dashboard Wireframing  
**Target Course Outcome:** **CO1** — Understand the fundamentals of Power BI, business intelligence concepts, and data visualization principles.

---

## Executive Overview & Pedagogical Strategy

This 5-day teaching plan delivers a structured, real-world lesson guide for **Week 1 (10 Total Hours: 6 Hours Lecture/Theory + 4 Hours Practical Lab)**. It bridges core academic principles with real-world enterprise applications, ensuring students understand *why* business analytics decisions are made before learning *how* to execute them in Power BI Desktop.

```
Week 1 Learning Pathway:
Day 1: BI Foundations & 4 Analytics Pillars  ──► Day 2: NOIR Data Measurement Scales 
                                                            │
Day 5: Wireframing & First Power BI Import   ◄── Day 4: Chart Selection & Z-Pattern ◄── Day 3: Cognitive Load & Gestalt Principles
```

---

## Day 1: The "Why" of Data & BI Foundations
* **Allocation:** 2 Hours (Lecture & Discussion)  
* **Core Focus:** DIKW Pyramid, Analytics Lifecycle, and the 4 Analytics Pillars.

### 1. Real-World Hook (15 Mins)
* **Industry Case Context:** *"Why does Starbucks spend millions analyzing location density, foot traffic, and mobile app orders, while once-popular retail chains went bankrupt guessing?"*
* **Key Concept:** Modern enterprise leaders (Netflix, Amazon, Nike) don't rely on "gut feeling"—they build **Business Intelligence (BI)** pipelines to convert raw operational noise into competitive advantages.

### 2. Core Principles & Lecture Content (60 Mins)
* **The DIKW Pyramid Framework:**
  * **Data:** Raw, unformatted facts and figures (e.g., `ORD-9021`, `149.99`, `2026-03-15`).
  * **Information:** Structured data with contextual meaning (e.g., "Order #9021 was a $149.99 transaction on March 15, 2026").
  * **Knowledge:** Patterns and trends derived across datasets (e.g., "March sales dropped 14% compared to February across European stores").
  * **Wisdom / Action:** Strategic business decisions based on derived insights (e.g., "Reallocate $50K marketing budget from European apparel to North American electronics").
* **The Four Analytics Pillars in Practice:**
  1. **Descriptive Analytics (*What happened?*):** Historical performance tracking (e.g., Quarterly Net Revenue reports).
  2. **Diagnostic Analytics (*Why did it happen?*):** Root-cause drill-down analysis (e.g., Isolating a revenue drop to a 28% return rate in European apparel due to sizing errors).
  3. **Predictive Analytics (*What is likely to happen?*):** Machine learning forecasts and trendlines (e.g., Forecasting Q4 inventory demand based on historical seasonal spikes).
  4. **Prescriptive Analytics (*What action should be taken?*):** Automated or guided business recommendations (e.g., Triggering an automated inventory reorder when stock falls below 15 units).

### 3. Clear Teaching Pathway & Pedagogical Strategy
* Move from high-level enterprise stories to structured frameworks.
* Emphasize that Power BI is a tool used to answer specific business questions, not just a charting program.

### 4. Interactive Classroom Exercise (45 Mins)
* **Exercise: "Identify the Analytics Pillar"**
  * Present 5 corporate headlines/scenarios and have students categorize them:
    1. *"Amazon logs a 12% increase in Prime Video subscriptions during Q1."* $\rightarrow$ **Descriptive**
    2. *"Data scientists discover shipping delays caused a 30% surge in customer cancellations."* $\rightarrow$ **Diagnostic**
    3. *"Predictive models estimate 5,000 customers will churn next month."* $\rightarrow$ **Predictive**
    4. *"An automated algorithm issues $10 discount vouchers to at-risk accounts."* $\rightarrow$ **Prescriptive**

---

## Day 2: Data Types & Measurement Scales (Knowing Your Raw Material)
* **Allocation:** 2 Hours (Lecture & Applied Classification)  
* **Core Focus:** Structured vs. Unstructured Data, The NOIR Measurement Scale Framework, and Permitted Mathematical Operations.

### 1. Real-World Hook (15 Mins)
* **Industry Case Context:** *"Can you calculate the average of customer satisfaction ratings 'Poor', 'Good', and 'Excellent' the same way you calculate average monthly revenue?"*
* **Key Concept:** Misidentifying data scales causes severe mathematical errors in enterprise reports (e.g., attempting to sum Customer IDs, averaging Zip Codes, or applying linear regression to ordinal survey labels).

### 2. Core Principles & Lecture Content (60 Mins)
* **Data Architecture Classification:**
  * **Structured Data:** Tabular rows and columns with fixed schemas (e.g., SQL tables, CSV logs, Excel spreadsheets).
  * **Semi-Structured / Unstructured Data:** Flexible schemas or raw text (e.g., JSON payloads, XML, customer service chat transcripts, social media posts).
* **The NOIR Measurement Framework:**
  * **Nominal Scale:** Qualitative labels without intrinsic order or numeric value.
    * *Examples:* `Region` (*North America, Europe*), `PaymentMethod` (*Credit, PayPal*), `CustomerName`.
    * *Permitted Operations:* Count, Mode, Equality testing ($\equiv, \neq$).
  * **Ordinal Scale:** Categorical ranks with a clear intrinsic order, but non-uniform mathematical distances between ranks.
    * *Examples:* `Survey Rating` (*1-Star, 2-Star, 3-Star*), `Customer Tier` (*Bronze, Silver, Gold*), `T-Shirt Size` (*S, M, L, XL*).
    * *Permitted Operations:* Median, Percentiles, Rank Order ($>, <$). *Mathematical addition/averaging is invalid.*
  * **Interval Scale:** Ordered quantitative values with uniform intervals between units, but without an absolute true zero point.
    * *Examples:* `Temperature` (°C/°F), `Calendar Year` (*2025, 2026*), `Credit Score` (300–850).
    * *Permitted Operations:* Addition, Subtraction, Mean. *Ratios are invalid (e.g., 40°C is not "twice as hot" as 20°C).*
  * **Ratio Scale:** Quantitative measurements with uniform intervals and an absolute, non-arbitrary true zero point.
    * *Examples:* `NetSales` ($0.00 = absence of revenue), `Quantity` (0 items), `TransitDays` (0 days).
    * *Permitted Operations:* All arithmetic operations (Addition, Subtraction, Multiplication, Division, Ratios, Geometric Mean).

### 3. Clear Teaching Pathway & Pedagogical Strategy
* Teach students to inspect data fields in raw files prior to building models.
* Reinforce how Power BI automatically assigns implicit aggregations (`SUM`, `COUNT`) based on inferred data types.

### 4. Interactive Classroom Exercise (45 Mins)
* **Exercise: Dataset Variable Audit**
  * Provide students with a 10-field sample schema from the **GlobalCart E-Commerce dataset**:
    `OrderID`, `OrderDate`, `Region`, `Category`, `UnitPrice`, `Quantity`, `DiscountPct`, `OrderStatus`, `CustomerSatisfactionRating`, `NetSales`.
  * Have students map each field to its **NOIR Scale** and check permitted Power BI aggregations (`SUM`, `AVERAGE`, `COUNT`, `DISTINCTCOUNT`).

---

## Day 3: The Science of Seeing — Visual Perception & Cognitive Load
* **Allocation:** 2 Hours (Theory & Usability Audit)  
* **Core Focus:** Cognitive Load Theory, Pre-Attentive Visual Processing, Gestalt Grouping Rules, and Tufte's Data-to-Ink Ratio.

### 1. Real-World Hook (15 Mins)
* **Industry Case Context:** Compare a cluttered, dark 3D dashboard featuring 20 competing rainbow colors against a clean, executive dashboard layout.
* **Key Concept:** Executives spend an average of 5 to 10 seconds evaluating a dashboard page. If a report induces visual cognitive fatigue, it will be rejected regardless of backend data accuracy.

### 2. Core Principles & Lecture Content (60 Mins)
* **Cognitive Load Theory in Visualization:**
  * **Intrinsic Load:** The inherent complexity of the underlying data.
  * **Extraneous Load:** Unnecessary mental effort forced on the user by poor visual design, clutter, and non-standard layouts.
  * **Germane Load:** Productive mental processing dedicated to synthesizing insights and detecting patterns.
* **Pre-Attentive Visual Processing:** Visual properties processed subconsciously by the human visual cortex in under 250 milliseconds:
  * **Form:** Length, width, size, orientation, shape.
  * **Color:** Hue (categorical distinction) vs. Saturation/Luminance (quantitative value intensity).
  * **Spatial Position:** 2D canvas placement ($x, y$ coordinates).
* **Gestalt Principles of Visual Grouping:**
  * **Proximity:** Visual elements placed near each other are perceived as belonging to the same functional group.
  * **Similarity:** Elements sharing visual attributes (e.g., matching dark blue visual headers) are perceived as related metrics.
  * **Enclosure:** Placing visual boundaries or subtle background cards around visual elements groups them together logically.
  * **Continuity:** The human eye naturally follows smooth paths, aligned borders, and structured grid columns.
* **Edward Tufte’s Data-to-Ink Ratio:**
  $$\text{Data-to-Ink Ratio} = \frac{\text{Data-Ink}}{\text{Total Ink used to print/render the graphic}}$$
  * *Design Rule:* Maximize data-ink; eliminate chartjunk, redundant gridlines, heavy visual borders, and decorative 3D effects.

### 3. Clear Teaching Pathway & Pedagogical Strategy
* Train students to view dashboards through the eyes of an executive decision-maker.
* Use visual critique exercises to build design discipline before software execution.

### 4. Interactive Classroom Exercise (45 Mins)
* **Exercise: "The Great Dashboard Roast" (Usability Audit)**
  * Display a intentionally flawed sales report containing 5 major design errors:
    1. 3D Pie Chart with 14 slices.
    2. Non-zero Y-axis baseline on a bar chart skewing relative comparisons.
    3. Bright red and green colors used arbitrarily for non-performance categories.
    4. Heavy black gridlines and dark background fill.
    5. Missing visual title and unit labels.
  * Have students work in pairs to document each violation, cite the applicable design principle, and propose a specific redesign fix.

---

## Day 4: Chart Selection Framework & Visual Hierarchy
* **Allocation:** 2 Hours (Lecture & Layout Blueprinting)  
* **Core Focus:** Matching Business Questions to Chart Types and Designing "Z-Pattern" Layout Hierarchies.

### 1. Real-World Hook (15 Mins)
* **Industry Case Context:** *"Why is a Pie Chart with 12 slices the absolute worst way to show regional sales distribution to a Chief Commercial Officer?"*
* **Key Concept:** **Form follows function.** Never select a visual visual because it looks "impressive"; select it because it provides the fastest path to an accurate answer.

### 2. Core Principles & Lecture Content (60 Mins)
* **The Chart Selection Decision Framework:**
  * **Categorical Comparison:**
    * *Horizontal Bar Chart:* Best for comparing categories with long text labels (e.g., `Product Sub-Category`).
    * *Vertical Column Chart:* Best for discrete, short-label categories (e.g., `Region`, `Quarter`).
  * **Trends Over Time:**
    * *Line Chart / Area Chart:* Required when the horizontal axis represents a continuous time dimension (`Date`, `Month`, `Year`).
  * **Part-to-Whole Relationships:**
    * *Donut / Pie Chart:* Strictly limited to $\le 4$ distinct categories with significant percentage differences.
    * *Treemap:* Effective for displaying multi-level hierarchical part-to-whole data (e.g., `Category` $\rightarrow$ `Sub-Category`).
  * **Correlation & Distribution:**
    * *Scatter Plot:* Used to analyze relationships between two continuous ratio variables (e.g., `Discount %` vs. `Profit Margin`).
  * **Executive Key Performance Indicators:**
    * *Card / Multi-Row Card / KPI Visual:* Prominent single-value display reserved for core business health metrics.
* **The "Z-Pattern" Visual Layout Hierarchy:**
  * Human visual scanning in Western languages follows a top-left to bottom-right "Z" scanning pattern:
    * **Top Banner (First Look):** High-level KPI Summary Cards (`Total Revenue`, `Net Profit`, `Order Volume`).
    * **Upper-Middle Section:** High-level macro trends (`Monthly Sales Line Chart`) and primary comparisons (`Sales by Region`).
    * **Lower Section:** Micro-level breakdown tables, detailed matrix reports, and interactive slicer controls.

```
┌─────────────────────────────────────────────────────────────┐
│  [ KPI 1: Revenue ]   [ KPI 2: Profit ]   [ KPI 3: Orders ]  │ ◄─ Top Banner (KPIs)
├──────────────────────────────┬──────────────────────────────┤
│                              │                              │
│   Monthly Sales Trend        │   Sales by Region            │ ◄─ Macro Trends
│   (Line Chart)               │   (Column Chart)             │
│                              │                              │
├──────────────────────────────┴──────────────────────────────┤
│                                                             │
│   Detailed Product Performance Table                        │ ◄─ Micro Details
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 3. Clear Teaching Pathway & Pedagogical Strategy
* Teach layout composition as a visual story: **Summary $\rightarrow$ Context $\rightarrow$ Details**.

### 4. Interactive Classroom Exercise (45 Mins)
* **Exercise: Business Question to Visual Mapping**
  * Present 4 business questions and require students to specify the visual type, X-axis field, Y-axis field, and color legend:
    1. *"How has monthly net revenue trended over the past 24 months?"* $\rightarrow$ **Line Chart** (X: `OrderDate [Month]`, Y: `NetSales`).
    2. *"Which 5 product categories generate the highest total profit?"* $\rightarrow$ **Horizontal Bar Chart** (X: `Profit`, Y: `Category`).
    3. *"What proportion of orders are Delivered vs. Returned?"* $\rightarrow$ **Donut Chart** (Legend: `OrderStatus`, Value: `OrderCount`).
    4. *"Is there a relationship between shipping delay days and return rates?"* $\rightarrow$ **Scatter Plot** (X: `DelayDays`, Y: `ReturnRate %`).

---

## Day 5: Hands-On Lab — Dashboard Wireframing & Power BI Desktop Walkthrough
* **Allocation:** 2 Hours (Practical Lab)  
* **Core Focus:** Low-Fidelity Paper Wireframing, Software Ingestion, and Workspace Controls.

### 1. Real-World Hook (15 Mins)
* **Industry Case Context:** *"Paper before Power BI!"* Senior BI consultants never open software without first sketching a validated paper wireframe with executive stakeholders.

### 2. Practical Hands-On Lab Guided Steps (105 Mins)

#### **Task 1: Low-Fidelity Paper Wireframing (30 Mins)**
* Students take out paper and draw a low-fidelity grid layout for our **LogiX Logistics Supply Chain case study**:
  * **Header Zone:** Title Banner (*Logistics & OTIF Performance Dashboard*) and 3 KPI Cards (`Total Shipments`, `OTIF %`, `SLA Penalty Fees`).
  * **Body Zone:** Line Chart (*Transit Days Trend by Carrier*) next to a Clustered Bar Chart (*Shipments by Origin Hub*).
  * **Footer Zone:** Interactive Slicer sidebar on the left and Detailed Carrier Performance Table on the right.

#### **Task 2: Power BI Desktop Installation & Environment Walkthrough (30 Mins)**
* Students launch **Microsoft Power BI Desktop** on their workstations and explore the primary navigation interface:
  * **Report View:** Canvas area, gridlines, page controls.
  * **Data View:** Inspecting table fields, rows, and data types.
  * **Model View:** Viewing relationships between tables.
  * **Key Panes:** Fields Pane, Visualizations Pane, Filters Pane, and Home Ribbon.

#### **Task 3: First Flat File Data Ingestion & KPI Card Creation (45 Mins)**
1. Click **Get Data $\rightarrow$ Text/CSV** on the Home Ribbon.
2. Browse and select `GlobalCart_ECommerce_Transactions.csv`.
3. Preview the dataset in the dialog window and click **Load**.
4. Verify table arrival in the **Fields Pane**.
5. Drag `NetSales` onto the canvas; Power BI generates a default bar chart.
6. In the **Visualizations Pane**, click the **Card Visual** icon to transform the bar chart into an executive summary card displaying Total Net Sales.
7. Save the Power BI project file as `Week1_Sales_Baseline.pbix`.

---

## Student Deliverable & Assessment (Week 1 Milestone)

* **Assignment 1 Title:** **Visual Design Audit, Wireframe Portfolio & Baseline Setup**
* **Submission Components:**
  1. **Part A (Report Audit):** 1-page written critique documenting 5 visual rule violations from a flawed sample report with proposed redesign fixes.
  2. **Part B (Wireframe Blueprint):** A visual wireframe sketch following Z-pattern hierarchy rules for an e-commerce dashboard.
  3. **Part C (Power BI File):** A `.pbix` file confirming dataset import from CSV and displaying 3 summary KPI cards.
* **Weightage:** 5% of Total Course Grade.

---

## Complete Reference Artifacts in Your Studio Panel

All supporting documents and datasets referenced in this teaching plan are available:
* **`power_bi_week1_lecture_notes_and_practical_guide-v2.md`** — Comprehensive week 1 guide with expanded case studies.
* **`GlobalCart_ECommerce_Transactions.csv`** — Practice dataset for Day 2 and Day 5 lab ingestion.
* **`power_bi_unit1_and_2_theory_exam.md`** — Mid-term theory exam covering Units I & II.
