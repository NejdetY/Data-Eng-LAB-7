# Data-Eng-LAB-7

Using Delta Lake in Azure Synapse Analytics

Step 1: Creating the Azure Synapse Workspace

What I did:
I used the Azure Portal and PowerShell Cloud Shell to deploy an Azure Synapse workspace using an ARM template. This process also created a Data Lake and a Spark pool. I downloaded the necessary files from GitHub and ran the setup.ps1 script to set up the environment.

Step 2: Exploring the Data in the Data Lake

What I did:
I opened the products.csv file in Azure Synapse Studio and loaded it into a PySpark DataFrame. I displayed the first 10 rows to understand the structure of the data.

Step 3: Creating a Delta Table from CSV

What I did:
I saved the DataFrame to the /delta/products-delta directory in Delta format. This converted the CSV data into a Delta Lake table.

Step 4: Updating Data in the Delta Table

What I did:
I used Delta Lake’s update feature to modify the data. Specifically, I reduced the price of the product with ProductID = 771 by 10%, and then displayed the updated data.

Step 5: Version Control (Time Travel)

What I did:
I used Delta Lake’s versioning feature to view the previous state of the data by specifying versionAsOf = 0. I also used the history command to view the change log of the Delta table.

Step 6: Creating Catalog Tables

What I did:
I created both external and managed Spark SQL tables based on the Delta data. For the external table, I provided the path to the data. For the managed table, the path was handled automatically. I queried these tables using SQL and reviewed their schemas.

Step 7: Deleting Tables and Observing Differences

What I did:
I deleted both tables to see the difference between managed and external tables. When I deleted the external table, the data files remained. But when I deleted the managed table, the data files were also removed.

Step 8: Creating a Delta Table Using SQL

What I did:
Using SQL, I created a new table based on the data in /delta/products-delta and queried it to confirm the data was accessible.

Step 9: Working with Streaming Data Using Delta Lake

What I did:
I simulated a real-time IoT data stream by writing JSON files to a folder. I created a Spark structured streaming job that read from this folder and saved the output in Delta format. I then queried the streaming data using SQL for real-time analysis.

Conclusion:

In this lab, I learned how to use key Delta Lake features in Azure Synapse Analytics, including data loading, updates, version control, table creation, and real-time data streaming with Delta format.
