# [Retail Customer Churn Prediction](https://gallery.cortanaintelligence.com/Solution/c2920246ecae45d28db7adc970d67c9b)

This folder contains the deployment instructions for the Retail Customer Churn Prediction solution in the Cortana Intelligence Gallery. To start a new solution deployment, visit the gallery page [here](https://gallery.cortanaintelligence.com/Solution/c2920246ecae45d28db7adc970d67c9b).

<Guide type="PostDeploymentGuidance" url="https://github.com/Azure/cortana-intelligence-churn-prediction-solution/blob/master/Automated%20Deployment%20Guide/Post%20Deployment%20Instructions.md"/>


## Summary
<Guide type="Summary">
Retail Customer Churn Prediction uses Cortana Intelligence Suite components to predict churn probability and helps find patterns in existing data associated with the predicted churn rate.
</Guide>


## Prerequisites
<Guide type="Prerequisites">
This solution requires the following prerequisites:

1.  An [Azure subscription](https://azure.microsoft.com/en-us/) with login credentials
2.  A free [Azure Machine Learning Studio](https://azure.microsoft.com/en-us/services/machine-learning/) subscription
3.  A [Microsoft Power BI](https://powerbi.microsoft.com/en-us/) account
4.  An installed copy of [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/?gated=0&number=0)
5.  A local installation of [Visual Studio with SQL Server Data Tools (SSDT)](https://azure.microsoft.com/en-us/documentation/articles/sql-data-warehouse-install-visual-studio/)
</Guide>

#### Estimated Provisioning Time: <Guide type="EstimatedTime">30 Minutes</Guide>


## Description
<Guide type="Description">

Keeping existing customers is five times cheaper than the cost of attaining new ones. For this reason, marketing executives often find themselves trying to estimate the likelihood of customer churn and finding the necessary actions to minimize the churn rate.

Customer Churn Prediction uses Azure Machine Learning to predict churn probability and helps find patterns in existing data associated with the predicted churn rate. This information empowers businesses with actionable intelligence to improve customer retention and profit margins.

The objective of this guide is to demonstrate predictive data pipelines for retailers to predict customer churn. Retailers can use these predictions to prevent customer churn by using their domain knowledge and proper marketing strategies to address at-risk customers. The guide also shows how customer churn models can be retrained to leverage additional data as it becomes available.

## What's Under the Hood
The end-to-end solution is implemented in the cloud, using Microsoft Azure. The solution is composed of several Azure components, including data ingest, data storage, data movement, advanced analytics and visualization. The advanced analytics are implemented in Azure Machine Learning Studio, where one can use Python or R language to build data science models (or reuse existing in-house or third-party libraries).  

## Solution Diagram
![Solution Diagram](https://user-images.githubusercontent.com/18489406/27402331-4c0e7520-5694-11e7-911b-a6ed2b51eabe.png)


## Technical details and workflow

1.  Historial sample data is loaded from **Azure Blob Stroage** into **Azure SQL Datawarehouse** using Polybase.

2.  Real-time event data will be ingested through Event Hub into **Azure Stream Analytics** and finally into **Azure SQL Datawarehouse**.

3.  The predictions from **Azure ML** webservice are performed in batches using the **Azure Data Factory**. Azure ML webservie takes the data from **Azure SQL Datawarehouse** as input and outputs the prediction results back to **Azure Blob Storage**. 

4.  Finally, **Power BI** is used for results visualization from **Azure SQL Datawarehouse**

</Guide>

#### Disclaimer

©2017 Microsoft Corporation. All rights reserved.  This information is provided "as-is" and may change without notice. Microsoft makes no warranties, express or implied, with respect to the information provided here.  Third party data was used to generate the solution.  You are responsible for respecting the rights of others, including procuring and complying with relevant licenses in order to create similar datasets.