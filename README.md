This repository contains an assignment for a data engineering position at TensorIoT

This Python notebook performs an ETL (Extract Transform and Load) function on data consisting of Amazon reviews, in order to reformat the dates contained in each review to match the specified pattern as assigned by TensorIoT.

Setup: Before performing the ETL function, I first set up the environment with the necessary tools. This involves:
  -Downloading, installing, importing, and starting Pyspark and a Postgresql server
  -Setting environment variables for Java to fulfill the requirements for Spark
  -Setting up the Postgresql server with a username, password, host, port number, and database name 
  -Downloading a driver so that the Postgresql server can connect to our code

**Extract**: I then extracted Amazon review data from the provided URL "http://jmcauley.ucsd.edu/data/amazon/links.html" by using a wget command and used Pyspark to load the file into a dataframe on which we can perform functions. 

**Transform**: I then transformed the data by adjusting the dates contained in the 'reviewTime' column. I used to_date() and date_format() to change the date's format from yyyy-MM-dd to MM-dd-yyyy and saved the new values in a new column. I then deleted the old ‘reviewTime’ column and renamed the new column as ‘reviewTime.’

**Load**: Finally, I loaded the data. Because Postgresql doesn't allow for NULL characters to be stored in text, I had to remove them from text fields such as "reviewText" using regexp_replace(). This dataframe with reformatted dates is then saved to a local Postgresql server in JDBC and saved as a parquet file locally.
