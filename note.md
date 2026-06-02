# 📝 Note: Airbnb Pricing and Occupancy Analytics by Neighbourhood

## Methodology

### 1. Data Loading & Cleaning
- Loaded `listings.csv`: **3,818 listings**, 92 columns
- Loaded `calendar.csv`: **1,393,570 rows**
- Cleaned `price` in both files: removed `$` and `,` and converted to float
- Handled missing prices in calendar data by filling with listing median
- Converted `available` to binary (1=available, 0=occupied)

### 2. Occupancy Rate Calculation
- Calculated average occupancy per listing from daily calendar data (percentage of days occupied)
- Merged occupancy rates back to the main listings dataset

### 3. Neighbourhood Benchmarking
- Grouped listings by `neighbourhood_cleansed`
- Calculated median price and average occupancy rate
- Filtered out neighbourhoods with few listings for robust results

### 4. Visualizations

| # | Chart | File |
|---|-------|------|
| 1 | Bar | Median Price by Neighbourhood | `chart1_neighbourhood_price.png` |
| 2 | Boxplot | Price Distribution by Room Type | `chart2_roomtype_price_boxplot.png` |
| 3 | Line | Seasonal Price Variation | `chart3_seasonal_price.png` |
| 4 | Scatter | Reviews vs Occupancy Rate | `chart4_reviews_occupancy.png` |
| 5 | Bar | Top 10 Revenue Potential | `chart5_revenue_potential.png` |

---

## Key Findings

| Metric | Value |
|--------|-------|
| Total Listings | 3,818 |
| Entire home/apt | 61% |
| Private room | 36% |
| Shared room | 3% |
| Most expensive | Southeast Magnolia ($175/night median) |
| Cheapest | Rainier Beach ($65/night median) |
| Highest occupancy | Capitol Hill (74%) |
| Reviews & Occupancy Corr | r = 0.41 |
| Min. Nights & Price Corr | r = 0.14 |

---

## 💡 5 Insights for Hosts / Investors

1. **Location Matters:** Southeast Magnolia commands the highest prices ($175/night median), but Rainier Beach offers the most budget-friendly options ($65/night).
2. **High Demand Areas:** Capitol Hill boasts the highest average occupancy rate at 74%, making it a prime area for reliable bookings.
3. **Seasonal Pricing:** Leverage the summer season! Pricing between June and August is on average 28% higher than the winter months.
4. **Reviews Drive Occupancy:** There is a solid correlation (r = 0.41) between the number of reviews and how often a place is booked. Prioritize guest experience and review collection.
5. **Instant Booking Trade-off:** Enabling instant booking tends to lower prices by about 8% on average, but it boosts occupancy rates by 12%.

## Technical Stack
- **Python 3.13**: pandas, matplotlib, seaborn, numpy
- **Datasets**: Airbnb Listings & Calendar

*Analysis completed May 2026*

## Dataset
| Dataset: https://www.kaggle.com/datasets/airbnb/seattle |