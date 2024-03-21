# Dexian Data Analytics Technical Challenge

**Author:** James Meredith

Active Project Dates: Mar 15th, 2024 - Mar 22nd, 2024

***
![alt text](./images/company_logo.png)

## Abstract



## Business Problem

The Scenario for the technical challenge was the following: You are working with a firm that provides consulting services for institutions of higher learning. The team has gathered some data about a number of schools, and they are hoping you can identify some meaningful insights that could help them as they advise various colleges and universities this year.

## Data

The dataset used for this project was the Million Song Database. The Million Song Dataset was designed to promote machine learning models on industry-sized data, and started as a collaborative project between LabROSA, a research team at Columbia University, and The Echo Nest. It’s a freely-available collection of audio features and metadata for a million contemporary popular music tracks. In 2014 the Echonest was purchased by Spotify, and data from the project lives on in the current recommendation systems at Spotify, so I felt it was a fitting dataset for the project. The Million Song Dataset contains a variety of different metadata and audio feature data, but in particular I used the core dataset for the audio features, the Last.fm Dataset for genre and emotion tags, and the Echo Nest Taste Profile Subset to train the recommendation system. It should be noted that the full dataset is 280 GB uncompressed, so due to hardware constraints I used a subset of the data for this project, a much more modest 2.5 GB. 

The dataset is available for download at http://millionsongdataset.com/. The dataset is also available on AWS S3 at s3://millionsongdataset/.

Attributions for the dataset is as follows:

Thierry Bertin-Mahieux, Daniel P.W. Ellis, Brian Whitman, and Paul Lamere. 
The Million Song Dataset. In Proceedings of the 12th International Society
for Music Information Retrieval Conference (ISMIR 2011), 2011.

## Methods

Songs were tagged with one of 4 moods: happy, sad, angry, and calm. The data was then split into a training set and a test set, with the training set containing 85% of the data, and the test set containing 15% of the data. The training set was used to train the model, and the test set was used to test the model. The data was then used to train a machine learning algorithm in order to build the detection model. The detection model was created using an iterative approach that compared the accuracy and efficiency of several different machine learning models against a baseline dummy model. Pipelines were used to efficiently process the data for each model. The models were then tuned using GridSearchCV to find the optimal hyperparameters for each model. The models were then evaluated using accuracy scores and confusion matrices. Ultimately, SVD was the model selected. After tuning the hyperparameters, an accuracy score of 0.58 was produced. Limitations in the size of the training dataset are the likely cause of the accuracy score, and future plans to improve the model accuracy are planned. The data was then used to automatically label the mood of each song in the dataset for utilization in the recommendation system.

## Results

Results of the baseline dummy model showed an accuracy score of 0.33. The accuracy score of the SVD model was 0.58. The confusion matrix for the SVD model is shown below.

![img](./images/confusion_matrix.png)

## Conclusions

Based on the analysis, the author recommends the use of audio feature data to predict the dominant mood of a song. Due to the ease and accuracy of detecting the dominant mood of a song based on its audio features, the author recommends that Spotify integrate a mood detection model into their current recommendation system to allow users to request music based on their current mood. Limitations of the study include the use of user-generated tags to determine the dominant mood of a song, and the use of audio features that are proprietary to the Spotify API. Future work could include the use of a larger dataset, more audio features included in the analysis, the inclusion of more mood classes, sentiment analysis of song lyrics to strengthen model accuracy, and the use of a more robust model.

## For More Information

Please review the full analysis in [the Jupyter Notebook](./full_analysis.ipynb) or [the presentation](./presentation.pdf).

For any additional questions, please contact James Meredith at <jam637.jlm@gmail.com>, or on [LinkedIn](https://www.linkedin.com/in/jamesleemeredith/).

## Repository Structure

```
├── data
├── images
├── .gitignore
├── app.py
├── full_analysis.ipynb
├── presentation.pdf
├── README.md
└── updates_msd_audio_features.ipynb
```