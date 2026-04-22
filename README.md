# Netflix Recommendation System

A full-stack, content-based movie recommendation engine with live IMDB sentiment analysis, built using Python, Flask, and Machine Learning.

## Overview

This project is an end-to-end movie recommendation web application that combines content-based filtering with NLP-powered sentiment analysis of real IMDB user reviews. Enter any movie title, and the system recommends 10 similar titles while classifying live critic reviews as Good or Bad in real time.

## Features

- **Content-Based Filtering** - Recommends movies based on genres, cast, director, and keywords using cosine similarity on a CountVectorizer matrix.
- **Live IMDB Sentiment Analysis** - Web-scrapes live user reviews directly from IMDB and classifies each as positive or negative using a trained NLP model.
- **Full Movie Details** - Displays poster, genre, rating, runtime, release date, and cast information via the TMDB API.
- **Cast and Crew Profiles** - Shows detailed biographical info for each cast member, including birthday, birthplace, and bio.
- **Flask Web App** - A responsive front-end built with HTML, CSS, and JavaScript served via Flask.
- **Autocomplete Search** - Movie title autocomplete powered by the full dataset for a seamless UX.

## Tech Stack

| Category | Technologies |
|---|---|
| Backend | Python, Flask |
| ML / NLP | scikit-learn, CountVectorizer, Cosine Similarity, Pickle |
| Data Processing | Pandas, NumPy |
| Sentiment Model | Multinomial Naive Bayes (trained on IMDB reviews) |
| Web Scraping | BeautifulSoup4, urllib |
| Frontend | HTML, CSS, JavaScript |
| Data Sources | TMDB API, IMDB |

## Project Structure

```
Netflix_Recommendation_System/
├── datasets/
│   └── final_data.csv
├── static/
├── templates/
│   ├── home.html
│   └── recommend.html
├── (1) data_1.ipynb
├── (2) data_2.ipynb
├── (3) data_3.ipynb
├── (4) scaling_2025.ipynb
├── (5) final_dataset.ipynb
├── (6) final_preprocessing.ipynb
├── main.py
├── nlp_model.pkl
├── transform.pkl
├── requirements.txt
└── Procfile
```

## How It Works

**Content-Based Recommendation**

Movie metadata (genres, cast, director, plot keywords) is combined into a single feature column. A CountVectorizer converts these into a term-document matrix and cosine similarity is computed between all movie pairs. When a user searches for a movie, the top 10 most similar movies are returned.

**Sentiment Analysis**

When a movie is selected, the app scrapes live user reviews from IMDB using BeautifulSoup. Each review is vectorized using the pre-trained transformer and fed into the NLP classifier. The model predicts whether each review is Good or Bad, displayed alongside the recommendations.

## Running Locally

**Prerequisites:** Python 3.9+

```bash
git clone https://github.com/tanaygattani8/Netflix_Recommendation_System.git
cd Netflix_Recommendation_System
pip install -r requirements.txt
python main.py
```

The app will be available at http://127.0.0.1:5000

## Dataset and Model

| Detail | Info |
|---|---|
| Dataset Source | TMDB (The Movie Database) + IMDB |
| Number of Movies | 5,000+ titles |
| Similarity Method | Cosine Similarity on CountVectorizer matrix |
| Sentiment Model | Naive Bayes Classifier |
| Sentiment Accuracy | ~90% on test set |

## Notebooks Walkthrough

| Notebook | Purpose |
|---|---|
| (1) data_1.ipynb | Initial TMDB data collection and raw EDA |
| (2) data_2.ipynb | Feature selection and initial engineering |
| (3) data_3.ipynb | Cosine similarity matrix generation |
| (4) scaling_2025.ipynb | Scaling the pipeline for larger datasets |
| (5) final_dataset.ipynb | Creating the final cleaned dataset |
| (6) final_preprocessing.ipynb | NLP preprocessing, model training, and evaluation |

## Author

**Tanay Gattani** - [@tanaygattani8](https://github.com/tanaygattani8)