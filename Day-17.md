# Day 17 – Hyperparameters in Classification

Today, I learned about **Hyperparameters**, which are settings used to control the learning process of a machine learning model. Hyperparameters are especially important in **classification algorithms** because they help improve model accuracy and performance. Unlike model parameters, hyperparameters are set **before training** the model.

---

# Topics Learned

* What are Hyperparameters?
* Parameters vs Hyperparameters
* Why Hyperparameters are Important
* Hyperparameters in Classification Algorithms
* Benefits of Hyperparameter Tuning

---

# What are Hyperparameters?

**Hyperparameters** are values or settings that are defined **before training** a machine learning model. They control how the model learns from the training data.

These values are chosen by the user and are not automatically learned by the model.

---

# Parameters vs Hyperparameters

| Parameters                            | Hyperparameters                          |
| ------------------------------------- | ---------------------------------------- |
| Learned automatically during training | Set before training                      |
| Updated by the model                  | Selected by the user                     |
| Example: Weights and Biases           | Example: `n_neighbors`, `max_depth`, `C` |

---

# Why Do We Use Hyperparameters?

Hyperparameters are used to:

* Improve model accuracy.
* Reduce overfitting and underfitting.
* Control the learning process.
* Improve prediction performance.
* Build a more efficient machine learning model.

---

# Where Are Hyperparameters Used?

Hyperparameters are commonly used in classification algorithms such as:

* Logistic Regression
* K-Nearest Neighbors (KNN)
* Support Vector Machine (SVM)
* Decision Tree
* Random Forest
* Naive Bayes

---

# Common Hyperparameters in Classification

## 1. Logistic Regression

Common Hyperparameters:

* `C` – Controls regularization strength.
* `max_iter` – Maximum number of training iterations.
* `solver` – Optimization algorithm.

### Example

```python
from sklearn.linear_model import LogisticRegression

model = LogisticRegression(C=1.0, max_iter=100)
```

---

## 2. K-Nearest Neighbors (KNN)

Common Hyperparameters:

* `n_neighbors` – Number of nearest neighbors.
* `weights` – Uniform or distance-based weighting.
* `metric` – Distance calculation method.

### Example

```python
from sklearn.neighbors import KNeighborsClassifier

model = KNeighborsClassifier(n_neighbors=5)
```

---

## 3. Support Vector Machine (SVM)

Common Hyperparameters:

* `C` – Controls classification errors.
* `kernel` – Type of decision boundary.
* `gamma` – Controls the influence of training samples.

### Example

```python
from sklearn.svm import SVC

model = SVC(C=1.0, kernel="rbf")
```

---

## 4. Decision Tree

Common Hyperparameters:

* `max_depth` – Maximum depth of the tree.
* `min_samples_split` – Minimum samples required to split a node.
* `criterion` – Split quality measure (`gini` or `entropy`).

### Example

```python
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier(max_depth=5)
```

---

## 5. Random Forest

Common Hyperparameters:

* `n_estimators` – Number of decision trees.
* `max_depth` – Maximum depth of each tree.
* `min_samples_split` – Minimum samples required for splitting.

### Example

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(n_estimators=100)
```

---

# What is Hyperparameter Tuning?

**Hyperparameter Tuning** is the process of testing different hyperparameter values to find the combination that gives the best model performance.

The goal is to improve accuracy while reducing overfitting and underfitting.

---

# Benefits of Hyperparameter Tuning

* Improves prediction accuracy.
* Reduces overfitting.
* Increases model reliability.
* Produces better generalization on unseen data.
* Optimizes overall model performance.
