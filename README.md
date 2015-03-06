# hawq-tools
Python tools for making life with HAWQ easier

## Python+HAWQ Querying and Analysis
[Using Python with HAWQ - IPython Notebook](http://nbviewer.ipython.org/github/kdunn-pivotal/hawq-tools/blob/master/hawqTest.ipynb)
In this notebook I've demonstrated using the following with HAWQ:
- PSYCOPG2 and Pandas (Querying in SQL)
- SQLAlchemy (Querying in SQL)
- Blaze (Descriptive querying - Pandas DataFrame like methods)

Also, I've shown how to parse HDFS recursive directory listing to visualize HAWQ table distribution quality. This was done with Pandas and the Matplotlib plotting interface for DataFrames.


## Python query plan parsing
[HAWQ Query plan parsing Python - IPython Notebook](http://nbviewer.ipython.org/github/kdunn-pivotal/hawq-tools/blob/master/explainToDot.ipynb)
In this notebook I've developed a Python parsing script for query plans generated using EXPLAIN ANALYZE. The goal is visualize query plans using Graphviz and eventually in D3.js as well. The following will eventually be incorporated *visually*:
- Relative row counts
- Relative costs
- Number of slices
- Number of segments
