## Pandas
Pandas is arguably the most important Python package for data analysis. With over 100 million downloads per month, it is the de facto standard package for data manipulation and exploratory data analysis. Its ability to read from and write to an extensive list of formats makes it a versatile tool for data science practitioners. Its data manipulation functions make it a highly accessible and practical tool for aggregating, analyzing, and cleaning data. 

In our blog post on how to learn pandas, we discussed the learning path you may take to master this package. This beginner-friendly tutorial will cover all the basic concepts and illustrate pandas' different functions. You can also check out our course on pandas Foundations for further details. 

This article is aimed at beginners with basic knowledge of Python and no prior experience with pandas to help you get started.

### What is pandas?
pandas is a data manipulation package in Python for tabular data. That is, data in the form of rows and columns, also known as DataFrames. Intuitively, you can think of a DataFrame as an Excel sheet. 

pandas’ functionality includes data transformations, like sorting rows and taking subsets, to calculating summary statistics such as the mean, reshaping DataFrames, and joining DataFrames together. pandas works well with other popular Python data science packages, often called the PyData ecosystem, including

### 1. NumPy for numerical computing
### 2. Matplotlib, Seaborn, Plotly, and other data visualization packages
### 3. scikit-learn for machine learning

## What is pandas used for?
pandas is used throughout the data analysis workflow. With pandas, you can:

Import datasets from databases, spreadsheets, comma-separated values (CSV) files, and more.
Clean datasets, for example, by dealing with missing values.
Tidy datasets by reshaping their structure into a suitable format for analysis.
Aggregate data by calculating summary statistics such as the mean of columns, correlation between them, and more.
Visualize datasets and uncover insights.
pandas also contains functionality for time series analysis and analyzing text data.

### Key benefits of the pandas package
Undoubtedly, pandas is a powerful data manipulation tool packaged with several benefits, including:

Made for Python: Python is the world's most popular language for machine learning and data science.
Less verbose per unit operations: Code written in pandas is less verbose, requiring fewer lines of code to get the desired output. 
Intuitive view of data: pandas offers exceptionally intuitive data representation that facilitates easier data understanding and analysis.
Extensive feature set: It supports an extensive set of operations from exploratory data analysis, dealing with missing values, calculating statistics, visualizing univariate and bivariate data, and much more.
Works with large data: pandas handles large data sets with ease. It offers speed and efficiency while working with datasets of the order of millions of records and hundreds of columns, depending on the machine.

## Install pandas
Installing pandas is straightforward; just use the pip install command in your terminal. 
```python
pip install pandas
```

## Importing data in pandas
To begin working with pandas, import the pandas Python package as shown below. When importing pandas, the most common alias for pandas is pd.

```python
import pandas as pd
```
Use read_csv() with the path to the CSV file to read a comma-separated values file

```python
df = pd.read_csv("diabetes.csv")
```
Example:
```python
import pandas as pd

df = pd.read_csv('data.csv')

print(df.to_string())
```

This read operation loads the CSV file diabetes.csv to generate a pandas Dataframe object df.

### Importing text files

Reading text files is similar to CSV files. The only nuance is that you need to specify a separator with the sep argument, as shown below. The separator argument refers to the symbol used to separate rows in a DataFrame. Comma (sep = ","), whitespace(sep = "\s"), tab (sep = "\t"), and colon(sep = ":") are the commonly used separators. Here \s represents a single white space character.


```python
df = pd.read_csv("diabetes.txt", sep="\s")
```
### Importing Excel files (single sheet)
Reading excel files (both XLS and XLSX) is as easy as the read_excel() function, using the file path as an input.
```python
df = pd.read_excel('diabetes.xlsx')
```
You can also specify other arguments, such as header for to specify which row becomes the DataFrame's header. It has a default value of 0, which denotes the first row as headers or column names. You can also specify column names as a list in the names argument. The index_col (default is None) argument can be used if the file contains a row index.

### Importing Excel files (multiple sheets)
Reading Excel files with multiple sheets is not that different. You just need to specify one additional argument, sheet_name, where you can either pass a string for the sheet name or an integer for the sheet position (note that Python uses 0-indexing, where the first sheet can be accessed with sheet_name = 0)

