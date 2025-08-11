# Movie Recommendation System 

This project is a content-based movie recommendation engine built with Python. It analyzes movie details—such as genres, keywords, cast members, directors, and plot summaries—to suggest five similar films. A Streamlit app provides an interactive interface, and movie posters are fetched through the TMDB API.

## What You’ll Find Here

- **Jupyter Notebook** (`Movies_Recommendation-checkpoint.ipynb`): Data cleaning, feature extraction, text processing, and model-building steps  
- **Streamlit App** (`app.py`): A simple web interface where you pick a movie and get five recommendations, complete with posters  
- **Pickle Files** (`movies.pkl`, `similarity.pkl`): Serialized movie dataset and precomputed similarity matrix ready for the app  

## How It Works

1. **Data Preparation**  
   - Merge the movies and credits datasets  
   - Keep only the columns we need: movie ID, genres, keywords, title, overview, tagline, cast, and crew  

2. **Feature Extraction**  
   - Convert JSON-formatted genre, keyword, cast, and crew data into Python lists  
   - Pull out the top three billed cast members and the director  
   - Lowercase everything and apply lemmatization to unify similar terms  

3. **Building the Recommendation Model**  
   - Combine genres, keywords, overview, cast, and director names into one text field per movie  
   - Use a CountVectorizer (up to 5,000 features) to turn text into numerical vectors  
   - Calculate cosine similarity between all movie vectors  

4. **Serving Recommendations**  
   - When you select a movie, look up its similarity scores against every other title  
   - Sort and return the five closest matches  
   - Use the TMDB API to fetch and display each movie’s poster  

## Getting Started

1. **Clone this repository**  
