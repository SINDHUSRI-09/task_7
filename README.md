# task_7
elevate labs internship task 7
# SQL Server Data Access with PyODBC and Pandas

This project demonstrates how to connect to a Microsoft SQL Server database using `pyodbc` in Python, execute SQL queries, and load data into `pandas` for analysis.

## Features

- Connects to SQL Server using `ODBC Driver 17 for SQL Server`
- Executes SQL queries
- Loads query results into pandas DataFrames
- Includes bar, scatter, and line graph visualizations using `matplotlib`
- Supports local trusted connections

## Requirements

- Python 3.10 or later
- SQL Server (local or remote)
- ODBC Driver 17 for SQL Server
- Required Python packages:
  - `pyodbc`
  - `pandas`
  - `numpy`
  - `matplotlib`

## Setup

1. **Install Dependencies**

```bash
pip install pyodbc pandas numpy matplotlib

2. Verify Installed Drivers



import pyodbc
print(pyodbc.drivers())

3. Database Connection



conn = pyodbc.connect(
    'Driver={ODBC Driver 17 for SQL Server};'
    'Server=YOUR_SERVER_NAME;'
    'Database=YOUR_DATABASE_NAME;'
    'Trusted_Connection=yes;'
)

4. Querying the Database



import pandas as pd

cursor = conn.cursor()
cursor.execute("SELECT * FROM your_table_name")

data = cursor.fetchall()
columns = [column[0] for column in cursor.description]
df = pd.DataFrame(data, columns=columns)

print(df.head())

Visualizations

This project includes the following types of charts created using matplotlib:

Bar charts

Scatter plots

Line graphs


These help in visualizing the queried data for better insights.
