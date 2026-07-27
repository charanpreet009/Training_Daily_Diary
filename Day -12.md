# Day 12 – Classification Algorithms: Logistic Regression, Naive Bayes, K-Nearest Neighbors (KNN), and Support Vector Machine (SVM)

Today, I learned about some of the most commonly used **classification algorithms** in supervised machine learning. I studied their basic concepts, when they should be used, how they work, and their real-life applications.

---

# Topics Learned

* Logistic Regression
* Naive Bayes
* K-Nearest Neighbors (KNN)
* Support Vector Machine (SVM)

---

# 1. Logistic Regression

## What is Logistic Regression?

Logistic Regression is a **supervised machine learning classification algorithm** used to predict **categorical outcomes**, especially when there are only two classes (Binary Classification).

It predicts the probability that a data point belongs to a particular class.

### Example

* Spam or Not Spam
* Pass or Fail
* Disease Positive or Negative

---

## When Should We Use Logistic Regression?

Use Logistic Regression when:

* The target variable is categorical.
* There are only two output classes.
* The relationship between features and the target is relatively simple.
* Fast and interpretable predictions are required.

---

## How Does Logistic Regression Work?

1. Takes input features.
2. Calculates a probability using the **Sigmoid Function**.
3. If the probability is greater than **0.5**, it predicts one class; otherwise, it predicts the other class.

### Python Example

```python
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()

model.fit(X_train, y_train)

prediction = model.predict(X_test)
```

---

## Real-Life Applications

* Email spam detection
* Disease prediction
* Loan approval
* Customer churn prediction

---

# 2. Naive Bayes

## What is Naive Bayes?

Naive Bayes is a **probability-based classification algorithm** that uses **Bayes' Theorem**. It assumes that all input features are independent of each other.

Despite this simple assumption, it performs very well on many classification tasks.

---

## When Should We Use Naive Bayes?

Use Naive Bayes when:

* Working with text data.
* Solving email spam filtering problems.
* Performing sentiment analysis.
* Classifying news articles or documents.

---

## How Does Naive Bayes Work?

1. Calculates the probability of each class.
2. Uses Bayes' Theorem to estimate the likelihood.
3. Predicts the class with the highest probability.

### Python Example

```python
from sklearn.naive_bayes import GaussianNB

model = GaussianNB()

model.fit(X_train, y_train)

prediction = model.predict(X_test)
```

---

## Real-Life Applications

* Spam detection
* News classification
* Language detection
* Sentiment analysis

---

# 3. K-Nearest Neighbors (KNN)

## What is KNN?

K-Nearest Neighbors (KNN) is a classification algorithm that predicts the class of a new data point based on the **K nearest neighbors** in the training dataset.

It is called a **lazy learning algorithm** because it stores the training data and makes predictions only when needed.

---

## When Should We Use KNN?

Use KNN when:

* The dataset is small or medium-sized.
* Similar data points belong to the same class.
* A simple algorithm is required.
* The relationship between data points is based on distance.

---

## How Does KNN Work?

1. Choose the value of **K**.
2. Calculate the distance between the new data point and all training samples.
3. Select the K nearest neighbors.
4. Predict the class that appears most frequently among those neighbors.

### Python Example

```python
from sklearn.neighbors import KNeighborsClassifier

model = KNeighborsClassifier(n_neighbors=5)

model.fit(X_train, y_train)

prediction = model.predict(X_test)
```

---

## Real-Life Applications

* Product recommendation
* Image recognition
* Handwriting recognition
* Customer classification

---

# 4. Support Vector Machine (SVM)

## What is SVM?

Support Vector Machine (SVM) is a supervised learning algorithm that finds the **best decision boundary (hyperplane)** to separate different classes.

Its objective is to maximize the distance (margin) between the classes for better classification.

---

## When Should We Use SVM?

Use SVM when:

* The dataset has clear class boundaries.
* There are many features.
* High classification accuracy is required.
* Working with image or text classification problems.

---

## How Does SVM Work?

1. Finds the optimal hyperplane that separates different classes.
2. Maximizes the margin between the classes.
3. Uses support vectors (closest data points) to define the decision boundary.

### Python Example

```python
from sklearn.svm import SVC

model = SVC(kernel="linear")

model.fit(X_train, y_train)

prediction = model.predict(X_test)
```

---

## Real-Life Applications

* Face recognition
* Image classification
* Text classification

---

# Comparison of Classification Algorithms

| Algorithm                    | Best Used For                          | Advantages                                      | Limitations                                              |
| ---------------------------- | -------------------------------------- | ----------------------------------------------- | -------------------------------------------------------- |
| Logistic Regression          | Binary classification                  | Fast, simple, easy to interpret                 | Not suitable for complex non-linear relationships        |
| Naive Bayes                  | Text classification and spam filtering | Fast and efficient                              | Assumes features are independent                         |
| K-Nearest Neighbors (KNN)    | Small to medium datasets               | Simple and easy to understand                   | Slow for large datasets and sensitive to feature scaling |
| Support Vector Machine (SVM) | High-dimensional datasets              | High accuracy and effective decision boundaries | Computationally expensive for very large datasets        |

---
