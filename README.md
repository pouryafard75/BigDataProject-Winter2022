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

(1) Product reviews(includes ratings, text and helpfulness votes) <br>
reviewerID - ID of the reviewer, e.g. A2SUAM1J3GNN3B <br>
asin - ID of the product, e.g. 0000013714 <br>
reviewerName - name of the reviewer <br>
vote - helpful votes of the review (1 to 5) <br>
style - a dictionary of the product metadata, e.g., "Format" is "Hardcover" <br>
reviewText - text of the review <br> 
overall - rating of the product <br>
unixReviewTime - time of the review (unix time) <br>
reviewTime - time of the review (raw) <br>

(2) Product metadata - includes ASIN, descriptions, category information, price,					 brand, and image features

asin - ID of the product, e.g. 0000031852
title - name of the product
feature - bullet-point format features of the product
description - description of the product
price - price in US dollars (at time of crawl)
imageURL - url of the product image
imageURL - url of the high resolution product image
related - related products (also bought, also viewed, bought together, buy after viewing)
salesRank - sales rank information
brand - brand name
categories - list of categories the product belongs to
tech1 - the first technical detail table of the product
tech2 - the second technical detail table of the product
similar - similar product table
Model: We chose Collaborative Filtering as it works for any kind of item and relies only on 	the utility matrix. 

### Methods: User-user or item-item //item-item is more straightforward while user-user can help us create a user profile across multiple categories

Frameworks and Libraries to use:

[Spark](https://spark.apache.org/docs/latest/api/python/)
Recmetrics library for MAP@K

[Matplotlib](https://matplotlib.org/) (for visualisation)

[Pandas](https://pandas.pydata.org)/[Numpy](https://numpy.org/) (as well visualization)

### Approach:
We employ a Collaborative Filtering system to build a model of user’s behavior and use it to predict user’s interests. Employed techniques:
Clustering
Collaborative Filtering Using k-Nearest Neighbors (KNN)
Cosine similarity(for object similarity)
Alternating Least Square (ALS)
Matrix Factorization (unsupervised)

Prototype using subsample of data - start with Cellphone & Accessories before increasing the scope

Evaluation: //precision
Mean Average Precision at K (MAP@K) //standard
Masking Matrix
Root-mean-square-error (RMSE) //