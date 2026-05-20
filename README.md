# ⚙️ Data Leverager: Power BI ETL & Data Transformation Project

Welcome to the **Data Leverager** repository! This project demonstrates an end-to-end Extract, Transform, Load (ETL) pipeline built entirely within **Power BI's Power Query Editor**. 

**Note:** This project focuses strictly on data engineering, cleaning, preparation, and integration. It does not include DAX or data visualization.

---

## 🎯 Project Objective
To simulate a real-world data engineering scenario by extracting, cleaning, reshaping, and combining data from multiple disparate sources using essential Power Query tools and techniques. The final output is a normalized, structured, and automated dataset ready for downstream analytical modeling.

---

## 🗂️ Data Sources
Data was ingested from a variety of sources to demonstrate versatile extraction capabilities:
* **Local Folder Source:** Combined monthly sales files (`Sales_Jan.xlsx`, `Sales_Feb.xlsx`, `Sales_Mar.xlsx`).
* **Standalone Excel File:** Relational dimension data containing employee details (`Employee_Data.xlsx`).
* **Web Scraping:** HTML table containing country-wise macroeconomic stats extracted directly from a Wikipedia page.

---

## 🛠️ ETL Workflow & Transformations

### 1. Data Extraction & Basic Cleaning
* Promoted headers and removed blank rows/duplicate records.
* Handled missing information by filtering null values.
* Applied **Change Type with Locale** to accurately parse regional currency and date formats.

### 2. Text & Numeric Engineering
* **Text Tools:** Standardized messy string data using `TRIM()`, `CLEAN()`, `UPPER()`, `LOWER()`, and `REPLACE()`.
* **Column Splitting:** Split complex customer and address fields using delimiters.
* **Numeric Tools:** Created a custom `Profit` column (`Revenue - Cost`) and rounded revenue data to two decimal places.

### 3. Date & Time Intelligence
* Extracted specific date parts (Day, Month, Year, Quarter) from standard Order Dates.
* Engineered a custom **Fiscal Month** column.
* Calculated an **Age** column derived dynamically from the Employee Birthdate field.

### 4. Advanced Reshaping & Integration
* **Conditional Logic:** Built a `Sales Category` column categorizing data into High (≥10,000), Medium (5,000–9,999), and Low (<5,000).
* **Indexing:** Generated 0-based and 1-based index keys.
* **Pivoting/Unpivoting:** Restructured monthly columns into normalized, single-column formats.
* **Merging & Appending:** Appended Q1 sales data into a master table and executed precise Merges (Joins) between Sales and Employee data using `Region` and `EmployeeID`.
* **Aggregation:** Grouped data by Region to compute *Total Sales*, *Average Order Value*, and *Transaction Count*.

### 5. Automation & Data Quality
* **Profiling:** Enabled Column Profile, Distribution, and Quality tools to audit distinct values and detect column-level errors.
* **Parameterization:** Configured a dynamic folder path using **Parameters** so the data source can be easily updated on different local machines.
* **Refresh Simulation:** Validated the pipeline's automation by simulating the addition of a new monthly file, ensuring transformations maintained their integrity upon refresh.

---

## 🚀 How to Run the Project Locally
To explore the Power Query transformations on your own machine:
1. Clone this repository to your local machine.
2. Open the `.pbix` file using Power BI Desktop.
3. Click on **Transform Data** to open the Power Query Editor.
4. Navigate to **Manage Parameters** and update the folder path parameter to match the local directory where your source data files are saved.
5. Click **Close & Apply** and hit **Refresh** to watch the data auto-load through the pipeline!

---

## 📂 Repository Contents
* `PR. 1 Data Leverager.pbix`: The core Power BI file containing all Power Query M-code and applied steps.
* `Data_Leverager_Project_Report.pdf`: Comprehensive documentation detailing the sources, transformations, and challenge-resolution strategies.
* `/Source_Data`: Directory containing the sample `.xlsx` files used for ingestion.

---

**Author:** Kunj Mistry  
*Aspiring Data Engineer / Data Analyst*

## 🧑‍💻 Project Information

- **Name:** Kunj Mistry  
- **GR ID:** 12078  
- **Branch:** RW6  
- **Project Type:** Data Analysis Project  
- **Date:** 20-05-2026
