# DS2002-ProjectOne

Overview

In this project I built an ETL pipeline that extracts Walmart store sales data from multiple sources and then transforms it and loads it into a SQLite data mart. This allowed me to analyze the data and answer several questions. The business process is retail sales. I tracked weekly sales performance across 45 Walmart stores over a two year period. I chose this dataset because it's a real world example of how a large retailer like Walmart might analyze sales trends over time across different store locations.

Data Sources

One of the main goals of this project was to pull data from three different sources. My first source is a CSV file containing the raw Walmart weekly sales data, which I downloaded from Kaggle. My second source is a local MySQL database where I stored store metadata like store type and size, which came from the original Walmart recruiting competition dataset on kaggle. My third source is MongoDB Atlas, a cloud based NoSQL database, where I stored some economic factors data such as fuel price, CPI, and unemployment rate.

Schema Design

The destination system is a SQLite database organized as a dimensional data mart. The fact table is called fact_sales and contains the core business transaction data — store number, date, and weekly sales amount. Supporting the fact table are four dimension tables: dim_store which holds store type and size pulled from MySQL, dim_date which breaks down each date into year, month, day and quarter, dim_weather which contains temperature and holiday flag data, and dim_economic which holds the economic indicators extracted from MongoDB.

How to Run

If you want to run this project, it only takes a few simple steps. First, make sure MySQL is running locally with the walmart_stores database set up. The stores.csv file in this repo contains the store data that needs to be loaded into MySQL before running. After you have made sure of this, open Project1.ipynb in Jupyter Notebook and run all the cells in the notebook. The pipeline will automatically extract data from the three sources, apply transformations, and load everything into a local sqlite database called sales.db. MongoDB Atlas is hosted in the cloud so no local setup is needed for that. You just need to make sure you have internet. Thank you for viewing my project.
