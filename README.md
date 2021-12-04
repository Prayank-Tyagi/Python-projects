# Python-projects

## Data Loading

### Data 1202- Data Tools and Analytics
#### Student Name- Prayank Tyagi Student Id-100841521


## Lets Start

### Prerequisites
##### 1) Anaconda Navigator url https://www.anaconda.com/products/individual
##### 2) Python url https://www.python.org/downloads/

### Installation
1) pip install mysql-connector-python


##### Import Python Libraries

###### import pandas as pd
pandas (all lowercase) is a popular Python-based data analysis toolkit which can be imported using import pandas as pd. It presents a diverse range of utilities, ranging from parsing multiple file formats to converting an entire data table into a NumPy matrix array. This makes pandas a trusted ally in data science and machine learning.

###### import numpy as np
when you call the statement import numpy as np , you are shortening the phrase "numpy" to "np" to make your code easier to read. It also helps to avoid namespace issues. (tkinter and ttk are a good example of what can happen when you do have that issue.

###### import matplotlib.pyplot as plt
matplotlib.pyplot is a collection of command style functions that make matplotlib work like MATLAB. Each pyplot function makes some change to a figure: e.g., creates a figure, creates a plotting area in a figure, plots some lines in a plotting area, decorates the plot with labels, etc. In matplotlib.pyplot various states are preserved across function calls, so that it keeps track of things like the current figure and plotting area, and the plotting functions are directed to the current axes (please note that “axes” here and in most places in the documentation refers to the axes part of a figure and not the strict mathematical term for more than one axis).

###### from sqlalchemy import create_engine
The Engine is the starting point for any SQLAlchemy application. It’s “home base” for the actual database and its DBAPI, delivered to the SQLAlchemy application through a connection pool and a Dialect, which describes how to talk to a specific kind of database/DBAPI combination.

#### Load complete Dataset

df = pd.read_csv("youtube_dataset.csv")
df.head()
Here we are loading the csv file in python and can see the top 5 rows and columns of the "youtube_dataset"

##### Function 

def funcChannelDist(df, row_select):
    new_df = df.iloc[:row_select, [2,9]]
    ChannelDist_df = new_df.groupby(['channeltype'],sort = True).count() 
    return ChannelDist_df
   
###### funcChannelDist is the function we have created 
Creating a new_df where it picks all the rows of the database of 2nd and 9th column of the youtube database and apply group by in channel type.
###### Python iloc() 
function enables us to select a particular cell of the dataset, that is, it helps us select a value that belongs to a particular row or column from a set of values of a data frame or dataset.

###### use of new_df.groupby
Pandas groupby is used for grouping the data according to the categories and apply a function to the categories. It also helps to aggregate data efficiently. Pandas dataframe. groupby() function is used to split the data into groups based on some criteria

#### distribution_df = funcChannelDist(df, 1000)
#### distribution_df

Here it picks the top 1000 records of the youtube_dataset and shows the distribution

### Distribution Chart

#### Plot Chart 

ChannelDist_df['userID'].plot(kind="bar", figsize=(12, 7), fontsize="14", color="red")
plt.xticks( horizontalalignment="center")
plt.title("Distribution of Top 1000 Youtube Channel by Channel Type", fontsize="30")
plt.xlabel("Type of Channel",fontsize="25")
plt.ylabel("Count", fontsize="25")

Here the bar chart shows the Distribution of Top 1000 Youtube Channel by Channel Type



#### Load to CSV
export_df = df.iloc[:1000,:] #filter top 1000 rows
export_df.to_csv("YoutubeTop1000.csv") # Load into CSV
print('Data Loaded Successfully into CSV')

Pandas DataFrames create an excel data structure with labeled axes (rows and columns). To define one DataFrame, you need at least the rows of data and columns name (header).


### Authors

#### > Prayank Tyagi

### Acknowledgemen

#### > Professor Omar
#### > https://durhamcollege.desire2learn.com/d2l/le/content/391138/viewContent/4980020/View
#### > https://towardsdatascience.com/how-to-export-pandas-dataframe-to-csv-2038e43d9c03
     












