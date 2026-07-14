# Day 6 – Feature Engineering Techniques

Today, I learned about **Feature Engineering**, an important step in data preprocessing that helps improve the performance of machine learning models. Feature engineering involves creating, modifying, and selecting features (columns) to make the data more useful for model training.

---

# Topics Learned

* What is Feature Engineering?
* Importance of Feature Engineering
* Common Feature Engineering Techniques

  * Create
  * Transform
  * Encode
  * Scale
  * Bin
  * Extract
  * Combine

---

# What is Feature Engineering?

Feature Engineering is the process of creating, modifying, or selecting features from raw data to improve the performance of machine learning models.

A **feature** is an individual column or attribute in a dataset. Good features help the model learn patterns more effectively and produce more accurate predictions.

### Example

Suppose a dataset contains:

```text
First_Name    Last_Name
John          Smith
Alice         Brown
```

We can create a new feature:

```text
Full_Name
John Smith
Alice Brown
```

---

# Importance of Feature Engineering

Feature engineering is important because it:

* Improves model accuracy.
* Makes data more meaningful.
* Reduces noise in the dataset.
* Helps algorithms learn better patterns.
* Converts raw data into useful features.
* Improves prediction performance.

---

# 1. Create

The **Create** technique involves generating new features from existing data.

### Example

Creating a new feature called **Total Price**.

```python
df["TotalPrice"] = df["Price"] + df["Tax"]
```

**Output**

If:

```text
Price = 500
Tax = 50
```

Then:

```text
TotalPrice = 550
```

---

# 2. Transform

Transformation changes the format or values of existing features without changing their meaning.

It is commonly used to reduce skewness or convert data into a suitable format.

### Example

Applying a logarithmic transformation.

```python
import numpy as np

df["Price"] = np.log(df["Price"])
```

**Purpose**

* Reduce skewed data
* Normalize distributions
* Improve model performance

---

# 3. Encode

Encoding converts categorical (text) data into numerical values because machine learning algorithms work with numbers.

### Example – Label Encoding

```python
from sklearn.preprocessing import LabelEncoder

encoder = LabelEncoder()

df["Gender"] = encoder.fit_transform(df["Gender"])
```

**Before**

```text
Male
Female
Male
```

**After**

```text
1
0
1
```

---

### Example – One-Hot Encoding

```python
pd.get_dummies(df["City"])
```

**Before**

```text
City
Delhi
Mumbai
Delhi
```

**After**

```text
Delhi  Mumbai
1       0
0       1
1       0
```

---

# 4. Scale

Scaling adjusts numerical values so that all features are on a similar range.

Scaling is important for algorithms such as KNN, SVM, and Logistic Regression.

### Example – Standard Scaling

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

df["Salary"] = scaler.fit_transform(df[["Salary"]])
```

---

### Example – Min-Max Scaling

```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()

df["Age"] = scaler.fit_transform(df[["Age"]])
```

---

# 5. Bin

Binning converts continuous numerical values into groups or categories.

### Example

```python
df["Age_Group"] = pd.cut(
    df["Age"],
    bins=[0, 18, 35, 60, 100],
    labels=["Child", "Young", "Adult", "Senior"]
)
```

**Output**

```text
Age    Age_Group
15     Child
25     Young
45     Adult
70     Senior
```

---

# 6. Extract

Extraction creates new features by extracting useful information from existing columns.

### Example – Extracting Year

```python
df["Year"] = pd.to_datetime(df["Date"]).dt.year
```

If:

```text
Date = 2026-07-14
```

Then:

```text
Year = 2026
```

---

### Example – Extracting Month

```python
df["Month"] = pd.to_datetime(df["Date"]).dt.month
```

---

# 7. Combine

Combining merges two or more existing features into a new feature.

### Example

```python
df["Full_Name"] = df["First_Name"] + " " + df["Last_Name"]
```

**Output**

```text
First_Name    Last_Name
John          Smith
```

Becomes:

```text
Full_Name
John Smith
```

---

* Understood the importance of scaling numerical features and extracting useful information from existing columns.
* Gained knowledge of preparing high-quality features for better machine learning predictions.
