# Global-Ecommerce-Revenue-Analytics
Power BI interactive dashboard analyzing retail revenue patterns, regional expansion opportunities, top customer segments, and monthly 2011 demand trends for online retail store

## Context (The Business Scenario)
The CEO and CMO of an international online retail enterprise required data-driven insights to shape their global expansion strategy and customer retention programs. The transactional dataset contained operational anomalies (negative order quantities from customer returns and non-positive unit prices) that required structured data hygiene rules in Power Query before analyzing monthly trends, international demand, and customer valuation.



## Data Governance & Data Cleaning Rules
Before constructing executive visuals, the following transformation rules were executed:
- **Quantity Audit:** Applied conditional filtering (`Quantity >= 1`) to eliminate product returns, cancelled orders, and negative entries.
- **Unit Price Audit:** Filtered out records with invalid zero or negative pricing (`UnitPrice > 0`).
- **Calculated Metrics:** Generated explicit custom column `Revenue` calculated as `Quantity * UnitPrice`.

  <img width="1271" height="425" alt="Online store" src="https://github.com/user-attachments/assets/53c791e3-0cac-4b8b-8d8e-457e27599828" />



## Key Executive Insights & Visual Breakdown

### 1. 2011 Monthly Revenue Trend Analysis (CEO Request)
- **Visual Type:** Time-Series Line Chart (`Sum of Revenue by Month For 2011`)
- **Key Data Points:** Revenue opens at **$0.63M** in January, hits a mid-year baseline averaging **~$0.65M–$0.70M** (May–August), accelerates through Q3/Q4 from **$0.99M** (September) to a peak of **$1.37M** in November, before dropping to **$0.59M** in December.
- **Business Insight:** Demand experiences explosive scaling starting in September, reaching maximum peak volume during the November pre-holiday shopping surge.

- <img width="800" height="457" alt="QST1" src="https://github.com/user-attachments/assets/720b981f-aa86-4a93-b198-ed5dcab3b434" />


### 2. Top 10 International Countries by Revenue & Quantity (CMO Request)
- **Visual Type:** Clustered Bar/Column Chart (`Sum of Revenue and Sum of Quantity by Country`, *excluding United Kingdom*)
- **Key Data Points:** 
  - **Netherlands:** #1 Market (**$285K** Revenue | **200K** Units Sold)
  - **EIRE:** #2 Market (**$269K** Revenue | **147K** Units Sold)
  - **Germany:** #3 Market (**$222K** Revenue | **119K** Units Sold)
  - **France:** #4 Market (**$197K** Revenue | **112K** Units Sold)
  - **Australia:** #5 Market (**$138K** Revenue | **84K** Units Sold)
- **Business Insight:** Netherlands, EIRE, Germany, and France dominate total non-UK international sales, serving as the core drivers for European expansion.

  <img width="821" height="442" alt="QST 2" src="https://github.com/user-attachments/assets/a031c70b-36d4-4cff-bb3c-ffa6b09e3ba4" />


### 3. Top 10 Customers by Revenue Contribution (CMO Request)
- **Visual Type:** Ranked Horizontal Bar Chart (`Sum of Revenue by CustomerID`)
- **Key Data Points:** 
  - **CustomerID 14646:** Top contributor at **$279.68K**
  - **CustomerID 18102:** Second largest contributor at **$259.65K**
  - **CustomerID 17450:** Third largest contributor at **$194.55K**
  - *Followed by:* 16446 ($168.47K), 14911 ($135.00K), 12415 ($124.44K), 14156 ($116.47K), 17511 ($91.01K), 12346 ($77.18K), and 16029 ($72.88K).
- **Business Insight:** High revenue concentration exists within top accounts (top two accounts alone generate over $539K), highlighting key revenue dependency risks.

  <img width="744" height="443" alt="QST 3" src="https://github.com/user-attachments/assets/6249fe33-dc3b-40d9-90cb-e3c45a0c9b0b" />


### 4. Global Demand & Regional Density Map (CEO Request)
- **Visual Type:** Interactive World Map (`Sum of Quantity by Country`, *excluding United Kingdom*)
- **Key Data Points:** Visual density highlights strong unit distribution concentrated across Western/Central Europe, North America, South America, Saudi Arabia, South Africa, and Australia/Japan.
- **Business Insight:** Demand is heavily concentrated in European markets. Regions like Asia, Africa, and Russia show zero existing sales, representing prime untapped targets for international expansion strategies.


<img width="803" height="468" alt="QST 4" src="https://github.com/user-attachments/assets/bca2a006-ea27-4e86-bb8a-35ce3c6b4ecc" />

## Executive Recommendations & Strategic Impact
- **Procurement & Inventory Planning:** Supply chains must ramp up inventory procurement starting in early August to prepare for the proven **$1.37M** November peak.
- **Key Account VIP Program:** Implement dedicated account management and custom pricing structures for top individual buyers like **CustomerID 14646** and **18102** to safeguard high-concentration revenue streams.
- **Fulfillment Expansion:** Prioritize regional logistics infrastructure in **Netherlands, EIRE, and Germany** to capture existing high-volume demand efficiently.

---

## Tools & Technologies Used
- **Business Intelligence Tools:** Microsoft Power BI Desktop
- **ETL & Data Transformation:** Power Query (M Language)
- **Geographic & Spatial Analytics:** Bing Maps Visualizer
