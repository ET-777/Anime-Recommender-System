Anime Recommendation Model
-----------------------

Deep network for recommending a new or existing user a list of anime to watch based on their preferences and ratings. This model uses feature engineering and content based filtering method to make recommendations. The datasets are of thousands of anime and millions of ratings, which were retrieved from myanimelist.net. Dataset is [here](https://www.kaggle.com/datasets/hernan4444/anime-recommendation-database-2020). You can see the data processing, model, code, and full explanations in the `AnimeRecommender.ipynb` notebook above.

Quick Overview
----------------------

The original datasets consist of one anime dataset with information about the shows, and a ratings dataset with ratings by users for multiple shows. The anime dataset is over 17k items and the ratings dataset is over 57 million items. I did not have enough RAM to process multiple 57 million dataframes, so I reduced it to 15 million.

<p align="center">
<br />
Anime Dataset
<br />
<br />
<img src="https://github.com/ET-777/Anime-Recommender-System/blob/master/images/anime_data.jpg"/>
<br />
<br />
<br />
User Ratings Dataset
<br />
<br />
<img src="https://github.com/ET-777/Anime-Recommender-System/blob/master/images/user_data.jpg"/>
<br />
<br />
<br />
</p>

To process the datasets, several steps and methods were used. These include:

* Data cleaning
* Creating new features
* Joining dataframes
* Row and column operations

The resulting datasets were an anime dataset with the year of its release and dummy variables for the genres, a user dataset with the user's average rating per genre, and a labels dataset with individual ratings. The anime and user datsets are grouped by user to match the ratings in the label dataset. Each dataset has 15 million items.

<p align="center">
<br />
Anime Dataset
<br />
<br />
<img src="https://github.com/ET-777/Anime-Recommender-System/blob/master/images/x_items.jpg"/>
<br />
<br />
<br />
User Ratings Dataset
<br />
<br />
<img src="https://github.com/ET-777/Anime-Recommender-System/blob/master/images/x_users.jpg"/>
<br />
<br />
<br />
</p>

The model was constructed using the functional API. After getting rid of the unecessary columns and scaling the data. Two neural networks with Dense layers with relu activations and an output linear activation were created and joined with dot product.

<p align="center">
<br />
Model
<br />
<br />
<img src="https://github.com/ET-777/Anime-Recommender-System/blob/master/images/model.jpg"/>
<br />
<br />
<br />
</p>

Results
----------------------

The model was trained for 10 epoch with a MeanSquaredError loss function and a learning rate of 0.01 with adam optimizer. Data was also split by 30% for testing.
<br /><br />
 Data | Loss 
------------ | -------------
Training | 0.0645
Testing | 0.0646

<br /><br />
Having a low loss score that is very close for test and train data, the model performs very well. To further test the model, a new user who likes action shows was created and the following recommendations were predicted:

<p align="center">
<br />
Model
<br />
<br />
<img src="https://github.com/ET-777/Anime-Recommender-System/blob/master/images/new_user.jpg"/>
<br />
<br />
<br />
</p>

Installation
----------------------

### Download the data

* Clone this repo to your computer.
* Create a `Data` folder in the project directory
* Download the data files from Kaggle into the `Data` folder.  
    * You can find the data [here](https://www.kaggle.com/datasets/hernan4444/anime-recommendation-database-2020).
    * You'll need to register with Kaggle to download the data.
* Extract the `.zip` file you downloaded into the `Data` folder.
    * Only `anime.csv` and `rating_complete.cvs` are used.

### Install the requirements
 
* Install the requirements with `anaconda` or with pip using `pip install -r requirements.txt`.
    * Make sure you use Python 3.
    * You may want to use a virtual environment for this.

Usage
-----------------------

* Open `AnimeRecommender.ipynb` with `Jupyter Notebook`.
* Run the notebook
    * Make sure you are running `tensorflow` with a `GPU`.
