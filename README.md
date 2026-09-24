# Indian Premier League (IPL) Match Analysis & Data Preprocessing Pipeline

A robust Exploratory Data Analysis (EDA) and data preprocessing pipeline built with Python and Pandas for Indian Premier League (IPL) match records spanning from 2008 through 2024.

---

## 📌 Overview

This project focuses on auditing, cleaning, and preparing historical IPL match datasets for downstream predictive modeling and statistical analysis. Key pipeline steps include dataset schema verification, missing-value handling, feature selection, and summary statistic generation.

---

## 📊 Dataset Metadata

* **Raw Observations:** 1,095 match entries
* **Cleaned Observations:** 1,028 valid match records
* **Features:** 19 features (post column pruning)

| Feature Name | Data Type | Description |
| :--- | :--- | :--- |
| `id` | `int64` | Unique match identification key |
| `season` | `object` | IPL season edition (e.g., 2007/08 to 2024) |
| `city` | `object` | Host city location |
| `date` | `object` | Date of match execution |
| `match_type` | `object` | Phase of match (League, Qualifier, Final, etc.) |
| `player_of_match` | `object` | Man of the match award recipient |
| `venue` | `object` | Stadium venue name |
| `team1` | `object` | First competing team |
| `team2` | `object` | Second competing team |
| `toss_winner` | `object` | Team winning the toss |
| `toss_decision` | `object` | Choice post-toss (`field` or `bat`) |
| `winner` | `object` | Match winning team |
| `result` | `object` | Win metric (`runs` or `wickets`) |
| `result_margin` | `float64` | Victory margin value |
| `target_runs` | `float64` | Inning target score set |
| `target_overs` | `float64` | Scheduled overs for target |
| `super_over` | `object` | Super over flag (`Y` / `N`) |
| `umpire1` | `object` | On-field primary umpire |
| `umpire2` | `object` | On-field secondary umpire |

---

## 🛠 Project Structure & Workflow

1. **Environment Setup**
   * Verification of core libraries (`pandas`, `numpy`).

2. **Data Ingestion & Inspection**
   * Loading match records from `matches.csv`.
   * Inspection of top (`head`) and bottom (`tail`) entries.
   * Assessment of structural dimensions (`shape`) and data type profiles (`info`).

3. **Data Preprocessing & Cleaning**
   * **Duplicate Verification:** Validated presence of duplicate records (`df.duplicated().sum()`).
   * **Feature Selection:** Pruned high-null sparse columns (`method` dropped due to ~98% missing records).
   * **Missing Value Handling:** Executed targeted row-wise removal (`dropna()`) on non-recoverable records across `city`, `winner`, `player_of_match`, and `result_margin`.

4. **Statistical Profiling**
   * Summary statistical analysis (`describe()`) covering numerical features such as target runs, target overs, and winning margins.

---

## 🚀 Quick Start

### Dependencies

```bash
pip install pandas numpy
