# TensorIoTAssignment
This repository contains an assignment for a data engineering position at tensorIoT

This Python notebook performs an ETL(Extract Translate and Load) function.

The very first thing to do is to set up the proper environment with the necessary tools. This involves:
  Downloading, installing, importing and starting pyspark and a postgresql server.
  Setting environment variables for java and spark
  Setting up the postgresql server with a user name, password, host, port number and database name.
  downloading a driver so that the postgresql server can connect to our code.


1. I extract Amazon review data from the provided URL "http://jmcauley.ucsd.edu/data/amazon/links.html" by using a wget command, and use Apache PySpark to load the file into a dataframe we can perform functins on. This data has over 1 million entries, so Apache spark is far more efficient than pandas due to distributed processes being better/faster on larger datasets. 

2. I then transform the data by adjusting the dates contained in the 'reviewTime' column. The date for each review was reformatted using PySpark's to_date() function from convert the string into a date, and date_format() to change the date's formate from yyyy-MM-dd to MM-dd-yyyy

3. The data is then loaded. Postgresql doesn't allow for NULL characters to be stored in strings, so first I had to remove them from text fields such as "reviewText" This dataframe with reformatted dates is saved to a local postgresql server in JDBC and saved as a parquet file locally.
