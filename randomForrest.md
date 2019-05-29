# Random Forrest
* an Ensemble (collection) of many Decision Trees

### Ensemble Methods
* aggregate more humble methods to a single great one



## Decision Trees (1)
* like SQL Queries ...
* you're asking questions about your data
* --- SQL: ask specific question
* --- Decision Tree: asks questions iteratively and selects the single question that provides the "most information"

## Information Gain
* measured by difference in entropy from previous state to current state, or current state to potential next

## Entropy
* --- in words:
* in terms of physics or chemistry... a measure of disorder in a system
* in the context of machine learning... we derive entropy to measure how confident an answer to a given question is
* --- with math:
* p(x == v) * log(p(x == v))
* When p(x) == 1 ... log(p(x)) == log(1) == 0 ... 1*0 == 0
* When p(x) == 0 ... log(0) == -inf ... 0*(-inf) == 0
* Minimizing entropy corresponds to higher confidence in answers

## Decision Trees (2)
* ID3 Algorithm
* ask (binary) questions
* split your data into two subsets, evaluate entropy
* select question that splits your data into a state of lowest entropy
* repeat

## Decision Trees (3)
* first question selected is root-node
* subsequent questions are interior nodes
* final questions for each branch in tree are "leaf" nodes

## One Tree is Good
* a single decision tree is very prone to over-fitting and reaching local minima
* dominant features in your train set can take over

## A Forrest is Better
* build a lot of (different) trees & use them in ensemble
* use bagging to fight against over-fitting (regularization)
* select possible questions (features) from random subspace

## Bagging
* each tree is trained on a random sample
* no tree sees all the data

## Random Subspace
* select questions from a random subspace of features
* each node is given a random sample of features to select from
* ---> preventing the most dominant features always being selected



# Advantages
* tasks are easily computed in parallel !!!
* intuitive and explainable
* handles both categorical and numeric features
* ---> most model types require pre processing to handle categorical features i.e. one-hot-encoding
* ---> do not need to normalize data
* ---> approximates non-linear functions

# Disadvantages
* prone to overfitting ... as with any model that can approximate non-linear functions
* trees can easily become too complex (so start simple, don't let them grow too deep)
* Biased towards "majority class"... make sure your data is balanced ... this is general good practice for ML
