# SC1015: Data Science Mini Project - Determining Happiness and Healthiness of Countries
Lab: A121 \
Group : 2

Video Link: https://youtu.be/yeOaMLBkJNM
--- 

### Description : 

This repository contains the main Jupyter Notebook of our Project, DataSet, video presentations and references for our Mini-Project 

Below is a short description of the overall project. The detailed analysis is found within the main Jupyter Notebook. All details are done in one single Jupyter Notebook.

Data Set : https://www.kaggle.com/datasets/prasertk/healthy-lifestyle-cities-report-2021
---

### Flow of Content

1. Problem Formulation
2. Data Preparation and Cleaning
3. Exploratory Data Analysis
4. Multi-Variate Analysis
5. Hierachal Clustering
6. Data Driven Insights and Conclusion
7. Learning Insights 
8. References

---
### 1. Problem Formulation


**Our Problem Formulation** : 
1. How can we expect the Happiness Level of a City be given its related health metrics? 
2. What determines if a City is both Happy and Healthy?
3. Can we identify underlying patterns or relationships among cities based on their health-related metrics?

**Motivation** : We believe that Health and Happiness are the most important factors in everyone. They are the factors in determining the quality of life that each indivdual experiences. Hence, we want to explore what constitutes to a Happy and Healthy Country and put forth ideas to bring the best quality of life to everyone.

--- 

### 2. Data Preparation and Cleaning

We cleaned the data and prepared them for our Exploratory Data Analysis & Machine Learning Model of choice. This includes filling in of NULL values with the appropriate values and removal of Characters that may interfere with the analysis. 

---


### 3. Exploratory Data Analysis

We then explore each variable to identify any pattern they may have with our Problem Forumulation or with each other. We used the visual aids of the Box Plots, Histogram, Violin, HeatMap and Scatterplots to understand the relationship the variables have with each other. 

As we are preparing the data for Multi-Variate Linear Regression, we calculated the correlations of the variables with `Happiness Levels` and found the variables with the highest correlation with it. They are : 

|                        Variable             |Correlation with `Happiness Levels` 
| :------------------------------------------ | :--------------------------------: |
| `Cost Of Bottled Water`                     |           0.81                  |       
| `Life Expectency`                           |           0.72                  |     
| `Pollution Index`                           |          -0.76                  |    
| `Obesity Levels`                            |           0.45                  |

--- 

### 4. Multi-Variate Analysis

We then performed Mutli-Variate Linear Regression to build a model that is able to predict `Happiness Levels` using `Life Expectancy`, `Cost of Bottled Water`, `Pollution Index` & `Obesity Levels` as predictors.

To test the accuracy of the model, we then find the Mean Square Error and Explained Variance of the model on the Train and Test Data Split. 
We found the Explained Variance of `0.8755` for the model on the Train Data Set and `0.5808` on the Test Data. This was a case of overfitting, and so we explored 2 ways to reduce the overfitting.


Firstly, we used `KFolds` methods to divide the dataset into k equally sized "folds" or subsets, and then train and evaluate the model k times. Given a small dataset sample size, using a traditional train-test split could lead to insufficient data for training, which might affect the model's performance. K-fold cross-validation helps to maximize the use of the available data by iteratively using different parts of the data for training and validation, ensuring that every sample is used for both training and validation at some point.

We found the optimal number of Folds by calculating the MSE and R^2 for each Fold Value and found the optimal Folds to be 4. After folding, we found that the Explained Variance on the test was improved to `0.7700`. 

However, overfitting may also be due to Multicollinearity between the predictor variables. To tackle this, we used Lasso Regreesion that will shrink coefficients in order to reduce multicollinearlity and lower overfitting. 

After using Lasso, the Explained Variance on the test improved to `0.7952`.

Results : 

|                        Model                                                         |Test Mean Square Error | Test Explained Variance |
| :------------------------------------------------------------------------------- | :------------------------: | :-------------------------------: | 
| `Multi Variate LinearRegression`                                                 |           0.33550          |     0.58083                       |     
| `Multi Variate LinearRegression with KFolds`                                     |           0.21030          |     0.77004                       | 
| `Lasso Regression`                                                               |           0.27560          |     0.79520                       | 


---

### 5. Hierachal Clustering 

For the next 2 Data Science Question, we used clustering. We chose  **Hierachal Clustering** as 

1. It gave us a powerful visualisation aid in terms of looking for similarites between Clusters of cities, which is the main goal of our question.
2. Cities that are anomalies would be easily seen from the dendrogram, as they are most dissimilar and result in high vertical distance. 

For the Second Question, we clustered based on `Happiness Levels` and `Life Expectency` & found the optimal clusters of `4` as it gives the highest Silhoutte Score and analysed the characteristics of each cluster.

We found that `Pollution Levels` and `Annual avg. Working Hours` contributes to the happiest and healthiest Countries.

For the third Question, we peformed similar anaylsis as above and found the optimal clusters of `2`.  To understand why the structure of the data that determines this number of optimal cluster, we used Random Forest Machine to determine the importance of each variable. This picks out the underlying relationship between the variables. 

We found that  `Cost of a monthly gym membership(City)`,`Number of take out places(City)`,`Obesity levels(Country)` and `Life expectancy(years) (Country)` are the strongest variables in determining the structure of the dataset. 

---

### 6. Data Driven Insights and Conclusion

From our EDA and Machine Learning, we are able to gain insights for our Data Science Question:

**Multi-Variate Analysis**
From our MultiVariate Analysis and exploring ways to reduce the overfitting, we found that using Lasso Regression allows us to tackle multicollinearity between predictors. This is essential as predictors may have high correlation with the response, but also with each other which would lead to overfitting of the model on the data.
By tackling this issue, we were able to create a model that captures the underlying relationship of the response and predictors and obtain a reliable model that is not overfitted, to possibly predict values of new data.

**Hierarchal Clustering** 
From our Second Data Science Question, for Countries that are looking to improve their `Happiness Levels` and `Life expectancy`, they should look to reduce `Pollution Index` and `Annual avg. hours worked` as they are the most important features in obtaining a healthy and happy City.

From the last Data Science Question, we see that Cities that are clustered based on `Monthly Gym Membership` ,`Number of take-out places (City`) and `Life expectancy (years) (Country)` have higher Happiness Levels, which are possible avenues for Countries to look at if they want to improve their Countries Happiness Levels.

---

### 7. Learning Insights 

* Exploring ways to tackle overfitting using KFolds
* Using Lasso Regression to handle multicolinearity between predictors 
* Choosing of a Clustering Technique that fufills our Data Science Question of finding similarities between data points.
* Using Random Forest for undertanding Feature Importance that determines how and why the Clusters formed are as such

---

### Contributers: 

1. Justin Tan https://github.com/tshjustin - Hierarchal Clustering
2. Jared Ng https://github.com/JaredNgwj - Linear Regression & Data Cleaning 
3. Dharinisri https://github.com/DhariniSa - Exploratory Data Analysis 


---
### 8. References 

1. https://www.yourdatateacher.com/2021/10/11/feature-selection-with-random-forest/

2. https://www.analyticsvidhya.com/blog/2017/06/a-comprehensive-guide-for-linear-ridge-and-lasso-regression/

3. https://statisticsbyjim.com/regression/multicollinearity-in-regression-analysis/

4. https://www.analyticssteps.com/blogs/what-hierarchical-clustering-machine-learning


