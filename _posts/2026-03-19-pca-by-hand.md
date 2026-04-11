---
layout: post
title: "PCA by hand"
date: 2026-03-19
excerpt: "A simple, no-frill guide to understanding PCA"
---


Almost every dataset that you work with is high-dimensional, meaning there are many features (or columns) in your dataset.
Dimensionality reduction is a way to reduce the dimensions in your dataset. Why though ? Well, more columns (features) means you need more storage space, and spend more time on processing the data.

Think of this with a simple example. Let's say you have 100 different types of medicines available to you at any time in your house. You wake up one day and find yourself down with a fever and cold. You do not want to leave your bed, and certainly do not want to shift through 100 medicines and find the one that can treat the fever.
What if you maybe had 5 medicines that compresses the "active ingredients" from all 100 medicines. While this may not be a safe choice, but hey, now you save space on your medicine shelf, and do not have to search through 100 boxes of medicine. 

Okay, this is the "explain like I am 5" definition of PCA. However, it is formally described as "eigenvectors of the covariance matrix".
**Big oooof** ? Let's break it down one by one.

### Covariance Matrix
$$cov(x, y) = \frac{\sum_{i=1}^{N}(x_i - \bar{x})(y_i - \bar{y})}{N - 1}$$

Imagine you have two lists. List A and List B (each containing some numbers). Next step is that you find the mean of each list, then subtract mean from every item in the list, and then multiply the resulting element in list A to the corresponding element in list B. Once you are done, you take the average of the resulting list. If covariance is large and positive, it means that potentially each element in list A is more than the mean of elements in list A. Similary, each element in list B is more than the mean in list B.

A covariance matrix for a dataset with 100 rows and 4 features will have a covariance matrix of size 4 * 4
Let's say we represent Feature 1 as F1, Feature 2 as F2, Feature 3 as F3 and Feature 4 as F4. Then the covaraince matrix looks like below.


| | Feature 1 | Feature 2 | Feature 3 | Feature 4 |
| :--- | :---: | :---: | :---: | :---: |
| **Feature 1** | cov(F1, F1) | cov(F1, F2) | cov(F1, F3) | cov(F1, F4) |
| **Feature 2** | cov(F2, F1) | cov(F2, F2) | cov(F2, F3) | cov(F2, F4) |
| **Feature 3** | cov(F3, F1) | cov(F3, F2) | cov(F3, F3) | cov(F3, F4) |
| **Feature 4** | cov(F4, F1) | cov(F4, F2) | cov(F4, F3) | cov(F4, F4) |

Okay, so what do we do with a covariance matrix. Here's where we need to understand what a matrix does to a vector. When we
multiply a column vector with a matrix, the orientation of the vector changes. This is because the vector is now a weighted sum of the matrix's columns or in other words, a linear transformation. Essentially, a matrix can do the following three transformations on a vector. 

1. Shrink
2. Stretch
3. Rotate 

An **eigenvector** is a vector that does not change its direction or in other words, stays on its original span, when multiplied by a matrix. It can, however, shrink or stretch along the same direction (or in the opposite direction) due to this matrix multiplication (or linear transformation). The amount by which this the vector shrinks or stretches is called the **eigenvalue**. For any given matrix, there may exists multiple eigenvectors, and therefore, multiple eigenvalues.
Why is an eigenvector valueable?

Now going back to our covariance matrix, if we find the eigenvectors of our covariance matrix, we 
We calculate the covariance matrix of our data, we calculate the eigenvectors of the covariance matrix, and this gives us our principal components.


