# Customer-Churn-Prediction-Project
## Problem Defination

Customer attrition, also known as customer churn, customer turnover, or customer defection, is the loss of clients or customers. In this project we are going to predict behaviors of churn or not churn to help retain customers.

The steps which we are going to follow to create the project:

- Understanding the data

- Exploratory Data Analysis (EDA)
   - Univariate Analysis
   - Bivariate Analysis
   - Correlation in Numerical variables
   
- Data Preprocessing
   - Encoding binary variables
   - One hot endcoding
   - Feature Scaling
   
- Model Building
- Feature Engineering
- Model Tuning
   - Hyperparameter Tuning
   - Grid Search
   - Random Search
- Feature Importance

## Discover the Data

The features in the data sets are and test_features are:

+ **Gender**: Male or Female
+ **Age**: Contains age >18+
+ **Race**: Race of the person
+ **Marital Status**: Married or Single
+ **Weight (lbs)**:Weight of a person in pounds
+ **Height (Inches)**: Hegiht in inches 
+ **BMI**: BMI of a person
+ **Condition of Teeth**: Oral Health of a person
+ **Diabetic/Not Diabetic**: Is the person diabatic or non diabetic
+ **Heart Attack**: Suffered from heart attack in the past or not
+ **Cholesterol**: High or Normal

## Exploratory Data Analysis 

### Basic observations

+ The datasets have total **3333 ** *number of observation*
+ **15** *numerical variables* and **5** *categorical variables*
+ Churn is our target variable
+ There are no duplicates in the data and there are no values missing in the dataset

### Univariate Analysis

+ The below figure shows the distribution of the categorical variables with target variables
![Target vs Categorical variable](https://github.com/DhruTewa/Customer-Churn-Prediction-Project/blob/master/images/univariate_analysis_cat.png)

+ The below figure shows the distribution of the numerical variables
![Numerical variables Distribution](https://github.com/DhruTewa/Customer-Churn-Prediction-Project/blob/master/images/univariate_analysis_num.png)

### Outliers Analysis

We can see some outliers in the cholestrol variable and will check it 
![Outliers Detection](https://github.com/DhruTewa/Customer-Churn-Prediction-Project/blob/master/images/outliers.png)


### Bivariate Analysis

+ The below graph shows the distribution of the target varaiable with the numberical varaiables:

![Target vs Numerical variable1](https://github.com/DhruTewa/Customer-Churn-Prediction-Project/blob/master/images/Bivariate%20Analysis_Itnl_PlanVsChurn.png)

![Target vs Numerical variable1](https://github.com/DhruTewa/Customer-Churn-Prediction-Project/blob/master/images/Bivariate%20Analysis_Vmail_PlanVsChurn.png)

### Features correlation

+ From the correaltion martix below we found that variables "Day_Mins","Eve_Mins","Night_Mins","Intl_Mins" are highly correlated with "Day_Charge","Eve_Charge","Night_Charge","Intl_Charge" 

![Features_Correlation](https://github.com/DhruTewa/Customer-Churn-Prediction-Project/blob/master/images/correlation_analysis.png)

### Data Preprocessing

It is preferable to have features like 'Churn' encoded as 0 and 1 instead of no and yes, so that we can then feed it into machine learning algorithms that only accept numeric values. Besides 'Churn', other features **Intl_Plan, Vmail_Plan** that are of type object can be converted into 0s and 1s.

## Model Developement

We will evaluate algorithms using the accuracy  and f1-score metrics.

For model developement we are selecting models

- Logistics regression(LR) - Accuracy -86%
- RandomForestClassifier - Accuracy -92%

![ROC_Before_Model Tuning](https://github.com/DhruTewa/Customer-Churn-Prediction-Project/blob/master/images/ROC_before_model_tuning.png)

## Model Tuning

To improve the performance of algorithms model tuning is performed with the below result
 - Bagging Method : Random Forests (RF) *increased* **accuracy to 94%**

![ROC_After_Model Tuning](https://github.com/DhruTewa/Customer-Churn-Prediction-Project/blob/master/images/ROC_after_model_tuning.png)

## Feature Importance:

By looking at the graph below we can say that day_charge and customer_service_call are two major factors in predicting the salary.

![Features_Importance](https://github.com/DhruTewa/Customer-Churn-Prediction-Project/blob/master/images/feature_importance.png)
