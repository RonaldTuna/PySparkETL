# TensorIoTAssignment
This repository contains an assignment for a data engineering position at tensorIoT

In this assignment, I take Amazon review data from "http://jmcauley.ucsd.edu/data/amazon/links.html" and use Apache PySpark to load the file into a Python notebook. This data has over 1 million entries, so Apache spark is far more efficient than pandas due to parallel processes being better/faster on larger datasets. The date for each review was then reformatted using PySpark's to_date() function from MM -D, YYYY to MM-DD-YYYY. This dataframe with reformatted dates is saved to a postgresql server, and saved as a parquet file locally.
