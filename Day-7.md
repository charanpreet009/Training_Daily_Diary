# Day 7 – Principal Component Analysis (PCA)

Today, I learned about **Principal Component Analysis (PCA)**, a popular dimensionality reduction technique used in machine learning. PCA helps reduce the number of features in a dataset while preserving most of the important information. It makes models faster, simpler, and more efficient.

---

# Topics Learned

* What is PCA?
* Why PCA is Used
* Importance of PCA
* How PCA Works
* Real-Life Examples of PCA
* Advantages and Limitations of PCA

---

# What is PCA?

**Principal Component Analysis (PCA)** is a dimensionality reduction technique used to reduce the number of features (columns) in a dataset while retaining as much important information as possible.

Instead of using all the original features, PCA creates a smaller set of new features called **Principal Components**.

These principal components capture the maximum variance (information) present in the original dataset.

---


---

# Why is PCA Used?

PCA is used to:

* Reduce the number of features.
* Remove redundant (highly correlated) information.
* Reduce computational time.
* Improve model performance.
* Simplify complex datasets.
* Reduce the risk of overfitting.

---

# Importance of PCA

PCA plays an important role in machine learning because it:

* Makes large datasets easier to analyze.
* Speeds up model training.
* Reduces memory usage.
* Eliminates unnecessary features.
* Improves visualization of high-dimensional data.
* Helps reduce noise in the dataset.

---

# How PCA Works

PCA works in the following steps:

1. Standardize the data.
2. Calculate the covariance matrix.
3. Find the eigenvalues and eigenvectors.
4. Select the principal components with the highest variance.
5. Transform the original dataset into a smaller set of components.

---

# Simple Example

Imagine a dataset with three features:

```text
Height
Weight
BMI
```

These features are closely related.

Instead of using all three, PCA may combine them into one or two principal components that still represent most of the information.

As a result:

* Less data
* Faster training
* Similar prediction accuracy

---

# PCA in Python

The `scikit-learn` library provides an easy way to apply PCA.

### Example

```python
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler

# Standardize the data
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Apply PCA
pca = PCA(n_components=2)

X_pca = pca.fit_transform(X_scaled)

print(X_pca)
```

---

# Real-Life Examples of PCA

## 1. Face Recognition

A facial recognition system may have thousands of pixel values for each image.

PCA reduces these thousands of features into a smaller number of principal components while preserving important facial characteristics. This makes face recognition faster and more efficient.

---

## 2. Image Compression

High-resolution images contain millions of pixels.

PCA reduces the image size while maintaining most of the visual information, making storage and transmission more efficient.

---

## 3. House Price Prediction

A house dataset may contain many related features such as:

* Area
* Building Area
* Land Size
* Number of Rooms
* Bathrooms
* Parking

Many of these features are correlated. PCA combines them into fewer components, reducing complexity while preserving useful information for prediction.

---
