# Day 11 – Supervised Machine Learning: Classification and Regression

Today, I learned about **Supervised Machine Learning**, one of the most widely used types of machine learning. In supervised learning, a model is trained using **labeled data**, where both the input features and the correct output are already known. I also learned about its two main categories: **Classification** and **Regression**, along with some commonly used algorithms.

---

# Topics Learned

* What is Machine Learning?
* Types of Machine Learning
* Supervised Learning
* Classification
* Types of Classification Algorithms
* Regression
* Types of Regression Algorithms

---

# What is Machine Learning?

Machine Learning (ML) is a branch of Artificial Intelligence (AI) that enables computers to learn from data and make predictions or decisions without being explicitly programmed.

The model learns patterns from historical data and uses them to make predictions on new data.

---

# Types of Machine Learning

Machine Learning is mainly divided into three types:

1. **Supervised Learning**
2. **Unsupervised Learning**
3. **Reinforcement Learning**

In today's session, I focused on **Supervised Learning**.

---

# What is Supervised Learning?

Supervised Learning is a type of machine learning in which the model is trained using **labeled data**. Each training example contains both the input (features) and the correct output (target).

The model learns the relationship between inputs and outputs so that it can predict results for new data.

### Example

Suppose we have a house price dataset:

| Area (sq ft) | Price ($) |
| ------------ | --------: |
| 1000         |    150000 |
| 1500         |    220000 |
| 2000         |    300000 |

The model learns the relationship between **Area** and **Price**, then predicts the price of a new house.

---

# Two Main Types of Supervised Learning

1. Classification
2. Regression

---

# 1. Classification

Classification is used when the target variable is a **category or class**. The model predicts which class a data point belongs to.

### Examples

* Email → Spam or Not Spam
* Disease → Positive or Negative
* Loan → Approved or Rejected
* Student → Pass or Fail

---

# Types of Classification Algorithms

## 1. Logistic Regression

Logistic Regression is a classification algorithm used to predict categorical outcomes, especially binary classes.

### Example

Predict whether an email is **Spam** or **Not Spam**.

---

## 2. Naive Bayes

Naive Bayes is a probability-based classification algorithm that uses Bayes' Theorem and assumes that features are independent.

### Example

Email spam detection and text classification.

---

## 3. K-Nearest Neighbors (KNN)

KNN classifies a new data point based on the majority class of its nearest neighbors.

### Example

Classifying a fruit as an apple or an orange based on similar fruits.

---

## 4. Support Vector Machine (SVM)

Support Vector Machine finds the best boundary (decision boundary) that separates different classes.

### Example

Handwritten digit recognition.

---

## 5. Decision Tree

A Decision Tree makes decisions by splitting the dataset into branches based on feature values.

### Example

Loan approval prediction.

---

## 6. Random Forest

Random Forest is an ensemble algorithm that combines multiple decision trees to improve prediction accuracy and reduce overfitting.

### Example

Customer churn prediction and fraud detection.

---

# 2. Regression

Regression is used when the target variable is a **continuous numerical value**.

It predicts values such as prices, temperatures, salaries, or sales.

### Examples

* House Price Prediction
* Salary Prediction
* Temperature Forecasting
* Sales Prediction

---

# Types of Regression Algorithms

## 1. Linear Regression

Linear Regression predicts a continuous value by fitting a straight-line relationship between input and output variables.

### Example

Predicting house prices based on area.

---

## 2. Ridge Regression

Ridge Regression is an improved version of Linear Regression that uses **L2 Regularization** to reduce overfitting.

### Advantages

* Reduces overfitting.
* Performs well when features are highly correlated.

### Example

House price prediction with many related features.

---

## 3. Lasso Regression

Lasso Regression is another extension of Linear Regression that uses **L1 Regularization**.

It can automatically reduce the coefficients of less important features to zero, making feature selection easier.

### Advantages

* Performs feature selection.
* Reduces model complexity.
* Helps prevent overfitting.

### Example

Selecting the most important features for predicting house prices.

---

