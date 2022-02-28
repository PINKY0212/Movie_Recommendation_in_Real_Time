# Product_Recommendation_in_Real_Time

A recommender system is a machine learning algorithm that predicts a user's future preferences for a set of offers personalized recommendations based on that prediction.It's similar to a firm salesperson who understands what a consumer could appreciate based on their past purchases and preferences. Every program you use on the internet records your behaviour, including how you interact with things, what you look for, who you communicate with, and so on. It won't be an exaggeration to suggest that, with the correct tool in hand, these applications will know you better than you know yourself. 

For Example, Facebook, utilizes your social media activity to enhance your newsfeed and determine which advertisements to show, YouTube uses its algorithms to choose which video to play next. They also serve as information filtering systems, removing extraneous content and allowing users to have a more tailored experience with whichever service they are using.

## Types of Recommender Systems
Different types of recommender systems and their use cases. There are primarily two techniques for building recommendation engines, the others are either extensions or hybrid recommender systems:

### 1) Content-Based Filtering
The main idea here is to suggest items based on a particular item. For example, when you are building a movie recommendation system, it would take into account a user’s preference for a movie using metrics such as ratings and then use item metadata, such as genre, director, description of the movie, cast, and crew, etc to find movies similar to the ones that a user has liked.

Content-based recommendation systems work more closely with item features or attributes rather than user data. They predict the behavior of a user based on the items they react to. A classic problem that millennials have today is finding a good movie to binge-watch over the weekend without having to do too much research. Through this project we can solve this problem recommender systems machine learning for millennials by helping them find a movie that they are most likely to enjoy.A movie can have various attributes like description, cast, crew, director, keywords, etc. These attributes help in finding similarities with other movies.

### Benefits of Content-Based Recommender Systems
- In content-based filtering, the machine learning model needs no information about the user to make recommendations. It only needs to know the interests of the user which makes it easier to scale the model.

- It also does not have a “cold-start problem”, since it recommends movies based on their metadata and would not weigh them according to their popularity.

### Limitations of Content-Based Recommender Systems
- In this example, we used movie overview, genre, and keywords. The quality of the recommendation is dependent on these hand-engineered features and thus requires a good amount of domain knowledge.
- The model has absolutely no way to recommend the user something outside their range of interests. It is not capable of capturing tastes and generating recommendations across genres.

### 2) Collaborative Filtering Recommender Systems
The movies recommended using the first approach are not really personalized in the sense that content-based recommendation engines do not capture the personal tastes and biases of a user. The recommendations are totally based on a particular item, two users with very different tastes except for one common item of interest will get the same results.

To deal with these problems, another method is collaborative filtering recommender systems. The collaborative filtering technique depends solely on the historical preferences of a user and the interaction between a user and an item. User preference is studied in two ways:  explicitly- this is the rating or feedback given to an item by the user explicitly, implicitly wherein a user preference is noted in terms of clicks, views, hovering time, etc.The collaborative filtering recommendation technique depends on finding similar users to a target user to make personalized recommendations. Collaborative filtering recommen,der systems do not require item metadata like content-based recommendation systems. It relies solely on past user-item interactions to render new recommendations.

There are basically two types of collaborative filtering recommendation methods based on whether they assume there is an underlying model governing the data.

### 1) Memory-Based Collaborative Filtering
Also known as neighborhood-based filtering in which past interactions between a user and item are stored in user-items interaction matrix. The recommendations are made either in a user-based or item-based fashion.


#### A) User-Based Collaborative Filtering:
This method aims at finding similar users and recommendations are made to a user based on what a similar user has liked. The similarity between users is calculated using either Cosine Similarity or Pearson Correlation. But one of the main disadvantages of user-based filtering is user preferences can change over time, therefore these calculations have to be updated regularly.


#### B) Item Based Collaborative Filtering
In this type, new items are recommended to users based on their similarity with the items that the user has rated- highly in the past.

### Limitations of Memory-Based Collaborative Filtering Recommendation Method
- Memory-based filtering systems do not scale easily, even with 24K distinct users it took a while to find similar users to a single user.
- When using huge datasets, the memory-based collaborative filtering technique is close to impractical.
- This technique also has the “cold-start” problem, it’s hard to get recommendations for new users or recommend new products.

### 2) Model-Based Collaborative Filtering Recommender System
As in the memory-based recommender system, the user-item interaction matrix is very sparse, to use it more efficiently we can reduce or compress the user-items interaction matrix into two matrices using a model.  The huge sparse item matrix is decomposed into two smaller dense matrices- a user-factor matrix that has user representations and an item-factor matrix that has item representation using Matrix Factorization Techniques for Recommender Systems.


The factor that I have mentioned above is nothing but a latent factor that captures the similarity between users and items. A latent factor can represent a property or concept that a user or an item might have. For a movie’s dataset, latent factor can represent the genre the movie belongs to. There are many algorithms for Matrix Factorization like Singular Value Decomposition(SVD), Principal Component Analysis(PCA), and Non-Negative Matrix Factorization(NMF).

Here used the SVD algorithm for matrix factorization of the recommender system. The recommendation model is turned into an optimization problem and measured how good we are in predicting the ratings of an item for a user by metrics like Root Mean Squared Error(RMSE).  SVD  decreases the dimensions of our user-items interaction matrix by using latent factors. We map users and items in a latent space with dimension d, which in turn helps us better understand the relationship between them. 

There can be useful features in the data like a User X who is a girl and a teenager who likes funny and female-oriented movies. The Princess Diaries is funny and female-oriented and would be a good recommendation. However, we do not hand engineer these features, we let the model discover these hidden representations of user interests and item attributes.

### Advantages of Memory-Based Collaborative Filtering Recommender Systems
- They are easy to scale and can be used to work on super large datasets.
- Overfitting can be avoided if the data on which we have trained is representative of the general population.
- The prediction speed is much faster than memory-based models- since you only query the model, not the whole dataset.

### Disadvantages of Memory-Based Collaborative Filtering Recommender Systems
- The quality of predictions is solely dependent on the quality of the model built.
- It is not very intuitive especially if you use Deep Learning models.
