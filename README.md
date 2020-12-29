# xPrize Challenge: Pandemic Response Challenge
This is my attempts and process to develop a model. 

## Data 
The input data is from the [Oxford Dataset](https://github.com/OxCGRT/covid-policy-tracker/tree/master/data).
This dataset is formed by 26 columns. These columns consist of information related with covid 19 by country. 
I first focused on the data. I tried to clean it and understand it. I also did some typical data processing steps like specifying the type. 
I realized some of the features were not important and we could drop them. 
I also found out that some countries had a lot of NaN data. 
I created new columns for the date, diving it in day, month and year to see if taking into acount the month in the model could help to predict. 
I also decided to drop the columns about the flag. 

### Dealing with missing values
This dataset has a lot of misisng values. I decided to fill the missing values by the previous value. All of the columns about the measurements taken by each country has a lot of missing values. In these columns, having the value before makes sense because it is the same measurement as it was the day before.

With ConfirmedCases and Confirmed Deaths, I also fill with the previous values. 

### Feature Importances
I tried to check the feature importances with a Random Forest Regressor model. 
First I did it with  France, and then I did it with all the countries. As I could predict, the most important feature was Confirmed Deaths. 

### Feature Engineering
I created new features that were the lineal combination of the categorical variables and their flag variable. For example, the variable C1_School_closing and the varibale C1_Flag. The first one is a categorical variable from 0 to 4 and the second one indicates if the measure was taken in the whole country or just in some areas. So I tried to give a weight depending on the flag. 

## Model
I decided to perform an Ada Boost Regressor with the Scikit-learn implementation. 
I tried to do the model with the weights for the flags and categorical variable,s but it didn't worked. Teh results were worse. 


 
