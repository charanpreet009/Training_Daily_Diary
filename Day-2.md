Here is a GitHub-ready report in the same format as your previous one.

# Day 2 – Data Fundamentals, Python Data Structures, Pandas, and Data Pipeline

Today, I continued my training by learning about data, different types of data, Python data structures, Pandas data structures, the data pipeline, and data transformation. These concepts are essential for data analysis and machine learning.

## Topics Learned

* What is Data?
* Types of Data
* Python Data Structures
* Pandas Data Structures
* Data Pipeline
* Data Transformation 
---

# What is Data?

Data is a collection of facts, figures, observations, or information that can be processed to gain useful insights. Data can be in the form of numbers, text, images, videos, or audio.

### Example

```python
name = "John"
age = 22
salary = 45000.50
```

Here,

* `"John"` is text data.
* `22` is numeric data.
* `45000.50` is decimal data.

---

# Types of Data

Data can be classified into different types.

## 1. Numerical Data

Numerical data consists of numbers and can be used for calculations.

### Example

```python
age = 24
price = 599.99
```

---

## 2. Categorical Data

Categorical data represents labels or categories instead of numbers.

### Example

```python
gender = "Male"
department = "Sales"
```

---

## 3. Boolean Data

Boolean data contains only two possible values.

* True
* False

### Example

```python
is_student = True
is_employed = False
```

---

## 4. Date and Time Data

This type of data represents dates and time.

### Example

```python
date = "2026-07-07"
time = "10:30 AM"
```

---

# Python Data Structures

Python provides several built-in data structures to store and organize data efficiently.

## List

A list is an ordered and mutable collection.

### Example

```python
fruits = ["Apple", "Banana", "Mango"]
print(fruits)
```

---

## Tuple

A tuple is an ordered but immutable collection.

### Example

```python
colors = ("Red", "Green", "Blue")
print(colors)
```

---

## Set

A set stores unique values and does not allow duplicates.

### Example

```python
numbers = {10, 20, 30, 20}
print(numbers)
```

**Output**

```python
{10, 20, 30}
```

---

## Dictionary

A dictionary stores data in key-value pairs.

### Example

```python
student = {
    "Name": "John",
    "Age": 21,
    "City": "New York"
}

print(student)
```

---

# Pandas Data Structures

Pandas is a powerful Python library used for data analysis and manipulation. It mainly provides two data structures.

## Series

A Series is a one-dimensional labeled array that stores a single column of data.

### Example

```python
import pandas as pd

marks = pd.Series([85, 90, 78, 95])

print(marks)
```

---

## DataFrame

A DataFrame is a two-dimensional table consisting of rows and columns.

### Example

```python
import pandas as pd

data = {
    "Name": ["John", "Alice", "David"],
    "Age": [21, 22, 20],
    "Marks": [85, 90, 88]
}

df = pd.DataFrame(data)

print(df)
```

---

# Data Pipeline

A Data Pipeline is a sequence of steps used to collect, process, analyze, and visualize data.

```
Raw Data
     ↓
Import Data
     ↓
Understand Data
     ↓
Data Cleaning
     ↓
Data Transformation
     ↓
Data Analysis
     ↓
Visualization
     ↓
Insights
```

## Step 1 – Raw Data

Raw data is the original data collected from different sources. It may contain errors, duplicate values, or missing values.

---

## Step 2 – Import Data

The raw data is imported into Python using libraries like Pandas.

### Example

```python
import pandas as pd

df = pd.read_csv("students.csv")
```

---

## Step 3 – Understand Data

Before analysis, it is important to understand the dataset.

Common functions:

```python
df.head()
df.info()
df.describe()
```

---

## Step 4 – Data Cleaning

Data cleaning removes errors and improves data quality.

Common tasks include:

* Removing duplicate values
* Handling missing values
* Correcting incorrect data
* Removing unnecessary columns

### Example

```python
df.drop_duplicates(inplace=True)
df.fillna(0, inplace=True)
```

---

## Step 5 – Data Transformation

Data transformation converts data into a suitable format for analysis and machine learning.

Common transformations include:

* Changing data types
* Scaling numerical values
* Encoding categorical variables
* Creating new features
* Renaming columns

### Example

```python
df["Age"] = df["Age"].astype(int)
```

---

## Step 6 – Data Analysis

In this step, useful information is extracted from the cleaned data.

### Example

```python
df.describe()
```

---

## Step 7 – Visualization

Visualization helps represent data using graphs and charts for better understanding.

Popular libraries include:

* Matplotlib
* Seaborn

### Example

```python
import matplotlib.pyplot as plt

df["Age"].plot(kind="hist")
plt.show()
```

---

## Step 8 – Insights

Insights are the meaningful conclusions obtained after analyzing the data. These insights help in making informed decisions and building machine learning models.
