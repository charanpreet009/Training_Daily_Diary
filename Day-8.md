# Day 8 – Handling Imbalanced Data

Today, I learned about **Imbalanced Data**, why it is a problem in machine learning, how to identify it, and different techniques to balance the dataset. I also learned popular resampling algorithms such as **Random Oversampling**, **Random Undersampling**, **SMOTE**, **ADASYN**, and **SMOTE + Tomek Links**.

---

# Topics Learned

* What is Imbalanced Data?
* Why is Imbalanced Data a Problem?
* How to Check for Imbalanced Data
* Random Oversampling
* Random Undersampling
* SMOTE (Synthetic Minority Over-sampling Technique)
* ADASYN (Adaptive Synthetic Sampling)
* SMOTE + Tomek Links

---

# What is Imbalanced Data?

An **Imbalanced Dataset** is a dataset where one class has significantly more samples than the other class(es).

For example, in a fraud detection dataset:

```text
Class           Number of Records

Not Fraud            980
Fraud                 20
```

Here, the dataset is **imbalanced** because the **Not Fraud** class has many more records than the **Fraud** class.

---

# Why is Imbalanced Data a Problem?

When a dataset is imbalanced:

* The machine learning model becomes biased toward the majority class.
* Minority class predictions become less accurate.
* Accuracy may appear high but the model performs poorly on rare cases.
* Important events (such as fraud or diseases) may not be detected.

---

# How to Check for Imbalanced Data

The easiest way is to count the number of records in each class.

### Using `value_counts()`

```python
df["Target"].value_counts()
```

**Output**

```text
0    980
1     20
```

---

### Checking Class Distribution in Percentage

```python
df["Target"].value_counts(normalize=True) * 100
```

**Output**

```text
0    98%
1     2%
```

This indicates that the dataset is highly imbalanced.

---

# Random Oversampling

Random Oversampling increases the number of samples in the minority class by randomly duplicating existing records.

### Example

Before Oversampling

```text
Class A : 900
Class B : 100
```

After Oversampling

```text
Class A : 900
Class B : 900
```

### Python Example

```python
from imblearn.over_sampling import RandomOverSampler

ros = RandomOverSampler(random_state=42)

X_resampled, y_resampled = ros.fit_resample(X, y)
```

### Advantages

* Easy to implement.
* Balances the dataset quickly.
* No information is lost.

### Disadvantages

* Creates duplicate records.
* May increase the risk of overfitting.

---

# Random Undersampling

Random Undersampling reduces the number of samples in the majority class by removing random records.

### Example

Before Undersampling

```text
Class A : 900
Class B : 100
```

After Undersampling

```text
Class A : 100
Class B : 100
```

### Python Example

```python
from imblearn.under_sampling import RandomUnderSampler

rus = RandomUnderSampler(random_state=42)

X_resampled, y_resampled = rus.fit_resample(X, y)
```

### Advantages

* Faster model training.
* Reduces dataset size.

### Disadvantages

* Important information may be lost.
* Can reduce model performance if too much data is removed.

---

# SMOTE (Synthetic Minority Over-sampling Technique)

SMOTE is one of the most popular techniques for handling imbalanced datasets.

Instead of copying existing minority samples, SMOTE creates **new synthetic samples** by interpolating between nearby minority class examples.

### Example

Before SMOTE

```text
Majority Class : 900
Minority Class : 100
```

After SMOTE

```text
Majority Class : 900
Minority Class : 900
```

The new minority samples are **generated**, not duplicated.

### Python Example

```python
from imblearn.over_sampling import SMOTE

smote = SMOTE(random_state=42)

X_resampled, y_resampled = smote.fit_resample(X, y)
```

### Advantages

* Generates new synthetic data.
* Reduces overfitting compared to random oversampling.
* Improves minority class learning.

### Disadvantages

* May create unrealistic synthetic samples.
* Works only with numerical features.

---

# ADASYN (Adaptive Synthetic Sampling)

ADASYN is an advanced version of SMOTE.

It generates **more synthetic samples for minority instances that are harder to learn**, while generating fewer samples for easier instances.

This adaptive approach helps the model focus on difficult cases.

### Python Example

```python
from imblearn.over_sampling import ADASYN

adasyn = ADASYN(random_state=42)

X_resampled, y_resampled = adasyn.fit_resample(X, y)
```

### Advantages

* Focuses on difficult minority samples.
* Improves model performance on complex datasets.
* Produces adaptive synthetic data.

### Disadvantages

* Slightly slower than SMOTE.
* May introduce noise if the dataset contains many outliers.

---

# SMOTE + Tomek Links

This technique combines **SMOTE** with **Tomek Links**.

* **SMOTE** first generates synthetic minority samples.
* **Tomek Links** then removes overlapping or noisy samples between classes.

This results in a cleaner and better-balanced dataset.

### Python Example

```python
from imblearn.combine import SMOTETomek

smote_tomek = SMOTETomek(random_state=42)

X_resampled, y_resampled = smote_tomek.fit_resample(X, y)
```

### Advantages

* Balances the dataset.
* Removes noisy and overlapping samples.
* Often improves classification performance.

### Disadvantages

* More computationally expensive.
* Slightly slower than using SMOTE alone.
