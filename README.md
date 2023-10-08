# House_Price_Estimator :- Project Overview

- Created a prediction tool for people who are looking to buy houses in the residence.
- Got the House Pricing Dataset from kaggle.
- Dataset contained 81 variable columns and about 1460 rows.
- Transformed the skewed data using log-transformation and also utilised yeo-Johnson transformation.
- For feature engineering optimised both regular as well as open-source packages. Open source packages utilisation was quite new to me and definitely learned a lot in the process.
- For model Building, given its a regression problem, only utilised Linear Regression.

## Code and Resources Used :- 

1. Python Version: 3.11.4
2. Packages: Pandas, Numpy, Matplotlib, Seaborn, scikit-learn, scipy, joblib
3. For all the packages: `pip install requirements.txt`
4. ChatGPT: GPT-3.5

## Data Analysis :-

1. First, checked the distribution of the target varibale. It was a non-gaussian right skewed distribution. Applied log-transformation and visualised it again and the distribution was normal.
2. Identified categorical variables.
3. Analysed the missing values and even visualized them in order to understand the impact of missing data has over the target variable.
4. Explored temporal variables with the year information. Found an interesting information that the sales price were decreasing as the years go by which is kinda unusal for real life. Found that most of the houses ahd old garages and they weren't remodelled recently, therefore, resulting in decrease of their sales price.
5. There were few variables which were highly skewed therefore utilised yeo-johnson transformation for them. And Visualized them.

### Some Visualizations :-

![image](https://github.com/anurag122002/House_Price_Prediction/assets/111629651/643a5d41-f6e9-4021-895a-e66e17abffcd)

![image](https://github.com/anurag122002/House_Price_Prediction/assets/111629651/dea87b1b-4fbf-4038-92e2-d54b515fc0e0)

![image](https://github.com/anurag122002/House_Price_Prediction/assets/111629651/a16b6099-2ee2-4874-a2ab-3bc8f8d7b7e5)

## Feature-Engineering :-

Optimised feature engineering with both regular and open-source libraries/Packages. 
Also, in the beginning only seperated the dataset into train and test sets for better grasping the transformations visually, applied to the dataset.

1. For categorical missing values imputed them with the string-> Missing.
2. For numerical variables added a binary missing indiactor variable and then replaced the original missing value with mean.
3. For the temporal variables, captured the time elapsed between the other year variables and the year in which the house was sold into three new engineered variables.
4. Also, there were quality variables in the dataset and by quality variables I mean variables representing any quality of the house. Replaced these categories by numbers increasing with the quality of the place or room.
   - Ex = Excellent
   - Gd = Good
   - TA = Average/Typical
   - Fa = Fair
   - Po = Poor
5. Encoded categorical variables.
6. Saved the engineered train and test sets into csv file for the next part.
7. Utilised joblib to save the scaler.

## Feautre-Selection :-

1. Utilised Lasso Regression and SelectFromModel library from sklearn package to select the right features for model training.
2. Out of total 81, 38 features were selected for model training.
3. Saved the selected features into a csv file for our model training.

## Model Building :-

1. Utilised Linear Regresison as the model for predicting house prices and applied lasso regression for regularization with alpha = 0.001.
2. Evaluated the Lasso predictions with respect to the original sales price.
   
   ![image](https://github.com/anurag122002/House_Price_Prediction/assets/111629651/b19d5097-c22e-4f6c-8ebb-b9ba44f020ab)
   
3. Evaluated and visulaized the distribution of errors. The error distribution showed a Gaussian Distribution suggesting that the model is doing a pretty good job.
   
   ![image](https://github.com/anurag122002/House_Price_Prediction/assets/111629651/6b7db302-6b89-4495-b32a-fd3a6b131c60)
   
4. Saved the model by optimising joblib.




