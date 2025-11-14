## Quiz 1
### Question 1 (1 point)
What is the main data structure used in pandas for handling tabular data?
Options:
 A) Series
B) Array
C) Dictionary
D) DataFrame


Answer: Dataframe. It's like Python's version of SQL.

Source: https://www.databricks.com/glossary/pandas-dataframe


### Question 2:
Which of the following methods is used to remove missing (NaN) values from a pandas DataFrame?
Options:
A) dropna()
B) fillna()
C) replace()
D) remove()


Answer: A) dropna().

fillna replaces the NULL values with a specified value. Replace replaces etc


### Question 3:
What function in NumPy is used to find the mean of an array?
Options:
A) np.mean()
B) np.avg()
C) np.median()
D) np.mode()


Ans: A) Mean


### Question 4:
NumPy arrays support element-wise arithmetic operations without the need for loops.
Options:
A) True
B) False


Ans: True.

Source: https://stackoverflow.com/questions/25817226/are-element-wise-operations-faster-with-numpy-functions-than-operators

NumPy has built in methods that bypass needing to use loops. So you don't need to do "for x in numpy.thing".



### Question 5 (1 point)
The groupby() function in pandas is used to filter out specific rows from a DataFrame.
Options:
 A) True
B) False


Ans: False. groupby() function is used to split data into groups based on some criteria, not to filter out rows. Filtering is typically done using methods like df[df['column'] > value].

Source: https://www.geeksforgeeks.org/python-pandas-dataframe-groupby/

### Question 6 (1 point)
NumPy arrays are more memory-efficient and faster than Python lists for numerical computations.
Options:
 A) True
B) False


Answer: True. Source: https://www.altexsoft.com/blog/numpy-pros-and-cons/

### Question 7 (1 point)
The iloc[] method in pandas is used for label-based indexing.
Options:
 A) True
B) False

Ans: False  The iloc[] method is used for integer-based indexing, while loc[] is used for label-based indexing. Source: https://www.w3schools.com/python/pandas/ref_df_iloc.asp


## Quiz 2

### Question 1 (1 point)
Which of the following transformations is used to stabilize variance and make the data more normally distributed?
Options:
 A) Logarithmic transformation
B) Square root transformation
C) Inverse transformation
D) All of the above



Answer: D) All of the above
Explanation: All these transformations (logarithmic, square root, and inverse) can be used to stabilize variance and make data more normally distributed, depending on the nature of the data.



### Question 2:
Substituting missing data with the mean value is always good as measures of spread are not affected.
Options:
A) True
B) False


Answer: B) False
Explanation: Substituting missing data with the mean can reduce the variability (spread) of the data, which can affect statistical analyses. It’s not always the best approach, especially if the data is not normally distributed.



### Question 3:
Which of the following is NOT a typical activity in Exploratory Data Analysis (EDA)?
Options:
A) Identifying interesting subsets of the observations
B) Testing a specific statistical hypothesis
C) Examining important interrelationships between attributes
D) Developing an initial idea of possible associations among predictors


Answer: B) Testing a specific statistical hypothesis
Explanation: EDA is about exploring data to understand its structure, patterns, and relationships. Hypothesis testing is more formal and typically comes after EDA.



### Question 4:
Why is it important to identify and handle outliers in a dataset?
Options:
A) Outliers have no impact on data analysis
B) Outliers can significantly affect the results of certain statistical analyses
C) Outliers always represent errors in data entry
D) Outliers should always be removed from the dataset


Answer: B) Outliers can significantly affect the results of certain statistical analyses
Explanation: Outliers can skew results and affect the accuracy of statistical analyses, so it’s important to identify and handle them appropriately.


### Question 5:
In Decimal Scaling, normalized values lie between 0 and 1.
Options:
A) True
B) False

Answer: B) False
Explanation: Decimal scaling normalizes data by moving the decimal point, but the range of the normalized values depends on the data and is not necessarily between 0 and 1.


