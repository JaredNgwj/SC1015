# SC1015
Regarding Analysis of the Heirachy Algorithm

1. In the code above , i used an analysis called RFM - which is often used in marketing and buisness since they are common and good metrics for customer prediction. 

This may change for different data set .


2. I also used this feature called scaling. Which is the Scaler = StandardScaler(). This sort of brings the features to a similar scale to prevent one feature from
being more dominant than another. 

For example like 

Age : 20 30 40 50 
Income : 5000 6000 7000 8000 

So the range for age and income are different and income is much higher than age. So scaling would make the mean = 0 , SD = 1. Maybe can do this to improve model 
performance. But can also use k means 


3. Regarding the dendrogram, can read as :  

there are 2 types - Top down to bottom up. In this case i used top down , so staart from 1 single cluster containing all the data points then split to 
2 - 4 - 6 -. .. . and would stop depending on the depth inputted which is 20 in this case. 

Each split is not randon but instead based on how simialr the features are in each datapoint. In this case look at time of sale, amount spent etc. 

Optimally, the leaf nodes should just be a single data point but since there are 500k data points and depth = 20 , would not get pure leaf nodes.
