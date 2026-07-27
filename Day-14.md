# Day 14 – Regression Algorithms: Linear Regression, Ridge Regression, and Lasso Regression

Today, I learned about **Regression Algorithms**, which are used in supervised machine learning to predict **continuous numerical values**. I studied the three most commonly used regression algorithms: **Linear Regression**, **Ridge Regression**, and **Lasso Regression**. I also learned their basic concepts, why they are used, when they should be used, how they work, and their advantages and limitations.

---

# Topics Learned

* What is Regression?
* Linear Regression
* Ridge Regression
* Lasso Regression
* Difference Between Linear, Ridge, and Lasso Regression

---

# What is Regression?

Regression is a type of **Supervised Machine Learning** used to predict **continuous numerical values**. The model learns the relationship between input features and the target variable to make future predictions.

### Examples

* House Price Prediction
* Salary Prediction
* Sales Forecasting
* Temperature Prediction
* Stock Price Prediction

---

# Why Do We Use Regression?

Regression is used to:

* Predict continuous numerical values.
* Understand the relationship between variables.
* Estimate future outcomes.
* Support business and financial decision-making.
* Analyze trends in data.

---

# 1. Linear Regression

## What is Linear Regression?

Linear Regression is the simplest regression algorithm. It predicts the target value by finding the **best-fit straight line** between the input feature(s) and the output.

The relationship is represented by the equation:

```text id="2ecm0w"
Y = mX + c
```

Where:

* **Y** = Predicted value
* **X** = Input feature
* **m** = Slope of the line
* **c** = Intercept

---

## When Should We Use Linear Regression?

Use Linear Regression when:

* The target variable is continuous.
* The relationship between variables is approximately linear.
* The dataset has little multicollinearity.
* A simple and interpretable model is required.

---

## How Does Linear Regression Work?

1. Takes input features.
2. Finds the best-fit line that minimizes prediction errors.
3. Uses the line to predict new values.

### Python Example

```python id="1xppjz"
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)

prediction = model.predict(X_test)
```

---

## Advantages

* Easy to understand.
* Fast to train.
* Simple to interpret.
* Works well for linear relationships.

---

## Limitations

* Performs poorly with non-linear data.
* Sensitive to outliers.
* Can overfit when many correlated features exist.



# 2. Ridge Regression

## What is Ridge Regression?

Ridge Regression is an improved version of Linear Regression that uses **L2 Regularization**. It adds a penalty to large coefficients, reducing overfitting and improving model performance.

Unlike Linear Regression, Ridge Regression **reduces coefficient values but does not make them exactly zero**.

---

## Why Do We Use Ridge Regression?

We use Ridge Regression when:

* The dataset contains many features.
* Features are highly correlated (multicollinearity).
* The Linear Regression model is overfitting.
* Better generalization is needed.

---

## How Does Ridge Regression Work?

1. Starts with Linear Regression.
2. Adds an L2 penalty to the loss function.
3. Shrinks large coefficient values.
4. Produces a more stable model.

### Python Example

```python id="pqk0po"
from sklearn.linear_model import Ridge

model = Ridge(alpha=1.0)

model.fit(X_train, y_train)

prediction = model.predict(X_test)
```

---

## Advantages

* Reduces overfitting.
* Handles multicollinearity well.
* Produces stable predictions.
* Improves generalization.

---

## Limitations

* Does not perform feature selection.
* All features remain in the model.


---

# 3. Lasso Regression

## What is Lasso Regression?

Lasso Regression is another extension of Linear Regression that uses **L1 Regularization**.

Unlike Ridge Regression, Lasso can reduce the coefficients of less important features to **zero**, automatically removing them from the model.

This makes Lasso useful for **feature selection**.

---

## Why Do We Use Lasso Regression?

Use Lasso Regression when:

* The dataset has many features.
* Some features are not important.
* Feature selection is required.
* A simpler model is preferred.

---

## How Does Lasso Regression Work?

1. Starts with Linear Regression.
2. Applies an L1 penalty.
3. Shrinks less important coefficients to zero.
4. Keeps only the most important features.

### Python Example

```python id="vk0rqe"
from sklearn.linear_model import Lasso

model = Lasso(alpha=0.1)

model.fit(X_train, y_train)

prediction = model.predict(X_test)
```

---

## Advantages

* Performs automatic feature selection.
* Reduces overfitting.
* Produces simpler models.
* Improves interpretability.

---

## Limitations

* May remove useful features if the penalty is too high.
* Performance depends on selecting an appropriate alpha value.

---
