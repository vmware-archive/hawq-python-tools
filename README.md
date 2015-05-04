# hawq-tools
Python tools for making life with HAWQ easier

## PySparkSQL Parquet to TSV(gzip) Converter
[Using PySparkSQL as an ETL tool for HAWQ - IPython Notebook](http://nbviewer.ipython.org/github/Pivotal-Field-Engineering/hawq-python-tools/blob/master/parquetRddTsv.ipynb)
In this notebook I use PySparkSQL to load Parquet files as an RDD in Spark and flatten nested objects into text fields so they can be loaded into HAWQ or GPDB. 
The TSV record is built line by line in a predictable way using a template string that gets formatted using a dictionary. Optional columns are populated with NULLs and multi-level nesting is handling by creating a large text field with distinct delimiters for every level to enable easy unpacking by splitting the column outside the database (e.g. Python's str.split(<delimiter>) function).
Tools used:
- Spark, SparkSQL, PySpark
- Parquet data input file, AVRO schema file

## Python+HAWQ Querying and Analysis
[Using Python with HAWQ - IPython Notebook](http://nbviewer.ipython.org/github/Pivotal-Field-Engineering/hawq-python-tools/blob/master/hawqTest.ipynb)
In this notebook I've demonstrated using the following with HAWQ:
- PSYCOPG2 and Pandas (Querying in SQL)
- SQLAlchemy (Querying in SQL)
- Blaze (Descriptive querying - Pandas DataFrame like methods)

Also, I've shown how to parse HDFS recursive directory listing to visualize HAWQ table distribution quality. This was done with Pandas and the Matplotlib plotting interface for DataFrames.


## Python query plan parsing
[Query plan parsing Python - IPython Notebook](http://nbviewer.ipython.org/github/Pivotal-Field-Engineering/hawq-python-tools/blob/master/explainToDot.ipynb)
In this notebook I've developed a Python parsing script for query plans generated using EXPLAIN ANALYZE. The goal is visualize query plans using Graphviz and eventually in D3.js as well. The following will eventually be better incorporated *visually* (e.g. color, size):
- Relative row counts
- Relative costs
- Number of slices
- Number of segments
