# Anime-Recommendation-System
A web based anime recommendation system. This system uses deep learning algorithms, along side other techniques, to give people qualitative recommendations based on shows they previously enjoyed, without putting much weight into how recent the recommended shows are. 

# Installation 

Clone this git repo (including the backend system submodule):
git clone --recurse-submodules -j8 

# Usage

1 First you'd need to scrape the data using the python scripts (ordered 1-5) in the ./scrap_data folder
cd scrap_data
python 1_scrap_by_genre.py

2 Then you'll have to build the algorithms from the data scraped, you can do this by running the individual build_algo.py files in each algorithms/*/. folder. For examples:
cd algorithms
cd word2vec
python build_algo.py

 3 Finally, once you have the files you need, you can run the following to set up the API and see it running on port localhost:8000
uvicorn main:api --reload

 # API Syntax
To see the latest API docs, you can go to http://3.131.210.47:8000/docs. It's currently a JSON format with each row as the key and an array of recommendationss. We've decided that the only changes are going to be the info stored in the recommendations themselves (we'll be adding genre/tags that match, recommendation_count (if applicable), words that match (if applicable)) for this next cycle.

