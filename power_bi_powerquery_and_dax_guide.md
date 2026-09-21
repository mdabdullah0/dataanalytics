# Power Query Import Guide & DAX Practice Exercises

**Dataset Reference:** `GlobalCart_PowerBI_Sample_Dataset.xlsx`  
**Target Modules:** Preprocessing (Unit II / Lab Unit 1 & 2) & Data Modeling / DAX (Unit III / Lab Unit 3)  
**Target Outcomes:** **CO2** (Data Transformation) & **CO3** (DAX Measures & Modeling)

---

## Part 1: Step-by-Step Power Query Import & Preprocessing Guide

This guide walks through loading, cleaning, and transforming raw Excel sheets into a star-schema ready data model using **Power Query Editor**.

### Step 1: Connecting to the Dataset
1. Launch **Power BI Desktop**.
2. On the **Home** ribbon, click **Get Data** $\rightarrow$ select **Excel Workbook**.
3. Browse and select `GlobalCart_PowerBI_Sample_Dataset.xlsx`.
4. In the **Navigator** dialog, check all three sheets:
   * `Sales Transactions`
   * `Logistics Shipments`
   * `Regional Targets`
5. Click **Transform Data** (Do NOT click Load directly). This opens the **Power Query Editor**.

---

### Step 2: Data Cleaning & Transformation Tasks

#### Task 2.1 — Data Hygiene & Filtering (`Sales Transactions`)
1. **Promote Headers:** Ensure the first row contains proper column headers (`OrderID`, `OrderDate`, etc.). If not, go to **Home** $\rightarrow$ **Use First Row as Headers**.
2. **Verify Data Types:**
   * `OrderDate`: Change to **Date**.
   * `UnitPrice`, `GrossSales`, `DiscountAmount`, `NetSales`: Change to **Fixed Decimal Number (Currency)**.
   * `Quantity`: Change to **Whole Number**.
   * `DiscountPct`: Change to **Percentage**.
3. **Filter Out Cancelled Orders:**
   * Click the drop-down arrow on `OrderStatus`.
   * Uncheck `Cancelled` to isolate revenue-generating or returned records.
4. **Handle Null Values in `ReturnReason`:**
   * Select the `ReturnReason` column.
   * Go to **Transform** tab $\rightarrow$ **Replace Values**.
   * Value To Find: `null` (or leave blank) $\rightarrow$ Replace With: `Not Applicable (Delivered)`.

#### Task 2.2 — Creating Custom & Conditional Columns
1. **Create Net Margin Conditional Column:**
   * Go to **Add Column** tab $\rightarrow$ **Conditional Column**.
   * Column Name: `Discount Severity`.
   * Rule:
     * If `DiscountPct` $\ge 0.15$ then `"High Discount"`
     * Else If `DiscountPct` $> 0.00$ then `"Standard Discount"`
     * Else `"No Discount"`.
2. **Add Custom Profit Calculation:**
   * Click **Custom Column**.
   * Column Name: `Estimated Margin`.
   * Formula: `[NetSales] * 0.35` (assuming 35% average gross margin).

#### Task 2.3 — Preprocessing Logistics & Targets
1. In `Logistics Shipments`:
   * Set `DispatchDate` to **Date**.
   * Set `SLAPenaltyAmount` to **Fixed Decimal Number**.
   * Ensure `OTIFStatus` contains clean string values (`On-Time` vs. `SLA Breach`).
2. Click **Close & Apply** on the top left of the Home ribbon to load transformed data into the Power BI Data Model.

---

## Part 2: DAX Practice Tasks & Metric Library

DAX (Data Analysis Expressions) formulas calculate custom metrics over your data model.

### 1. Fundamental Calculated Columns vs. Measures
* **Calculated Column:** Evaluated row-by-row during data refresh (stored in memory).
* **Measure:** Evaluated dynamically on-the-fly based on report filter context (recommended for aggregations).

---

### 2. Core Aggregation Measures

#### Exercise 1: Total Net Sales
```dax
Total Net Sales = 
SUM('Sales Transactions'[NetSales])
```

#### Exercise 2: Total Orders Count
```dax
Total Orders = 
DISTINCTCOUNT('Sales Transactions'[OrderID])
```

#### Exercise 3: Average Order Value (AOV)
```dax
Average Order Value = 
DIVIDE([Total Net Sales], [Total Orders], 0)
```

---

### 3. Conditional & Ratio Measures

#### Exercise 4: Total Returned Orders
```dax
Returned Orders Count = 
CALCULATE(
    [Total Orders],
    'Sales Transactions'[OrderStatus] = "Returned"
)
```

#### Exercise 5: Return Rate Percentage
```dax
Return Rate % = 
DIVIDE([Returned Orders Count], [Total Orders], 0)
```

#### Exercise 6: On-Time Delivery Rate (OTIF %)
```dax
OTIF % = 
DIVIDE(
    CALCULATE(COUNTROWS('Logistics Shipments'), 'Logistics Shipments'[OTIFStatus] = "On-Time"),
    COUNTROWS('Logistics Shipments'),
    0
)
```

---

### 4. Time Intelligence Measures

*Note: Ensure a dedicated Date Table (`DimDate`) is marked as a Date Table in Power BI.*

#### Exercise 7: Year-to-Date (YTD) Revenue
```dax
Sales YTD = 
TOTALYTD([Total Net Sales], 'DimDate'[Date])
```

#### Exercise 8: Prior Year (PY) Revenue
```dax
Sales Prior Year = 
CALCULATE(
    [Total Net Sales],
    SAMEPERIODLASTYEAR('DimDate'[Date])
)
```

#### Exercise 9: Year-over-Year (YoY) Sales Growth %
```dax
YoY Sales Growth % = 
VAR _CurrentSales = [Total Net Sales]
VAR _PYSales = [Sales Prior Year]
RETURN
    DIVIDE(_CurrentSales - _PYSales, _PYSales, 0)
```

---

### 5. Target Variance DAX Measures

#### Exercise 10: Target Variance
```dax
Sales vs Target Variance = 
VAR _ActualSales = [Total Net Sales]
VAR _TargetSales = SUM('Regional Targets'[TargetRevenue])
RETURN
    _ActualSales - _TargetSales
```

---

## Part 3: Student Lab Assignment Requirements

1. Load `GlobalCart_PowerBI_Sample_Dataset.xlsx` into Power BI Desktop following **Part 1**.
2. Create a **Measures Table** named `_AllMeasures` to organize DAX metrics.
3. Write DAX measures 1 through 10 as listed in **Part 2**.
4. Construct a 2-page dashboard:
   * **Page 1:** Executive Sales & Return Rate Overview (featuring `Total Net Sales`, `AOV`, `Return Rate %`, and `YoY Growth`).
   * **Page 2:** Logistics OTIF Performance & SLA Penalty Tracker.
