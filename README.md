# TensorIoTAssignment
This repository contains an assignment for a data engineering position at tensorIoT

This Python notebook performs an ETL(Extract Translate and Load) function.
1. I extract Amazon review data from "http://jmcauley.ucsd.edu/data/amazon/links.html" and use Apache PySpark to load the file into a Python notebook. This data has over 1 million entries, so Apache spark is far more efficient than pandas due to parallel processes being better/faster on larger datasets. 

2. I then transform the data by adjusting the dates contained in the 'reviewTime' column. The date for each review was reformatted using PySpark's to_date() function from MM -D, YYYY to MM-DD-YYYY. 

3. The data is then loaded. This dataframe with reformatted dates is saved to an sql server, Microsoft express, and saved as a parquet file locally.
