# Azure-Data-Engineering-Project

# 📌 Project Overview

This project demonstrates an end-to-end ETL pipeline built on Azure, processing the Olist eCommerce dataset using Azure Data Factory, Azure Databricks (PySpark), and Azure Data Lake Storage Gen2. It follows a modern medallion architecture (Bronze, Silver, Gold) for layered data management.


# 🔁 Project Architecture

<img width="1015" height="567" alt="image" src="https://github.com/user-attachments/assets/9109bd47-026c-4b31-9ac8-bcb487f78a75" />

# ⚙️ Tools & Technologies

Azure Data Factory (ADF)

Azure Databricks (PySpark)

Azure Data Lake Storage Gen2 (ADLS Gen2)

Delta Lake / Parquet

Python / PySpark


# 🧭 ETL Architecture

<img width="676" height="236" alt="image" src="https://github.com/user-attachments/assets/1d380822-1f9e-43dd-84af-80ce90028eb5" />

              
# 1️⃣ Data Extraction

Linked ADLS Gen2 to ADF using service principal authentication.

Created ADF pipelines to load .csv files from blob into Bronze Layer in ADLS Gen2.

![image](https://github.com/user-attachments/assets/3d3c7666-ad47-43ad-b40d-5b07757e1269)

# 2️⃣ Data Exploration / EDA

Loaded data into PySpark DataFrames.


- Constructed a basic data model for joins.
  

<img width="2486" height="1496" alt="image" src="https://github.com/user-attachments/assets/00782ce0-aae5-480b-ba02-a5b615d51d20" />


- Performed schema inference, null checks, and profiling.
  

<img width="1385" height="763" alt="image" src="https://github.com/user-attachments/assets/9710b4c7-8911-441b-973d-26848a2c0bb7" />


# 3️⃣ Data Validation / Quality Analysis

- Validated: Null values, Column types, Uniqueness and referential integrity

<img width="1326" height="426" alt="image" src="https://github.com/user-attachments/assets/9efce441-d943-45e6-9a49-5d1f72c26ebf" />


<img width="1329" height="643" alt="image" src="https://github.com/user-attachments/assets/19116027-779a-4216-a4e9-fe19b8e59836" />



# 4️⃣ Data Curation

- Selected necessary columns from each dataset, Renamed columns and applied logical grouping, Joined key datasets.

 
<img width="1319" height="622" alt="image" src="https://github.com/user-attachments/assets/c1bd5b22-9ed7-4195-a4fd-edddd31f9816" />


- Joining Datasets.
  


<img width="1317" height="291" alt="image" src="https://github.com/user-attachments/assets/d4f855b7-c794-4357-9985-8cd6bddb3701" />



# 5️⃣ Optimization

Applied .cache() on final joined DataFrame to optimize repeated usage.



<img width="1323" height="232" alt="image" src="https://github.com/user-attachments/assets/1c37993c-c106-4b02-b228-3262925d77ca" />



# 7️⃣ Data Transformation

- Renaming Columns: Used .withColumnRenamed() for clarity.
  

<img width="1384" height="394" alt="image" src="https://github.com/user-attachments/assets/20490072-8ca8-4b6e-b702-382568211065" />


- Structuring Columns: Grouped fields logically.


<img width="1369" height="170" alt="image" src="https://github.com/user-attachments/assets/cefa065d-d2fb-46ab-8629-bf05294486d2" />

- Data Cleaning :


<img width="1317" height="149" alt="image" src="https://github.com/user-attachments/assets/bdce03cd-8ca3-4551-b056-077866a3d00d" />


# 8️⃣ Feature Engineering

- Filling Null Columns with Respective Values 


<img width="1387" height="490" alt="image" src="https://github.com/user-attachments/assets/fdf9801e-60fb-4a31-887d-2c312da9f822" />


<img width="1349" height="293" alt="image" src="https://github.com/user-attachments/assets/403d1fb7-93a1-492f-9a06-176864a7811d" />


- Caculating Average Order Value ( AOV = Total_Spent / Total_Orders )


<img width="1367" height="421" alt="image" src="https://github.com/user-attachments/assets/64f51abb-e902-4465-b588-49d6b2aeca4c" />


# 9️⃣ Business Insight :

- Analyzing delivery performance (Delivery Gap Analysis): 


<img width="1340" height="682" alt="image" src="https://github.com/user-attachments/assets/5deb4433-2b4b-4662-8b44-66570790f450" />

- Customer Segmentation ( Based on AOV ) : 


<img width="1343" height="745" alt="image" src="https://github.com/user-attachments/assets/6754ace6-3a20-4e37-bd80-3b3c518dc9b8" />


<img width="1338" height="418" alt="image" src="https://github.com/user-attachments/assets/d9a985d3-9dd5-46dd-93f8-42c898adc401" />


# 🔟 Data Serving :

- Saved the final aggregated datasets to Gold Layer in Delta format.

- Partitioned datasets based on Customer Segmentation.


  <img width="1319" height="309" alt="image" src="https://github.com/user-attachments/assets/46d8b936-941b-4b90-803e-7cfc564d5b26" />



