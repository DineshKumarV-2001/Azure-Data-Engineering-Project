# Azure-Olist-Data-Engineering-Project

# 📌 Project Overview

This project demonstrates an end-to-end ETL pipeline built on Azure, processing the Olist eCommerce dataset using Azure Data Factory, Azure Databricks (PySpark), and Azure Data Lake Storage Gen2. It follows a modern medallion architecture (Bronze, Silver, Gold) for layered data management.


# 🔁 Project Architecture

<img width="1011" height="568" alt="image" src="https://github.com/user-attachments/assets/a2d804a7-aab4-4bbf-8f71-f810263c7900" />


# ⚙️ Tools & Technologies

Azure Data Factory (ADF)

Azure Databricks (PySpark)

Azure Data Lake Storage Gen2 (ADLS Gen2)

Python / PySpark


# 🧭 ETL Architecture

<img width="676" height="236" alt="image" src="https://github.com/user-attachments/assets/1d380822-1f9e-43dd-84af-80ce90028eb5" />

              
# 1️⃣ Data Extraction

Linked ADLS Gen2 to ADF using service principal authentication.

Created ADF pipelines to load .csv files from http(github) into Bronze Layer in ADLS Gen2.

![image](https://github.com/user-attachments/assets/3d3c7666-ad47-43ad-b40d-5b07757e1269)

# 2️⃣ Data Exploration / EDA

Loaded data into PySpark DataFrames.


- Constructed a basic data model for joins.
  

<img width="2486" height="1496" alt="image" src="https://github.com/user-attachments/assets/00782ce0-aae5-480b-ba02-a5b615d51d20" />


- Performed schema inference (not recommended for Real-Time Use-Case), Prefer - Manual Schema using **StructType**.
  

<img width="626" height="241" alt="image" src="https://github.com/user-attachments/assets/eaed8bd2-4f74-42cf-9425-71d72b32b654" />

<img width="614" height="525" alt="image" src="https://github.com/user-attachments/assets/dd9aa7b0-9017-4c8b-b7d2-a2fadbc229da" />


# 3️⃣ Data Validation / Quality Analysis

- Validated: Null values, Column types, Uniqueness and referential integrity

<img width="1326" height="426" alt="image" src="https://github.com/user-attachments/assets/9efce441-d943-45e6-9a49-5d1f72c26ebf" />


<img width="547" height="636" alt="image" src="https://github.com/user-attachments/assets/f708c976-45c9-4e1d-ba24-3c6c267f8b30" />




# 4️⃣ Data Curation

- Selected necessary columns from each dataset, Renamed columns and applied logical grouping, Joined key datasets.

 
<img width="1319" height="622" alt="image" src="https://github.com/user-attachments/assets/c1bd5b22-9ed7-4195-a4fd-edddd31f9816" />


- Joining Datasets.
  


<img width="907" height="292" alt="image" src="https://github.com/user-attachments/assets/332af3c6-c718-4445-9d8f-be33d1bda8c2" />




# 5️⃣ Optimization

Applied .cache() on final joined DataFrame to optimize repeated usage.



<img width="1323" height="232" alt="image" src="https://github.com/user-attachments/assets/1c37993c-c106-4b02-b228-3262925d77ca" />



# 7️⃣ Data Transformation

- Renaming Columns: Used .withColumnRenamed() for clarity.
  

<img width="941" height="344" alt="image" src="https://github.com/user-attachments/assets/86e5f9bc-60b7-4a9f-b2a8-58b8d417e8d0" />



- Structuring Columns: Grouped fields logically.

<img width="914" height="131" alt="image" src="https://github.com/user-attachments/assets/eae1b6c1-6424-4750-83ee-c5f8f38a29e9" />


- Data Cleaning :

<img width="493" height="99" alt="image" src="https://github.com/user-attachments/assets/d26dd415-6737-4527-9600-a346c517d890" />


# 8️⃣ Data Serving to Silver Layer :

<img width="929" height="105" alt="image" src="https://github.com/user-attachments/assets/efd93900-66e7-43c0-a386-26f650deef60" />

<img width="571" height="280" alt="image" src="https://github.com/user-attachments/assets/104274db-bfba-478a-898c-e97ded7949be" />


# 9️⃣ Feature Engineering

- Filling Null Columns with Respective Values 


<img width="1387" height="490" alt="image" src="https://github.com/user-attachments/assets/fdf9801e-60fb-4a31-887d-2c312da9f822" />


<img width="1349" height="293" alt="image" src="https://github.com/user-attachments/assets/403d1fb7-93a1-492f-9a06-176864a7811d" />


- Calculating Delivery Gap : 


<img width="1340" height="682" alt="image" src="https://github.com/user-attachments/assets/5deb4433-2b4b-4662-8b44-66570790f450" />


- Extracting Year From Pruchase Date :

<img width="768" height="377" alt="image" src="https://github.com/user-attachments/assets/2a1be756-f62a-497a-9ba7-690ed94d9a4b" />

<img width="498" height="202" alt="image" src="https://github.com/user-attachments/assets/b8fce979-0471-48a2-8b9b-d9f278b9c103" />




# 🔟 Business Insight :



# 1️⃣1️⃣ Data Serving to Gold Layer :

- Saved the final aggregated datasets to Gold Layer in Parquet format.

- Partitioned datasets based on Customer Segmentation.

<img width="521" height="330" alt="image" src="https://github.com/user-attachments/assets/4dda3a4e-3acc-46e6-9bc5-873f3a6970e6" />








