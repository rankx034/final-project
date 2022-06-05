![deeplearninggeneral](https://user-images.githubusercontent.com/95719819/168449229-3b4df5d7-3ded-4cda-92c4-9c519a8229c9.png)
# New Delhi Weather Machine Learning Model

## Files Description

- *delhi_weather_cleaned.csv: The original dataset obtained from Kaggle that has been cleaned for our use*
- *Database/conds.csv: CSV version of the conditions table from the database*
- *Database/features.csv: CSV version of the features table from the database*
- *Database/database_creation.ipynb: Creation of the SQLite database and the join Database/delhi.sqlite: The database in SQLite format*
- *MachineLearningModels/: Includes all machine learning models we created.*
- *MachineLearningModels/RandomForestClassifier.ipynb: Machine learning model we chose as the best performing model for this project.* 

## Overview

Weather forecasting is a science and a very important and crucial requirement in daily life. In this project we will develop a machine learning model accurate enough for predicting the weather conditions.

## Reason for selecting the topic

We chose this topic because weather forecasting is one of the most complex equations to solve. Machine learning model will give an accurate result as desired in weather forecasting.

## Description of the source of data

The source of our dataset is from https://www.kaggle.com/datasets/mahirkukreja/delhi-weather-data. It is a weather dataset for the New Delhi city in India. 
This data was taken out from wunderground with the help of their easy to use api. It contains various features such as temperature, pressure, humidity, rain, precipitation,etc. from the year 1996 to 2017.

## Questions to answer with the data

With the given atmospheric condition such as temperature, pressure, humidity, rain, snow, etc. we are trying to predict the weather if it is haze, rain, cloudy or clear.

## Outline

The first step for this project was to locate a suitable dataset. We found delhi_weather.csv and performed the cleaning process by dropping unnecessary columns and removing NaN values. We then created two preliminary machine learning models to test on the dataset. For this, logistic regression and decision tree were the two models. Initially, the decision tree model had good results, but we decided to test additional models in segment 2.

In segment two, we also created a database using SQLite which can be found in delhi.sqlite in the Database folder. We began with two tables split from the original database, both using the datetime column as their primary key. The two tables were then merged, written into the database file, and then we were able to connect the database into the second set of machine learning models tested. 

For segment 2, we tested logistic regression, decision tree, and random forest models with a variety of oversampling and undersampling techniques. We aggregated the accuracy and precision scores in ML_Models.ipynb and discussed which would be the most fitting to move forward with. In this segment we also began preparing our presentation by creating a draft of our final slide deck. An outline of what we would like the blueprint to look like was created in Dashboard_blueprint.txt, and much of the next week will be spent continuing to add to the dashboard and finalizing the machine learning model.

For segment 3, to organize our main branch we splitted the ML_Models.ipynb into DecisionTreeModel.ipynb, LogisticRegression.ipynb and RandomForestClassifier.ipynb. We also created an excel table to compare the results of our models. We found that RandomForestClassifier model with RandomOverSampling performed well with accuracy score 0.94. We modified our google slides and fleshed in more about database, machine learning models and dashboard. 

## Database
[Link to Database](https://github.com/rankx034/final-project/tree/main/Database "Link to Database")

We created a database using SQLite which can be found in delhi.sqlite. We began with two tables split from the original database, both using the datetime column as their primary key. The two tables were then merged, written into the database file, and then we were able to connect the database into the second set of machine learning models tested. 

### Preliminary feature selection: 
The dataset we started with contained 18 features, which we subsequently reduced to 18. Features such as snow, tornado, hail, and a wind direction column as string were determined not to contribute to the success of the machine learning model as they were too rare to provide meaningful change in outcome. Apart from this, we determined to drop all NaN values. Due to the nature of a weather dataset, we felt this would not have a significant impact on the spread of the dataset, as any given feature from any given day would not have a critical impact on the classification and would be difficult to provide an accurate value. We also narrowed down a total of 37 possible conditions to four. The four conditions now are haze, rain, cloudy, and clear. The haze category contains conditions such as sandstorm, smoke, and blowing sand. The rain category contains conditions such as drizzle, rain, and thunderstorm. The cloudy category contains conditions such as overcast and partly cloudy. The clear category remains the same and only contains the condition clear. Following the consolidation these categories and cleaning the dataset from missing values and unnecessary columns, the dataset was exported as a CSV, plugged into a SQLite database, and connected into our machine learning models.

## Machine Learning

[Link to Machine Learning Models](https://github.com/rankx034/final-project/tree/kiruthikasbranch/MachineLearningModels)

### Feature Engineering
The 'datetime-utc' column was converted to two separate columns 'year' and 'month' so that we were dealing strictly with numeric values. We also dropped the 'wdire' column because it was a duplicate column where wind directions were labeled as string values. This left us with a total of 16 features including the target variable.

### Data splitting
We separated our target value, 'conds', from our features and imported sklearns 'train_test_split' library to split our training and test sets.

### Models Results/Comparison 
We used Logistic Regression, Decision Tree, and Random Forest classifiers and added over and undersampling techniques to these models and compared the performance of the models

![Models_Classification](https://user-images.githubusercontent.com/95719819/172074453-5d8a5837-3164-4dcc-8f8d-24004d183d20.png)

## Model Choice

Our final model choice is the **Random Forest classifier** with Oversampling techniques applied. Benefits to using a Random Forest classifier are that the model is robust against overfitting as well as it runs efficiently on large datasets such as ours. Some cons to this model specifically is that it has a low balanced accuracy score but high recall and precision scores which show not very many false negatives and false positives.

![Confusion Matrix](https://user-images.githubusercontent.com/75644168/172050389-672985ed-e5c5-4914-a9f5-2d6d1f023cd4.png)

![Classification Report](https://user-images.githubusercontent.com/75644168/172050400-c768a6a1-c382-475b-8c57-3f23299c641f.png)

## Dashboard

The dashboard was created using Tableau: [Link to Dashboard](https://public.tableau.com/app/profile/dan.nyhan/viz/Final_project_dashboard_16541324242110/DelhiWeather_1 "Link to Dashboard")

## Presentation

[Link to Presentation](https://docs.google.com/presentation/d/1KeeU3EgppuTGKXcuOER7i4_vZN0HvCgSK5DiS5jiEsY/edit#slide=id.g12edf083185_0_1 "Link to Presentation")

