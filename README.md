Movie Recommendation System using KNN
This project implements a Movie Recommendation System based on the TMDb 5000 Movies dataset. It uses a custom K-Nearest Neighbors approach to recommend similar movies and predict their ratings, based on genres, cast, director, and keywords.

📂 Datasets Used
tmdb_5000_movies.csv

tmdb_5000_credits.csv

Both datasets are merged and preprocessed for feature extraction and similarity computation.

🧹 Data Preprocessing
JSON Conversion: Fields like genres, keywords, cast, and production_companies were initially stored as JSON strings. These were parsed and converted into lists.

Director Extraction: The director’s name was extracted from the crew data.

One-Hot/Binary Encoding: Applied to genres, cast, director, and keywords for calculating cosine similarity.

Data Cleaning: Removed movies with missing director names or zero vote_average.

📊 Data Visualization
Top Genres: Horizontal bar plot of the most common genres.

Top Actors: Visualization of the actors with the highest number of movie appearances.

Top Directors: Plot showing the directors with the most movies.

WordCloud: Visualization of most common keywords after removing stopwords using NLTK.

🤖 Movie Recommendation Algorithm (KNN)
🔍 Similarity Function
The similarity between two movies is computed using cosine distance on:

Genre vectors

Cast vectors

Director vectors

Keyword vectors

The total distance is the sum of these cosine distances.

📈 Score Predictor
Given a movie title:

The system finds the 10 most similar movies.

Computes the average rating of the recommended movies.

Predicts the rating of the input movie.

Displays actual vs. predicted rating for comparison.

💡 Usage Example
python
Copy
Edit
predict_score('Godfather')
predict_score('Donnie Darko')
predict_score('Notting Hill')
predict_score('Despicable Me')
This will:

Output the selected movie

List 10 most similar movie recommendations

Show the average rating of the recommendations

Predict the rating for the selected movie

Show the actual rating from the dataset

🛠 Technologies Used
Python

Pandas & NumPy

Seaborn & Matplotlib

NLTK (Natural Language Processing)

SciPy (Cosine similarity)

WordCloud (visualization)

📌 Requirements
Install dependencies using:

bash
Copy
Edit
pip install pandas matplotlib seaborn nltk wordcloud
Don’t forget to download NLTK data:

python
Copy
Edit
import nltk
nltk.download('stopwords')
nltk.download('punkt')
✅ Results
The system effectively distinguishes between vastly different movies.

Recommendations are based on meaningful metadata, not collaborative filtering.

Predictive scores are relatively close to actual ratings.

🧠 Future Enhancements
Use TF-IDF for keyword weighting.

Apply collaborative filtering or matrix factorization.

Integrate movie posters or trailers for UI improvements.
