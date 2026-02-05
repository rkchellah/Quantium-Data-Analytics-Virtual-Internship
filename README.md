# Quantium Virtual Internship - Retail Strategy and Analytics

## Project Overview
This repository contains the complete analysis for the Quantium Virtual Internship. The goal was to act as a Data Analyst and Consultant for the Category Manager of Chips, analyzing transaction data to identify customer segments and evaluating a trial store layout to recommend a strategic rollout.

**Key Tools:** Python (Pandas, Matplotlib), Excel, PowerPoint, Jupiter Notebooks.

---

## Task 1: Data Preparation & Customer Analytics
**Goal:** Analyze purchasing trends to identify the high-value customer segments for the chips category.

### Methodology
*   **Data Cleaning:** Removed outliers (e.g., a commercial transaction of 200 packets) and non-chip products (salsa) to ensure data integrity.
*   **Feature Engineering:** Created `PACK_SIZE` and `BRAND` features from product names, standardizing brand variations (e.g., "Red" to "RRD").
*   **Segmentation:** Grouped customers by `LIFESTAGE` and `PREMIUM_CUSTOMER` status to calculate metrics.

### Key Insights
*   **Top Segment:** "Mainstream - Young Singles/Couples" are the highest value target. While they buy fewer units than families, they pay the **highest price per unit** ($4.00+), indicating a willingness to pay for premium products.
*   **Brand Affinity:** This segment is **24% more likely** to purchase **Tyrells** chips compared to the general population.
*   **Pack Size:** They prefer 270g "Sharing Packs" (Lift: 1.27x).

---

## Task 2: Experimentation & Uplift Testing
**Goal:** Evaluate the performance of a store trial (new layout) in Stores 77, 86, and 88 against a control group to determine if the strategy should be rolled out.

### Methodology
*   **Control Store Selection:** Used Python to calculate **Pearson Correlation** and **Magnitude Distance** to find control stores that matched the trial stores' pre-trial behavior.
    *   *Store 77* matched with *Store 233*
    *   *Store 86* matched with *Store 155*
    *   *Store 88* matched with *Store 91*
*   **Uplift Calculation:** Compared total sales of Trial vs. Control during the trial period (Feb 2019 - April 2019).

### Results
*   **Store 77:** **+17.9%** Uplift (Significant Success)
*   **Store 88:** **+48.4%** Uplift (Significant Success)
*   **Store 86:** **+4.3%** Uplift (Modest Growth)
*   **Conclusion:** The trial was highly effective in 2 out of 3 locations.

---

## Task 3: Commercial Recommendations
**Goal:** Synthesize technical findings into a clear, commercial strategy for the Category Manager.

### Strategic Recommendations
1.  **Rollout Strategy:** Expand the new trial layout to all "Mainstream" focused stores, given the significant uplift found in Task 2.
2.  **Assortment Strategy:** Increase stock of **Tyrells** and **Doritos** in **270g pack sizes** to cater to the high-margin "Young Singles" segment.
3.  **Placement:** Position these high-value products at eye level in high-traffic aisles to maximize impulse purchases.

---

## Code Structure
*   `Task_1_Data_Preparation.ipynb`: Contains the cleaning logic, outlier removal, and the 4 key metric visualizations.
*   `Task_2_Uplift_Testing.ipynb`: Contains the control store matching function and the T-test visualization for sales uplift.

## Visualizations
<img width="1510" height="708" alt="Screenshot 2026-02-02 191351" src="https://github.com/user-attachments/assets/4f3e10a6-972a-4768-bcee-dc61ad4ed830" />

