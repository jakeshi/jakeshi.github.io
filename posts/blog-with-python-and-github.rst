.. title: Blog with Python and Github
.. slug: blog-with-python-and-github
.. date: 2017-04-16 21:52:16 UTC-04:00
.. tags: python, github
.. category: 
.. link: 
.. description: 
.. type: text

I created this blog using Nikola.
Step1: Download and install Anaconda
Step 2: Launch IPython
Step 3: Copy code from below and paste to your Notebook

::
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