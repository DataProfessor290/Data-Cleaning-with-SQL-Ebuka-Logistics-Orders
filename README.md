# Ebuka Logistics Order Data Cleaning with SQL

## 📌 Project Overview  
This project focuses on **cleaning and transforming customer order data** for **Ebuka Logistics** using **MySQL**.  
The raw dataset was imported from a CSV file and contained issues such as:  

- Duplicates  
- Inconsistent customer names  
- Invalid and inconsistent dates  
- Malformed price and quantity values  
- Null and missing entries  
- Messy notes with unnecessary characters  

As a **Data Professional**, my goal was to design a structured **SQL workflow** simulating a real-world **ETL (Extract, Transform, Load)** process.  
The final dataset is **standardized, reliable, and ready for analysis or reporting**.  

---

## 📂 Dataset  
- **Source:** CSV file `customer_orders - Sheet1.csv`  
- **Imported into:** MySQL database (`Ebuka Logistics`)  
- **Raw Table:** `order_table`  
- **Working Copy:** `data_engine`  

---

## ⚙️ SQL Workflow  

### 1. Database & Table Setup  
- Created database `Ebuka Logistics`  
- Defined `order_table` schema  
- Imported raw CSV data into MySQL  

### 2. Working Copy Creation  
- Created `data_engine` table  
- Preserved raw data integrity by working on a duplicate  

### 3. Duplicate Handling  
- Built a stored procedure `check_duplicates()`  
- Counted total rows and previewed distinct records  

### 4. Customer Name Standardization  
- Converted names to **proper case**  
- Split into `first_name` and `last_name` columns  

### 5. Missing / Invalid Values  
- Replaced null IDs, customer names, and emails with `"Unknown"`  
- Removed invalid rows where necessary  

### 6. Date Standardization  
- Normalized formats (`YYYY-MM-DD`, `MM-DD-YYYY`)  
- Converted to proper **DATE** datatype  

### 7. Product Name Standardization  
- Replaced missing product names with `"Unknown"`  

### 8. Quantity Cleanup  
- Converted text-based numbers (e.g., `"two" → 2`)  
- Converted column type to **INT**  

### 9. Price Cleanup  
- Removed currency symbols and commas  
- Replaced blanks with `0`  
- Converted column type to **FLOAT**  

### 10. Derived Metrics  
- Added new column `amount_due = quantity × price`  

### 11. Country Standardization  
- Unified variations of `"US"` and `"UK"`  
- Converted other countries to **Title Case**  

### 12. Order Status Standardization  
- Converted to proper case (e.g., `"Shipped"`)  

### 13. Notes Column Cleaning  
- Converted to lowercase  
- Trimmed whitespace and hidden characters  
- Standardized placeholders (`"-"`, `""` → `"NA"`)  
- Unified duplicate-related entries  

### 14. Final Verification  
- Reviewed fully cleaned dataset  
- Validated schema using `DESCRIBE data_engine`  

---

## ✅ Final Output  
The **`data_engine`** table is:  
- Duplicate-free  
- Standardized in format  
- Free from invalid entries  
- Enriched with derived metrics  
- Ready for **reporting, dashboards, or further analytics**  

---

## 🛠️ Tools & Technologies  
- **SQL (MySQL 9.3)**  
- **CSV (raw data import)**  
- **ETL Workflow Simulation**  

---

## 📜 Author  
👤 **Tolulope Emuleomo (Data Professor)**  
- [LinkedIn](https://www.linkedin.com/in/tolulope-emuleomo-77a231270/)   

---
