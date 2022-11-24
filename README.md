Anime Recommendation Model
-----------------------

Recommend a new or existing user an list of anime to watch based on the user's preferences and ratings. This model utilizes content based filtering to make recommendations. The dataset is of thousands of anime and millions of ratings, which were reteived from myanimelist.net. Dataset is here. [here](https://www.kaggle.com/datasets/hernan4444/anime-recommendation-database-2020).

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