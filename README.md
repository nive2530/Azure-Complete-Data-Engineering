# **AdventureWorks ETL and Analytics Pipeline in Azure**

## **Project Overview**
This project implements an **end-to-end ETL and analytics pipeline** using **Microsoft Azure** services. The goal is to extract, transform, store, and analyze the **AdventureWorks dataset**, generating valuable business insights using **Power BI**.

## **Workflow**

### **1. Data Ingestion**
- Used the **AdventureWorks dataset** provided by Microsoft.
- Created a **Resource Group** in Azure for centralized resource management.
- Configured **Azure Data Lake Storage Gen2** with three containers:
  - **Raw** (stores unprocessed data)
  - **Transform** (stores transformed data in Parquet format)
  - **Serving** (for optimized storage for end users (Data Analyst, Data Scientist)

### **2. ETL Pipeline Development using Azure Data Factory**
- Developed an **ETL pipeline** in **Azure Data Factory (ADF)** utilizing **dynamic parameter passing**.
- **Extracted data** from GitHub using **HTTP Linked Service**.
- Loaded the extracted raw data into the **"raw" storage container** in Azure Data Lake.

### **3. Data Transformation using Azure Databricks**
- Used **Azure Databricks** and **PySpark** to process and clean data.
- Performed transformations such as data formatting required for analytics.
- Converted processed data into **Parquet format** and stored it in the **"transform" container**.

### **4. Data Warehousing with Azure Synapse Analytics**
- Utilized **Azure Synapse Analytics** as a **data warehouse**.
- Accessed the transformed data stored in **Data Lake** using **OPENROWSET()** in SQL.
- Created a **serverless SQL Database Pool** for scalable querying.
- Queried the dataset using **SQL** to generate key business insights.

### **5. Data Visualization with Power BI**
- Established a **connection between Azure Synapse Analytics and Power BI** using the server address.
- Developed an **interactive dashboard** in **Power BI** to visualize key insights.
- Published the dashboard for stakeholders to explore analytical findings.

---

## **Key Features**
✅ **Automated ETL pipeline** with **Azure Data Factory**  
✅ **Data transformation** using **Azure Databricks (PySpark)**  
✅ **Serverless querying** with **Azure Synapse Analytics**  
✅ **Business intelligence dashboard** in **Power BI**  

---

## **Project Structure**
```
AdventureWorks-ETL-Azure/
│── data/                  # Raw and transformed data (not stored in repo)
│── notebooks/             # PySpark scripts for data transformation
│── sql_queries/           # SQL scripts for querying data in Synapse Analytics
│── powerbi/               # Power BI dashboard file (.pbix)
│── pipeline/              # Azure Data Factory pipeline JSON definitions
│── README.md              # Project documentation
```

---

## **Technologies Used**
- **Azure Data Lake Storage Gen2** (Cloud storage)
- **Azure Data Factory** (ETL pipeline)
- **Azure Databricks (PySpark)** (Data transformation)
- **Azure Synapse Analytics** (Data warehousing)
- **Power BI** (Data visualization)
- **SQL** (Data querying)
