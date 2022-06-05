# final-project

## Files

ML_Models.ipynb: Final version of the machine learning model used for this project. 
delhi_weather_cleaned.csv: The original dataset obtained from Kaggle that has been cleaned for our use
Database/conds.csv: CSV version of the conditions table from the database
Database/features.csv: CSV version of the features table from the database
Database/database_creation.ipynb: Creation of the SQLite database and the join
Database/delhi.sqlite: The database in SQLite format
MachineLearningModels/ : Includes various preliminary machine learning models. 


## Exploratory Analysis

The dataset we started with contained 18 features, which we subsequently reduced to 18. Features such as snow, tornado, hail, and a wind direction column as string were determined not to contribute to the success of the machine learning model as they were too rare to provide meaningful change in outcome. Apart from this, we determined to drop all NaN values. Due to the nature of a weather dataset, we felt this would not have a significant impact on the spread of the dataset, as any given feature from any given day would not have a critical impact on the classification and would be difficult to provide an accurate value. We also narrowed down a total of 37 possible conditions to four. The four conditions now are haze, rain, cloudy, and clear. The haze category contains conditions such as sandstorm, smoke, and blowing sand. The rain category contains conditions such as drizzle, rain, and thunderstorm. The cloudy category contains conditions such as overcast and partly cloudy. The clear category remains the same and only contains the condition clear. Following the consolidation these categories and cleaning the dataset from missing values and unnecessary columns, the dataset was exported as a CSV, plugged into a SQLite database, and connected into our machine learning models. 

## Outline

The first step for this project was to locate a suitable dataset. We found delhi_weather.csv and performed the cleaning process by dropping unnecessary columns, and removing NaN values. We then created two preliminary machine learning models to test on the dataset. For this, logistic regression and decision tree were the two models. Initiallly, the decision tree model had good results, but we decided to test additional models in segment 2. I

In segment two, we also created a database using SQLite which can be found in delhi.sqlite in the Database folder. We began with two tables split from the original database, both using the datetime column as their primary key. The two tables were then merged, written into the database file, and then we were able to connect the database into the second set of machine learning models tested. 

For segment 2, we tested logistic regression, decision tree, and random forest models with a variety of oversampling and undersampling techniques. We aggregated the accuracy and precision scores in ML_Models.ipynb and discussed which would be the most fitting to move forward with. In this segment we also began preparing our presentation by creating a draft of our final slide deck. An outline of what we would like the blueprint to look like was created in Dashboard_blueprint.txt, and much of the next week will be spent continuing to add to the dashboard and finalizing the machine learning model. 
