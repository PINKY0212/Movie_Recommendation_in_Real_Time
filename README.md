# Product_Recommendation_in_Real_Time

A Recommender System is a machine learning algorithm that predicts a user's future preferences for a set of offers personalized recommendations based on that prediction.It's similar to a firm salesperson who understands what a consumer could appreciate based on their past purchases and preferences. Every program you use on the internet records your behaviour, including how you interact with things, what you look for, who you communicate with, and so on.

It won't be an exaggeration to suggest that, with the correct tool in hand, these applications will know you better than you know yourself. Netflix, for example, utilizes algorithms that filter content based on each individual user profile and determine which shows/movies you may like, YouTube uses its algorithms to choose which video to play next.In this project I have created a Movie Recommender system based on different Filtering.

## Types of Recommender Systems
There are primarily two techniques for building recommendation engines, the others are either extensions or hybrid recommender systems: 1. Content-Based Filtering & 2. Collaborative Filtering Recommender.Using the Sample Data from Microsoft Machine Learning Studio(classic), I have trained, scored and evaluated the dataset from Matchbox Recommender Module created 6 different metrics to create a list of movie recommendations for each user depending upon the movie titles and rating.Below is the Screenshot of Azure Pipelines created for 6 types of recommendation metrics.

![ss1](https://user-images.githubusercontent.com/69427575/157966569-f473b7b6-1286-4460-b174-abb70830307c.PNG)

The Six Types of metric performed in this project are:

Sno.     Recommendation kind Prediction          Recommended Item Selection              Recommendation System Type
1        Item Recommendation                     From Rated Items                        Collaborative User Based Filtering
2        Related Items                           From Rated Items                        Matrix Factorization on Item-factor
3        Rating Prediction                       User-Item Based                         Rating Prediction           
4        Related Users                           From Users that Rated Items             Matrix Factorization on User-factor
5        Item Recommendation                     From All Items                          Content Based Filtering
6        Related Items                           From All Items                          Collaborative Item Based Filtering

To evaluate the accuracy of the predictions the Evaluate Recommender module compares the predictions of a recommendation model with the corresponding “ground truth” data by computing the average normalized discounted cumulative gain (NDCG) for each model.The training data is approximately 225,000 ratings for 15,742 movies by 26,770 users.This project utilizes collaborative and content-based filtering and matrix factorization to create a Movie Recommendation System.Now, the ellaboration about different filtering and Azure Webservice is created for two metrics listed above.

### 1) Content-Based Filtering
The fundamental concept of this filtering is to provide suggestions based on a user. When creating a movie recommendation system, for example, you would take into account a user's preference for a movie using metrics like ratings, and then use item metadata like genre, director, movie description, cast, and crew, and so on to find movies that are similar to the ones that a user has enjoyed.

In this Content-Based Filtering based on related items approach performed best.This is the Azure Pipeline specifically for Content-Based Recommendation System considering all items for recommendation available in data in commom with the query user and related user. Further, I have created a Azure AI WebService for this type of recommendation. 

![ss2](https://user-images.githubusercontent.com/69427575/157967136-407fe3fd-d715-404b-a3be-80037f1dfc04.PNG)

Before creating a new service, Testing of webservice is all done by manual input and the results are shown:

![ss3](https://user-images.githubusercontent.com/69427575/157967160-402a0abf-08b7-43d5-81cc-1d5407158f7b.PNG)

Once, the webserice is deployed, we get Test Preview of the service and then by creating New Web Service Experiencce we get request-response and APIKey to use this web service into Azure Machine Learning in Excel.Also tested the sample data after creation of Webservice.

![ss4](https://user-images.githubusercontent.com/69427575/157967537-31f72857-4d3d-4e66-ab8f-14a62adf68cd.PNG)

![ss5](https://user-images.githubusercontent.com/69427575/157967575-ee143cec-7436-4629-a366-3299adf64de4.PNG)

Also checked this Webservice on Microsoft Excel - Azure Machine Learning, output is shown on:

I have also publised this Web Service into Azure AI gallery.The gallery link is:
https://gallery.cortanaintelligence.com/Experiment/Movie-Recommendation-Using-Content-Based-Filtering-System

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
This approach seeks to locate comparable users, and it makes suggestions to a user based on what a similar user enjoyed. Cosine Similarity or Pearson Correlation are used to determine how similar users are. However, one of the major drawbacks of user-based filtering is that user preferences might vary over time, necessitating constant updates to these computations.calculating the similarity between items isn’t as straightforward as calculating the similarity between users.For this approach I have used Item Recommendation type as kind of prediction and recommendation item selection is done from Rated Items in the Score Matchbox of the Recommender Module.The output of these specifications is shown.

![2022-03-12 (7)](https://user-images.githubusercontent.com/69427575/158027853-23dde623-8828-409e-a1f5-f23348e5c8e1.png)

#### B) Item Based Collaborative Filtering
In this type, new items are recommended to users based on their similarity with the items that the user has watched/watching now. In this Item-Based filtering based on related items performed as kind of prediction and recommendation item selection is done from All Items in the Score Matchbox of the Recommender Module.This is the Azure Pipeline specifically for Collaborative-Based Recommendation System by Item Based Approach using related items with users. And Further i Have created a Azure AI WebService for this type of recommendation. 

![ss6](https://user-images.githubusercontent.com/69427575/157967997-d5b88a58-db00-4d8b-90d5-07ca0600f74f.PNG)

![ss8](https://user-images.githubusercontent.com/69427575/157968163-7ca71bf4-34e9-45d8-bfe9-8a58fc2c3ff5.PNG)

Before creating a new service, Testing of WebService is all done by manual input and the results are shown:

![ss7](https://user-images.githubusercontent.com/69427575/157968077-eac57f08-2a6d-4d65-ad98-3675bc2efa27.PNG)


Once, the WebSerice is deployed, we get Test Preview of the service and then by creating New Web Service Experiencce we get Request-Response and APIKey to use this Web Service into Azure Machine Learning Excel ss a Product.Also tested the sample data after creation of Webservice.

![ss9](https://user-images.githubusercontent.com/69427575/157968279-8ffbdf3c-449a-425f-9a6d-78a735cf978d.PNG)

![ss10](https://user-images.githubusercontent.com/69427575/157968353-6ec64cd1-8189-41ad-a99d-f33340beaf78.PNG)

Also checked this Webservice on Microsoft Excel- Azure Machine Learning, output is shown on:

I have also publised this Web Service into Azure AI gallery.The gallery link is:
https://gallery.cortanaintelligence.com/Experiment/Movie-Recommendation-Using-Collaborative-Filtering-System-Items-Approach

### Limitations of Memory-Based Collaborative Filtering Recommendation Method
- Memory-based filtering techniques are difficult to scale; even with 24K unique users, it took a long time to discover users that were similar to a single user.

- Memory-based collaborative filtering is nearly impracticable when dealing with large datasets.

- This method also suffers from the "cold-start" problem, making it difficult to obtain suggestions for new users or to suggest new goods.

### 2) Model-Based Collaborative Filtering Recommender System
Because the User-Item Interaction Matrix is sparse, like in the memory-based recommender system, we may condense or compress it into two matrices using a model to make it more efficient. Using Matrix Factorization Techniques for Recommender Systems, the large sparse item matrix is divided into two smaller dense matrices: a user-factor matrix with user representations and an item-factor matrix with item representations.

The above-mentioned factor is only a latent factor that captures the similarity between users and products. A latent factor is a trait or notion that a user or an item may possess. A latent component may be used to indicate the genre of a movie in a dataset. Matrix Factorization may be done using a variety of techniques, including Singular Value Decomposition (SVD), Principal Component Analysis (PCA), and Non-Negative Matrix Factorization (NMF).

![Matrix+Factorization+for+Recommender+Systems](https://user-images.githubusercontent.com/69427575/156032053-d3a86c63-9e71-42cd-b429-32d510e17dca.png)

For matrix factorization of the recommender system, the SVD technique was utilised. The recommendation model is transformed into an optimization problem, and measures like Root Mean Squared Error are used to assess how well we are at predicting a user's rating of an item (RMSE). SVD uses latent variables to reduce the dimensions of our user-item interaction matrix. Users and things are mapped in a latent space with dimension d, which helps us better comprehend their connection.This approach utilized Related Item type as kind of Recommendation prediction and Recommendation item selection is done from Rated Items in the Score Matchbox of the Recommender Module for the Item-factor Matrix.And Related Users type as kind of Recommendation prediction and Recommendation item selection is done from Users tha rated Items in the Score Matchbox of the Recommender Module for the User-factor Matrix.The output of these specifications of both metrics is shown.

![2022-03-12 (8)](https://user-images.githubusercontent.com/69427575/158028324-e93b62ac-e1d2-4cb5-867f-8cb27a12ce0d.png)

![2022-03-12 (10)](https://user-images.githubusercontent.com/69427575/158028329-3d3f8f38-9db5-4036-b07a-9e9adc1da8fc.png)

There may be valuable characteristics in the data, such as a User X who is a girl and a teen who enjoys comedies and female-oriented films. The Princess Diaries is a wonderful choice since it is hilarious and female-oriented. We do not, however, hand-code these characteristics; instead, we let the model to uncover these underlying representations of user preferences and item properties.

![Collaborative+Filtering+Python](https://user-images.githubusercontent.com/69427575/156032020-332b37a7-e109-497f-8c8d-3e3f8f31b9ff.png)

### Advantages of Memory-Based Collaborative Filtering Recommender Systems
- They're simple to grow and can handle extremely massive datasets.

- If the data on which we trained is representative of the overall population, overfitting may be avoided.

- Because you simply query the model, not the entire dataset, the prediction speed is substantially faster than memory-based models.


### Disadvantages of Memory-Based Collaborative Filtering Recommender Systems
- The accuracy of forecasts is solely determined by the model used to make them.

- It's not particularly user-friendly, especially when using Deep Learning models.
