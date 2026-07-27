# Day 16 – Wrapper Feature Selection Methods

Today, I learned about the **Wrapper Method**, a feature selection technique that selects the best features by training and evaluating a machine learning model. Unlike filter methods, wrapper methods use the model's performance to decide which features should be selected. I also learned about **Forward Selection**, **Backward Elimination**, and **Recursive Feature Elimination with Cross Validation (RFECV)**.

---

# Topics Learned

* Wrapper Method
* Forward Selection
* Backward Elimination
* Recursive Feature Elimination with Cross Validation (RFECV)

---

# What is the Wrapper Method?

The **Wrapper Method** is a feature selection technique that selects the best subset of features by repeatedly training a machine learning model and checking its performance.

Instead of using statistical tests, it evaluates different combinations of features and chooses the one that gives the highest accuracy.

---

# Why Do We Use the Wrapper Method?

We use the Wrapper Method because it:

* Selects the most useful features.
* Improves model accuracy.
* Removes unnecessary features.
* Reduces overfitting.
* Helps build a better-performing machine learning model.

---


# Advantages

* High prediction accuracy.
* Selects the best feature combination.
* Considers model performance during feature selection.

---

# Limitations

* Computationally expensive.
* Slower than Filter Methods.
* Not ideal for very large datasets.

---

# 1. Forward Selection

## What is Forward Selection?

Forward Selection starts with **no features** and adds one feature at a time. At each step, it selects the feature that improves the model performance the most.

The process continues until adding more features no longer improves the model.

---

## Why Do We Use Forward Selection?

We use Forward Selection when:

* The dataset has many features.
* We want to identify only the most important features.
* We want to build the model gradually.

---

---

## How Does Forward Selection Work?

1. Start with no features.
2. Train the model using one feature at a time.
3. Select the feature with the best performance.
4. Add the next best feature.
5. Repeat until no significant improvement is achieved.

### Python Example

```python
from sklearn.feature_selection import SequentialFeatureSelector
from sklearn.linear_model import LinearRegression

model = LinearRegression()

forward = SequentialFeatureSelector(
    model,
    direction="forward",
    n_features_to_select=3
)

forward.fit(X, y)
```

---

# 2. Backward Elimination

## What is Backward Elimination?

Backward Elimination starts with **all available features** and removes the least important feature one by one until only the most useful features remain.

---

## Why Do We Use Backward Elimination?

We use Backward Elimination when:

* Most features may be useful.
* We want to remove only irrelevant features.
* We need a simpler and more efficient model.

---


## How Does Backward Elimination Work?

1. Start with all features.
2. Train the model.
3. Remove the least important feature.
4. Retrain the model.
5. Repeat until only important features remain.

### Python Example

```python
from sklearn.feature_selection import SequentialFeatureSelector
from sklearn.linear_model import LinearRegression

model = LinearRegression()

backward = SequentialFeatureSelector(
    model,
    direction="backward",
    n_features_to_select=3
)

backward.fit(X, y)
```

---

# 3. Recursive Feature Elimination with Cross Validation (RFECV)

## What is RFECV?

**RFECV (Recursive Feature Elimination with Cross Validation)** is an advanced feature selection technique that automatically finds the **best number of features** by combining **Recursive Feature Elimination (RFE)** with **Cross Validation**.

It repeatedly removes the least important features and evaluates the model using cross validation.

---

## Why Do We Use RFECV?

We use RFECV because it:

* Automatically selects the optimal number of features.
* Improves model performance.
* Reduces overfitting.
* Produces more reliable results.


---

## How Does RFECV Work?

1. Train the model using all features.
2. Remove the least important feature.
3. Evaluate the model using cross validation.
4. Repeat the process until the best feature subset is found.
5. Select the feature set with the highest validation score.

### Python Example

```python
from sklearn.feature_selection import RFECV
from sklearn.linear_model import LinearRegression

model = LinearRegression()

rfecv = RFECV(
    estimator=model,
    cv=5
)

rfecv.fit(X, y)
```

--
