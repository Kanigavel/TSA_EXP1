# Ex.No: 01A PLOT A TIME SERIES DATA
###  Date:25.07.2026
## Data set : Walmart_sales
# AIM:
To Develop a python program to Plot a time series data (population/ market price of a commodity
/temperature.
# ALGORITHM:
1. Import the required packages like pandas and matplot
2. Read the dataset using the pandas
3. Calculate the mean for the respective column.
4. Plot the data according to need and can be altered monthly, or yearly.
5. Display the graph.
# PROGRAM:
~~~
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px

df = pd.read_csv('/content/Walmart_Sales.csv')
df['Date'] = pd.to_datetime(df['Date'], format='%d-%m-%Y') # Convert 'Date' column to datetime

avg_weekly_sales_by_store = df.groupby('Date')['Weekly_Sales'].mean().reset_index()

fig = px.line(avg_weekly_sales_by_store, x='Date', y='Weekly_Sales', title='Average Weekly Sales Over Time')

fig.update_xaxes(
    title_text='Date (Month)', # Update the x-axis title
    tickformat='%b-%Y' # Format ticks to show month and year (e.g., Jan-2010)
)
fig.update_yaxes(title_text='Average Weekly Sales')
fig.show()

~~~




# OUTPUT:

<img width="839" height="535" alt="image" src="https://github.com/user-attachments/assets/8be688c9-0d7a-4d94-a1b6-540285e1066e" />


# RESULT:
Thus we have created the python code for plotting the time series of given data.
