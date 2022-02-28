# Product_Recommendation_in_Real_Time

A recommender system is a machine learning algorithm that predicts a user's future preferences for a set of offers personalized recommendations based on that prediction.It's similar to a firm salesperson who understands what a consumer could appreciate based on their past purchases and preferences. Every program you use on the internet records your behaviour, including how you interact with things, what you look for, who you communicate with, and so on. It won't be an exaggeration to suggest that, with the correct tool in hand, these applications will know you better than you know yourself. 

For Example, Facebook, utilizes your social media activity to enhance your newsfeed and determine which advertisements to show, YouTube uses its algorithms to choose which video to play next. They also serve as information filtering systems, removing extraneous content and allowing users to have a more tailored experience with whichever service they are using.

## Types of Recommender Systems
Different types of recommender systems and their use cases. There are primarily two techniques for building recommendation engines, the others are either extensions or hybrid recommender systems:

### 1) Content-Based Filtering
The fundamental concept is to provide suggestions based on a certain item. When creating a movie recommendation system, for example, you would take into account a user's preference for a movie using metrics like ratings, and then use item metadata like genre, director, movie description, cast, and crew, and so on to find movies that are similar to the ones that a user has enjoyed.

Instead than using user data, content-based recommendation systems focus on item traits or attributes. They can forecast a user's behaviour based on the objects they react to. Finding a decent movie to binge-watch over the weekend without having to do too much research is a typical challenge that millennials face nowadays. We can tackle this problem recommender systems machine learning for millennials by assisting them in finding a movie that they are most likely to appreciate through our initiative. A film might have a variety of qualities, such as a description, cast, crew, director, keywords, and so on. These characteristics aid in the discovery of parallels with other films.
![Recommendation+Engine+Python+Content+Based](https://user-images.githubusercontent.com/69427575/156031754-289839b0-a722-48fd-9a2d-b328e471defc.png)

### Benefits of Content-Based Recommender Systems
- In content-based filtering, the machine learning model makes suggestions without knowing anything about the user. It simply needs to know the user's interests, which makes scaling the model easy.

- It also doesn't have a "cold-start problem," because it recommends movies based on metadata rather than popularity.

### Limitations of Content-Based Recommender Systems
- We utilised a movie synopsis, genre, and keywords in this example. These hand-engineered elements determine the quality of the advice, which necessitates a fair deal of topic knowledge.
- The model has no method of recommending something to the user that is outside of their interests. It is unable to recognise tastes and make suggestions across genres.

### 2) Collaborative Filtering Recommender Systems
The movies advised using the first method aren't truly customised since content-based recommendation algorithms don't account for a user's unique preferences and prejudices. Because the suggestions are entirely based on a single item, two people with completely diverse interests will obtain the same results if they share one common interest.

Collaborative filtering recommender systems are another approach for dealing with these issues. The collaborative filtering approach is completely based on a user's previous choices and their involvement with an item. User preference is examined in two ways: overtly, where a user preference is noted in terms of clicks, views, hovering time, and so on; and implicitly, where a user preference is noted in terms of clicks, views, hovering time, and so on. To produce tailored suggestions, the collaborative filtering recommendation approach looks for users who are similar to the target user. Unlike content-based recommendation systems, collaborative filtering recommendation systems do not require item information. It generates fresh suggestions exclusively based on previous user-item interactions.

There are basically two types of collaborative filtering recommendation methods based on whether they assume there is an underlying model governing the data.

### 1) Memory-Based Collaborative Filtering
Also known as neighborhood-based filtering, this method stores previous interactions between a user and an object in a user-item interaction matrix. The recommendations are either based on the user or on the item.
![Memory+Based+Collaborative+Filtering](https://user-images.githubusercontent.com/69427575/156031798-dc41425d-fa81-4699-9dee-a5ad63ce9769.png)

#### A) User-Based Collaborative Filtering:
This approach seeks to locate comparable users, and it makes suggestions to a user based on what a similar user enjoyed. Cosine Similarity or Pearson Correlation are used to determine how similar users are. However, one of the major drawbacks of user-based filtering is that user preferences might vary over time, necessitating constant updates to these computations.calculating the similarity between items isn’t as straightforward as calculating the similarity between users. 
The similarity between users can be calculated as -
![Cosine+Similarity+Dot+Product+of+Vectors](https://user-images.githubusercontent.com/69427575/156031854-3eb9122e-adfe-4bae-b16a-21b2a4653558.png)

![Calculating+Similarity](https://user-images.githubusercontent.com/69427575/156031942-63361d4d-1ef5-49f9-93a3-a8855d8e6031.png)
The formula makes a lot more sense now. Item-based filtering avoids the dynamic preference problem posed by user-based filtering.

#### B) Item Based Collaborative Filtering
In this type, new items are recommended to users based on their similarity with the items that the user has rated- highly in the past.

### Limitations of Memory-Based Collaborative Filtering Recommendation Method
- Memory-based filtering techniques are difficult to scale; even with 24K unique users, it took a long time to discover users that were similar to a single user.
- Memory-based collaborative filtering is nearly impracticable when dealing with large datasets.
- This method also suffers from the "cold-start" problem, making it difficult to obtain suggestions for new users or to suggest new goods.

### 2) Model-Based Collaborative Filtering Recommender System
Because the user-item interaction matrix is sparse, like in the memory-based recommender system, we may condense or compress it into two matrices using a model to make it more efficient. Using Matrix Factorization Techniques for Recommender Systems, the large sparse item matrix is divided into two smaller dense matrices: a user-factor matrix with user representations and an item-factor matrix with item representations.

The above-mentioned factor is only a latent factor that captures the similarity between users and products. A latent factor is a trait or notion that a user or an item may possess. A latent component may be used to indicate the genre of a movie in a dataset. Matrix Factorization may be done using a variety of techniques, including Singular Value Decomposition (SVD), Principal Component Analysis (PCA), and Non-Negative Matrix Factorization (NMF).
![Matrix+Factorization+for+Recommender+Systems](https://user-images.githubusercontent.com/69427575/156032053-d3a86c63-9e71-42cd-b429-32d510e17dca.png)

For matrix factorization of the recommender system, the SVD technique was utilised. The recommendation model is transformed into an optimization problem, and measures like Root Mean Squared Error are used to assess how well we are at predicting a user's rating of an item (RMSE). SVD uses latent variables to reduce the dimensions of our user-item interaction matrix. Users and things are mapped in a latent space with dimension d, which helps us better comprehend their connection.

There may be valuable characteristics in the data, such as a User X who is a girl and a teen who enjoys comedies and female-oriented films. The Princess Diaries is a wonderful choice since it is hilarious and female-oriented. We do not, however, hand-code these characteristics; instead, we let the model to uncover these underlying representations of user preferences and item properties.
![Collaborative+Filtering+Python](https://user-images.githubusercontent.com/69427575/156032020-332b37a7-e109-497f-8c8d-3e3f8f31b9ff.png)

### Advantages of Memory-Based Collaborative Filtering Recommender Systems
- They're simple to grow and can handle extremely massive datasets.
- If the data on which we trained is representative of the overall population, overfitting may be avoided.
- Because you simply query the model, not the entire dataset, the prediction speed is substantially faster than memory-based models.

### Disadvantages of Memory-Based Collaborative Filtering Recommender Systems
- The accuracy of forecasts is solely determined by the model used to make them.
- It's not particularly user-friendly, especially when using Deep Learning models.
