# Self-Serve Kiosks Sales Analysis – Addition Technologies Pvt Ltd

## Overview
This project analyzes **self-serve kiosk sales data** for **Addition Technologies Pvt Ltd**, a self-serve kiosks company operating in Bangalore.  
The analysis covers **4 client restaurants** over **3 months (October – December 2025)** and delivers two Power BI-ready dashboards:

- **Dashboard 1** – Individual restaurant food-item level sales analysis
- **Dashboard 2** – Company-level monthly sales comparison & customer footfall across all 4 clients

### Client Restaurants (Bangalore)
| Client | Type |
|--------|------|
| Veena Stores | South Indian food store |
| Rameshwaram Cafe | South Indian restaurant |
| Bigbyte | Multi-cuisine fast food |
| Asha Sweets | Sweets, snacks & beverages |

---

## Project Structure
```
Sales-Data-Analysis/
│
├── README.md                            # Project documentation
│
├── Self_Serve_Kiosks_Sales_Data.csv     # Raw generated kiosks sales dataset (93,100 rows)
├── Kiosks_Sales_PowerBI_Ready.csv       # Cleaned & Power BI-ready export
│
├── Kiosks_Sales_Analysis.ipynb          # Jupyter Notebook – data generation, EDA & dashboards
│
├── kpi_summary.png                      # Company KPI cards (Oct–Dec 2025)
├── dashboard1_top_items.png             # D1: Top food items by net sales (all 4 restaurants)
├── dashboard1_top_qty.png               # D1: Top food items by quantity sold
├── dashboard1_category_pie.png          # D1: Sales by menu category per restaurant
├── dashboard1_monthly_bar.png           # D1: Monthly net sales grouped bar chart
├── dashboard1_payment_mode.png          # D1: Payment mode distribution
├── dashboard2_monthly_trend.png         # D2: Monthly sales trend line (all 4 restaurants)
├── dashboard2_stacked_bar.png           # D2: Stacked monthly sales comparison
├── dashboard2_footfall_trend.png        # D2: Monthly customer footfall trend
├── dashboard2_footfall_bar.png          # D2: Footfall grouped bar by restaurant & month
├── dashboard2_sales_share_donut.png     # D2: Total sales share donut chart
├── dashboard2_avg_txn_value.png         # D2: Average transaction value per restaurant
└── dashboard2_weekend_weekday.png       # D2: Weekday vs weekend footfall comparison
```

---

## Dataset Schema (`Kiosks_Sales_PowerBI_Ready.csv`)

| Column | Description |
|--------|-------------|
| `Transaction_ID` | Unique transaction identifier |
| `Date` | Date of order (YYYY-MM-DD) |
| `Month` | Month label (October / November / December 2025) |
| `Month_Num` | Month number (10, 11, 12) |
| `Year` | Year (2025) |
| `Day_of_Week` | Day name (Monday–Sunday) |
| `Order_DateTime` | Exact date and time of kiosk order |
| `Restaurant` | Client restaurant name |
| `Kiosk_ID` | Self-serve kiosk terminal ID |
| `Customer_ID` | Unique customer identifier per visit |
| `Food_Item` | Name of the food/beverage ordered |
| `Category` | Menu category (e.g. South Indian, Fast Food, Sweets) |
| `Unit_Price` | Price per single unit (₹) |
| `Quantity` | Number of units ordered |
| `Total_Sales` | Gross sales (Unit_Price × Quantity) |
| `Discount` | Discount applied (₹) |
| `Net_Sales` | Net revenue after discount |
| `Payment_Mode` | UPI / Card / Cash |
| `City` | Location city (Bangalore) |
| `Is_Weekend` | True if Saturday or Sunday |
| `Is_Festival_Day` | True if a festival/holiday date |

---

## Technologies Used
- **Python** (Pandas, NumPy, Matplotlib, Seaborn)
- **Jupyter Notebook**
- **Power BI** (for interactive dashboards)

---

## Key Steps

1. **Data Generation**
   - Simulated realistic kiosk order data for 4 Bangalore restaurants
   - 93,100 transactions across October–December 2025
   - Includes festival-day and weekend demand spikes

2. **Data Cleaning & Validation**
   - Verified no null values or duplicates
   - Correct data types for all columns
   - Exported Power BI-ready CSV

3. **Dashboard 1 – Individual Restaurant Analysis**
   - Top 10 food items by net sales (horizontal bar chart)
   - Top 10 food items by quantity sold
   - Sales by menu category (donut chart)
   - Monthly net sales trend (grouped bar)
   - Payment mode distribution (pie chart)

4. **Dashboard 2 – Company-Level Analysis**
   - Monthly sales trend line (Oct–Dec 2025) for all 4 restaurants
   - Stacked monthly sales comparison
   - Monthly customer footfall trend on self-serve kiosks
   - Footfall grouped bar by restaurant & month
   - Total sales share donut chart
   - Average transaction value per restaurant
   - Weekday vs weekend footfall comparison

---

## Company KPIs (Oct – Dec 2025)

| KPI | Value |
|-----|-------|
| 💰 Total Net Sales | ₹90,18,570 |
| 🧾 Total Transactions | 93,100 |
| 👣 Unique Customer Footfall | 54,766 |
| 📦 Total Items Sold | 1,07,053 |
| 🏆 Top Restaurant by Sales | Bigbyte |
| 💳 Avg Total Spend per Unique Customer (3 months) | ₹165 |

---

## Power BI Import Instructions

1. Open **Power BI Desktop**
2. Click **Get Data → Text/CSV** → select `Kiosks_Sales_PowerBI_Ready.csv`
3. Set `Date` column type → **Date**; `Order_DateTime` → **Date/Time**
4. Set `Month` as text with sort-by column = `Month_Num`
5. Add slicers on **Month** and **Restaurant** for interactivity

### Dashboard 1 Visuals (one page per restaurant)
| Visual | Axis | Values | Filter |
|--------|------|--------|--------|
| Clustered Bar Chart | Food_Item | Sum of Net_Sales | Restaurant |
| Clustered Bar Chart | Food_Item | Sum of Quantity | Restaurant |
| Donut Chart | Category | Sum of Net_Sales | Restaurant |
| Grouped Bar | Month | Sum of Net_Sales | Restaurant |
| Card KPIs | — | Total Sales, Transactions, Footfall | — |

### Dashboard 2 Visuals (company summary page)
| Visual | Axis | Values | Legend |
|--------|------|--------|--------|
| Line Chart | Month | Net_Sales | Restaurant |
| Stacked Bar | Month | Net_Sales | Restaurant |
| Line Chart | Month | Count of Customer_ID | Restaurant |
| Donut Chart | Restaurant | Net_Sales | — |
| Grouped Bar | Restaurant | Count of Customer_ID | Is_Weekend |
| Card KPIs | — | Total Sales, Footfall, Best Month | — |

---

## Insights & Outcomes
- **Bigbyte** leads in total net sales (₹40.8L) driven by higher per-item prices
- **Rameshwaram Cafe** has the highest customer footfall (~17,113 unique customers)
- **December 2025** is the peak month across all restaurants (festival + year-end boost)
- **UPI** is the dominant payment mode (~55% of all transactions)
- **Weekends** generate ~30% more footfall than weekdays across all outlets
