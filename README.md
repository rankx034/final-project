![deeplearninggeneral](https://user-images.githubusercontent.com/95719819/168449229-3b4df5d7-3ded-4cda-92c4-9c519a8229c9.png)
# Weather Prediction

## Overview

Weather forecasting is a science and a very important and crucial requirement in daily life. In this project we will develop a machine learning model accurate enough for predicting the weather conditions.

## Reason for selecting the topic

We chose this topic because weather forecasting is one of the most complex equations to solve. Machine learning model will give an accurate result as desired in weather forecasting.

## Description of the source of data

The source of our dataset is from https://www.kaggle.com/datasets/mahirkukreja/delhi-weather-data. It is a weather dataset for the New Delhi city in India. 
This data was taken out from wunderground with the help of their easy to use api. It contains various features such as temperature, pressure, humidity, rain, precipitation,etc. from the year 1996 to 2017.

## Questions to answer with the data

With the given atmospheric condition such as temperature, pressure, humidity, rain, snow, etc. we are trying to predict the weather if it is haze, rain, cloudy or clear.

## Communication Protocol
Our group meets on Zoom every 2-3 days to discuss whether our work in the project is ready to be uploaded to the main GitHub branch. In between those meetings, we use our "Group 8" Slack groupchat to share files and ideas for the project's direction. Each individual team member has their own GitHub branch.

## Outline

The first step for this project was to locate a suitable dataset. We found delhi_weather.csv and performed the cleaning process by dropping unnecessary columns and removing NaN values. We then created two preliminary machine learning models to test on the dataset. For this, logistic regression and decision tree were the two models. Initially, the decision tree model had good results, but we decided to test additional models in segment 2.

In segment two, we also created a database using SQLite which can be found in delhi.sqlite in the Database folder. We began with two tables split from the original database, both using the datetime column as their primary key. The two tables were then merged, written into the database file, and then we were able to connect the database into the second set of machine learning models tested. 

For segment 2, we tested logistic regression, decision tree, and random forest models with a variety of oversampling and undersampling techniques. We aggregated the accuracy and precision scores in ML_Models.ipynb and discussed which would be the most fitting to move forward with. In this segment we also began preparing our presentation by creating a draft of our final slide deck. An outline of what we would like the blueprint to look like was created in Dashboard_blueprint.txt, and much of the next week will be spent continuing to add to the dashboard and finalizing the machine learning model.

## Database
[Link to Database](https://github.com/rankx034/final-project/tree/main/Database "Link to Database")

We created a database using SQLite which can be found in delhi.sqlite. We began with two tables split from the original database, both using the datetime column as their primary key. The two tables were then merged, written into the database file, and then we were able to connect the database into the second set of machine learning models tested. 


## Machine Learning Model
[Link to Model Results](https://github.com/rankx034/final-project/blob/main/ML_Models.ipynb "Link to Model Code")

### Preliminary feature selection: 
The dataset we started with contained 18 features, which we subsequently reduced to 18. Features such as snow, tornado, hail, and a wind direction column as string were determined not to contribute to the success of the machine learning model as they were too rare to provide meaningful change in outcome. Apart from this, we determined to drop all NaN values. Due to the nature of a weather dataset, we felt this would not have a significant impact on the spread of the dataset, as any given feature from any given day would not have a critical impact on the classification and would be difficult to provide an accurate value. We also narrowed down a total of 37 possible conditions to four. The four conditions now are haze, rain, cloudy, and clear. The haze category contains conditions such as sandstorm, smoke, and blowing sand. The rain category contains conditions such as drizzle, rain, and thunderstorm. The cloudy category contains conditions such as overcast and partly cloudy. The clear category remains the same and only contains the condition clear. Following the consolidation these categories and cleaning the dataset from missing values and unnecessary columns, the dataset was exported as a CSV, plugged into a SQLite database, and connected into our machine learning models.

### Feature Engineering
The 'datetime-utc' column was converted to two separate columns 'year' and 'month' so that we were dealing strictly with numeric values. We also dropped the 'wdire' column because it was a duplicate column where wind directions were labeled as string values. This left us with a total of 16 features including the target variable.

### Data splitting
We separated our target value, 'conds', from our features and imported sklearns 'train_test_split' library to split our training and test sets.

### Model Choice

We used Logistic Regression, Decision Tree, and Random Forest classifiers and added over and undersampling techniques to these models and compared the performance of the models

#### Classifiers
- The Logistic Regression classifier had an extremely low balanced accuracy score at 0.42.
- The recall scores for the Decision Tree and Random Forest classifiers were 0.90 and 0.93, respectively.
- The precision score for the Decision Tree and Random Forest classifiers were 0.90 and 0.93, respectively.
- The Random Forest Classifier outperformed each model.

![Classifiers](https://user-images.githubusercontent.com/75644168/170896908-ae426ebd-94fc-4b02-a0e6-ae25c623192b.png)
)

#### Random Oversampling 
- The Logistic Regression model when applied with oversampling techniques also had a low balanced accuracy score of 0.63 in this case as well.
- The recall scores for the Decision Tree and Random Forest classifiers were 0.90 and 0.93, respectively. Performing virtually the same as without any techniques applied.
- The precision score for the Decision Tree and Random Forest classifiers were 0.90 and 0.93, respectively. Performing virtually the same as without any techniques applied.
- The balanced accuracy scores for the Random Forest Classifier did increase from 0.75 to 0.78 with oversampling techniques applied.

![Oversampling](https://user-images.githubusercontent.com/75644168/170896914-88eef73a-b85d-4ff5-b899-68a9a8c2f3f6.png)
)

#### Random Undersampling
- The Logistic Regression model when applied with undersampling techniques also had a low balanced accuracy score of 0.64 in this case as well.
- The recall scores for the Decision Tree and Random Forest classifiers were 0.75 and 0.84, respectively. Performing worse than the oversampling method.
- The precision score for the Decision Tree and Random Forest classifiers were 0.87 and 0.90, respectively. Performing worse than the oversampling method.
- The balanced accuracy scores for the Random Forest Classifier did increase from 0.78 using the oversampling method 0.82 with oversampling techniques applied.

![Undersampling](https://user-images.githubusercontent.com/75644168/170896930-bbac7c3a-07db-4ee7-888a-d1510c5add47.png)
)

Our model choice in the case is the Random Forest classifier with Oversampling techniques applied. Benefits to using a Random Forest classifier are that the model is robust against overfitting as well as it runs efficiently on large datasets such as ours. Some cons to this model specifically is that it has a low balanced accuracy score but high recall and precision scores which show not very many false negatived and false positives.

[Link to Presentation](https://docs.google.com/presentation/d/1KeeU3EgppuTGKXcuOER7i4_vZN0HvCgSK5DiS5jiEsY/edit#slide=id.g12edf083185_0_1 "Link to Presentation")
