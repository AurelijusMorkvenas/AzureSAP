AzureSAP: End-to-End Sales Analytics ETL Pipeline
Overview
AzureSAP is a complete ETL (Extract, Transform, Load) pipeline designed for processing and analyzing sales data. The project extracts data from an on-premises SQL Server database, processes it in Azure, and delivers business insights through interactive Power BI dashboards. The solution showcases the integration of modern Azure services to achieve scalable and efficient data engineering workflows.

Objectives
Data Extraction: Retrieve data from an on-premises SQL Server instance and load it into Azure Data Lake Storage Gen2.
Data Transformation: Clean, structure, and aggregate the data in two phases using PySpark on Azure Databricks.
Data Analysis: Load processed data into Azure Synapse Analytics for querying and connect it to Power BI for visualization and reporting.
ETL Process
Extract:
Use Azure Data Factory with Integration Runtime to securely extract data from SQL Server.
Load the extracted data into the Bronze layer of Azure Data Lake Storage Gen2 as raw, unprocessed data.
Transform:
Bronze to Silver:
Perform data cleaning and apply basic transformations to prepare the data for further processing.
Silver to Gold:
Execute advanced transformations and aggregations to make the data analytics-ready.
Load and Analyze:
Load the fully transformed data from the Gold layer into Azure Synapse Analytics for analysis.
Use Power BI to create interactive dashboards and generate insights for decision-making.
Folder Structure in Azure Data Lake
Azure Data Lake Gen2 is used for organizing the data in different stages of the ETL pipeline:

Bronze Layer: Contains raw, unprocessed data extracted directly from the SQL Server.
Silver Layer: Stores intermediate data that has been cleaned and partially transformed.
Gold Layer: Holds the final, fully transformed, and aggregated data that is ready for analytics and reporting.
Setup Instructions
Prerequisites:
An active Azure subscription.
An on-premises SQL Server with the AdventureWorks2022 database installed.
Azure services configured:
Azure Data Factory
Azure Data Lake Storage Gen2
Azure Databricks
Azure Synapse Analytics
Power BI Desktop (or access to the Power BI Service)
Steps to Set Up:
Clone the Repository: Clone this repository to your local machine:

bash
Kopiera kod
git clone https://github.com/AurelijusMorkvenas/AzureSAP
Set Up Linked Services in Azure Data Factory:

Configure a Linked Service for SQL Server using the Integration Runtime.
Create a Linked Service for Azure Data Lake Storage Gen2.
Pipeline Setup in Azure Data Factory:

Import the provided pipeline JSON file into Azure Data Factory.
Modify connection strings, credentials, and configurations as needed.
Set up a trigger to run the pipeline as per your schedule.
Azure Data Lake Storage Gen2:

Create a storage account with the following folder structure:
bronze/ for raw extracted data.
silver/ for cleaned and partially processed data.
gold/ for analytics-ready data.
Azure Databricks:

Create a Databricks workspace and a compute cluster.
Import the provided notebooks and configure the cluster for PySpark execution.
Use the notebooks to perform the Bronze-to-Silver and Silver-to-Gold transformations.
Azure Synapse Analytics:

Set up a Synapse Analytics workspace.
Create a database and deploy the provided stored procedure for serverless views.
Use the provided SQL scripts to create views on the Gold layer data.
Power BI:

Install Power BI Desktop.
Connect to Azure Synapse Analytics to build interactive reports and dashboards.
Publish your Power BI reports to the Power BI Service (optional).
Tools and Technologies
SQL Server: Source database hosting AdventureWorks2022.
Azure Data Factory: For extracting and moving data into Azure.
Azure Data Lake Gen2: To store data in Bronze, Silver, and Gold layers.
Azure Databricks: For scalable data transformations using PySpark.
Azure Synapse Analytics: For querying and integrating the Gold layer data.
Power BI: For building dashboards and visualizing insights.
License
This project is licensed under the MIT License. See the LICENSE file for more details.