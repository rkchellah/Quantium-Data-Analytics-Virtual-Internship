# Quantium Data Analytics Job Simulation

A end-to-end retail analytics project completed as part of the **Quantium Data Analytics Virtual Experience Program**. The simulation involved analysing chip sales data to uncover customer insights and evaluate the impact of a new store layout trial across three retail stores.

---

## Project Structure
```
quantium-data-analytics/
│
├── Quantium_Task_1.ipynb                        # Customer & sales analysis
├── Quantium_Task_2.ipynb                        # Trial store layout evaluation
│
├── reports/
│   ├── Task1_Customer_Analytics_Report.docx     # Detailed Word report — Task 1
│   ├── Task2_Trial_Store_Evaluation_Report.docx # Detailed Word report — Task 2
│   └── Executive_Summary.pptx                   # PowerPoint presentation
│
└── data/
    └── QVI_transaction_data_clean.csv           # Cleaned dataset (prepared in Excel)
```

---

## Project Overview

### Task 1: Customer & Sales Analysis
Explored a full year of chip sales data (July 2018 – June 2019) to identify which customer segments drive the most revenue, what products they prefer, and what behavioural patterns explain their spending.

### Task 2: Trial Store Layout Evaluation
Evaluated whether a new chip aisle layout introduced in three trial stores (77, 86, 88) produced a statistically significant improvement in sales and customer numbers compared to matched control stores.

---

## Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Microsoft Excel / Power Query** | Initial data cleaning, outlier removal, feature creation |
| **Python (pandas, numpy)** | Data wrangling and segmentation analysis |
| **Matplotlib & Seaborn** | Data visualisation |
| **SciPy** | Statistical testing (independent t-test) |
| **Microsoft Word / PowerPoint** | Business reporting and presentation |

---

## Methodology

### Data Cleaning
- Initial cleaning was performed in **Microsoft Excel** before importing into Python via `pandas`
- Removed outliers such as a commercial bulk transaction of **200 packets** that skewed the data
- Removed non-chip products (e.g., salsa) that had been incorrectly included in the dataset
- Verified there were **no missing values** across all columns after cleaning

### Feature Engineering
- Extracted **`PACK_SIZE`** (in grams) and **`BRAND`** directly from raw product name strings
- Standardised inconsistent brand naming conventions (e.g., `"Red"` → `"RRD"`, `"Snbts"` → `"Sunbites"`)
- Engineered a **`PRICE`** column (`TOT_SALES / PROD_QTY`) for per-unit price analysis
- Created **`YEAR_MONTH`** period column for monthly trend aggregation in Task 2

### Customer Segmentation
- Grouped customers by **`LIFESTAGE`** (e.g., Young Singles/Couples, Retirees, Older Families) and **`PREMIUM_CUSTOMER`** status (Budget, Mainstream, Premium)
- Calculated segment-level metrics: total sales, unique customer count, average units per customer, and average price per unit

### Control Store Selection (Task 2)
- Matched each trial store to the most similar control store using a **combined similarity score** built from:
  - **Pearson correlation** of monthly sales trends
  - **Magnitude distance** of absolute sales levels
- Applied a **95% confidence interval** around scaled control store performance to determine whether trial store results were statistically significant

---

## Key Findings

### Task 1
- **Top revenue segments:** Budget Older Families, Mainstream Young Singles/Couples, Mainstream Retirees
- **Most popular pack size:** 175g — outsells every other size by a large margin
- **Most purchased brand:** Kettle chips, ahead of Smiths and Pringles
- **Seasonal pattern:** Sales spike through December up to Christmas Eve, then drop to **zero** on Christmas Day (stores closed)
- **Price insight:** Mainstream Young and Mid-Age Singles/Couples pay a statistically significantly higher price per bag than Budget or Premium shoppers in the same age group (*p* < 0.05)
- **Brand affinity:** Mainstream Young Singles/Couples are 23% more likely to buy Tyrrells and 56% less likely to buy Burger brand compared to other segments

### Task 2
| Trial Store | Control Store | Sales Result | Customer Result | Verdict |
|-------------|--------------|-------------|----------------|---------|
| Store 77 | Store 233 | ✅ Significant uplift (2/3 months) | ✅ Significant uplift (2/3 months) | Roll out |
| Store 86 | Store 155 | ⚠️ No significant uplift | ✅ Significant uplift (all 3 months) | Pair with promotions |
| Store 88 | Store 237 | ✅ Significant uplift (2/3 months) | ✅ Significant uplift (all 3 months) | Roll out — strongest results |

---

## Sample Visualisations

> *Charts generated in Python using Matplotlib and Seaborn*

- Total chip sales timeline with Christmas Day annotation
 <img width="1486" height="690" alt="image" src="https://github.com/user-attachments/assets/f6c6ef73-0444-482f-96e1-7a743d3f06fe" />

- December daily sales breakdown highlighting the Christmas closure
  <img width="1246" height="602" alt="image" src="https://github.com/user-attachments/assets/b58f7730-395b-4068-a39a-fe5ed9d12cc4" />

- Stacked bar charts of sales and customer counts by lifestage and premium tier
  <img width="1554" height="624" alt="image" src="https://github.com/user-attachments/assets/90f066b8-97e9-4267-a4ad-6f0cade8c42f" />

- Confidence interval charts for each trial store vs its control 
  <img width="1005" height="701" alt="image" src="https://github.com/user-attachments/assets/380072ba-4838-4e61-b9b4-d7327a58d661" />


---

## Business Recommendations

1. **Stock aggressively in the first 3 weeks of December**: The pre-Christmas sales surge is consistent and predictable
2. **Prioritise 175g pack shelf space**: It is the dominant purchase size across all customer types
3. **Protect Kettle brand availability**: It is the clear market leader and likely drives store visits
4. **Run bundle promotions for Family segments**: They buy the most bags per trip and respond to volume deals
5. **Roll out the new layout to stores similar to Store 88 first**: It produced the strongest and most consistent trial results
6. **At Store 86-type locations, pair the new layout with in-store promotions**: The layout attracts customers but needs a conversion trigger to lift sales

---

## How to Run
```bash
# Clone the repository
git clone https://github.com/your-username/quantium-data-analytics.git
cd quantium-data-analytics

# Install dependencies
pip install pandas numpy matplotlib seaborn scipy

# Launch notebooks
jupyter notebook
```

> **Note:** The raw dataset is sourced from the [Quantium Virtual Experience Program](https://www.theforage.com/virtual-internships/prototype/NkaC7knWtjSbi6aYv/Data-Analytics) on Forage. You will need to download it directly from the program to run the notebooks.

---

## Certificate

Completed via **[Forage](https://www.theforage.com/)** — Quantium Data Analytics Virtual Experience Program

---

## Author

**Chella Kamina**
[LinkedIn](https://linkedin.com/in/rkchellah) • [GitHub](https://github.com/rkchella)
