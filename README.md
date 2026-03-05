# Self-Serve Kiosks Sales Analysis – Addition Technologies Pvt Ltd

## Overview
This project analyzes **self-serve kiosk sales data** for **Addition Technologies Pvt Ltd**, a self-serve kiosks company operating in Bangalore.  
The analysis covers **4 client restaurants** over **3 months (October – December 2025)** and delivers two focused dashboards:

| # | Dashboard Title |
|---|----------------|
| **Dashboard 1** | Kiosk Sales Analytics – Food Item Revenue of All Clients/Restaurants (Oct–Dec 2025) |
| **Dashboard 2** | Sales Comparison of All 4 Clients (Oct–Dec 2025) |

### Client Restaurants (Bangalore) — Sales Rank
| Rank | Client | Type |
|------|--------|------|
| 🥇 1 | **Veena Stores** | South Indian food store |
| 🥈 2 | **Rameshwaram Cafe** | South Indian restaurant |
| 🥉 3 | **Asha Sweets** | Sweets, snacks & beverages |
| 4 | **Bigbyte** | Multi-cuisine fast food |

---

## Project Structure
```
Sales-Data-Analysis/
│
├── README.md                            # Project documentation
│
├── Self_Serve_Kiosks_Sales_Data.csv     # Raw kiosks sales dataset (136,804 rows)
├── Kiosks_Sales_PowerBI_Ready.csv       # Cleaned & Power BI-ready export
│
├── Kiosks_Sales_Analysis.ipynb          # Jupyter Notebook – data generation & dashboards
│
├── d1_kpis.png                          # Dashboard 1: KPI cards
├── d1_top15_items_combined.png          # Dashboard 1: Top 15 food items by revenue (all restaurants)
├── d1_items_by_restaurant.png           # Dashboard 1: Top 12 food items split by restaurant
├── d1_category_revenue.png              # Dashboard 1: Revenue by menu category (donut + bar)
│
├── d2_kpis.png                          # Dashboard 2: Per-restaurant KPI cards
├── d2_monthly_trend.png                 # Dashboard 2: Monthly sales trend line (all 4 clients)
├── d2_monthly_grouped_bar.png           # Dashboard 2: Monthly grouped bar comparison
├── d2_sales_share_donut.png             # Dashboard 2: Total revenue share donut chart
└── d2_footfall_trend.png                # Dashboard 2: Monthly customer footfall trend
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
| `Category` | Menu category (South Indian, Fast Food, Sweets, etc.) |
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
   - 136,804 transactions across October–December 2025
   - Demand shaped by festival days, weekends, and peak hours

2. **Data Cleaning & Validation**
   - Zero null values or duplicates
   - All column types verified
   - Exported Power BI-ready CSV

3. **Dashboard 1 – Kiosk Sales Analytics: Food Item Revenue (All Clients)**
   - KPI cards: Total Revenue, Transactions, Footfall, Items Sold, Best Item, Top Restaurant
   - Top 15 food items by combined revenue (all 4 restaurants)
   - Top 12 food items split by restaurant (stacked bar)
   - Revenue by menu category (donut + horizontal bar)

4. **Dashboard 2 – Sales Comparison of All 4 Clients**
   - Per-restaurant KPI cards: Revenue, Transactions, Footfall, Best Month
   - Monthly sales trend line (Oct–Dec 2025)
   - Monthly grouped bar comparison
   - Total revenue share donut chart
   - Monthly customer footfall trend on self-serve kiosks

---

## Company KPIs (Oct – Dec 2025)

| KPI | Value |
|-----|-------|
| 💰 Total Net Revenue | ₹107.88L |
| 🧾 Total Transactions | 1,36,804 |
| 👣 Unique Customer Footfall | 80,277 |
| 📦 Total Items Sold | 1,57,306 |
| 🥇 Best Selling Food Item | Masala Dosa (₹9.87L revenue) |
| 🏆 Top Restaurant | Veena Stores |

### Revenue by Restaurant
| Rank | Restaurant | Net Revenue |
|------|-----------|-------------|
| 🥇 1 | Veena Stores | ₹36.13L |
| 🥈 2 | Rameshwaram Cafe | ₹31.79L |
| 🥉 3 | Asha Sweets | ₹24.26L |
| 4 | Bigbyte | ₹15.71L |

---

## Power BI Import Instructions

1. Open **Power BI Desktop**
2. **Get Data → Text/CSV** → select `Kiosks_Sales_PowerBI_Ready.csv`
3. Set `Date` → **Date**; `Order_DateTime` → **Date/Time**
4. Sort `Month` column by `Month_Num`
5. Add slicers on **Month** for Oct / Nov / Dec filtering

### Dashboard 1 – Kiosk Sales Analytics: Food Item Revenue
| Visual | Field | Values | Notes |
|--------|-------|--------|-------|
| KPI Cards (6) | — | Total Revenue, Transactions, Footfall, Items Sold, Best Item, Top Restaurant | — |
| Horizontal Bar | Food_Item | Sum of Net_Sales | Top N = 15, all restaurants |
| Stacked Bar | Food_Item | Net_Sales | Legend = Restaurant, Top 12 items |
| Donut + Bar | Category | Net_Sales | All restaurants combined |
| Month Slicer | Month | — | Oct / Nov / Dec |

### Dashboard 2 – Sales Comparison of All 4 Clients
| Visual | Field | Values | Legend |
|--------|-------|--------|--------|
| KPI Cards (4) | Restaurant | Revenue, Transactions, Footfall, Best Month | per restaurant |
| Line Chart | Month | Net_Sales | Restaurant |
| Grouped Bar | Month | Net_Sales | Restaurant |
| Donut Chart | Restaurant | Net_Sales | — |
| Line Chart | Month | Count of Customer_ID | Restaurant |

---

## Key Insights
- **Veena Stores** leads all 4 restaurants with ₹36.13L revenue — highest kiosk adoption driven by daily breakfast demand
- **Masala Dosa** is the single best-selling item across all restaurants (₹9.87L combined)
- **South Indian** is the top-grossing category (34.6% revenue share)
- **October 2025** was the peak month across all restaurants
- **UPI** is the dominant payment mode (~55% of all transactions)
- **Weekends** generate ~30% more footfall than weekdays
