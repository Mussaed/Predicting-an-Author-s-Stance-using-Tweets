# Predicting an Author's Stance Using Tweets

## Overview
This project focuses on **predicting an author's stance based on their tweets** using a combination of **machine learning and natural language processing (NLP) techniques**. The task was part of a **Kaggle competition**, where the goal was to classify users' stance based on tweet content while handling missing sentiment values.

## Methodology

### 1. Data Preprocessing & Cleaning
- **Text Normalization & Cleaning**:
  - Used **Tnkeeh**, an Arabic preprocessing library, to clean tweets by removing:
    - Special characters, English letters, and diacritics ("Tashkeel/تشكيل").
    - Elongation (Tatweel, e.g., التـــحول → التحول).
    - Normalization (e.g., **أا → ا**).
    - HTML elements (e.g., URLs, Twitter mentions, links, and hashtags).
    - Repeated characters and long words (e.g., **هههههه**, **حلووووو**).

- **Stopword Removal**:
  - Identified **most common words** in tweets and found that stopwords dominated all categories.
  - Removed stopwords to **reduce noise and improve model accuracy**.

- **Manual Text Cleaning**:
  - Removed extra spaces, numbers, and underscores.

### 2. Feature Engineering
- **Time-based Features**:
  - Extracted **year, month, day, weekday, and time categories** from tweet timestamps.

- **Embeddings & NLP Features**:
  - Used **AraBERT**, a transformer-based Arabic NLP model, to generate word embeddings for better text representation.

### 3. Model Training & Evaluation

- **Sentiment Prediction**:
  - Since some sentiment labels were missing, a **Support Vector Machine (SVM) classifier** was trained to predict sentiment values.

- **Stance Prediction**:
  - Used a **Multi-Layer Perceptron (MLP) classifier** to predict the stance of a tweet.

- **Evaluation Metric**:
  - **Accuracy** was used as the primary metric for model performance, in accordance with the Kaggle competition rules.

## Key Findings
1. **Text preprocessing improved model performance** by removing noise and ensuring clean input for the models.
2. **Stopword removal led to better results**, as most frequent words were not useful for stance prediction.
3. **AraBERT embeddings enhanced feature quality**, making stance classification more effective.
4. **SVM effectively handled missing sentiment values**, allowing for a more complete dataset.
5. **MLP outperformed other models for stance prediction**, achieving the best accuracy in the competition setup.

This project successfully applies **machine learning and NLP techniques** to classify author stance based on tweets, demonstrating a structured approach to **data cleaning, feature engineering, and model selection**.
