Build Recommendation Systems with IBM
Introduction
This projec is to build recommendations for articles on the IBM Watson Studio platform.

Three types of recommendation systems are explored in this project, including rank-based recommendations, user-user based collaborative filtering, and matrix factorization with Singular Value Decompositio(SVD).

Finally, by splitting the data into train and test sets, I was able to assess the accuracy of the recommendations with different number of latent features.

Installation
Python 3
NumPy, pandas, matplotlib.pyplot

File Description
Recommendations_with_IBM.ipynb
A Jupyter notebook containing Python scripts for this project.

Recommendations_with_IBM.html
A html copy of the Jupyter notebook.

Visuals
This folder contains some visuals from this project.

Some Visuals
Distribution of User-Article Interactions

Fig. 1. Distribution of user-article interactions in the original dataset.

Accuracy vs. Number of Latent Features

Fig. 2. Accuracy vs. number of latent features

Some Thoughts on Matrix Factorization
As the dataset used in this project doesn't contain missing values, I was able to use the SVD method to make recommendations. However, very often we get missing data in the dataset due various reasons. In these cases we won't be able to use SVD, as this methods doesn't work with missing values. Instead, FunkSVD will be a good alternative in such cases.

Further Thoughts on How to Test the Recommendations
There are various possible ways to determine if the recommendations we make are an improvement to how users find articles.

One possible way is an offline method, which evaluates if the recommendation systems have been an improvement by splitting the data into train and test sets and test how accurate our predictions are, as illustrated in Part V in this notebook.

Other possible ways may involve partly deployment of the recommendation systems, i.e. running the recommendation systems to only part of the users on the platform. Then we can use the principles of A/B testing to decide if our recommendation systems have improved how users find articles or not.

To decide if it has been an improvement, we need to decide on what metrices which we can direcly measure to reflect the improvement. For example, one possible evaluation metrice could be the click ratio i.e. number of clicks on the recommended articles by a user / number of recommended articles to a user.

On the other hand, one invariant metric could be the number of users on the platform per day. Running statistical tests on the control and experiment groups for these metrices should give us an idea if our recommendation systems have made an improvement.

In addition to statistical significance, a practical significance level should be decided by the decision makers and this should be met before a full deployment of the recommendation systems.
