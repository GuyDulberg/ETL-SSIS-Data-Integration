# ETL-SSIS-Data-Integration
ETL project using SQL Server Integration Services (SSIS). Includes metadata validation, file classification (Processed/Wrong), and automated report generation.

This project demonstrates an **ETL (Extract, Transform, Load)** process built with **SQL Server Integration Services (SSIS)**.  
It focuses on metadata validation, automated file classification, and reporting.

---

## 📌 Project Overview
- **Extract**: Read multiple CSV files from the `Data` folder.  
- **Transform**: Validate metadata (column names) against a reference file (`File1.csv`).  
- **Load**:  
  - Files with valid metadata are moved to the `Processed` folder and their records are loaded into SQL Server (`SourceData` table).  
  - Files with invalid metadata are moved to the `Wrong` folder and excluded from loading.  

---

## 📂 Folder Structure

ETL-SSIS-Data-Integration/
│
├── Data/ # Input files
├── Processed/ # Validated files
├── Wrong/ # Invalid files
├── SourceData.csv # Final export from SQL Server
├── ETL_Report.csv # Run log & summary report
├── Integration Services Project21.sln # SSIS solution file
├── Ex-1.doc # Exercise instructions

## ⚙️ Technologies
- **SQL Server Integration Services (SSIS)**
- **SQL Server**
- **CSV / Flat File handling**
- **Metadata validation with Script Task & Foreach Loop Container**

---

## 📊 ETL Workflow
1. **Foreach Loop Container** – Iterates over files in `Data`.  
2. **Script Task** – Compares file metadata with `File1.csv`.  
3. **Conditional Flow** –  
   - If metadata matches → move file to `Processed` and insert rows into `SourceData` table.  
   - If metadata mismatches → move file to `Wrong`.  
4. **Export** –  
   - `SourceData.csv`: Export of the loaded table.  
   - `ETL_Report.csv`: Status report with filename, records loaded, and timestamp.  

---

## 🚀 How to Run
1. Copy all input files into `C:\SSIS-1\Data\`.  
2. Open the solution file `Integration Services Project21.sln` in Visual Studio (with SSIS).  
3. Run the package.  
4. Check the generated outputs in:  
   - `C:\SSIS-1\SourceData.csv`  
   - `C:\SSIS-1\ETL_Report.csv`  

---
