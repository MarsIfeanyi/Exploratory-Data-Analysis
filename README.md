# Exploratory Data Analysis with Pandas

Some of the Key Metrics to look out for while doing exploratory data analysis on any dataset

### df.info():
prints a summary of your DataFrame, showing:

the total number of rows and columns
each column's name
how many non-null (non-missing) values each column has
each column's data type (int64, float64, object, etc.)
the total memory usage

It's typically one of the first things you run when you load a new dataset to quickly understand its structure and spot missing values or columns with the wrong data type (like a number column stored a

### df.describe():
generates summary statistics for all numeric columns in your DataFrame, showing:

count — number of non-null values
mean — average value
std — standard deviation (how spread out the values are)
min — smallest value
25% — first quartile (25% of values fall below this)
50% — median (middle value)
75% — third quartile (75% of values fall below this)
max — largest value

It's useful for quickly spotting outliers, understanding the range of your data, and checking if distributions look reasonable. Like df.info(), it's a standard first step in exploratory data analysis.

### df.isnull():
checks every cell in your DataFrame for missing values. It returns a DataFrame of the same shape filled with True where a value is missing and False where it isn't.

### df.duplicated().sum()
counts the total number of duplicate rows in your DataFrame.
It works in two steps:

df.duplicated() returns a Series of True/False for every row — True if that row is an exact duplicate of a previous row, False if it's unique
.sum() counts all the True values, giving you the total number of duplicates

### df.dtypes()
It returns the data type of every column in your DataFrame

### df.shape()
It returns a tuple of (rows, columns). It is used to check the size of your DataFrame, and commonly used after cleaning operations to confirm rows were dropped correctly:

### df.corr()
computes the pairwise correlation between all numeric columns in your DataFrame, returning a correlation matrix.
Each value in the matrix ranges from -1 to 1:

1 — perfect positive correlation (both columns increase together)
0 — no correlation
-1 — perfect negative correlation (one increases as the other decreases)

### df.value_counts()
counts the frequency of unique values in a column, returning them sorted from most to least common.
It's typically used on a single column (Series), not the whole DataFrame

### df.hist(figsize=(12,8))
plots a histogram for every numeric column in your DataFrame at once, giving you a quick visual overview of how each column's values are distributed.
Breaking it down:

df.hist() — generates one histogram per numeric column
figsize=(12,8) — sets the overall figure size in inches (width=12, height=8)