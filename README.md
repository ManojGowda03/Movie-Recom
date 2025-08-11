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
  -git clone https://github.com/ManojGowda03/Movie-Recom.git
  -cd Movie-Recom

2. **Install dependencies**
   -pip install streamlit pandas scikit-learn nltk requests
    
3. **Download NLTK resources** (if not already installed)
   -import nltk
   -nltk.download('wordnet')

4. **TMDB API Key**  
Sign up at The Movie Database (TMDB) to get an API key, then replace `YOUR_TMDB_API_KEY` in `app.py` with your key.  

## Running the App

Start the Streamlit server:
streamlit run app.py

A browser window will open. Choose a movie from the dropdown menu and click **Show Recommendations** to see five similar films with their posters.

## Exploring the Notebook

Open `Movies_Recommendation-checkpoint.ipynb` to dive into:
- Detailed data cleaning procedures  
- Feature engineering logic  
- Similarity model construction  

Feel free to tweak preprocessing steps, try different vectorization methods, or combine this with collaborative filtering for a hybrid system.

## Future Enhancements

- Incorporate user ratings to personalize recommendations  
- Add more metadata (e.g., reviews, box office revenue)  
- Experiment with TF-IDF or word embeddings instead of basic counts  
- Deploy the app to a cloud service for wider access  

## Contributing

Contributions are welcome! Fork the repo, create a branch for your feature, commit your changes, and submit a pull request.

---

Enjoy discovering new movies! 


