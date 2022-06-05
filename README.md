![deeplearninggeneral](https://user-images.githubusercontent.com/95719819/168449229-3b4df5d7-3ded-4cda-92c4-9c519a8229c9.png)
# Weather Prediction

## File Description
- *ML_Models.ipynb: Final version of the machine learning model used for this project.* 
- *delhi_weather_cleaned.csv: The original dataset obtained from Kaggle that has been cleaned for our use*
- *Database/conds.csv: CSV version of the conditions table from the database*
- *Database/features.csv: CSV version of the features table from the database*
- *Database/database_creation.ipynb: Creation of the SQLite database and the join Database/delhi.sqlite: The database in SQLite format*
- *MachineLearningModels/: Includes various preliminary machine learning models.*

## Overview

Weather forecasting is a science and a very important and crucial requirement in daily life. In this project we will develop a machine learning model accurate enough for predicting the weather conditions.

## Reason for selecting the topic

We chose this topic because weather forecasting is one of the most complex equations to solve. Machine learning model will give an accurate result as desired in weather forecasting.

## Source of Data

The source of our dataset is from Kaggle [Link to Source](https://www.kaggle.com/datasets/mahirkukreja/delhi-weather-data "Link"). It is a weather dataset for the New Delhi city in India. 
This data was taken out from wunderground with the help of their easy to use api. It contains various features such as temperature, pressure, humidity, rain, precipitation,etc. from the year 1996 to 2017.

## Purpose

With the given atmospheric conditions such as temperature, pressure, humidity, rain, snow, etc. can our machine learning model accurately predict if the weather is hazey, rainy, cloudy or clear?

## Database
[Link to Database](https://github.com/rankx034/final-project/tree/main/Database "Link to Database")

![ERD](https://user-images.githubusercontent.com/75644168/172050370-d961992e-2924-4470-9d5f-0e4c33a3ca21.png)

We created a database using SQLite which can be found in delhi.sqlite. We began with two tables split from the original database, both using the datetime column as their primary key. The two tables were then merged, written into the database file, and then we were able to connect the database into the second set of machine learning models tested. 


## Machine Learning Model
[Link to Model Results](https://github.com/rankx034/final-project/blob/main/ML_Models.ipynb "Link to Model Code")

### Preliminary Feature Selection: 
The dataset we started with contained 18 features, which we subsequently reduced to 18. Features such as snow, tornado, hail, and a wind direction column as string were determined not to contribute to the success of the machine learning model as they were too rare to provide meaningful change in outcome. Apart from this, we determined to drop all NaN values. Due to the nature of a weather dataset, we felt this would not have a significant impact on the spread of the dataset, as any given feature from any given day would not have a critical impact on the classification and would be difficult to provide an accurate value. We also narrowed down a total of 37 possible conditions to four. The four conditions now are haze, rain, cloudy, and clear. The haze category contains conditions such as sandstorm, smoke, and blowing sand. The rain category contains conditions such as drizzle, rain, and thunderstorm. The cloudy category contains conditions such as overcast and partly cloudy. The clear category remains the same and only contains the condition clear. Following the consolidation these categories and cleaning the dataset from missing values and unnecessary columns, the dataset was exported as a CSV, plugged into a SQLite database, and connected into our machine learning models.

### Feature Engineering
The 'datetime-utc' column was converted to two separate columns 'year' and 'month' so that we were dealing strictly with numeric values. We also dropped the 'wdire' column because it was a duplicate column where wind directions were labeled as string values. This left us with a total of 16 features including the target variable.

### Data Splitting
We separated our target value, 'conds', from our features and imported sklearns 'train_test_split' library to split our training and test sets. Our data was split 75/25 between testing and training sets, respectively.

### Model Performance

We used Logistic Regression, Decision Tree, and Random Forest classifiers and added over and undersampling techniques to these models and compared the performance of the models

#### Classifiers
- The Logistic Regression classifier had an extremely low balanced accuracy score at 0.42.
- The recall scores for the Decision Tree and Random Forest classifiers were 0.90 and 0.93, respectively.
- The precision score for the Decision Tree and Random Forest classifiers were 0.90 and 0.93, respectively.
- The Random Forest Classifier outperformed each model.

![Classifiers](https://user-images.githubusercontent.com/75644168/170896908-ae426ebd-94fc-4b02-a0e6-ae25c623192b.png)


#### Random Oversampling 
- The Logistic Regression model when applied with oversampling techniques also had a low balanced accuracy score of 0.63 in this case as well.
- The recall scores for the Decision Tree and Random Forest classifiers were 0.90 and 0.93, respectively. Performing virtually the same as without any techniques applied.
- The precision score for the Decision Tree and Random Forest classifiers were 0.90 and 0.93, respectively. Performing virtually the same as without any techniques applied.
- The balanced accuracy scores for the Random Forest Classifier did increase from 0.75 to 0.78 with oversampling techniques applied.

![Oversampling](https://user-images.githubusercontent.com/75644168/170896914-88eef73a-b85d-4ff5-b899-68a9a8c2f3f6.png)


### Random Undersampling
- The Logistic Regression model when applied with undersampling techniques also had a low balanced accuracy score of 0.64 in this case as well.
- The recall scores for the Decision Tree and Random Forest classifiers were 0.75 and 0.84, respectively. Performing worse than the oversampling method.
- The precision score for the Decision Tree and Random Forest classifiers were 0.87 and 0.90, respectively. Performing worse than the oversampling method.
- The balanced accuracy scores for the Random Forest Classifier did increase from 0.78 using the oversampling method 0.82 with oversampling techniques applied.

![Undersampling](https://user-images.githubusercontent.com/75644168/170896930-bbac7c3a-07db-4ee7-888a-d1510c5add47.png)


#### Model Choice

Random Forest Classifier with Oversampling Performance:
- Accuracy: 0.93
- F1 Score: 0.93

![Confusion Matrix](https://user-images.githubusercontent.com/75644168/172050389-672985ed-e5c5-4914-a9f5-2d6d1f023cd4.png)

![Classification Report](https://user-images.githubusercontent.com/75644168/172050400-c768a6a1-c382-475b-8c57-3f23299c641f.png)

Our model choice in this case is the Random Forest classifier with Oversampling techniques applied. Benefits to using a Random Forest classifier are that the model is robust against overfitting as well as it runs efficiently on large datasets such as ours. Some cons to this model specifically is that it has a low balanced accuracy score but high recall and precision scores which show not very many false negatives and false positives.

## Dashboard

The dashboard was created using Tableau: [Link to Dashboard](https://public.tableau.com/app/profile/dan.nyhan/viz/Final_project_dashboard_16541324242110/DelhiWeather_1 "Link to Dashboard")

## Presentation

[Link to Presentation](https://docs.google.com/presentation/d/1KeeU3EgppuTGKXcuOER7i4_vZN0HvCgSK5DiS5jiEsY/edit#slide=id.g12edf083185_0_1 "Link to Presentation")
