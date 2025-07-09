# Tuning into Popularity: Predicting Spotify Track Success Through Audio Features 🎧
**By: Victoria Brigola**


### Kaggle dataseets used
- **Spotify Audio Features (April 2019 & Novemeber 2018):** https://www.kaggle.com/datasets/tomigelo/spotify-audio-features?select=SpotifyAudioFeaturesApril2019.csv
- **Spotify Tracks Dataset:**
https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset?utm_source=chatgpt.com


______________________________________________________________________________________________


## Introduction
Spotify is more than a music streaming platform, it's a space where users discover, connect, and lose themselves in sound. With millions of tracks constantly uploaded, predicting which songs will rise to popularity is a business-critical challenge.

My projct uses supervised machine learning to classify tracks into popularity tiers (low, medium, anf high) using only their audio features and data, no stream counts or listener behavior required.


## Problem at Hand
Spotify needs a scalable method to predict track popularity based on a song's audio signature. Manual curation is limited and biased. The objective is to train a model that flags high-potential songs early using features like: 
- danceability
- energy
- valence
- and loudness


## Approach
My project pipeline has 4-phases:
1. **Data Wrangling**
   - Cleaned and merged two Kaggle datasets on 'track_id'.
   - Removed duplicates, low-variance columns, and noise.
  
2. **Exploratory Data Analysis (EDA)**
   - Visualized relationships between audio features and popularity.
   - Identified skew in distribution and inter-feature dependencies.
  
3. **Preprocessing**
   - Normalized numeric features using 'StandardScaler'.
   - Encoded categories ('genre_category', 'mode') using OneHotEncodding.
   - Converted binned popularity classes using 'LabelEncoder'.
  
4. **Modeling**
   - Tested multiple classifiers: Decision Tree (Gini & Entropy), Logistic Regression, Random Forest, and Bagging.
   - Ultimately chose **Bagging Classifier** based on F1 macro score and balanced performance.

  

## Final Model: Bagging Classifier
- **Target:** Popularity (binned: (0 = low, 1 = medium, 2 = high).
- **Accuracy:** 80%
- **Key Features:** danceability, energy, valence, loudness



## Recommendations for Spotify
**Integrate prediction model into editorial tools**
- Use audio features during ingestion to highlight songs with strong popularity potential.

**Align feature trends with playlist categories**
- Songs with high 'energy' and 'danceability' are ideal for curates lists workout or party mixes.

**Create genre-specific classifiers**
- Popularity drivers vary across style-custom models can improve precision.



## Respitory Structure
| File | Description |
|______|_____________|
|'FinalProjectReport_TrackPopularityPrediction.pdf' | Full summary report findings, figures, and insigts. |
|'2_Capstone2Popularity_DataWrangling.ipynb'| Cleaning and merging both Spotify datasets (Spotify tracks and audio feature csv, links to each datasets above. |
|'3_Capstone2Popularity_EDA.ipynb'| Visuals and statistical relationships. |
|'4_Capstone2Popularity_PreProcessing.ipynb'| Data transformation and train/test preparation. |
|'5_Capstone2Popularity_Modeling.ipynb'| Model training, evaluation, and selection. |
  
