# 📘 Time Intelligence in Power BI (YTD, LY, YoY%)

## 📌 Project Overview
This Power BI project demonstrates how to implement **time intelligence** using **DAX measures** for key performance indicators like:

- **Year-To-Date (YTD)**
- **Last Year (LY)**
- **Year-over-Year % Change (YoY%)**
- **Dynamic switching** between metrics using a slicer

The model uses a star schema with `FactSales` and a well-formatted `DimDate` table to enable time-based analysis.

---

## 🧱 Model Structure

### Tables Used:
- **FactSales**: Contains sales data (Quantity, Revenue, Dates)
- **DimDate**: Custom-built Date Table with fields like `Date`, `Year`, `MonthName`, `Quarter`, `DayOfWeek`, etc.
- **MeasureTable** (Disconnected): Holds the metric selection slicer (e.g., "Revenue", "Quantity")

### Relationships:
- `FactSales[OrderDate]` ➝ `DimDate[Date]` (Many-to-One, Single Direction)

---

## 📊 DAX Measures

### Basic Measures
```DAX
Total Quantity = SUM(FactSales[Quantity])
Total Revenue = SUM(FactSales[Revenue])
