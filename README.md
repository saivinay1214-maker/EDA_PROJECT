# Exploratory Data Analysis (EDA) on Vehicle Sales Dataset

## 📌 Project Overview
This project performs an end-to-end Exploratory Data Analysis (EDA) on a vehicle sales dataset (`vehicle_sales_dirty.csv`). The primary objective is to clean unstructured and dirty data, perform feature engineering/encoding, handle missing values and outliers, and uncover key trends and relationships across vehicle attributes through multi-level visualizations.

---

## 🛠️ Key Steps & Methodology

### 1. Data Cleaning & Imputation
* **Missing Value Treatment:** 
  * Imputed missing numerical values (`Selling_Price`, `Selling_Price_dup`) using **Mean Imputation**.
  * Imputed missing categorical columns (`Brand`, `Fuel_Type`, `Transmission`, `Owner`) using **Mode Imputation** (most frequent value).
* **Data Standardization & Deduplication:**
  * Removed redundant duplicate columns (`Brand_dup`, `Selling_Price_dup`).
  * Fixed inconsistent string casing across categorical attributes (e.g., standardizing `'ford'`/ `'Ford'`, `'diesel'`/ `'Diesel'`, `'auto'`/ `'Automatic'`).
* **Feature Encoding:**
  * Ordinal mapping of the `Owner` feature from text to numerical integers (`First` $\rightarrow 1$, `Second` $\rightarrow 2$, `Third` $\rightarrow 3$).

### 2. Outlier Detection
* Applied the **Interquartile Range (IQR) method** ($1.5 \times \text{IQR}$) across all numerical features (`Driven_KMs`, `Engine_CC`, `Mileage_kmpl`, `Selling_Price`, `Present_Price`, `Model_Year`, `Owner`) to systematically detect extreme variance and numerical anomalies.

### 3. Visualizations & Statistical Analysis
Executed three levels of visual data exploration using `seaborn` and `matplotlib`:

* **Univariate Analysis:**
  * Evaluated individual feature distributions, skewness, and category proportions using Histograms with KDE curves (`Selling_Price`), Boxplots (`Driven_KMs`), and Count Plots (`Fuel_Type`).
* **Bivariate Analysis:**
  * Investigated direct feature-to-target relationships using Scatter Plots (`Driven_KMs` vs `Selling_Price`), Grouped Boxplots (`Selling_Price` across `Brand`), and Categorical Bar Plots (`Transmission` vs `Selling_Price`).
* **Multivariate Analysis:**
  * Mapped multi-feature interactions using Correlation Matrix Heatmaps, 3-Variable Scatter Plots (`Present_Price` vs `Selling_Price` grouped by `Fuel_Type`), and Pairplots across key numeric metrics.

---

## 🚀 Tech Stack
* **Language:** Python
* **Environment:** Google Colab / Jupyter Notebook
* **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`
