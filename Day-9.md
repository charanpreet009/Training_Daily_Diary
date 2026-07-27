# Day 9 – Pattern Detection and Anomaly Detection

Today, I learned about **Pattern Detection**, **Group Comparison**, **Anomaly Detection using the Z-Score Method**, **Pattern Detection with Pivot Tables**, and **Finding Patterns using Clustering**. These techniques help discover hidden trends, unusual observations, and meaningful relationships in data, making them valuable for data analysis and machine learning.

---

# Topics Learned

* Pattern Detection
* Group Comparison
* Z-Score Method for Anomaly Detection
* Detecting Patterns with Pivot Tables
* Finding Patterns with Clustering

---

# Pattern Detection

Pattern Detection is the process of identifying meaningful trends, relationships, or repeated behaviors within a dataset. Detecting patterns helps analysts understand the data and make informed decisions.

### Why Pattern Detection is Important

* Identifies trends and relationships.
* Helps in decision-making.
* Detects unusual behavior.
* Improves machine learning models.
* Supports business and scientific analysis.

### Example

Suppose a store records monthly sales:

```text
Month      Sales
January    1200
February   1350
March      1500
April      1700
```

From this data, we can identify an increasing sales trend over time.

---

# Group Comparison

Group Comparison is the process of comparing different groups within a dataset to identify similarities or differences.

### Example

Compare the average salary of employees from different departments.

| Department | Average Salary |
| ---------- | -------------: |
| Sales      |          52000 |
| HR         |          48000 |
| IT         |          70000 |
| Finance    |          65000 |

### Python Example

```python
import pandas as pd

df.groupby("Department")["Salary"].mean()
```

### Benefits

* Compares performance between groups.
* Identifies high-performing categories.
* Supports business decision-making.

---

# Z-Score Method for Anomaly Detection

The **Z-Score** method is a statistical technique used to detect **anomalies (outliers)** in numerical data.

A **Z-Score** tells us how many standard deviations a data point is away from the mean.

### Formula

```text
Z = (X − Mean) / Standard Deviation
```

Where:

* **X** = Data value
* **Mean** = Average value
* **Standard Deviation** = Measure of data spread

### Interpretation

* **Z-Score between -3 and +3** → Normal value
* **Z-Score less than -3 or greater than +3** → Possible anomaly (outlier)

### Python Example

```python
from scipy.stats import zscore

df["Z_Score"] = zscore(df["Salary"])

outliers = df[df["Z_Score"].abs() > 3]

print(outliers)
```

### Advantages

* Easy to calculate.
* Effective for normally distributed data.
* Quickly identifies unusual values.

### Limitations

* Works best with normally distributed data.
* Sensitive to extreme outliers.

---

# Detecting Patterns with Pivot Tables

A **Pivot Table** summarizes large datasets and helps identify patterns by organizing data into rows, columns, and aggregated values.

### Example

Find the average sales by department and region.

```python
import pandas as pd

pivot = pd.pivot_table(
    df,
    values="Sales",
    index="Department",
    columns="Region",
    aggfunc="mean"
)

print(pivot)
```

### Sample Output

| Department | North | South |
| ---------- | ----: | ----: |
| Sales      |  1500 |  1400 |
| HR         |   900 |   850 |
| IT         |  2100 |  1950 |

### Benefits

* Summarizes large datasets.
* Makes comparisons easier.
* Reveals hidden trends.
* Supports quick reporting.

---

# Finding Patterns with Clustering

**Clustering** is an unsupervised machine learning technique that groups similar data points into clusters based on their characteristics.

Objects in the same cluster are more similar to each other than to objects in other clusters.

### Example

A shopping company groups customers based on:

* Age
* Annual Income
* Spending Score

The algorithm may produce:

```text
Cluster 1 → Students
Cluster 2 → Working Professionals
Cluster 3 → Senior Citizens
```

These groups help the company provide personalized marketing strategies.

---

## K-Means Clustering Example

```python
from sklearn.cluster import KMeans

kmeans = KMeans(n_clusters=3, random_state=42)

df["Cluster"] = kmeans.fit_predict(df[["Age", "Income"]])

print(df.head())
```

### Applications of Clustering

* Customer segmentation
* Market analysis
* Recommendation systems
* Image segmentation
* Fraud detection
* Medical diagnosis

