

# Home Sales Analysis with PySpark

This project performs an analysis on home sales data using Apache Spark and SparkSQL. The data is loaded from a public AWS S3 bucket and queried using SQL-style syntax via PySpark.

## Dataset
The dataset (`home_sales_revised.csv`) contains home sale transactions, including columns such as:
- `date`
- `price`
- `bedrooms`
- `bathrooms`
- `date_built`
- `lot_size`

## Technologies Used
- Apache Spark
- PySpark (SparkSQL)
- Jupyter Notebook
- Google Colab

## Analyses
The notebook performs the following:

1. **Load CSV from AWS S3 into a Spark DataFrame**
2. **Create a SQL Temporary View** using `createOrReplaceTempView`
3. **Query 1**: Average price of 4-bedroom homes sold each year
4. **Query 2**: Average price by year built for homes with 3 beds and 3 baths
5. *(More queries may be added depending on the code later in the notebook)*

## Insights Example

### Average Price for 4 Bedroom Homes per Year
```sql
SELECT YEAR(date) AS year_sold, ROUND(AVG(price), 2) AS avg_price
FROM home_sales
WHERE bedrooms = 4
GROUP BY year_sold
ORDER BY year_sold



## Throughout the project, ChatGPT was used to help

1. Draft SparkSQL queries based on analysis goals.

2. Clarify Spark syntax and best practices for filtering, grouping, and rounding values.

3. Troubleshoot issues related to data types and query structure.

4. Summarize results and suggest ways to present insights clearly.

