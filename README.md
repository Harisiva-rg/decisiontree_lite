## Decision Tree Implementation from Scratch [![PyPI version](https://badge.fury.io/py/decisiontree-lite.svg)](https://badge.fury.io/py/decisiontree-lite)

## Overview

This package provides a Python implementation of a decision tree algorithm from scratch, along with training and evaluation utilities. This lightweight implementation has performance comparable to scikit-learn's implementation.

## Files

 - DecisionTree.py: Contains the core classes and functions for building and using the decision tree model.
 - utils.py: Provides helper functions for loading datasets, splitting data, calculating evaluation metrics, and comparing custom and scikit-learn implementations.    

## Key Features

 - Custom implementation of a decision tree algorithm.
 - Supports both Gini impurity and entropy criteria for splitting.
 - Options to control maximum depth and minimum samples for splitting.
 - Functions for loading and processing various inbuilt datasets.
 - Comparison with scikit-learn's DecisionTreeClassifier in terms of accuracy, precision, recall, F1-score, time taken, and memory usage.

## Usage

Make sure the labels are numeric(Use label encoder).

```python

from decisiontree_lite.decisiontree import DecisionTree
from decisiontree_lite.utils import load_data, train_test, model_metrics

# You can use one of inbuilt datasets('iris', 'digits', 'breast_cancer', 'wine') or an external dataset of your choice  
X, y = load_data('iris')

# Perform test train split
test_split_size = 0.3
X_train, X_test, y_train, y_test = train_test(X, y, test_split_size)

clf = DecisionTree()
clf.fit(X_train, y_train)
y_pred = clf.predict(X_test)
accuracy, precision, recall, f1score = model_metrics(y_test, y_pred)
print("Accuracy: {},\nPrecision: {},\nRecall: {},\nF1-score: {}".format(accuracy, precision, recall, f1score))

```



## Customization

Adjust hyperparameters like max_depth, min_samples_split, and criteria in the DecisionTree to tune the model.

 - max_depth: The maximum depth of the tree [1, 2, 4, 8, 16, 32, 64, 100].
 - min_samples_split: The minimum number of samples required to split an internal node [2, 50, 100].
 - criteria: To split based on gini or entropy impurity ['gini', 'entropy'].

```python

clf = DecisionTree(max_depth  = maxDepth, min_samples_split = minSplit, criteria = impCriteria)

```

## Additional Notes

- The code is structured for clarity and modularity.
- Comments are included to explain key concepts and steps.
- Feel free to contribute to this project or use it for your own learning and experimentation!
