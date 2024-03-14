# Home Sales Data Analysis

## Overview
This document outlines the steps and SQL queries required for analyzing a dataset of home sales. The process involves creating Spark DataFrames, temporary tables, caching strategies, and partitioning to efficiently query the dataset for specific insights related to home prices based on various criteria.

## Requirements
- Apache Spark environment for data processing and analysis.
- A dataset containing home sales data, with fields such as year sold, bedrooms, bathrooms, floors, square feet, view, price, and date built.

## Steps

### 1. Create Spark DataFrame
Begin by loading the home sales dataset into a Spark DataFrame to prepare the data for subsequent analysis.

### 2. Create Temporary Table
Create a temporary view of the DataFrame. This allows for the execution of SQL queries on the dataset.

### 3. Query for Four-Bedroom Houses
Execute a SQL query to find the average price of four-bedroom houses sold, rounded to two decimal places, for each year.

### 4. Average Price for 3 Bedrooms and 3 Bathrooms
Query to find the average price of homes with three bedrooms and three bathrooms, for each year the home was built, rounded to two decimal places.

### 5. Specific Criteria Home Prices
Query the average price for homes meeting specific criteria: three bedrooms, three bathrooms, two floors, and square footage greater than or equal to 2,000, by year built, rounded to two decimal places.

### 6. Average Price per View Rating
Query the average price of homes per "view" rating for homes with an average price greater than or equal to $350,000, rounded to two decimal places. Note the runtime for this query.

### 7. Cache the Temporary Table
Improve query performance by caching the `home_sales` temporary table and validate the cache.

### 8. Run Cached Query
Re-run the query from step 6 on the cached table and measure the runtime improvement.

### 9. Data Partitioning
Partition the home sales dataset by the `date_built` field and save it as formatted Parquet data.

### 10. Create Temporary Table from Parquet
Load the partitioned data as a DataFrame and create a temporary view for querying.

### 11. Query on Parquet Table
Execute the query from step 6 on the `p_home_sales_p` table and note the runtime. 

### 12. Uncache and Verify
Finally, uncache the `home_sales` temporary table and verify that it is no longer cached.

## Conclusion
By adhering to the outlined steps, you can conduct an effective analysis of the home sales dataset, taking full advantage of Apache Spark's data processing and querying strengths. This methodology enhances query efficiency and unveils critical trends in home sales. However, it's important to note that for the Parquet table, queries were organized by the 'view' column, as opposed to the partitioning based on the 'date_built' column. This distinction means that while partitioning aids in performance enhancement, the specific grouping by 'date_built' does not directly improve query runtimes in this context.

