# Big-Mart-Sales-Prediction
A regression practice problem wherein we have to predict product-wise and store-wise sales.Sales prediction is a very common real-life problem that each company faces atleast once in its lifetime. If done correctly, it can have a significant impact on the success and performance of that company. According to a study, companies with accurate sales predictions are 10% more likely to grow their revenue year-over-year and 7.3% more likely to hit quota.

# The course is divided into below modules:
Exploratory Data Analysis |
Data Preparation |
Predictive Modeling using different techniques.

# We will handle this problem in a structured way. We will be following the table of content given below.
Problem Statement |
Hypothesis Generation |
Loading Packages and Data |
Data Structure and Content |
Exploratory Data Analysis |
Univariate Analysis |
Bivariate Analysis |
Missing Value Treatment |
Feature Engineering |
Encoding Categorical Variables |
Label Encoding | 
One Hot Encoding |
PreProcessing Data |
Modeling |
Linear Regression |
Regularized Linear Regression |
RandomForest |
XGBoost |
Summary |

# What is hypothesis generation?
This is a very important stage in any machine learning process. It involves understanding the problem in detail by brainstorming as many factors as possible which can impact the outcome. It is done by understanding the problem statement thoroughly and before looking at the data.

# How to do hypothesis generation?
One very effective technique to generate hypotheses is by creating mindmaps. You can draw it even using a pen and paper. The general methodology is as follows: Write the main idea in the center. Draw branches from the center such they are connected with one another with final outputs shown towards the end.

# We can start the process by working on four levels: Store Level, Product Level, Customer Level and Macro Level.

Store Level : City type | Population Density | Competitors | Marketing | Location | Ambiance

Product Level : Brand | Packaging | Utility | Display Area | Advertising

Customer Level : Customer Behavior | Job Profile | Family Size | Annual Income

Macro Level : Environment | Economic Growth

# Combine Train and Test
To explore data in any data science competition, it is advisable to append test data to the train data. Combining train and test sets saves a lot of time and effort because if we have to make any modification in the data, we would make the change only in the combined data and not in train and test data separately. Later we can always split the combined data back to train and test.

For example, if we wish to multiply Item_Fat_Content variable by 100, we can do it for the train and test data separately or we can do the same operation once for the combined dataset. The latter approach is more efficient when there are a lot of changes to be made.

So, we will go ahead combine both train and test data and will carry out data visualization, feature engineering, one-hot encoding, and label encoding. Later we would split this combined data back to train and test datasets.

# Issues found after Extrapolatory Data Analysis are 
1. Missing values in Item_Weight ==> Replaced by Item_Weight of corresponding Item_Identifier
2. Missing Values in Outlet_Size ==> Replaced NaN values by "Small"
3. Outlet_Sales is positively skewed
4. Item_Visibility is Positively skewed
5. Item_Visibility = 0.0 ==> Replaced by mean of Item_Visibility of corresponding Item_Identifier

# Feature Engineering
Most of the times, the given features in a dataset are not sufficient to give satisfactory predictions. In such cases, we have to create new features which might help in improving the model’s performance. Let’s try to create some new features for our dataset.

In this section we will create the following new features:

Item_Type_new: Broader categories for the variable Item_Type.
Item_category: Categorical variable derived from Item_Identifier.
Outlet_Years: Years of operation for outlets.
price_per_unit_wt: Item_MRP/Item_Weight
Item_MRP_clusters: Binned feature for Item_MRP.

