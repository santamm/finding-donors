# finding-donors
Finding Donors for CharityML

### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [File Descriptions](#files)
4. [Results](#results)
5. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>
The code in this project is written in Python 3.6.6 :: Anaconda custom (64-bit).  
The following additional libraries have been used:
- sklearn
- IPython.display
- visuals (supplied)

## Project Motivation<a name="motivation"></a>
In this project we  employ several supervised algorithms to accurately model individuals' income using data collected from the 1994 U.S. Census. The best candidate algorithm is then chosen from preliminary results and optimized to best model the data. We construct a model that accurately predicts whether an individual makes more than $50,000. This sort of task can arise in a non-profit setting, where organizations survive on donations. Understanding an individual's income can help a non-profit better understand how large of a donation to request, or whether or not they should reach out to begin with. While it can be difficult to determine an individual's general income bracket directly from public sources, we can (as we will see) infer this value from other publically available features.



## File Descriptions <a name="files"></a>
The Jupyter notebooks included in this project are:
- plot_learning_curve.py, code to generate a simple plot of the test and training learning curve
- finding_donors.ipynb, jupyter notebook including data exploration, data preprocessing, models instantiation, model performance evaluation, models tuning.

## Results<a name="results"></a>
The following results are showed in the notebook:
Three supervised learning algorithms are chosen and the performances evaluated against a fourth algorithm known as a "naive predictor":
- Logistic Regression
- Decision Trees
- Ensemble methods (AdaBoost)
Considering the metrics on the test set after training the algorithms on 100% of training examples, Adaboost gives  te best accuracy and Fbeta score than Logistic Regression and Decision Trees.
The model is then optimized using a GridSearch on the parameters.
Final results:
Metric	Unoptimized Model	Optimized Model
Accuracy Score	0.8576	0.8669
F-score	0.7246	0.7442
ROC AUC Score	0.7716	0.7889

Feature Importance evaluation: which five features do you believe to be most important for prediction, and in what order would you rank them and why?
Answer: According to the explanatory analysis, the most important features for prediction are:
Marital status: 85% of the 11208 (9564) examples with income > 50k have marital-status "Married"
Years of Education: most of the examples with income > 50 have more than 9 years of education (>95%)
Capital Gains: the mean capital gain among <=50K is 149.023402 while among >50K is 3991.791667
Capital Losses: the mean capital loss among <=50K is 54.032428 while among >50K is 193.487063
Age: the mean among <=50k is 36.75 while among >50k is 44.00
We have extracted the features from the model and got the following: the features extracted are the same ones we were expecting to be important during the data exploratory analysis.
In particular marital status and education-num, as out of the 11208 examples with income >50k, almost 10000 are married (more than 85%), and 10870 (more than 96%) have education level at least 9.

## Licensing, Authors, Acknowledgements<a name="licensing"></a>
The dataset for this project originates from the UCI Machine Learning Repository. The datset was donated by Ron Kohavi and Barry Becker, after being published in the article "Scaling Up the Accuracy of Naive-Bayes Classifiers: A Decision-Tree Hybrid". The article by Ron Kohavi can be found [here](https://www.aaai.org/Papers/KDD/1996/KDD96-033.pdf). The data we investigate here consists of small changes to the original dataset, such as removing the 'fnlwgt' feature and records with missing or ill-formatted entries.


