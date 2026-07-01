# 📱 PhonePe Payment Insights Dashboard

![PhonePe Dashboard](images/dashboard-image.jpg)

## 📊 Overview
A professional Power BI dashboard analyzing 300K+ transaction records to provide actionable insights into user demographics, payment behaviors, and service usage.

---

## 🛠️ 1. Data Preparation & Transformation
- **Data Source:** Processed 300,000 rows of raw transaction data using Power Query.
- **Payment Status Formatting:** Standardized payment statuses by keeping "Failed" and "Successful", and replacing all other extraneous values with **"Pending"** for clarity.
- **Demographic Segmentation:** Added a conditional column in the `All_Users` table to group users by generation:
  - **GenZ:** `<= 26`
  - **Millennials:** `<= 42`
  - **GenX:** `<= 58`
  - **Boomers:** `Else` (> 58)

---

## 📅 2. Data Modeling
Generated a custom **Date Table** to enable accurate time-intelligence tracking (e.g., Month-over-Month metrics) across the dashboard.

```dax
Date_Table = ADDCOLUMNS(
    CALENDAR(MIN(All_Transactions[Date]), MAX(All_Transactions[Date])),
    "Year", YEAR([Date]),
    "Month No.", MONTH([Date]),
    "Month", FORMAT([Date], "mmm"),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Weekday", FORMAT([Date], "dddd"),
    "Day No.", WEEKDAY([Date], 2),
    "Weekend", IF(WEEKDAY([Date], 2) >= 6, "Weekend", "Weekday")
)