```python
# Extracting the second sheet since Python uses 0-indexing
df = pd.read_excel('diabetes_multi.xlsx', sheet_name=1)
```

### Importing JSON file
Similar to the read_csv() function, you can use read_json() for JSON file types with the JSON file name as the argument. The below code reads a JSON file from disk and creates a DataFrame object df.

```python
df = pd.read_json("diabetes.json")
```

**Example**

```python
import pandas as pd

df = pd.read_json('data.json')

print(df.to_string())
```

### Dictionary as JSON

#2.Example
```python
import pandas as pd

C_Data = { 'Name' :['Bharath','Bharath','Sumathi','Lalit','Abdul'],
          'Age': [27,28,33,34,23],
          'Address': ['Chennai','Chennai','Delhi','Hyd','bangalore'],
          'Company':['Aspire system','Aspire system','Aspire system','Aspire system','Aspire system']}
df =pd.DataFrame(C_Data)

print(df)
```

## Outputting data in pandas
Just as pandas can import data from various file types, it also allows you to export data into various formats. This happens especially when data is transformed using pandas and needs to be saved locally on your machine. Below is how to output pandas DataFrames into various formats.

### Outputting a DataFrame into a CSV file
A pandas DataFrame (here we are using df) is saved as a CSV file using the .to_csv() method. The arguments include the filename with path and index – where index = True implies writing the DataFrame’s index.

```python
df.to_csv("diabetes_out.csv", index=False)
```
**Code Explanation**

. This code saves a pandas DataFrame df to a CSV file named "diabetes_out.csv" in the current working directory.
• The to_csv() method is used to write the DataFrame to a CSV file.
• The index=False argument specifies that the index column should not be included in the output file.
• This is useful when the index is not meaningful or when it is already included as a separate column in the DataFrame.

## Outputting a DataFrame into a JSON file
Export DataFrame object into a JSON file by calling the .to_json() method.
```python
df.to_json("diabetes_out.json")
```

**Note:** A JSON file stores a tabular object like a DataFrame as a key-value pair. Thus you would observe repeating column headers in a JSON file.

## Outputting a DataFrame into a text file
As with writing DataFrames to CSV files, you can call .to_csv(). The only differences are that the output file format is in .txt, and you need to specify a separator using the sep argument.

```python
df.to_csv('diabetes_out.txt', header=df.columns, index=None, sep=' ')
```
## Outputting a DataFrame into an Excel file
Call .to_excel() from the DataFrame object to save it as a “.xls” or “.xlsx” file.
```python
df.to_excel("diabetes_out.xlsx", index=False)
```

## Viewing and understanding DataFrames using pandas 
After reading tabular data as a DataFrame, you would need to have a glimpse of the data. You can either view a small sample of the dataset or a summary of the data in the form of summary statistics.

## How to view data using .head() and .tail()

You can view the first few or last few rows of a DataFrame using the .head() or .tail() methods, respectively. You can specify the number of rows through the n argument (the default value is 5).

```python
df.head()
```
**Code Explanation**
This code is written in Python and it calls the head() method on a Pandas DataFrame object named df.
• The head() method is used to display the first few rows of the DataFrame.
• By default, it displays the first 5 rows, but you can pass an integer argument to display a different number of rows.
• This code is useful for quickly inspecting the contents of a DataFrame and getting a sense of what kind of data it contains.

