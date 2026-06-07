#  Music Recommendation System-Intrest-base

## Project Overview

This project implements a Hybrid Music Recommendation System inspired by Spotify. The system combines:

1. Content-Based Filtering
2. Collaborative Filtering
3. User Search Tracking

The recommendation engine learns from user behavior and dynamically updates recommendations based on search frequency and listening preferences.

---

## Features

### Content-Based Recommendation

The system recommends songs similar to a selected song by comparing audio features such as:

* Danceability
* Energy
* Acousticness
* Instrumentalness
* Liveness
* Valence
* Tempo

A K-Nearest Neighbors (KNN) model with cosine similarity is used to find similar songs.

### Collaborative Filtering

User listening history is analyzed using:

* userID
* artistID
* weight

A user-item matrix is created, and cosine similarity is used to identify users with similar interests.

### Search Tracking System

The system records:

* Total searches performed
* Individual song search counts

Every time a song is searched:

* Its search count increases
* User preferences are updated
* Recommendations are adjusted accordingly

### Dynamic Learning

The system continuously learns from user interactions.

When a song is searched multiple times:

* Its popularity score increases
* It appears higher in future recommendations

### New Song Handling

If a song does not exist in the dataset:

* It is automatically added to the system
* A placeholder artist and genre are assigned
* The recommendation model is rebuilt

---

## Dataset

### Songs Dataset

Contains information about songs including:

* track_name
* artists
* album_name
* popularity
* danceability
* energy
* acousticness
* instrumentalness
* liveness
* valence
* tempo
* track_genre

Total Records:

Approximately 114,000 songs.

### User Dataset

Contains user listening history:

* userID
* artistID
* weight

Where:

* userID = unique user identifier
* artistID = artist identifier
* weight = listening frequency

---

## Machine Learning Techniques

### StandardScaler

Audio features are normalized before similarity calculations.

### Nearest Neighbors (KNN)

Used for content-based recommendations.

Metric:

Cosine Similarity

### Collaborative Filtering

A user-item matrix is generated and user similarity is computed using cosine similarity.

---

## System Workflow

### Step 1

Load song dataset and user dataset.

### Step 2

Build content-based recommendation model.

### Step 3

Build collaborative filtering model.

### Step 4

Display initial recommendations.

### Step 5

User enters a song name.

### Step 6

System:

* Tracks search count
* Updates user profile
* Finds similar songs

### Step 7

Recommendations are refreshed based on:

* User behavior
* Search frequency
* Similar users

---

## Example Output

### Initial Recommendations

| track_name | artists  | genre |
| ---------- | -------- | ----- |
| Song A     | Artist X | Pop   |
| Song B     | Artist Y | Rock  |

### User Search

Enter song name:

Hold On

Output:

This song has been searched 5 times.

### Similar Songs

| Rank | Song Name | Artist   |
| ---- | --------- | -------- |
| 1    | Song X    | Artist A |
| 2    | Song Y    | Artist B |

### Updated Recommendations

Songs with higher search counts automatically move toward the top of the recommendation list.

---

## Advantages

* Real-time learning
* Dynamic recommendations
* Search behavior tracking
* Content-based filtering
* Collaborative filtering
* Scalable architecture
* Spotify-inspired recommendation workflow

---

## Future Improvements

* Streamlit Web Application
* User Login System
* Playlist Generation
* Deep Learning Recommendation Model
* Recommendation Evaluation Metrics
* Database Integration
* Real-Time Music API Integration

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* K-Nearest Neighbors
* Cosine Similarity
* StandardScaler

---

## Author

Muhammad Zeeshan

Computer Science Student

AI and Recommendation Systems Enthusiast
