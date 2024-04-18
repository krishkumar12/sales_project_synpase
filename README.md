sales_project_adf (Azure Data Factory)
Sample project to use ADF, ADLS Gen2 and transformed into aggregated data and stored into ADLS Gen 2.

To read three input files (Sales, Product, customer) and ingest, transform and Load by data following medallion Architecture (Bronze, Silver & Gold layers)

Data flow of this project
Step 1 : Copy the csv data from external landing container (data-ext-landing) to raw container (data-raw-bronze) - Used Copy data, delete activities

Step 2 : Data from container (data-raw-bronze) are processed and pre validation like Null checks , converted the csv to parquet - Used Dataflow transformation

Step 3 : Curated data is processed, aggregated and final datasets are created that provides busines insights like (fast moving products, total Sales per day )- Used Dataflow transformation

Inputs
Sales - Sales information of each order

Product - Product specific data (Product ID, name, family )

Customer - Customer data (Customer ID, name etc)

Outputs
1.Fast Moving product

2.Total Sales per day

Dataset formats
Delimited (csv)
parquet
Linked Services
Azure Data Lake Storage Gen 2
Trigger types
Scheduled trigger
Storage event trigger
Activities used
Copy Data
Dataflow
Execute Dataflow
Delete Activity
Pipeline
Execute Pipeline
Dataflow Transformations
Aggregate Transformation
Derived column Transformation
Conditional Split Transformation
Join Transformation
Select Transformation
Sort Transformation
Source Transformation
Sink Transformation
