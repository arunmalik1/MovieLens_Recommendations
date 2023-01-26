# MovieLens Recommendations
This project is for recommending movies to users based on ratings. The stakeholder can be any company that houses user based movie ratings and wants to increase viewership by making recommendations.

# Data Collection
The data is provide by the GroupLens research lab at the University of Minnesota.
https://grouplens.org/datasets/movielens/latest/

# Methodology 
Data Exploration: This step involved exploring each variable in the data set. Their types, value ranges, distributions and deleting or imputing missing values.

Data visualization: Creating visuals gives insights such as how skewed data affects models.

Model deployment and selection: I chose to use the surprise package to create singular value decomposition(SVD), Knn basic, Knn baseline and Knn means models. SVD is the best performing model and I used it to ask a user to give ratings to movies in a genre. The ratings are stored and the model uses those ratings to return movie recomendations. 

# Data Exploration:
The ratings dataframe has a column named timestamp, which we do not need for this model and was removed. We have some users who rated many more movies and this will lead to an inbalanced dataset. The vast majority of movies were rated by less than twenty five users. 

![UsersWhoRatedMovies](https://user-images.githubusercontent.com/115169255/214904605-c98339bd-f300-45d5-aa01-ab3d3deba17b.png)

The result is that some genres will become more popular then others. For example, comedy and drama become extremly popular and have the highest ratings. Models will lean towards recommending those types of movies.
![genre_popularity](https://user-images.githubusercontent.com/115169255/214906713-89bc326b-22db-40e1-8c48-d6782c4e6fbc.png)

There is also an inblance in the distribution of ratings. Perhaps people do not bother rating movies they do not like. The average rating for movies is 3.5 and the ratings are split into 10 categoires ranging from 0.5 to 5.0.
![AverageRatings](https://user-images.githubusercontent.com/115169255/214908815-16f151da-b13e-4450-84a1-7912343af3f0.png)

Lastly, I wanted to see the average number or ratings over the years. This informaton was collected by combining the movies and ratings dataset. 

![AverageYearlyRatings](https://user-images.githubusercontent.com/115169255/214910225-d422eebb-9c93-4f52-b59d-01e62e5e9685.png)

# Model selection.
SVD model had the best results with an error of 0.897
<img width="1006" alt="SVD Model Results" src="https://user-images.githubusercontent.com/115169255/214911065-0c9f9378-c654-4230-be80-e2bec84be4fa.png">

# Recomendations.
I created a function that asks a user to give ratings to movies in a genre. It then makes recommendations for movies based on user feedback. 

<img width="807" alt="Recommendations" src="https://user-images.githubusercontent.com/115169255/214912111-905856ae-a351-4a4d-a552-b5b355889fe6.png">

# Future Work
Overall the model works well and ill give users movie recommendations. To further improve the model I recommend getting a better distribution of user ratings. That will enable models to make recommendations for other genres. 
