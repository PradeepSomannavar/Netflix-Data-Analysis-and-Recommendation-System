# Netflix Data Analysis and Hybrid Recommendation System using NLP & Similarity Learning

## Project Overview

Content discovery is a major challenge for modern OTT platforms like Netflix due to the massive volume of available content. Users often face decision fatigue, and ineffective personalization can lead to reduced engagement and churn.

This project presents an **EDA-driven hybrid recommendation system** built on top of an in-depth **Exploratory Data Analysis (EDA)** of the Netflix catalog. Instead of relying on assumptions, all feature selection, weighting, and modeling decisions are informed directly by insights discovered during data analysis.

The system combines **Natural Language Processing (NLP)** techniques with **structured numerical features** to generate context-aware and interpretable content recommendations.

---

## Objectives

- Perform deep exploratory data analysis on Netflix content
- Extract actionable insights to guide feature engineering
- Build a **hybrid content-based recommender system**
- Combine **textual similarity** and **numeric similarity**
- Handle noisy or partial user input
- Demonstrate an end-to-end data science workflow

---

## Dataset Description

The dataset is a public snapshot of Netflix’s catalog containing metadata for Movies and TV Shows.

**Key attributes include:**
- Title
- Content type (Movie / TV Show)
- Genres
- Director
- Country
- Rating
- Duration
- Release year
- Date added
- Description

The raw data contains missing values, mixed formats, and unstructured text, requiring significant preprocessing before modeling.

---

## Exploratory Data Analysis (EDA)

EDA forms the backbone of this project and directly influences model design.

**Key insights derived from EDA:**
- Movies significantly outnumber TV Shows
- Content additions increased sharply after 2015
- A small set of genres dominates the catalog
- Certain directors contribute disproportionately large volumes of content
- Country and rating provide cultural and audience-level signals

These insights guided feature inclusion, weighting, and similarity strategy.

---

## Data Cleaning & Preprocessing

- Removed records with missing critical fields
- Dropped duplicate entries
- Parsed mixed-format duration values
- Extracted year and month from date fields
- Normalized text data for NLP processing
- Treated multi-word entities as single tokens

---

## Feature Engineering

### Text Features (NLP)

The following fields are combined into a single text representation:
- Title
- Genres (weighted higher based on EDA)
- Director
- Country
- Rating

TF-IDF vectorization is applied to extract meaningful textual patterns.

### Numerical Features

- Duration (minutes)
- Number of genres
- Content type flag
- Release age
- Title length

All numeric features are scaled using MinMaxScaler.

---

## Recommendation Modeling

This is an **unsupervised, similarity-based system**.

- **Text similarity:** TF-IDF + cosine similarity (linear kernel)
- **Numeric similarity:** cosine similarity on scaled features

### Hybrid Similarity Formula
Hybrid Similarity = 0.85 × Text Similarity + 0.15 × Numeric Similarity

This approach prioritizes semantic relevance while preserving structural alignment.

---

## Recommendation Strategy

- Uses fuzzy title matching to handle typos and partial inputs
- Generates Top-N recommendations based on similarity scores
- Provides interpretable results by analyzing common attributes among recommendations

---

## Interactive Interface

The system includes an interactive **IPython widget-based UI** that enables:
- Real-time title search
- Automatic fuzzy matching
- HTML-rendered recommendation tables
- Insightful contextual explanations

---

## Technologies Used

- Python
- Pandas, NumPy
- Scikit-learn
- TF-IDF, Cosine Similarity
- Matplotlib, Seaborn
- IPython Widgets
- HTML rendering

---

## Results & Key Learnings

- Demonstrated how **EDA improves model quality**
- Built a practical **hybrid recommendation system**
- Combined structured and unstructured data effectively
- Gained hands-on experience with NLP feature engineering
- Designed a scalable, interpretable similarity-based ML system

---

## Future Enhancements

- Integrate collaborative filtering using user behavior
- Replace TF-IDF with semantic embeddings (SBERT)
- Add evaluation metrics (Precision@K, NDCG)
- Deploy as a web application or REST API

---

## Domain Relevance

This project aligns with roles in:
- Data Science
- Machine Learning Engineering
- NLP Engineering
- Recommendation Systems

---

*This project is open-source and created for learning and portfolio demonstration.*
