.. title: Your First Step by Step Machine Learning Project
.. slug: your-first-step-by-step-machine-learning-project
.. date: 2017-04-23 20:12:25 UTC-04:00
.. tags: machine learning
.. category: 
.. link: 
.. description: 
.. type: text

Step1: Download and install Anaconda

Step 2: Launch IPython

Step 3: Copy code from below and paste to your Notebook

.. code-block:: python
   :number-lines:

# Load libraries
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