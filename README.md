**Objective:** Segment customers based on their purchasing behavior using clustering algorithms to identify distinct customer groups.

**Dataset:** You can use the Mall Customer Segmentation Data from Kaggle or a similar dataset.

```
RangeIndex: 200 entries, 0 to 199
Data columns (total 5 columns):
 #   Column                  Non-Null Count  Dtype
---  ------                  --------------  -----
 0   CustomerID              200 non-null    int64
 1   Gender                  200 non-null    object
 2   Age                     200 non-null    int64
 3   Annual Income (k$)      200 non-null    int64
 4   Spending Score (1-100)  200 non-null    int64
dtypes: int64(4), object(1)
memory usage: 7.9+ KB
None
```

This is the result when showing the information about the data, here we can see that we have 5 columns in which 4 of them are integers and 1 is object.

```
       CustomerID         Age  Annual Income (k$)  Spending Score (1-100)
count  200.000000  200.000000          200.000000              200.000000
mean   100.500000   38.850000           60.560000               50.200000
std     57.879185   13.969007           26.264721               25.823522
min      1.000000   18.000000           15.000000                1.000000
25%     50.750000   28.750000           41.500000               34.750000
50%    100.500000   36.000000           61.500000               50.000000
75%    150.250000   49.000000           78.000000               73.000000
max    200.000000   70.000000          137.000000               99.000000
```

Here is the description of the dataset:

**1. Customer ID**
We have 200 unique values that represent the 200 different customers

**2. Age**
The average age is 38.85 years old

Youngest customer: 18 years old
Oldest customer: 70 years old 

25% (Q1): Customers are younger than 28.75 years old
50%(Q2): Customers are younger than 36 years old
75% (Q3): Customers are younger than 49 years old

Standard deviation: 13.96 years 

**3. Annual Income (K$)**
The average Annual Income (k$) is 60.56 K

The minimum annual income: 15 K
The maximum annual income: 137 K

25%(Q1): Annual Income is lower than 41.5 K
50%(Q2):Annual Income is lower than 61.5 K
75%(Q3): Annual Income is lower than 78 K

Standard deviation: 26.26 K 

**4.Spending Score (1-100)**
The average score is 50 points

The lowest spending score is: 1 point
The maximum spending score is: 99 points 

25%(Q1): Customers scored under 34.75 points
50%(Q2): Customers scored under 50 points
75%(Q3): Customers scored under 73 points

```
CustomerID                0
Gender                    0
Age                       0
Annual Income (k$)        0
Spending Score (1-100)    0
dtype: int64
```

**Age:** This graph is right-skewed which mean that there are more customers are younger
**Annual Income:** This graph is right-skewed which means that more customer have lower income
**Spending Score:** This graph is normal distributed, meaning most customers have average spending behavior.

***Age vs Annual Income:*** This shows that the older the costumer the more income they have.

***Age vs Spending Score :*** This has no visible trend but it show that younger costumers have higher spending scores and older customers have lower spending scores. This shows the behavior of the customers

***Annual Income vs Spending Score:*** This has 5 clusters which probably show 5 segments of customers meaning
1. Low income may be correlated to low spending score
2. Low income may show correlation with high spending score
3. Average income can be correlated with average spending score
4. High income can be correlated to low spending score
5. High income can be correlated to high spending score 

***Age:*** has a strong negative relationship with spending score meaning age might not be a significant factor in spending behavior.

The conclusion is that to have a more granular result of the data K=5 will be a better option.

**For 𝑘=5*k*=5:**

- **Cluster 0:** High annual income, high spending score.
- **Cluster 1:** Low annual income, low spending score.
- **Cluster 2:** Moderate annual income, moderate spending score.
- **Cluster 3:** High annual income, low spending score.
- **Cluster 4:** Low annual income, high spending score.
- **Segmented Marketing Strategies:** Different marketing strategies can be tailored for each cluster.

**Cluster 0:** Marketing should target to offer premium products
    
    **Cluster 1:** Add different promotions to increase spending score
    
    **Cluster 2:** Focus on delivering products that can be constantly purchased 
    
    **Cluster 3:** Marketing should give premium quality products 
    
    **Cluster 4:** Add different benefits when you buy more
    
- **Resource Allocation:** Resources can be allocated more efficiently by focusing marketing efforts on high-potential clusters.
- **Customer Retention:** Understanding the characteristics of each cluster helps in designing retention strategies for low-spending but high-income customers.
