# Azure-Data-Engineering-Project

📌 Project Overview

This project demonstrates an end-to-end ETL pipeline built on Azure, processing the Olist eCommerce dataset using Azure Data Factory, Azure Databricks (PySpark), and Azure Data Lake Storage Gen2. It follows a modern medallion architecture (Bronze, Silver, Gold) for layered data management.

⚙️ Tools & Technologies

Azure Data Factory (ADF)

Azure Databricks (PySpark)

Azure Data Lake Storage Gen2 (ADLS Gen2)

Delta Lake / Parquet

Python / PySpark


🧭 ETL Architecture

<img width="676" height="236" alt="image" src="https://github.com/user-attachments/assets/1d380822-1f9e-43dd-84af-80ce90028eb5" />

              
1️⃣ Data Extraction

Linked ADLS Gen2 to ADF using service principal authentication.

Created ADF pipelines to load .csv files from blob into Bronze Layer in ADLS Gen2.

![image](https://github.com/user-attachments/assets/3d3c7666-ad47-43ad-b40d-5b07757e1269)

2️⃣ Data Exploration / EDA

Loaded data into PySpark DataFrames.

-- Constructed a basic data model for joins.

<img width="2486" height="1496" alt="image" src="https://github.com/user-attachments/assets/00782ce0-aae5-480b-ba02-a5b615d51d20" />

-- Performed schema inference, null checks, and profiling.

<img width="1385" height="763" alt="image" src="https://github.com/user-attachments/assets/9710b4c7-8911-441b-973d-26848a2c0bb7" />


3️⃣ Data Validation / Quality Analysis

Validated: Null values, Column types, Uniqueness and referential integrity

<img width="1400" height="476" alt="image" src="https://github.com/user-attachments/assets/052f35eb-ea7a-4d21-8578-cb05a8e73148" />

<img width="1359" height="766" alt="image" src="https://github.com/user-attachments/assets/dc8058a5-b985-4286-9555-c919f0a2d31f" />


4️⃣ Data Curation

Selected necessary columns from each dataset, Renamed columns and applied logical grouping, Joined key datasets.

<img width="1384" height="722" alt="image" src="https://github.com/user-attachments/assets/baa96b10-831d-428e-a14c-d4e86941b77a" />

<img width="1399" height="392" alt="image" src="https://github.com/user-attachments/assets/0ab6fdd1-bb14-4940-b4ab-2eebc40da04d" />

5️⃣ Optimization

Applied .cache() on final joined DataFrame to optimize repeated usage.

<img width="1348" height="267" alt="image" src="https://github.com/user-attachments/assets/1d9a6ed7-e4c4-41a1-9e12-cb9fad6e455b" />


7️⃣ Data Transformation

-- Renaming Columns: Used .withColumnRenamed() for clarity.

<img width="1384" height="394" alt="image" src="https://github.com/user-attachments/assets/20490072-8ca8-4b6e-b702-382568211065" />


--Structuring Columns: Grouped fields logically.

<img width="1369" height="170" alt="image" src="https://github.com/user-attachments/assets/cefa065d-d2fb-46ab-8629-bf05294486d2" />


Feature Engineering:

--Filling Null Columns with Respective Values 

<img width="1387" height="490" alt="image" src="https://github.com/user-attachments/assets/fdf9801e-60fb-4a31-887d-2c312da9f822" />

<img width="1349" height="293" alt="image" src="https://github.com/user-attachments/assets/403d1fb7-93a1-492f-9a06-176864a7811d" />

-- Caculating Average Order Value ( AOV = Total_Spent / Total_Orders )


<img width="1367" height="421" alt="image" src="https://github.com/user-attachments/assets/64f51abb-e902-4465-b588-49d6b2aeca4c" />


Business Insights :

-- Analyzing delivery performance (Delivery Gap Analysis): 

<img width="1340" height="682" alt="image" src="https://github.com/user-attachments/assets/5deb4433-2b4b-4662-8b44-66570790f450" />

-- Customer Segmentation ( Based on AOV ) : 

<img width="1343" height="745" alt="image" src="https://github.com/user-attachments/assets/6754ace6-3a20-4e37-bd80-3b3c518dc9b8" />

<img width="1338" height="418" alt="image" src="https://github.com/user-attachments/assets/d9a985d3-9dd5-46dd-93f8-42c898adc401" />




