# Day 13 – Decision Tree and Random Forest

Today, I learned about **Decision Tree** and **Random Forest**, two powerful supervised machine learning algorithms used for both **classification** and **regression** problems. I studied their basic concepts, when they should be used, how they work, and their real-life applications.

---

# Topics Learned

* Decision Tree
* Random Forest

---

# 1. Decision Tree

## What is a Decision Tree?

A **Decision Tree** is a supervised machine learning algorithm that makes predictions by splitting the data into smaller groups based on feature values. It creates a tree-like structure consisting of **root nodes, decision nodes, branches, and leaf nodes**.

Each decision helps the model move closer to the final prediction.

### Example

Suppose a bank wants to decide whether to approve a loan.

```text
Income > 50000?
       /      \
     Yes      No
      |         |
Credit Score?  Reject
   /      \
Good      Poor
 |          |
Approve   Reject
```

---

## When Should We Use Decision Tree?

Use a Decision Tree when:

* The data contains both numerical and categorical features.
* You need a model that is easy to understand and explain.
* You want to identify important features.
* The relationship between input and output is not linear.

---

## How Does a Decision Tree Work?

1. Starts with the entire dataset.
2. Selects the best feature to split the data.
3. Divides the data into smaller groups.
4. Repeats the process until a stopping condition is reached.
5. Makes the final prediction at the leaf node.

### Python Example

```python
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier(random_state=42)

model.fit(X_train, y_train)

prediction = model.predict(X_test)
```

---

## Advantages

* Easy to understand and visualize.
* Works with both numerical and categorical data.
* Requires little data preprocessing.
* Can perform both classification and regression.

---

## Limitations

* Can easily overfit the training data.
* Sensitive to small changes in the dataset.
* May become complex if the tree grows too large.


---

# 2. Random Forest

## What is Random Forest?

**Random Forest** is an ensemble machine learning algorithm that combines multiple Decision Trees to make more accurate and reliable predictions.

Instead of relying on a single tree, Random Forest builds many trees and combines their predictions using **majority voting** (classification) or **average prediction** (regression).

---

## When Should We Use Random Forest?

Use Random Forest when:

* High prediction accuracy is required.
* The dataset is large.
* You want to reduce overfitting.
* The data contains many features.
* You need a robust model for real-world applications.

---

## How Does Random Forest Work?

1. Creates multiple random samples from the dataset.
2. Builds a separate Decision Tree for each sample.
3. Each tree makes its own prediction.
4. Combines all predictions.
5. Returns the final result using majority voting or averaging.

### Python Example

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(
    n_estimators=100,
    random_state=42
)

model.fit(X_train, y_train)

prediction = model.predict(X_test)
```

---

## Advantages

* High prediction accuracy.
* Reduces overfitting.
* Handles large datasets efficiently.
* Works well with missing values and noisy data.
* Provides feature importance.

---

## Limitations

* Slower than a single Decision Tree.
* Requires more memory.
* More difficult to interpret.

---

