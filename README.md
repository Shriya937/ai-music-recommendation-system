# 🎵 AI-Powered Music Recommendation System

An AI-based music recommendation system that recommends songs based on their musical characteristics. The project begins with a traditional content-based recommendation approach using feature scaling and cosine similarity, and is then extended using a neural-network autoencoder to learn lower-dimensional song representations.

## 📌 Project Overview

Music streaming platforms contain millions of songs, making it difficult for users to discover tracks that match the characteristics of a song they already enjoy.

This project explores how machine learning and deep learning can be used to represent songs numerically and identify relationships between tracks.

The system was developed in two phases:

### Phase 1 — Content-Based Recommendation

The first version represents every song using Spotify audio features and calculates similarity between songs using cosine similarity.

### Phase 2 — Neural Network Enhancement

The second version introduces an autoencoder neural network to learn compressed latent representations of songs. Cosine similarity is then applied to these learned embeddings to generate recommendations.

The project therefore compares:

**Raw Audio Features → Cosine Similarity**

with

**Neural Embeddings → Cosine Similarity**

---

## 🎯 Objectives

* Build a content-based music recommendation system.
* Understand how numerical audio features can represent songs.
* Apply feature preprocessing and standardization.
* Implement cosine similarity for song-to-song comparison.
* Develop a neural-network-based representation of songs.
* Compare traditional and neural-network-based recommendations.
* Visualize model behavior and recommendation patterns.
* Understand the role of machine learning and deep learning in recommendation systems.

---

## 📊 Dataset

The project uses a Spotify tracks dataset containing song metadata and numerical audio features.

The main features used by the recommendation system are:

* Danceability
* Energy
* Tempo
* Valence
* Acousticness
* Speechiness
* Liveness
* Instrumentalness

Due to computational limitations when calculating a full song-to-song similarity matrix, a subset of approximately 10,000 tracks was used during experimentation.

---

## 🧠 Methodology

### 1. Data Loading

The dataset is loaded into a Pandas DataFrame.

### 2. Data Preprocessing

Rows containing missing values in the selected audio features are removed.

### 3. Feature Selection

Eight numerical audio features are selected as the input representation for each song.

### 4. Feature Scaling

`StandardScaler` is used to standardize the selected features so that features with different numerical ranges can be compared fairly.

### 5. Classical Similarity Model

Cosine similarity is calculated between the standardized feature vectors of all songs.

For a pair of song vectors A and B:

$$
Cosine\ Similarity(A,B) =
\frac{A \cdot B}{||A|| ||B||}
$$

The songs with the highest similarity scores are returned as recommendations.

### 6. Neural Network Enhancement

An autoencoder is trained using the selected audio features.

The autoencoder learns to:

**Input Features → Compressed Representation → Reconstructed Features**

The compressed representation, or latent representation, is then used as a learned embedding for each song.

### 7. Neural Similarity

Cosine similarity is calculated again, this time using the learned neural embeddings.

This creates a second recommendation approach that can be compared with the original feature-based model.

---

## 🔬 Technologies Used

* Python
* Google Colab
* Pandas
* NumPy
* Scikit-learn
* TensorFlow / Keras
* Matplotlib
* Seaborn

---

## 📈 Model Comparison

| Aspect         | Phase 1                 | Phase 2                         |
| -------------- | ----------------------- | ------------------------------- |
| Representation | Original audio features | Learned neural embeddings       |
| Similarity     | Cosine similarity       | Cosine similarity               |
| Learning       | Feature-based           | Representation learning         |
| Model          | Classical ML approach   | Neural network autoencoder      |
| Main Purpose   | Establish baseline      | Explore learned representations |

---

## 📊 Results

The project produces a list of songs similar to a user-provided input track.

Example:

```text
Input Song
     ↓
Feature Extraction
     ↓
Similarity Calculation
     ↓
Top-N Similar Songs
```

The neural-network phase allows the recommendations generated from learned embeddings to be compared against the original feature-based recommendations.

Visualizations are included to analyze:

* feature distributions
* training loss
* similarity patterns
* recommendation differences between phases

---

## 🚧 Current Limitations

* Approximately 10,000 tracks were used for the main similarity experiment because the full pairwise similarity matrix becomes computationally expensive as the dataset grows.
* The current system is primarily content-based and does not use individual user listening histories.
* Recommendations depend on the quality and coverage of the available audio features.
* The current implementation is a research/academic prototype rather than a production-scale recommendation engine.

---

## 🚀 Future Improvements

Possible extensions include:

* Collaborative filtering using user listening behavior.
* Hybrid recommendation combining content and user preferences.
* Lyrics-based sentiment and mood analysis.
* Real-time recommendation through a web interface.
* More scalable nearest-neighbor search instead of storing a complete similarity matrix.
* Integration with additional music metadata.
* Deployment as an interactive application.

---

## 📁 Repository Structure

```text
ai-music-recommendation-system/
│
├── notebooks/
│   └── music_recommendation.ipynb
│
├── data/
│   └── README.md
│
├── visualizations/
│
├── results/
│
├── README.md
│
└── requirements.txt
```

---

## 👩‍💻 Author

**Shriya A**

AI / ML | Robotics | Computer Vision

---

## 📌 Project Status

**Completed prototype — further improvements and deployment planned.**

