# 🚚 Supply Chain, Inventory & Supplier Quality Optimization

![Executive Overview](Dashboard_Screenshots/1_Executive_Overview.png)

## 📌 Executive Summary & Client Problem Statement

Organizations managing multi-tier supply chains face margin erosion due to **inventory stock-outs on high-velocity SKUs, prolonged supplier lead times, elevated supplier defect rates (driving downstream warranty/replacement costs), and inefficient expedited shipping**.

This end-to-end consulting analytics project evaluates **100 SKUs** using **Python, PostgreSQL, Excel, and Power BI**. It diagnoses operational bottlenecks and charts a transformation from a reactive, spreadsheet-driven **As-Is state** to an automated, ERP/BI-integrated **To-Be enterprise environment**.

---

## 🧭 Consulting Framework & Requirement Traceability Matrix (RTM)

### As-Is vs. To-Be Enterprise Workflow
* **As-Is Process:** Siloed procurement and quality records across disconnected spreadsheets $\rightarrow$ excessive working capital tied up in low-margin stock $\rightarrow$ **36% of completed quality inspections failing** and over-reliance on expensive Air freight.
* **To-Be Enterprise Process:** Automated ingestion of **SAP MM / ERP** inventory logs into **PostgreSQL** $\rightarrow$ **Python** ABC-differentiated Safety Stock and Reorder Point ($ROP$) engine $\rightarrow$ real-time **Power BI** control tower triggering automated purchase requisitions.

### Requirement Traceability Matrix (RTM)
| Req ID | Client Business Requirement | Analytical Solution (`Python` / `SQL` / `Power BI`) | Quantified Finding & Strategic Impact |
| :--- | :--- | :--- | :--- |
| **BR-01** | Optimize working capital & prevent stockouts | ABC revenue segmentation & lead-time adjusted Reorder Point ($ROP$) model | **Class A SKUs** generate 70% of revenue but face stockout risks due to static buffering; implemented dynamic $ROP = d \times L + SS$ to protect high-velocity sales. |
| **BR-02** | Reduce supplier warranty & rework costs | SQL CTE Supplier benchmarking & Warranty Cost calculation | **Supplier 1** leads in revenue with the lowest defect rate (1.80%); **Supplier 5** has the highest mean defect rate (2.67%), driving targeted vendor consolidation. |
| **BR-03** | Optimize logistics spend vs. transit speed | Multimodal route cost vs. transit-time distribution analysis | Mode-shift strategy: **Road** provides the optimal balance (4.72 days avg, $540 median cost) vs. expensive **Air** ($628 median) and slow **Sea** (7.12 days avg). |
| **BR-04** | Maximize product-line profitability | Gross margin `(Price - Mfg Cost) / Price` decomposition | Identified true product-line margin leaders, correcting legacy revenue-only reporting to prioritize high-margin replenishment. |

---

## 📊 Interactive Power BI Dashboard Modules

1. **Executive Overview:** Tracks total revenue, product performance, and defect monitoring.
2. **Inventory & Supplier Quality:** Evaluates production volumes and quality inspection pass/fail distributions.
3. **Logistics & Profitability:** Analyzes transportation mode economics vs. transit times.
4. **Business Insights:** Actionable recommendations for procurement and carrier routing.

---

## 📈 Financial Business Case & Key Recommendations

* **Logistics Rebalancing:** A recommended shift of non-urgent Air freight (median $628) to Road transport (median $540) yields a projected **14% reduction in per-route logistics costs**, without sacrificing transit speed. (Sea freight remains cheapest at $323 but averages a slow 7.12-day transit).
* **Inventory Capital Reallocation:** Implementing the Python-based ABC-ROP model automatically reallocates safety stock away from slow-moving Class C items and toward Class A SKUs, maximizing service levels for the top 70% of revenue generators.
* **Supplier Consolidation:** Transitioning order volume away from Supplier 4 (highest manufacturing cost & highest inspection failure rate) toward Supplier 1 will directly reduce estimated warranty replacement costs.

---

## ⚠️ Data Limitations & Modeling Assumptions
* **Synthetic Dataset:** Analysis is built on a normalized 100-SKU public dataset.
* **Demand Forecasting:** Daily demand ($d$) in the ROP model assumes `Number_of_products_sold` represents annualized (365-day) volume.
* **Variance & Service Levels:** Safety Stock calculations assume demand variability is 20% of the mean. Service levels are mapped dynamically (Class A: 98%, Class B: 95%, Class C: 90%).

---

## 📁 Repository Structure
```text
Supply-Chain-Inventory-and-Operations-Optimization
│
├── Dataset
│   ├── supply_chain_data.csv
│   └── supply_chain_clean_data.csv
│
├── Python
│   └── supply_chain_eda.ipynb
│
├── SQL
│   └── supply_chain_analysis.sql
│
├── Power BI
│   └── Supply_Chain_Analysis.pbix
│
├── Dashboard_Screenshots
│   └── (4 PNG views)
│
└── README.md

## 👤 Author & Attribution

**Hari Keerthan Reddy**  
*B.Tech Mechanical Engineering, Indian Institute of Technology Hyderabad (IIT Hyderabad)*  
**Skills:** Python | SQL (PostgreSQL) | Power BI | Excel | Supply Chain & Operations Analytics