![image](https://github.com/naveen9596/Datascience-AI-Topics/assets/108785228/f653f88b-e36f-4950-858d-553b5a4a3ce7)

                                    First five rows of the DataFrame 
```python
df.tail(n = 10)
```
![image](https://github.com/naveen9596/Datascience-AI-Topics/assets/108785228/f7d7f04f-b7da-429a-a195-8b4d74eb9265)

### Understanding data using .describe()

The .describe() method prints the summary statistics of all numeric columns, such as count, mean, standard deviation, range, and quartiles of numeric columns.

```python
df.describe()
```

**Code Explanation**
This code is written in Python and it calls the describe() method on a Pandas DataFrame object named df.
• The describe() method generates descriptive statistics of the DataFrame, including count, mean, standard deviation, minimum, maximum, and quartile values for each column.
• This method is useful for quickly understanding the distribution of data in a DataFrame.

![image](https://github.com/naveen9596/Datascience-AI-Topics/assets/108785228/1d931b2b-2068-4fd1-9d60-268d97719568)

It gives a quick look at the scale, skew, and range of numeric data.

You can also modify the quartiles using the percentiles argument. Here, for example, we’re looking at the 30%, 50%, and 70% percentiles of the numeric columns in DataFrame df.

```python
df.describe(percentiles=[0.3, 0.5, 0.7])
```

![image](https://github.com/naveen9596/Datascience-AI-Topics/assets/108785228/af9886f7-c8b2-4a8b-b0b1-5803dbee333d)

You can also isolate specific data types in your summary output by using the include argument. Here, for example, we’re only summarizing the columns with the integer data type. 

```python
df.describe(include=[int])
```

* This code is written in Python and it uses the describe() method to generate descriptive statistics of a DataFrame.
• The include parameter is used to specify the data types to be included in the output.
• In this case, it includes only integer columns in the output.
• So, df.describe(include=[int]) will generate descriptive statistics of only the integer columns in the DataFrame df.
• This includes the count, mean, standard deviation, minimum, maximum, and quartile values of the integer columns.

![image](https://github.com/naveen9596/Datascience-AI-Topics/assets/108785228/97942374-bd98-4570-993d-a7727c5545bc)

Similarly, you might want to exclude certain data types using exclude argument.

```python
df.describe(exclude=[int])
```
![image](https://github.com/naveen9596/Datascience-AI-Topics/assets/108785228/850f22b4-d7d9-412e-bc0e-a5ec1b783ffe)


Often, practitioners find it easy to view such statistics by transposing them with the .T attribute.

```python
df.describe().T
```
* This code uses the describe() method to generate summary statistics of a pandas DataFrame df.
• The T attribute is then used to transpose the resulting summary statistics table, so that the rows become columns and vice versa.
• This makes it easier to read and compare the statistics for different columns.
• For example, if df has columns for "age", "income", and "education", the resulting table will have rows for "count", "mean", "std", "min", "25%", "50%", "75%", and "max", and columns for "age", "income", and "education".
• Overall, this code is useful for quickly getting an overview of the distribution and range of values in a DataFrame.

![image](https://github.com/naveen9596/Datascience-AI-Topics/assets/108785228/83d37e5f-485e-4913-9c58-4b0f942bf634)

### Understanding data using .info()
The .info() method is a quick way to look at the data types, missing values, and data size of a DataFrame. Here, we’re setting the show_counts argument to True, which gives a few over the total non-missing values in each column. We’re also setting memory_usage to True, which shows the total memory usage of the DataFrame elements. When verbose is set to True, it prints the full summary from .info(). 

```python
df.info(show_counts=True, memory_usage=True, verbose=True)
```
![image](https://github.com/naveen9596/Datascience-AI-Topics/assets/108785228/5fa32930-edaa-4b00-9dfa-0a84ac332d35)

### Understanding your data using .shape
The number of rows and columns of a DataFrame can be identified using the .shape attribute of the DataFrame. It returns a tuple (row, column) and can be indexed to get only rows, and only columns count as output.

```python
df.shape # Get the number of rows and columns
df.shape[0] # Get the number of rows only
df.shape[1] # Get the number of columns only
```
```python
(768,9)
768
9
```
### Get all columns and column names
Calling the .columns attribute of a DataFrame object returns the column names in the form of an Index object. As a reminder, a pandas index is the address/label of the row or column.

```python
df.columns
```

![image](https://github.com/naveen9596/Datascience-AI-Topics/assets/108785228/4dc09e7b-9a92-48ff-971e-9a8b953f1fc9)

It can be converted to a list using a list() function.

```python
list(df.columns)
```
![image](https://github.com/naveen9596/Datascience-AI-Topics/assets/108785228/6f0fe88c-bd05-41ea-a233-49bda3400be4)



****************************************************************************************
                                
