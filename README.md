# Predict survivors during the Titanic

The purpose of this project was to predict weather a person survived the titanic or not given certain parameters(1 = 'Survived', 0 = 'Didn't Survive') . This dataset was found on [kaggle.com](https://www.kaggle.com/datasets/yasserh/titanic-dataset). 

This file shows how:
  1. The data was cleaned.
  2. What features were kept and which ones were dropped.
  3. Encoding certain columns.
  4. Splitting the data into training and testing sets.
  5. Finding the predicted values.
  6. Then seeing how well our model works.


## About the data:
  - Passengerid - Unique id for each person (dropped)
  - Survived - 1 = 'Survived', 0 = 'Didn't survive' (kept)
  - Pclass - Tick class: 1 = 1st, 2 = 2nd, 3 = 3rd (dropped)
  - Name - Full name of each passenger (dropped)
  - Sex - Gender of each passenger (kept)
  - Age - Age of each passenger (kept)
  - SibSp - No. of siblings/spouses aboard (dropped)
  - Parch - No. of parents/ children aboard (dropped)
  - Ticket - Ticket Number (dropped)
  - Fare - Passenger Fare (dropped)
  - Embark - Entrance of the ship (kept)

## Process

### Cleaning
The data was read in using pandas dataframe. With this we are then able to manipulate the data so that it can be used for machine learning. After inspecting the dataframe (titanic_df), it was found that there were 177 'NaN' values found in the 'Age' column, 687 in the 'Cabin' column and 2 in the 'Embarked' column. 

The 'NaN' values found in the 'Age' column was replaced with the average age found in that column ~ 30.0 years. The columns 'Passengerid', 'Pclass', 'Name', 'Sibsp', 'Parch', 'Ticket', 'Fare' along with 'Cabin' were dropped from the model due to the fact that these coulmns were found not to have an impact on being able to predict wether a passenger survived the titanic or not. Finally, them 'Embarked' coulmn's missing values were replaced with mode of the column.

## Encoding
The dataframe that was left over had two columns that were considered to have 'categorical' data. Machine learning only works for numerical values so these column values had to be encoded. This was done by making use of LabelEncoder() from sklearn. This function will convert categorical data into a number from 0 to the number of unique categories. Lastly, the final dataframe was used by the logistic regression model. 

## Splitting
There are two key components needed for machine learning, the target value (y) and the features (X). Features are considered to be any coulmn that will influence the target value. The target value is the column that shows what the outcome has been. The data was split in a way were 20% of the data will be used for training and %80 will be used for testing. 

## Findings
A confusion matrix was used to evaluate the accuracy of the model. The following values were give:
  - True Positives (TP): The number of passengers correctly predicted as 'Survived' (88).
  - True Negatives (TN): The number of passengers correctly predicted as "Not Survived" (56).
  - False Positives (FP): The number of passengers incorrectly predicted as "Survived" when they did not survive (17).
  - False Negatives (FN): The number of passengers incorrectly predicted as "Not Survived" when they actually survived (18).



