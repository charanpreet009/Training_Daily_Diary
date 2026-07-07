# Day 3 – Data Cleaning, Missing Values, and Outliers

Today, I learned about **Data Cleaning**, its importance in data analysis, common Pandas operations, methods to handle missing values, and the concept of outliers. Data cleaning is one of the most important steps before performing data analysis or building machine learning models.

---

## Topics Learned

* Data Cleaning
* Importance of Data Cleaning
* Common Pandas Operations
* Handling Missing Values
* Methods to Fill Missing Values
* Outliers

---

# Data Cleaning

Data Cleaning is the process of identifying and correcting inaccurate, incomplete, duplicate, or inconsistent data. Clean data improves the quality of analysis and helps machine learning models produce more accurate results.

### Example

```python
import pandas as pd

df = pd.read_csv("students.csv")
```

Before analyzing the dataset, we clean it by removing errors and handling missing values.

---

# Importance of Data Cleaning

Data cleaning is essential because:

* Improves data quality.
* Removes duplicate records.
* Handles missing values.
* Reduces errors in analysis.
* Increases the accuracy of machine learning models.
* Makes data consistent and reliable.

---

# Common Pandas Operations

Pandas provides many built-in functions to understand a dataset.

## `head()`

The `head()` method displays the first five rows of the dataset by default.

### Example

```python
df.head()
```

---

## `tail()`

The `tail()` method displays the last five rows of the dataset.

### Example

```python
df.tail()
```

---

## `info()`

The `info()` method provides information about the dataset, including:

* Number of rows and columns
* Column names
* Data types
* Non-null values
* Memory usage

### Example

```python
df.info()
```

---

## `describe()`

The `describe()` method generates statistical summaries of numerical columns.

It provides:

* Count
* Mean
* Standard Deviation
* Minimum Value
* Maximum Value
* Quartiles (25%, 50%, 75%)

### Example

```python
df.describe()
```

---

## `isnull()`

The `isnull()` method checks whether each value is missing (`NaN`) or not.

### Example

```python
df.isnull()
```

Output:

```text
Name     Age
False    False
True     False
False    True
```

---

## `isnull().sum()`

This method counts the total number of missing values in each column.

### Example

```python
df.isnull().sum()
```

Output:

```text
Name      1
Age       2
Marks     0
dtype: int64
```

---

# Handling Missing Values

Missing values are empty or unknown values in a dataset. They can reduce the quality of analysis if not handled properly.

There are several methods to handle missing values.

---

## Method 1 – Remove Rows with Missing Values

If only a few rows contain missing values, they can be removed.

### Example

```python
df.dropna(inplace=True)
```

This removes all rows containing at least one missing value.

---

## Method 2 – Fill Missing Values with Mean

The **mean** is the average of all numerical values.

It is suitable for numerical data that does not contain extreme outliers.

### Example

```python
df["Age"].fillna(df["Age"].mean(), inplace=True)
```

---

## Method 3 – Fill Missing Values with Median

The **median** is the middle value after sorting the data.

It is preferred when the data contains outliers because it is less affected by extreme values.

### Example

```python
df["Salary"].fillna(df["Salary"].median(), inplace=True)
```

---

## Method 4 – Fill Missing Values with Mode

The **mode** is the most frequently occurring value.

It is commonly used for categorical data.

### Example

```python
df["Department"].fillna(df["Department"].mode()[0], inplace=True)
```

---

# What is an Outlier?

An **Outlier** is a data value that is significantly different from the other values in a dataset. Outliers may occur due to measurement errors, data entry mistakes, or genuine unusual observations.

### Example

Consider the following ages:

```text
20, 21, 22, 23, 24, 25, 120
```

Here, **120** is an outlier because it is much larger than the other values.

---


---

# Detecting Outliers

One simple way to detect outliers is by using a **Box Plot**.

### Example

```python
import matplotlib.pyplot as plt

df.boxplot(column="Age")
plt.show()
```

The points outside the box plot are considered potential outliers.

---
