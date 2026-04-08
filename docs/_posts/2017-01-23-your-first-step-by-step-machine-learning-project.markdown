---
layout: post
title: "Your First Step-by-Step Machine Learning Project"
date: 2017-01-23
---

I've been learning machine learning for a few months now, and the hardest part isn't the math — it's knowing where to start. Most tutorials assume you already know what you're doing. This post is for people like me who just want a simple, working example they can run and modify.

Here's a step-by-step walkthrough using the classic Iris dataset. All you need is Anaconda and a Jupyter notebook.

## Setup

1. Download and install [Anaconda](https://www.anaconda.com/download/)
2. Launch Jupyter Notebook
3. Copy the code below into cells and run them

## Load the libraries

```python
import pandas
from pandas.tools.plotting import scatter_matrix
import matplotlib.pyplot as plt
from sklearn import model_selection
from sklearn.metrics import classification_report
from sklearn.metrics import confusion_matrix
from sklearn.metrics import accuracy_score
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier
from sklearn.neighbors import KNeighborsClassifier
from sklearn.discriminant_analysis import LinearDiscriminantAnalysis
from sklearn.naive_bayes import GaussianNB
from sklearn.svm import SVC
```

This gives you everything: pandas for data handling, matplotlib for plotting, and scikit-learn for the actual ML models.

The beauty of this example is that you're comparing six different classifiers on the same dataset — logistic regression, decision trees, KNN, LDA, naive Bayes, and SVM — and you can see which one performs best. No theory required. Just run it, see the results, and then start asking why.

That's how I'm learning: code first, theory second. If something works, I dig into why. If it doesn't, I dig into why not. The Iris dataset isn't going to change the world, but it's a solid foundation to build on.
