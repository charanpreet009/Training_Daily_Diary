# Day 4 – Exploratory Data Analysis (EDA) and Data Analysis Techniques

Today, I learned about **Exploratory Data Analysis (EDA)**, which is the process of exploring and understanding a dataset before building machine learning models. I also learned important Pandas functions like `unique()` and `value_counts()`, along with the concepts of **Univariate**, **Bivariate**, and **Multivariate Analysis**.

---

## Topics Learned

* Exploratory Data Analysis (EDA)
* `unique()`
* `value_counts()`
* Univariate Analysis
* Bivariate Analysis
* Multivariate Analysis

---

# Exploratory Data Analysis (EDA)

Exploratory Data Analysis (EDA) is the process of examining, summarizing, and visualizing a dataset to understand its structure, identify patterns, detect anomalies, and discover relationships between variables.

EDA helps data analysts clean data, choose suitable machine learning algorithms, and make informed decisions based on the dataset.

### Objectives of EDA

* Understand the structure of the dataset.
* Identify missing values and duplicates.
* Detect outliers.
* Discover patterns and trends.
* Find relationships between variables.
* Prepare the data for machine learning.

---

# `unique()`

The `unique()` function returns all the distinct (unique) values present in a column.

It is useful for finding different categories available in the dataset.

### Example

```python
import pandas as pd

df = pd.read_csv("students.csv")

print(df["Department"].unique())
```

**Output**

```python
['Computer Science' 'Mechanical' 'Civil' 'Electrical']
```

---

# `value_counts()`

The `value_counts()` function counts how many times each unique value appears in a column.

It is commonly used for categorical data.

### Example

```python
df["Department"].value_counts()
```

**Output**

```python
Computer Science    40
Mechanical          25
Civil               20
Electrical          15
```

---

# Univariate Analysis

Univariate Analysis is the analysis of **only one variable** at a time.

Its purpose is to understand the distribution, frequency, and characteristics of a single feature.

### Common Methods

* Histogram
* Bar Chart
* Pie Chart
* Box Plot
* Frequency Table

### Example

```python
df["Department"].value_counts()
```

Another example:

```python
df["Age"].describe()
```

### What We Learn

* Distribution of values
* Maximum and minimum values
* Most frequent category
* Presence of outliers

---

# Bivariate Analysis

Bivariate Analysis studies the relationship between **two variables**.

It helps determine whether one variable affects another.

### Common Methods

* Scatter Plot
* Bar Plot
* Correlation
* GroupBy
* Cross Tabulation

### Example 1 – Average Marks by Department

```python
df.groupby("Department")["Marks"].mean()
```

### Example 2 – Correlation

```python
df[["Age", "Marks"]].corr()
```

### What We Learn

* Relationship between two variables.
* Positive or negative correlation.
* Comparison between different groups.

---

# Multivariate Analysis

Multivariate Analysis examines **three or more variables simultaneously** to understand complex relationships in the dataset.

It provides deeper insights compared to univariate and bivariate analysis.

### Common Methods

* GroupBy with multiple columns
* Pivot Table
* Cross Tabulation
* Correlation Matrix
* Pair Plot

### Example 1 – Multiple GroupBy

```python
df.groupby("Department")[["CGPA", "Attendance"]].mean()
```

This calculates the average **CGPA** and **Attendance** for each department.

---

### Example 2 – Pivot Table

```python
pd.pivot_table(
    df,
    values="Marks",
    index="Department",
    columns="Gender",
    aggfunc="mean"
)
```

This compares the average marks of male and female students across different departments.

---

### Example 3 – Correlation Matrix

```python
df.corr(numeric_only=True)
```

This shows the relationship among multiple numerical variables.

---


# Importance of EDA

* Helps understand the dataset before analysis.
* Detects missing values and outliers.
* Identifies patterns and trends.
* Improves data quality.
* Assists in selecting appropriate machine learning models.
* Leads to better decision-making through data insights.

---
