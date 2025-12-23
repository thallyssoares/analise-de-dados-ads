```
# Google Ads Elasticity & Marginal ROI Analysis 📈

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

A data-driven analysis of Google Ads performance, focusing on **Marginal ROI**, **Account Elasticity**, and **Algorithm Behavior** (Performance Max vs. Standard Shopping).

---

## 🎯 Project Overview

Scaling ad spend is rarely linear. As investment increases, efficiency typically decreases due to auction saturation. The main goal of this project was to determine the **optimal spending point** for a large E-commerce account that needed to scale aggressively due to budget shifts from other channels.

**The core question:** Are we hitting a market saturation ceiling, or is the account structure inefficient?

### Key Business Problems Solved:
* **The "Average ROAS" Trap:** Moved the KPI focus from Average ROAS (which masks inefficiency) to **Marginal ROI** (the return on the *next* dollar spent).
* **Cannibalization Check:** Verified if Paid Search was stealing traffic from Organic/Direct channels (Hypothesis testing).
* **Algorithm Behavior:** Analyzed how **Performance Max (PMax)** and **Standard Shopping** react differently to "Target ROAS" constraints.

---

## 📊 Key Findings

### 1. The "Profit Zone" & Saturation
By plotting the saturation curves, I identified that the account has a clear efficiency ceiling.
* **Insight:** Spending above the "Profit Zone" resulted in a Marginal ROI < 1.0 (generating revenue at a loss), even though the dashboard showed a healthy Average ROAS.

### 2. PMax vs. Shopping Behavior
The most critical technical insight came from analyzing how different campaign types reacted to a **Target ROAS increase**:

* **🛒 Standard Shopping (High Elasticity):**
    * Restricted to Search/Shopping inventory.
    * When forced to hit a higher ROAS, the algorithm **qualified the auction**, bringing in higher-intent users.
    * **Result:** Revenue increased with efficiency.

* **🤖 Performance Max (Low Elasticity):**
    * Has access to cheaper inventory (Display, Discovery, YouTube).
    * When forced to hit a higher ROAS, the algorithm **shifted spend away from Search** (expensive) to Display/Discovery (cheap) to satisfy the math.
    * **Result:** Revenue stagnated, and lead quality dropped despite "hitting the target."

### 3. No Cannibalization
* Correlation analysis between Paid Sessions and Organic/Direct Sessions showed a coefficient near **0**. The saturation was structural to the paid channel, not a channel conflict.

---

## 🛠️ Methodology & Stack

**Tech Stack:**
* **Python:** Core language.
* **Pandas:** Data manipulation and ETL.
* **Matplotlib / Seaborn:** Visualization and trend lines.
* **Statsmodels / Scikit-learn:** Trend analysis and correlation.

**Approach:**
1.  **ETL:** Merged Google Ads (Cost, Clicks, ROAS) with GA4 data (Sessions, Bounce Rate).
2.  **Saturation Modeling:** Plotted Cost vs. Revenue using polynomial regression to visualize the diminishing returns.
3.  **Marginal ROI Calculation:** Calculated the derivative of the revenue curve to find the exact point where $1 spent = $1 returned.

---

## 🔒 Data Privacy & Anonymization

**Note to Readers:**
The dataset used in this repository (`dummy_google_ads_data.csv`) has been strictly **anonymized** to protect client confidentiality.

* **Campaign Names:** Mapped to generic labels (e.g., `Campaign_PMax_1`).
* **Data Scaling:** All monetary values and volumes were transformed using a random scaling factor and noise injection.
* **Integrity:** While the absolute numbers are fake, the **statistical correlations, trends, and saturation curves** were preserved to ensure the analysis code remains valid and reproducible.

---

## 📂 Repository Structure

```text
├── data/
│   ├── dummy_google_ads_data.csv   # Anonymized Ads data
│   ├── dummy_ga4_data.csv          # Anonymized Analytics data
├── src/
│   ├── main.ipynb                     # Data Analysis
│
└── README.md

```

## 🚀 How to Run

1. Clone this repository:
```bash
git clone [https://github.com/thallyssoares/analise-de-dados-ads.git](https://github.com/thallyssoares/analise-de-dados-ads.git)

```


2. Install dependencies:
```bash
pip install pandas matplotlib seaborn numpy

```


3. Open the notebook:
```bash
jupyter notebook src/main.ipynb

```



---

## 📝 Author

**Thallys Soares**
*Performance Marketing Specialist & Data Analyst*

I specialize in bridging the gap between Marketing Strategy and Data Science.

* [Medium Article about this project](https://medium.com/@antoniothallys2017/why-scaling-ads-was-killing-our-profit-d5f31a5e10cc)
* [LinkedIn Profile](www.linkedin.com/in/thallys-soares-media-analyst)

---

*If you found this analysis useful, feel free to star ⭐ this repository!*

´´´