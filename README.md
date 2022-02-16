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
Amazon Review Data (2018) available [here](https://nijianmo.github.io/amazon/index.html).

### Dataset description:
The dataset contains over 230 million reviews across all item categories 
It consists of two subsets for each product category: <br> 

(1) Product reviews(includes ratings, text and helpfulness votes) which contains: <br>

reviewerID - ID of the reviewer, e.g. A2SUAM1J3GNN3B <br>
asin - ID of the product, e.g. 0000013714 <br>
reviewerName - name of the reviewer <br>
vote - helpful votes of the review (1 to 5) <br>
style - a dictionary of the product metadata, e.g., "Format" is "Hardcover" <br>
reviewText - text of the review <br> 
overall - rating of the product <br>
unixReviewTime - time of the review (unix time) <br>
reviewTime - time of the review (raw) <br>

(2) Product metadata which contains additional information about each product including

asin( ID of the product e.g. 0000031852), 
title,
feature,
description,
price,
imageURL,
related products,
salesRank,
brand,
categories, ...

<b> However the main focus of this research is on the <i> vote </i> in Product reviews. </b> 

In other words, we have the following sparse matrix:

| UserID<br/>ProductId |  1  |  2  |  3  | ... |
|----------------------|:---:|:---:|:---:|:---:|
| 1                    | 4.5 |  3  | NaN | ... |
| 2                    | 1.5 |  NaN  |  3  | ... |
| 3                    |  NaN  |  2  |  5  | ... |
| 4                    |  1  |  2  | NaN | ... |
| ...                  | ... | ... | ... | ... |

and we aim to predict the <i>NaN</i> values in order to build the recommendation system.

### Methods: 
User-user or item-item <br>
Item-item is more straightforward while user-user can help us create a user profile across multiple categories

Frameworks and Libraries to use:

[Spark](https://spark.apache.org/docs/latest/api/python/)
Recmetrics library for MAP@K

[Matplotlib](https://matplotlib.org/) (for visualisation)

[Pandas](https://pandas.pydata.org)/[Numpy](https://numpy.org/) (as well visualization)

### Approach:
We employ a Collaborative Filtering system to build a model of user’s behavior and use it to predict user’s interests. 
Employed techniques: <br>
Collaborative Filtering Using k-Nearest Neighbors (**KNN**) <br>
Cosine similarity(for object similarity) <br>
Alternating Least Square (**ALS**) <br>
Matrix Factorization (unsupervised) <br>
Clustering

Prototype using subsample of data - start with Cellphone & Accessories before increasing the scope

Evaluation: 
Precision of the predictions:

Root-mean-square-error (RMSE) 
Mean Average Precision at K (MAP@K) //standard
Masking Matrix
