# Gas Prices Analysis in France (2022–2024)

A PySpark-based data pipeline to analyze and forecast fuel price dynamics in France (2022–2024). Includes ETL, spatial visualization, and predictive modeling with Spark ML.

## Authors
* **Federica Sfeir**
* **Paola Maria Lepore**

---

## Project Overview
The objective of this project is to analyze the evolution of gas prices in France between **2022 and 2024**. Using **Apache Spark**, we processed large-scale daily fuel price datasets to extract meaningful insights, visualize spatial disparities, and build predictive models.

The workflow covers the entire data science lifecycle:
1.  **Distributed Data Ingestion** and cleaning.
2.  **Exploratory Data Analysis (EDA)** with temporal and spatial components.
3.  **Machine Learning** for price forecasting.

---

## Tech Stack
* **Language:** Python
* **Processing Engine:** Apache Spark (PySpark)
* **Environment:** Google Colab / Jupyter Notebook
* **Libraries:** * `pyspark.sql` & `pyspark.ml`
    * `folium` (Geospatial visualization)
    * `pandas` & `matplotlib` (Local visualization)
    * `urllib` (Data automation)

---

## 📊 Data Pipeline

### 1. Data Ingestion & Cleaning
The project automatically downloads and processes daily fuel price data (S1/S2 2022, 2023, and 2024). 
* **Feature Engineering:** Extracted temporal features (Year, Month, Week).
* **Geodata Normalization:** Converted raw coordinate formats into decimal degrees.
* **Outlier Removal:** Filtered erroneous price points (e.g., placeholder values like 0.001 or 9.999).

### 2. Exploratory Analysis
* **Trend Analysis:** Comparison of average weekly prices across different fuel types (Gazole, E10, SP98, etc.).
* **Spatial Analysis:** Created interactive **Heat Maps** using Folium to visualize price indexes at the department level, identifying regional disparities.

### 3. Machine Learning
We implemented a pipeline to forecast **next-day fuel prices**:
* **Models:** Evaluated **Linear Regression** as a baseline and **Random Forest Regressor** for improved accuracy.
* **Results:** The Random Forest model successfully captured non-linear relationships, outperforming the baseline by leveraging lag-based features.

---

## Key Findings
* Fuel prices show strong common dynamics across types, but regional differences are significant, especially for premium fuels (SP98).
* The use of lag-based features in a Spark ML pipeline proves effective for short-term price forecasting in a volatile market.

---

## How to Run
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    ```
2.  **Environment Setup:** Ensure you have an active Spark session (local or via Google Colab).
3.  **Run the Notebook:** Open `SparkProject_Sfeir_Lepore(1).ipynb` and execute the cells. The data will be automatically downloaded into a `/data` directory.

---
