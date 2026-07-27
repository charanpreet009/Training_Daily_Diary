# Day 15 – Feature Selection Techniques

Today, I learned about **Feature Selection**, an important step in machine learning that helps select the most relevant features (columns) from a dataset. Feature selection improves model performance by removing unnecessary or irrelevant features. I also learned about the three main types of feature selection methods: **Filter Method**, **Wrapper Method**, and **Embedded Method**, along with common techniques such as **Variance Threshold**, **Correlation Coefficient**, **Chi-Squared Test**, **Mutual Information**, and **F-Test**.

---

# Topics Learned

* What is Feature Selection?
* Benefits of Feature Selection
* Types of Feature Selection

  * Filter Method
  * Wrapper Method
  * Embedded Method
* Variance Threshold
* Correlation Coefficient
* Chi-Squared Test
* Mutual Information
* F-Test

---

# What is Feature Selection?

**Feature Selection** is the process of selecting the most important features (columns) from a dataset while removing unnecessary, duplicate, or irrelevant features.

It helps machine learning models learn from only the useful information.

### Example

Suppose a house price dataset contains:

```text
Area
Bedrooms
Bathrooms
Owner Name
House Color
Price
```

Features like **Owner Name** and **House Color** may not affect the house price, so they can be removed during feature selection.

---

# Why Do We Use Feature Selection?

Feature Selection is used to:

* Improve model accuracy.
* Reduce overfitting.
* Reduce training time.
* Remove irrelevant features.
* Simplify the machine learning model.
* Improve model interpretability.

---

# Benefits of Feature Selection

* Faster model training.
* Better prediction accuracy.
* Reduces memory usage.
* Removes noise from the dataset.
* Makes the model easier to understand.
* Improves overall performance.

---

# Types of Feature Selection

There are **three main types** of Feature Selection:

1. Filter Method
2. Wrapper Method
3. Embedded Method

---

# 1. Filter Method

## What is the Filter Method?

The **Filter Method** selects features based on statistical techniques before training the machine learning model.

It is fast and does not depend on any specific algorithm.

### Common Filter Techniques

* Variance Threshold
* Correlation Coefficient
* Chi-Squared Test
* Mutual Information
* F-Test

### Advantages

* Very fast.
* Easy to implement.
* Works well with large datasets.

### Disadvantages

* Does not consider the performance of the machine learning model.

---

# 2. Wrapper Method

## What is the Wrapper Method?

The **Wrapper Method** selects features by repeatedly training and evaluating a machine learning model using different feature combinations.

It chooses the combination that gives the best model performance.

### Examples

* Forward Selection
* Backward Elimination
* Recursive Feature Elimination (RFE)

### Advantages

* Produces highly accurate feature selection.
* Considers model performance.

### Disadvantages

* Computationally expensive.
* Slower for large datasets.

---

# 3. Embedded Method

## What is the Embedded Method?

The **Embedded Method** performs feature selection during the model training process.

The machine learning algorithm automatically determines which features are important.

### Examples

* Lasso Regression
* Decision Tree
* Random Forest

### Advantages

* Faster than Wrapper methods.
* Considers model performance.
* Performs feature selection automatically.

### Disadvantages

* Depends on the chosen machine learning algorithm.

---

# Common Feature Selection Techniques

---

# 1. Variance Threshold

## What is Variance Threshold?

Variance Threshold removes features that have **very little or no variation**.

If all values in a feature are almost the same, that feature provides little useful information.

### Example

```text
Feature A : 1 1 1 1 1
```

Since there is no variation, this feature can be removed.

# 2. Correlation Coefficient

## What is Correlation Coefficient?

The **Correlation Coefficient** measures the strength of the relationship between two numerical features.

If two features are highly correlated, one of them can often be removed to reduce redundancy.

### Example

Suppose:

```text
BuildingArea ↔ TotalArea
Correlation = 0.95
```

Since both features carry almost the same information, one feature may be removed.



# 3. Chi-Squared Test

## What is the Chi-Squared Test?

The **Chi-Squared Test** measures the relationship between **categorical features** and the target variable.

Features with higher Chi-Square scores are generally more important.


### Used For

* Classification problems.
* Categorical data.

---

# 4. Mutual Information

## What is Mutual Information?

Mutual Information measures how much information one feature provides about the target variable.

Higher mutual information means the feature is more useful for prediction.


### Used For

* Classification problems.
* Capturing both linear and non-linear relationships.

---

# 5. F-Test

## What is the F-Test?

The **F-Test** compares the relationship between numerical features and the target variable.

Features with higher F-scores are considered more significant.


### Used For

* Regression problems.
* Selecting important numerical features.

---
