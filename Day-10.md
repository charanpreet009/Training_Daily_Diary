# Day 10 – Automated Exploratory Data Analysis (Auto EDA)

Today, I learned about **Automated Exploratory Data Analysis (Auto EDA)**. Auto EDA is a technique that automatically analyzes a dataset and generates a detailed report with statistics, visualizations, and insights. It helps data analysts and machine learning engineers save time by reducing manual analysis.

---

# Topics Learned

* What is Auto EDA?
* Why Auto EDA is Important
* Popular Auto EDA Libraries
* Generating an Auto EDA Report
* Advantages and Limitations of Auto EDA

---

# What is Auto EDA?

**Automated Exploratory Data Analysis (Auto EDA)** is the process of automatically exploring and analyzing a dataset using Python libraries. Instead of manually checking data using multiple functions, Auto EDA generates a complete report with just a few lines of code.

The report usually includes:

* Dataset overview
* Data types
* Missing values
* Duplicate values
* Statistical summary
* Correlation analysis
* Distribution of features
* Outlier detection
* Visualizations
* Data quality warnings

---

# Why is Auto EDA Important?

Auto EDA is important because it:

* Saves time.
* Reduces manual work.
* Quickly identifies missing values and duplicates.
* Detects outliers and data quality issues.
* Provides statistical summaries automatically.
* Helps understand the dataset before machine learning.

---

# Popular Auto EDA Libraries

## 1. ydata-profiling

`ydata-profiling` is one of the most popular Auto EDA libraries. It generates a complete HTML report containing dataset statistics, correlations, missing values, visualizations, and alerts.

### Example

```python
import pandas as pd
from ydata_profiling import ProfileReport

df = pd.read_csv("house_price.csv")

profile = ProfileReport(df, title="Auto EDA Report")

profile.to_file("EDA_Report.html")
```

---

## 2. Sweetviz

Sweetviz creates attractive and interactive HTML reports. It is useful for exploring datasets and comparing training and testing data.

### Example

```python
import sweetviz as sv

report = sv.analyze(df)

report.show_html("Sweetviz_Report.html")
```

---

## 3. AutoViz

AutoViz automatically generates different types of charts and visualizations from a dataset with very little code.

### Example

```python
from autoviz.AutoViz_Class import AutoViz_Class

AV = AutoViz_Class()

AV.AutoViz(
    filename="house_price.csv",
    depVar="Price"
)
```

---

# Steps to Perform Auto EDA

1. Import the dataset.
2. Install the required Auto EDA library.
3. Generate the report.
4. Review the statistics, charts, and insights.
5. Use the findings to clean and prepare the data.

---

# Advantages of Auto EDA

* Generates reports automatically.
* Saves significant time and effort.
* Easy to use, even for beginners.
* Provides interactive visualizations.

---

# Limitations of Auto EDA

* Large datasets may take longer to process.
* Reports can consume more memory.
* Does not replace domain knowledge or manual analysis.

