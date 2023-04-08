# SC1015: Data Science Mini Project - What are the structures in countries? 

School of Computer Science and Engineering \
Lab: A121 \
Group : 2

Members: 
1. Justin Tan //Add Gitmail 
2. 
3. 

--- 

### Description : 

This repository contains the main Jupyter Notebook of our Project, DataSet, video presentations and references for our Mini-Project 

Below is a short description of the overall project. The detailed analysis is found within the main Jupyter Notebook. All details are done in one single Jupyter Notebook.

---

### Flow of Content

1. Problem Formulation
2. Data Preparation and Cleaning
3. Exploratory Data Analysis
4. Multi-Variate Analysis
5. Hierachal Clustering
6. Data Driven Insights and Conclusion
7. References

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

We used the visual aids of the Box Plots, Histogram, Vionlin , HeatMap and Scatterplots to understand the relatinoship the variables have with each other. 

--- 

### 4. Multi-Variate Analysis

Now that we have done EDA, we picked the 4 best variables using `KBest` to obtain strong predictors for our Multi-Variate Analysis. 

We then obtained a Explained Variance of `0.8755` for the model on the Train Data Set and `0.5808` on the Test Data. This was a case of overfitting, and so we explored 2 ways to reduce the overfitting.


Firstly, we used `KFolds` methods to divide the dataset into k equally sized "folds" or subsets, and then train and evaluate the model k times. Given a small dataset sample size, using a traditional train-test split could lead to insufficient data for training, which might affect the model's performance. K-fold cross-validation helps to maximize the use of the available data by iteratively using different parts of the data for training and validation, ensuring that every sample is used for both training and validation at some point.

After folding, we found that the Explained Variance on the test was improved to `0.7700`. 

Secondly, we also used Lasso Model to reduce overfitting. Lasso can handle multicollinearity among the predictor variables effectively. In our case where some features are highly correlated, Lasso can select one of them while shrinking the others' coefficients to zero, reducing the model complexity and improves the interpretability of the model.

After using Lasso, the Explained Variance on the test improved to `0.7952`.




