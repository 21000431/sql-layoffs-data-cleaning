# 📊 Layoffs Data Cleaning & Preparation (SQL Project)

## 🔍 Overview

Raw data is messy. Always has been. Always will be.

This project focuses on transforming a real-world layoffs dataset into a clean, analysis-ready format using SQL. The goal was simple but powerful: take inconsistent, duplicated, and incomplete data — and turn it into something trustworthy.

Because in data… if the foundation is weak, everything built on top collapses.

---

## 🎯 Objectives

* Create a structured data cleaning pipeline
* Remove duplicates using advanced SQL techniques
* Standardize inconsistent text data
* Handle missing values intelligently
* Convert data types for accurate analysis
* Prepare a final dataset ready for exploration and visualization

---

## 🛠️ Tools & Technologies

* SQL (MySQL)
* Window Functions (`ROW_NUMBER`)
* Joins & CTEs
* Data Transformation Functions

---

## 🧱 Data Cleaning Process

### 1. Creating a Staging Environment

To preserve the integrity of the raw dataset, a staging table was created:

* Prevents accidental data loss
* Allows safe experimentation

---

### 2. Removing Duplicates

Used `ROW_NUMBER()` with partitioning to identify duplicate records:

```sql
ROW_NUMBER() OVER (
  PARTITION BY company, location, industry, total_laid_off,
  percentage_laid_off, date, stage, country, funds_raised_millions
)
```

* Duplicates were isolated and removed
* Ensured each record is unique and reliable

---

### 3. Standardizing Data

Cleaned inconsistent formatting across multiple columns:

* Trimmed whitespace from company names
* Standardized industry labels (e.g., "Crypto%" → "Crypto")
* Fixed country naming inconsistencies

---

### 4. Date Formatting

Converted text-based dates into proper SQL `DATE` format:

* Enables time-based analysis
* Improves query performance and accuracy

---

### 5. Handling Missing Values

Instead of dropping incomplete records blindly:

* Used self-joins to fill missing industry values based on existing data
* Removed records where key metrics were entirely missing

---

### 6. Data Type Optimization

* Converted date fields to `DATE`
* Prepared numeric fields for analysis

---

### 7. Final Cleanup

* Removed helper columns (e.g., `row_num`)
* Delivered a clean, structured dataset ready for analysis

---

## 📈 Key Skills Demonstrated

* Data Cleaning & Preprocessing
* Analytical Thinking
* SQL Window Functions
* Data Integrity Management
* Problem Solving with Real-World Data

---

## 🚀 Future Work

This project is the foundation. Next steps include:

* Exploratory Data Analysis (EDA)
* Data Visualization (Power BI / Tableau)
* Trend analysis (layoffs by industry, country, time)
* Building dashboards for business insights

---

## 📂 Project Structure

```
/project-folder
│── layoffs_staging.sql
│── layoffs_staging2.sql
│── README.md
```

---

## 💡 Final Thoughts

Data doesn’t lie — but it does hide.

Cleaning data is not glamorous work. It’s quiet, methodical, and often overlooked. But it’s where real analysis begins.

This project reflects a simple belief:

> “Before you can trust the data… you must first earn its truth.”

---

## 👤 Author

**King Maliehe**
Aspiring Data Analyst | Software Developer | Problem Solver

---

## ⭐ If You Found This Useful

Give the project a star ⭐ and feel free to connect or collaborate!
