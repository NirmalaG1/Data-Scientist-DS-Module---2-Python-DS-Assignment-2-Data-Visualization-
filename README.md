# Data-Scientist-DS-Module---2-Python-DS-Assignment-2-Data-Visualization-
In this project, you will act as a data analyst to clean, analyze, and visualize taxi data. You will handle  missing values, explore trends, and create visualizations to gain insights into fare, distance, and  customer behavior using Pandas, Matplotlib, and Seaborn. 



1) Loading the Taxis Dataset using the following code: 
import seaborn as sns  
# Load the 'taxis' dataset  
df = sns.load_dataset("taxis") -------------->loaded data set as df 


2) Handling Missing Values  
● Check for missing values in the dataset and identify columns with missing data.  ------------>used df.isnull().sum() to calculate number of null values
  
●  Impute missing values using appropriate strategies based on the column type (e.g., 
using the mean, median, or mode for numerical columns and the mode for categorical 
columns).  ---------------------> used df.select_types method to extract categorical and nemerical columns. and using functions mean() and mode()[0] filled missing  values


●  For columns that are critical and cannot be reasonably imputed, remove rows with 
missing values to maintain data integrity.  ------------>#cosidering  coloum "pickup_zone" as critical. so removing its rows which has missing values. used 
df.dropna with sunset method inplace as True


4) Visualizations using Matplotlib/Pandas Plot:  
★ Line Chart  
Plot a line chart to visualize the fare over time, using the pickup timestamp as the x-axis and 
fare as the y-axis. Ensure the pickup column is converted to a datetime format before plotting.-------------->coververted pickup column to datetime type

and grouped df with respect  to pickup and calulated mean of fare .from this plotted line plot input as pickup and mean of fare



★ Bar Chart  
Create a bar chart to show the total fare for each pickup_borough. Group the data by 
pickup_borough and sum the fare for each group.  ----------> grouped df by pickup_borough and calculated sum of fare and plotted 



★ Pie Chart  
Plot a pie chart showing the distribution of trips based on the payment method (credit card, 
cash, etc.). Each slice should represent the count of trips for a specific payment method.  -->grouped by payment and calculated its count


★ Histogram  
Create a histogram to visualize the distribution of distance. Customize the number of bins for 
better granularity and ensure the plot is easy to interpret. ------> plotted hist by taking disatnce  as input



★ Box Plot  
Plot a box plot to visualize the distribution of tip amounts for each pickup_borough. Use 
pickup_borough as the categorical axis and tip as the numeric axis.  -----> grouped by picup_borough and calculated sum of tip amounts


Visualizations using Seaborn:  
★ Count Plot  
Create a count plot to visualize the number of trips in each pickup_borough. The x-axis should 
represent the boroughs, and the y-axis should show the count of trips.  

★ Scatter Plot  
Plot a scatterplot to show the relationship between distance and fare. Use distance on the 
x-axis and fare on the y-axis to visualize any correlation. Color the points based on the 
pickup_borough to differentiate the trips by their respective boroughs.  

★ Heatmap  
Plot a heatmap to visualize the correlation between numerical variables such as distance, fare, 
tip, tolls, and total. Use a correlation matrix to highlight the relationships. ---------------->calculated corlation matrix for the given columns and ploted heatmap for correlation matrix with annot as True 


★ Pair Plot  
Create a pair plot to visualize the pairwise relationships between distance, fare, tip, and total. 
Color the data points according to the pickup_zone column. to compare how different zones 
affect these variables.  --------------------------->plotted the columns as var and hue as pickup_zone. since pickup_zone has many unique values the legend become  unreadable. so filtered the df with  most occurring pickup_zone values. with that plotted pairplat again


★ Violin Plot  
Plot a violin plot to show the distribution of fare for each payment method. Use the payment 
method as the categorical axis and fare as the numeric axis to visualize its distribution. 

