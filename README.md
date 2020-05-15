# Big Mart Sales Prediction

A regression practice problem wherein we have to predict product-wise and store-wise sales.Sales prediction is a very common real-life problem that each company faces atleast once in its lifetime. If done correctly, it can have a significant impact on the success and performance of that company. According to a study, companies with accurate sales predictions are 10% more likely to grow their revenue year-over-year and 7.3% more likely to hit quota.

## The project is divided into below modules:

* Exploratory Data Analysis
* Data Preparation
* Predictive Modeling using different techniques.

## We will handle this problem in a structured way. We will be following the table of content given below.
* 1. Problem Statement
* 2. Loading Packages and Data
* 3. Understanding The Data
* 4. Exploratory Data Analysis
* 5. Imputing Missing Value 
* 6. Feature Engineering
* 7. Encoding Categorical Variables
* 8. Data PreProcessing
* 9. Linear Regression Model
* 10. Using KFold with Linear Regression
* 11. RandomForest Model
* 12. XGBoost Model
* 13. CatBoosting
* 14. Summary


## What is hypothesis generation?

This is a very important stage in any machine learning process. It involves understanding the problem in detail by brainstorming as many factors as possible which can impact the outcome. It is done by understanding the problem statement thoroughly and before looking at the data.

## How to do hypothesis generation?

One very effective technique to generate hypotheses is by creating mindmaps. You can draw it even using a pen and paper. The general methodology is as follows: Write the main idea in the center. Draw branches from the center such they are connected with one another with final outputs shown towards the end.

## We can start the process by working on four levels: Store Level, Product Level, Customer Level and Macro Level.

**Store Level** : City type | Population Density | Competitors | Marketing | Location | Ambiance

**Product Level** : Brand | Packaging | Utility | Display Area | Advertising

**Customer Level** : Customer Behavior | Job Profile | Family Size | Annual Income

**Macro Level** : Environment | Economic Growth

## Combine Train and Test

To explore data in any data science competition, it is advisable to append test data to the train data. Combining train and test sets saves a lot of time and effort because if we have to make any modification in the data, we would make the change only in the combined data and not in train and test data separately. Later we can always split the combined data back to train and test.

For example, if we wish to multiply Item_Fat_Content variable by 100, we can do it for the train and test data separately or we can do the same operation once for the combined dataset. The latter approach is more efficient when there are a lot of changes to be made.

So, we will go ahead combine both train and test data and will carry out data visualization, feature engineering, one-hot encoding, and label encoding. Later we would split this combined data back to train and test datasets.

## Issues found after Extrapolatory Data Analysis are 

1. Missing values in Item_Weight ==> Replaced by Item_Weight of corresponding Item_Identifier
2. Missing Values in Outlet_Size ==> Replaced NaN values by "Small"
3. Outlet_Sales is positively skewed
4. Item_Visibility is Positively skewed
5. Item_Visibility = 0.0 ==> Replaced by mean of Item_Visibility of corresponding Item_Identifier

## Feature Engineering

Most of the times, the given features in a dataset are not sufficient to give satisfactory predictions. In such cases, we have to create new features which might help in improving the model’s performance. Let’s try to create some new features for our dataset.

In this section we will create the following new features:

* **Item_Type_new**: Broader categories for the variable Item_Type.  
* **Item_category**: Categorical variable derived from Item_Identifier.  
* **Outlet_Years**: Years of operation for outlets.  
* **price_per_unit_wt**: Item_MRP/Item_Weight.  
* **Item_MRP_clusters**: Binned feature for Item_MRP. 

## Data PreProcessing
* Removed skewness from Item_Visibility variable using log transformation.
* Removed skewness from price_per_unit_weight variable using log transformation.
* Removed skewness from Item_Outlet_Sales variable using log transformation.

## Linear Regression model 
**With log transformation of Item_Outlet_Sales**
* MAE: 0.4013948690353487
* MSE: 0.2741788727205858
* RMSE: 0.5236209246397491
* Rsquared : 73.8333245654847

**Without log transformation of Item_Outlet_Sales**
* MAE: 810.0715791198803
* MSE: 1158323.0500781583
* RMSE: 1076.254175405679
* Rsquared : 56.88539060798533

## KFolds With Linear Regression
**With log transformation of Item_Outlet_Sales**
* RMSE: 0.5223383073684176

**Without log transformation of Item_Outlet_Sales**
* RMSE: 1074.4775761353715

## Random Forest Model
**With log transformation of Item_Outlet_Sales**
* RMSE: 0.4582341745618182

**Without log transformation of Item_Outlet_Sales**
* RMSE: 896.3160736695859

## XGBoost Model
**With log transformation of Item_Outlet_Sales**
* RMSE: 0.34808372157504675

**Without log transformation of Item_Outlet_Sales**
* RMSE: 638.5169522174853

## CatBoosting
* R-Squared : 99.9842171223728

## Summary
It seems that CatBoosting methodolgy has overfitted the data but XGBoost is giving some practical result with RMSE ~638.
