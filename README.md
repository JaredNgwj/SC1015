# SC1015: Data Science Mini Project - Determining Happiness and Healthiness of Countries
School of Computer Science and Engineering \
Lab: A121 \
Group : 2

Members: 
1. Justin Tan https://github.com/tshjustin - Clustering
2. Jared Ng https://github.com/JaredNgwj - Linear Regression
3. Dharinisri https://github.com/DhariniSa - EDA

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

**Data Set** : 

**Our Questions** : 
1. How can we predict the Happiness Level of a City given several of it's Health metrics? 
2. What determines if a City is both Happy and Healthy?
3. Can we identify underlying patterns or relationships among cities based on their health-related metrics?

**Rationale of Questions** : We believe that Health and Happiness are the most important factors in everyone. They are the factors in determining the quality of life that each indivdual experiences. Hence, we want to explore how are we able to achieve a Happy and Healthy Country and bring the best quality of life to everyone.

--- 

### 2. Data Preparation and Cleaning

We cleaned the data and prepared them for our Exploratory Data Analysis & Machine Learning Model of choice. This includes filling in of NULL values with the appropriate values and removal of Characters that may interfere with the analysis. 

---


### 3. Exploratory Data Analysis

We then explore each variable to identify any pattern they may have with our Problem Forumulation or with each other. We also kept an eye out for anomalies that may affect our Machine Learning. 

We used the visual aids of the Box Plots, Histogram, Violin, HeatMap and Scatterplots to understand the relatinoship the variables have with each other. 

--- 

### 4. Multi-Variate Analysis

Now that we have done EDA, we picked the 4 best variables using `KBest` to obtain strong predictors for our Multi-Variate Analysis for our First Data Science Question. 

We then obtained a Explained Variance of `0.8755` for the model on the Train Data Set and `0.5808` on the Test Data. This was a case of overfitting, and so we explored 2 ways to reduce the overfitting.


Firstly, we used `KFolds` methods to divide the dataset into k equally sized "folds" or subsets, and then train and evaluate the model k times. Given a small dataset sample size, using a traditional train-test split could lead to insufficient data for training, which might affect the model's performance. K-fold cross-validation helps to maximize the use of the available data by iteratively using different parts of the data for training and validation, ensuring that every sample is used for both training and validation at some point.

After folding, we found that the Explained Variance on the test was improved to `0.7700`. 

Secondly, we also used Lasso Model to reduce overfitting. Lasso can handle multicollinearity among the predictor variables effectively. In our case where some features are highly correlated, Lasso can select one of them while shrinking the others' coefficients to zero, reducing the model complexity and improves the interpretability of the model.

After using Lasso, the Explained Variance on the test improved to `0.7952`.

---

### 5. Hierachal Clustering 

For the next 2 Data Science Question ,we then performed clustering. We chose  **Hierachal Clustering** as 

1. It gave us a powerful visualisation aid in terms of looking for similarites between Clusters of cities, which is the main goal of our question.
2. Cities that are anomalies would be easily seen from the dendrogram, as they are most dissimilar and result in high vertical distance. 

For the Second Question, we found the optimal clusters of `4` and analysed the characteristics of each cluster to find the greatest contributers to a Happy and Healthy City. 

We found that `Pollution Levels` and `Annual avg. Working Hours` contributes to the happiest and healthiest Countries.


For the third Question, we found the optimal clusters of `2` and analysed the characteristic. To generate more insights, we used a modification of the Random Forest Machine Learning Model to determine the importance of each variable. This allows us to determine the variables that structure the clusters as such. This picks out the underlying relationship between the variables. 

We found that  `Cost of a monthly gym membership(City)`,`Number of take out places(City)`,`Obesity levels(Country)` and `Life expectancy(years) (Country)` are the strongest variables in determining the structure of the dataset. 

---

### 6. Data Driven Insights and Conclusion

From our EDA and Machine Learning, we are able to gain insights for our Data Science Question:

From our MultiVariate Analysis, we found that `Cost of a bottle of water(City)` , `Obesity levels(Country)`, `Life expectancy(years) (Country)`, `Pollution(Index score) (City)` to be good predictors, which would allow countries to predict Happiness Levels of their countries.
Furthermore, after exploring ways to reduce the overfitting, we found that using Lasso Regression allows us to obtain a higher Explained Variance at the cost of slightly higher Mean Square Error. This means that we were able to capture more noise in the Data but perform slighly worse in the predicting the actual values.

This means that it was better than our original model, as it was able to reduce the overfitting by a larger margin and keeping the loss in predicting low!

From our Second Data Science Question, for Countries that are looking to improve their `Happiness Levels` and `Life expectancy(years) (Country)`, they should look to reduce `Pollution Index` and `Annual avg. hours worked` as they are important features in determining if a City is healthy and happy.

From the last Data Science Question, we see that Cities that are clustered based on `Monthly Gym Membership` ,`Number of take-out places (City`) and `Life expectancy (years) (Country)` have higher Happiness Levels, which are possible avenues for Countries to look at if they want to improve their Countries Happiness Levels.
Conclusion of Clustering:

Cost of a `monthly gym membership(City)` ,`Number of take out places(City)` ,`Obesity levels(Country)` and `Life expectancy(years) (Country)` are the most important factors in determining if the structure in the Data.

It differs from the variables of MultiVariate analysis as it assumes linearity between the features and the target variable. Whereas for Clustering with the use of Random Forest to determine Variable Importance, it can capture complex, non-linear relationships between features and the target variable, which is the primary goal of the Second and Third Data Science Question to capture the overall relationship.

---

### 7. Learning Insights 

During this project, we learnt about what overfitting was and how it could impact our model performance. We also learnt about methods, such as `KFolds and Lasso`, and how to utilize these methods to overcome our overfitting problem.

We learnt how to use `Silhouette score and Hierarchical Clustering model` to help us answer our data science questions and provide better analysis with the use of these methods.

---

### 8. References 

1. https://www.yourdatateacher.com/2021/10/11/feature-selection-with-random-forest/

2. https://www.analyticsvidhya.com/blog/2017/06/a-comprehensive-guide-for-linear-ridge-and-lasso-regression/

3. https://statisticsbyjim.com/regression/multicollinearity-in-regression-analysis/

4. https://www.analyticssteps.com/blogs/what-hierarchical-clustering-machine-learning
