X-Role
Technologies Used

Data Cleaning and Analysis
Pandas will be used to clean the data and perform an exploratory analysis. Further analysis will be completed using Python. For cleaning the dataset, we first have to identify the features we seek to analyze, and see which columns are irrelevant. 

Procedure for data cleaning:

- Drop rows with blank and unknown conditions in _conds column
- Drop unnecessary columns:  _heatindexm,  _precipm, 
- Drop rows with NaNs :  _vism,  _wgustm,  _windchillm,  _wspdm
- Change column titles


Database Storage
SQLlite is the database we intend to use, and we will integrate Flask to display the data.

Machine Learning
SciKitLearn is the ML library we'll be using to create a classifier. Our training and testing setup features SciKitLearn's traintestsplit model. We designed our DecisionTreeModel to describe what we want our machine learning model to pick up on to research our hypothesis. 

Dashboard
In addition to using a Flask template, we will also integrate D3.js for a fully functioning and interactive dashboard. It will be hosted on Tableau.
