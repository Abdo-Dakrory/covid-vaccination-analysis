# COVID-19 Vaccination Analysis & Impact Assessment

## 📌 Overview
This project analyzes and models global COVID-19 vaccination data, combining it with COVID-19 case and death statistics to generate deeper insights.  
The work involves **data cleaning, exploratory data analysis (EDA), merging multiple datasets, building machine learning models, and performing statistical impact analysis**.  
The aim is to understand the relationship between vaccination coverage and the spread/severity of COVID-19, classify countries by vaccination rollout speed, and identify high-risk areas.

---

## 📊 Data Sources
1. **Vaccination Data**: Global vaccination data including total vaccinations, people vaccinated, fully vaccinated, daily vaccinations, and percentage metrics.
2. **Cases & Deaths Data**: COVID-19 case and death statistics per country, including total cases, daily cases, total deaths, daily deaths, and population size.

Both datasets were obtained from [Our World in Data](https://ourworldindata.org/) and merged using `country` and `date` as keys.

---

## 🛠 Project Workflow

### 1. **Data Cleaning & Preparation**
- Loaded both vaccination and case/death datasets.
- Standardized column names and formats.
- Converted `date` columns to proper datetime format.
- Handled missing values (filled zeros where logical, kept NaN where uncertainty exists).
- Sorted data by country and date.

### 2. **Feature Engineering**
- Created **daily_vaccinations_calc** from cumulative totals.
- Computed **7-day rolling averages** for smoother trends.
- Calculated per-million metrics:
  - `cases_per_million`
  - `deaths_per_million`
  - `vaccinations_per_million`
- Merged vaccination and case/death datasets to form a unified analysis-ready dataset.

### 3. **Exploratory Data Analysis (EDA)**
- **Time-series plots** of daily vaccinations and rolling averages for specific countries.
- **Comparative analysis** of top countries by vaccination rate.
- **Scatter plots** to examine relationships between vaccination coverage and cases/deaths.
- **Correlation heatmaps** of key metrics.

### 4. **Impact Analysis**
- Regression plots showing the relationship between `fully_vaccinated_%` and `cases_per_million` / `deaths_per_million`.
- Correlation coefficients (Pearson and Spearman) to quantify the relationship.
- Lag analysis (14–21 days) to assess delayed effects of vaccination.

### 5. **Risk Scoring**
- Defined a `risk_score` metric:
