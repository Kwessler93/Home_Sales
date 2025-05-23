# Home Sales Spark SQL Analysis

## Overview

This analysis uses Apache Spark and PySpark SQL to process and analyze a large home sales dataset. The notebook demonstrates how to load data, transform it into a Spark DataFrame, cache tables, perform SQL queries, and compare performance across different formats (cached vs. Parquet). The goal was to practice distributed querying with Spark SQL and understand optimizations through caching and partitioning.

## Summary of Tasks Completed

- ✅ **Created a Spark DataFrame from the home sales dataset sourced from a remote CSV file using Spark's file reading capabilities.**
- ✅ **Created a temporary table named `home_sales` from the initial DataFrame to enable SQL-style queries using Spark SQL.**
- ✅ **Wrote a SQL query to calculate the average sale price (rounded to two decimals) for four-bedroom homes, grouped by the year the home was sold.**
- ✅ **Queried the average sale price (rounded) for homes with three bedrooms and three bathrooms, grouped by the year the home was built.**
- ✅ **Extended the previous query to filter for homes with three bedrooms, three bathrooms, two floors, and a size of at least 2,000 square feet, calculating the average price per year built.**
- ✅ **Calculated the average home price per 'view' rating, filtering results to include only those view ratings where the average home price was $350,000 or more. Also recorded the query's runtime.**
- ✅ **Cached the `home_sales` temporary table using `spark.catalog.cacheTable()` and validated the cache with `isCached()`.**
- ✅ **Re-ran the previous query on the cached data and measured the new runtime to compare performance improvement.**
- ✅ **Partitioned the home sales dataset by the `date_built` field and wrote it as Parquet files for optimized querying.**
- ✅ **Read the partitioned Parquet data into a new DataFrame using Spark's Parquet reader.**
- ✅ **Created a new temporary table from the Parquet DataFrame for further querying.**
- ✅ **Executed the same average price per 'view' query from earlier on the Parquet-based table and compared the runtime.**
- ✅ **Uncached the `home_sales` table using `spark.catalog.uncacheTable()` and validated it with `isCached()`.**

## Tools Used

- Apache Spark
- PySpark SQL
- Jupyter Notebook

## Performance Comparison

Each query was timed under three different conditions:
1. Uncached temporary table
2. Cached temporary table
3. Partitioned Parquet table

The runtime comparisons provided insight into the benefits of caching and partitioning when processing large datasets.

---