### Question 6:
What is the primary goal of data mining?
Options:
A) Replacing traditional databases with machine learning models
B) Extracting useful patterns and knowledge from large datasets
C) Organizing data into structured tables
D) Ensuring data privacy and security


Answer: B) Extracting useful patterns and knowledge from large datasets
Explanation: The primary goal of data mining is to discover patterns, correlations, and knowledge from large datasets.


This is why every company does it.

### Question 7:
In the context of EDA, what is the significance of visual tools such as graphs and plots?
Options:
A) They are used primarily for presentation purposes and do not aid in analysis
B) They help uncover important relationships and patterns within the data
C) They are only useful for large datasets
D) They replace the need for any statistical analysis

Answer: B) They help uncover important relationships and patterns within the data
Explanation: Visual tools like graphs and plots are essential in EDA for uncovering patterns, trends, and relationships in the data.

Basically, visual tools let you get an overview of the data.

### Question 8:
Which of the following is not correct?
Options:
A) Outliers are extreme values that go against the trend of the remaining data
B) Outliers may represent errors in data entry
C) If outliers are valid data points, then there is no chance to produce unstable results by applying statistical methods
D) Outliers can result in a skewed distribution

Answer: C) If outliers are valid data points, then there is no chance to produce unstable results by applying statistical methods
Explanation: Even if outliers are valid, they can still produce unstable results in statistical analyses because they can skew the data.

### Question 9:
In the context of data preprocessing, what does the acronym GIGO stand for?
Options:
A) Grouped Input, Grouped Output
B) General Information, General Output
C) Garbage In, Garbage Out
D) Great Input, Great Output

Answer: C) Garbage In, Garbage Out
Explanation: GIGO stands for "Garbage In, Garbage Out," meaning that the quality of the output is determined by the quality of the input.

### Question 10:
Bars are same-sized in normalized charts.
Options:
A) True
B) False

Answer: B) False
Explanation: In normalized charts, bars represent proportions or percentages, so their sizes vary depending on the data.



### Question 11:
Which of the following is a graphical method for identifying outliers in a dataset?
Options:
A) Mean calculation
B) Histogram
C) Correlation matrix
D) Standard deviation

Answer: B) Histogram
Explanation: A histogram is a graphical method that can help identify outliers by showing the distribution of data.


Mean Calcs, Correlation Matrix and Stds incorporate all data and calc stuff. So outliers skew them. Histograms just show the actual points in a graph with no adjustment or calcs. This question is basically asking "which of these is a graph that just shows the raw data".

### Question 12:
Why is data preprocessing essential in data mining?
Options:
A) It reduces the size of the dataset
B) It increases the complexity of data models
C) It enhances the quality and suitability of data for analysis
D) It eliminates the need for data visualization

Answer: C) It enhances the quality and suitability of data for analysis

Explanation: Basically better setting up your data for analysis.

### Question 13:
EDA is useful for:
Options:
A) Delving into data
B) Examining interrelationships between attributes
C) Developing an initial idea of possible associations among predictors
D) All of the above

Answer: D) All of the above
Explanation: EDA is useful for all these activities: delving into data, examining relationships, and developing initial ideas about associations.

### Question 14:
Which method can be used to handle missing data by estimating and filling in the missing values?
Options:
A) Deletion
B) Imputation
C) Clustering
D) Normalization

Answer: B) Imputation
Explanation: Imputation is the process of estimating and filling in missing values, often using methods like mean, median, or regression.

Source: https://en.wikipedia.org/wiki/Imputation_(statistics)

### Question 15:
Which of the following is a measure of center?
Options:
A) Mean
B) Median
C) Mode
D) All of the above

Answer: D) All of the above
Explanation: Mean, median, and mode are all measures of central tendency, which describe the center of a data distribution.

Source: https://www.abs.gov.au/statistics/understanding-statistics/statistical-terms-and-concepts/measures-central-tendency


