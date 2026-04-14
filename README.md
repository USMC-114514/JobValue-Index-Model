# JobValue-Index-Model

![Status](https://img.shields.io/badge/Status-MVP_Phase-brightgreen)
![Architecture](https://img.shields.io/badge/Architecture-MVC-blue)

## 📌 Project Overview
The **JobValue Index (JVI)** is a quantitative valuation model designed to break the "TC Delusion" (Total Compensation Delusion) in the Bay Area tech industry. Instead of comparing static gross salaries, this engine evaluates tech offers through a **Mean-Variance utility framework**, factoring in Geo-Arbitrage (cost of living), rigorous tax retention, and invisible friction costs (commuting & excessive working hours).

## ⚙️ Core Architecture (Current MVP in Excel)
The initial MVP is built using a strict **MVC (Model-View-Controller)** separation to ensure data integrity and robust pipeline routing:

* **Controller (`Assumptions`):** User input console with Hard/Soft constraints and Foreign Key validation for custom internal tech levels (e.g., translating "ZP3" to standard "L4").
* **Database (`Market_Comps`):** A decoupled "Single Source of Truth" integrating:
  * Tier-based baseline compensation arrays.
  * Level mapping dictionaries.
  * Micro-geographic ZIP-code level COLI (Cost of Living Index) and housing metrics.
* **Engine (`Valuation`):** The core calculation black-box utilizing `XLOOKUP` composite keys and `SUMIFS` aggregation to compute the **True Net Hourly Yield**.

## 🧠 Valuation Methodology
JVI translates subjective work experiences into standardized Alpha factors:
1. **Financial Alpha:** Premium over market baseline after applying Bay Area retention rate constraints.
2. **Time/WLB Penalty:** Exponential decay of hourly yield based on required office presence and commute friction.
3. **Utility Vectors:** User-defined weights applied to aggregate the final composite score.

## 🗺️ Roadmap (Future Python/Quant Upgrades)
- [ ] **Data Pipeline:** Build automated web scrapers for real-time compensation data.
- [ ] **Risk Matrix:** Implement the **Ledoit-Wolf Shrinkage Estimator** to smooth covariance matrices across sparse crowd-sourced data.
- [ ] **Dynamic Weighting:** Maximize Composite Information Ratio (IR) replacing static user weights.
- [ ] **Time-Series Analysis:** Introduce Half-life exponential decay for historical comp packages.
