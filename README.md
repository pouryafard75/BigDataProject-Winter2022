# BigDataProject-Winter2022

## Project Name: Amazon Item Recommendation System

| Name                  | StudentID |  
|-----------------------|:---------:|
| Pouria Alikhanifard   | 40220990  | 
| Mohammod Suhel Firdus | 40163582  |  
| Gwladys Djuikom       | 40239239  |
| Dmytro Chychkov       | 40034351  | 


### Abstract:
The Amazon Item Recommendation System collects preferences and taste information from Amazon shoppers and employs different collaborative filtering algorithms 
to find users with similar interests. It then uses this information to make automatic item predictions tailored to the user's taste.

### Dataset of interest: 
Amazon Review Data (2018) which is available [here](https://nijianmo.github.io/amazon/index.html).

### Dataset description:
The dataset contains over 230 million reviews across all item categories 
It consists of two subsets for each product category: <br> 

(1) Product reviews: <br>

reviewerID - ID of the reviewer, e.g. A2SUAM1J3GNN3B <br>
asin - ID of the product, e.g. 0000013714 <br>
reviewerName - name of the reviewer <br>
vote - helpful votes of the review (1 to 5) <br>
style - a dictionary of the product metadata, e.g., "Format" is "Hardcover" <br>
reviewText - text of the review <br> 
overall - rating of the product <br>
unixReviewTime - time of the review (unix time) <br>
reviewTime - time of the review (raw) <br>

(2) Product metadata:

asin( ID of the product e.g. 0000031852), <br>
title,<br>
feature,<br>
description,<br>
price,<br>
imageURL,<br>
related products,<br>
salesRank,<br>
brand,<br>
category

### Methods: 
User-user collaborative filtering or Item-item filtering <br>
Item-item is more straightforward while user-user can help us create a user profile across multiple categories.

Frameworks and Libraries to use:

[Spark](https://spark.apache.org/docs/latest/api/python/)

[Recmetrics library for MAP@K](https://github.com/statisticianinstilettos/recmetrics)

[Matplotlib](https://matplotlib.org/) (for visualisation)

[Pandas](https://pandas.pydata.org)/[Numpy](https://numpy.org/) (as well visualization)

### Approach:
We'll build a Utility Matrix by crossreferencing the two datasets described above to link reviews to their corresponding items.<br>
We'll then extrapolate unknown ratings from the known ones focusing on users' likes over what users don't like.<br>
In other words we'll employ a Collaborative Filtering system to find users with similar tastes and ratings and use this information to recomend them new items to purchase based on their review history, taking into account the global average of all ratings in the dataset and rating deviation of users and items.<br> 

Employed techniques include but are not limited to: <br>
Collaborative Filtering Using k-Nearest Neighbors (**KNN**) <br>
Cosine similarity(for object similarity) <br>
Alternating Least Square (**ALS**) <br>
Matrix Factorization (unsupervised) <br>

Prototype using a subsample of data - start with Cellphone & Accessories before increasing the scope.

| UserID<br/>ProductId |  1  |  2  |  3  | ... |
|----------------------|:---:|:---:|:---:|:---:|
| 1                    | 4.5 |  3  | NaN | ... |
| 2                    | 1.5 |  NaN  |  3  | ... |
| 3                    |  NaN  |  2  |  5  | ... |
| 4                    |  1  |  2  | NaN | ... |
| ...                  | ... | ... | ... | ... |

### Evaluation: 
To measure the performance of our recommendation methods we plan to use <b>Root-mean-square-error (RMSE)</b> and <b>Mean Average Precision at K (MAP@K)</b> techniques applied to a masked portion of the matrix.

### Research questions: 


 


