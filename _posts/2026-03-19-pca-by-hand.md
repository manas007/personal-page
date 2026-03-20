---
layout: post
title: "PCA by hand - A simple guide to PCA"
date: 2026-03-19
excerpt: "A simple, no-frill guide to understanding PCA"
---

Almost every dataset that you work with is high-dimensional, meaning there are many features (or columns) in your dataset.
Dimensionality reduction is a way to reduce the dimensions in your dataset. Why though ? Well, more columns (features) means you need more storage space, and spend more time on processing the data.

Think of this with a simple example. If you catch a cold, and let's say you have 100 different types of medicines available to you at any time in your house. What if instead of shifting through the entire rack of 100 medicines, you maybe had 5 medicines that compresses the "Active ingredients" from all 100 medicines. Well, maybe it is not safe, but you no longer need to guess which once is the correct medicine. 

Okay, this is the "explain like I am 5" definition. PCA is formally described as "eigenvectors of the covariance matrix".
Big oooof ? Let's break it down one by one.
Covariance matrix: 
$$cov(x, y) = \frac{\sum_{i=1}^{N}(x_i - \bar{x})(y_i - \bar{y})}{N - 1}$$
Imagine you have two lists. List A and List B (each containing some numbers). Next step is that you find the mean of each list, then subtract mean from every item in the list, and then multiply each element in list A to the corresponding element in list B. Once you are done, you take the average of the resulting list. If covariance is large and positive, it should mean that potentially each element in list A if more than the mean, and each element in list B is more than the mean. 

A covariance matrix for a dataset with 100 rows and 4 features will have a covariance matrix of size 4 * 4
Let's say we represent Feature 1 as F1, Feature 2 as F2, Feature 3 as F3 and Feature 4 as F4. Then the covaraince matrix looks like below.

            Feature 1   Feature 2	Feature 3	Feature 4
Feature 1	cov(F1,F1)  cov(F1,F2)  cov(F1,F3)  cov(F1,F4)
Feature 2	cov(F2,F1)  cov(F2,F2)  cov(F2,F3)  cov(F2,F4) 
Feature 3	cov(F3,F1)  cov(F3,F2)  cov(F3,F3)  cov(F3,F4)
Feature 4	cov(F4,F1)  cov(F4,F2)  cov(F4,F3)  cov(F4,F4)



