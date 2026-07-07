# Day 5 – Data Visualization and Visualization Methods

Today, I learned about **Data Visualization**, its importance in data analysis, and different visualization techniques used for various types of data. Data visualization helps transform raw data into meaningful graphs and charts, making it easier to understand patterns, trends, and relationships.

---

# Topics Learned

* Data Visualization
* Why Visualization is Important
* Visualization Libraries
* Visualization Methods According to Data Type

---

# Data Visualization

Data Visualization is the graphical representation of data using charts, graphs, and plots. It helps present complex information in a simple and understandable way.

Instead of reading large tables of data, visualization allows us to identify trends, patterns, and outliers quickly.

### Example

```python
import matplotlib.pyplot as plt

sales = [120, 150, 180, 200]
months = ["Jan", "Feb", "Mar", "Apr"]

plt.plot(months, sales)
plt.show()
```

---

# Why Does Visualization Help Us?

Data visualization is useful because it:

* Makes data easier to understand.
* Identifies trends and patterns.
* Detects outliers and anomalies.
* Compares different categories.


---

# Popular Python Libraries for Visualization

## Matplotlib

Matplotlib is the most commonly used Python library for creating basic charts and graphs.

```python
import matplotlib.pyplot as plt
```

---

## Seaborn

Seaborn is built on top of Matplotlib and provides more attractive and statistical visualizations.

```python
import seaborn as sns
```

---

# Visualization Methods According to Data Type

Different types of data require different visualization techniques.

---

# 1. Numerical Data

Numerical data contains numbers that can be measured or calculated.

### Common Charts

* Histogram
* Box Plot
* Line Chart
* Scatter Plot

### Histogram

A histogram shows the distribution of numerical data.

```python
import matplotlib.pyplot as plt

plt.hist(df["Age"])
plt.show()
```

**Used for:**

* Distribution of values
* Frequency of numerical data

---

### Box Plot

A box plot is used to detect outliers and understand data spread.

```python
df.boxplot(column="Salary")
```

**Used for:**

* Finding outliers
* Comparing distributions

---

### Line Chart

A line chart shows changes or trends over time.

```python
plt.plot(df["Month"], df["Sales"])
plt.show()
```

**Used for:**

* Time-series data
* Trend analysis

---

### Scatter Plot

A scatter plot shows the relationship between two numerical variables.

```python
plt.scatter(df["Age"], df["Salary"])
plt.show()
```

**Used for:**

* Correlation
* Relationship between variables

---

# 2. Categorical Data

Categorical data contains labels or categories.

### Common Charts

* Bar Chart
* Pie Chart
* Count Plot

---

### Bar Chart

A bar chart compares different categories.

```python
df["Department"].value_counts().plot(kind="bar")
```

**Used for:**

* Comparing categories
* Frequency comparison

---

### Pie Chart

A pie chart shows the proportion of each category.

```python
df["Department"].value_counts().plot(kind="pie", autopct="%1.1f%%")
```

**Used for:**

* Percentage distribution
* Part-to-whole comparison

---

### Count Plot (Seaborn)

A count plot displays the frequency of each category.

```python
import seaborn as sns

sns.countplot(x="Department", data=df)
```

**Used for:**

* Counting categorical values
* Frequency analysis

---

# 3. Numerical vs Numerical Data

When comparing two numerical variables:

### Scatter Plot

```python
plt.scatter(df["Height"], df["Weight"])
plt.show()
```

**Purpose**

* Shows positive or negative relationships.
* Identifies clusters and outliers.

---

# 4. Categorical vs Numerical Data

When comparing one categorical and one numerical variable:

### Bar Plot

```python
import seaborn as sns

sns.barplot(x="Department", y="Salary", data=df)
```

**Purpose**

* Compare average numerical values across categories.

---

### Box Plot

```python
sns.boxplot(x="Department", y="Salary", data=df)
```

**Purpose**

* Compare distributions between different categories.

---

# 5. Multiple Numerical Variables

### Heatmap

A heatmap displays the correlation between numerical variables.

```python
import seaborn as sns

sns.heatmap(df.corr(numeric_only=True), annot=True)
```

**Used for:**

* Correlation analysis
* Multivariate relationships

---

