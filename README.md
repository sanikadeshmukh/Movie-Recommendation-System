Movie Recommendation System
Overview
This project implements a movie recommendation system using collaborative filtering with the recommenderlab package in R. It processes movie and rating data, preprocesses the data to create a genre-based search matrix, visualizes movie ratings and similarities, and builds an Item-Based Collaborative Filtering (IBCF) model to recommend movies to users.
The code uses datasets such as movie metadata (e.g., movies.csv) and user ratings (e.g., ratings.csv), typically from the MovieLens dataset.
Features

Data Preprocessing: Converts movie genres into a binary matrix for analysis.
Exploratory Data Analysis: Visualizes movie views, user similarities, movie similarities, and rating distributions.
Recommendation System: Builds an IBCF model to recommend movies based on user ratings.
Visualizations: Includes bar plots, heatmaps, and histograms to explore data patterns.
Data Normalization and Binarization: Normalizes ratings and binarizes them for specific analyses.

Prerequisites

R Environment: R (version 4.0 or higher recommended).
Required R Packages:
recommenderlab: For building the recommendation system.
ggplot2: For data visualization.
data.table: For efficient data manipulation.
reshape2: For reshaping data into matrices.


Datasets:
movies.csv: Contains movie metadata (movieId, title, genres).
ratings.csv: Contains user ratings (userId, movieId, rating).



Install the required packages by running:
install.packages("recommenderlab")
install.packages("ggplot2")
install.packages("data.table")
install.packages("reshape2")

Dataset
The code expects two CSV files:

movies.csv: Contains columns movieId, title, and genres (pipe-separated genres, e.g., "Action|Comedy").
ratings.csv: Contains columns userId, movieId, and rating (ratings typically on a scale of 1 to 5).

You can obtain these datasets from the MovieLens dataset (e.g., the MovieLens 10M or 100K dataset).
Usage

Load the Data:

Place movies.csv and ratings.csv in your working directory.
Run the script, which prompts you to select these files using file.choose().


Run the Script:

Execute the R script (recommendation_system.R) in an R environment (e.g., RStudio).
The script will:
Preprocess the movie genres into a binary matrix.
Create a user-item rating matrix using recommenderlab.
Generate visualizations (e.g., bar plots of most-viewed movies, heatmaps of ratings, and similarity matrices).
Build and evaluate an IBCF recommendation model.
Output movie recommendations for users in the test set.




Key Outputs:

Visualizations:
Bar plot of the top 6 most-viewed movies.
Heatmaps of user and movie similarities.
Distribution of average user ratings and column counts.


Recommendations:
A list of top 10 movie recommendations for each user in the test set.
Example output for the first user’s recommended movie titles.




Example Command:
source("recommendation_system.R")



Code Structure

Data Loading and Preprocessing:

Reads movies.csv and ratings.csv.
Converts genres into a binary matrix (genre_mat2) for 18 predefined genres.
Creates a sparse rating matrix using recommenderlab.


Exploratory Analysis:

Computes user and movie similarities using cosine similarity.
Visualizes rating distributions, movie views, and similarity heatmaps.


Model Building:

Splits data into training (80%) and testing (20%) sets.
Builds an IBCF model with k=30 nearest neighbors.
Generates top 10 movie recommendations for test users.


Visualizations:

Bar plot of top-viewed movies.
Heatmaps of raw, normalized, and binarized ratings.
Histogram of average user ratings.



Example Output
For the first user in the test set, the script outputs movie titles recommended based on their rating history. Example:
[1] "The Shawshank Redemption (1994)"
[2] "Pulp Fiction (1994)"
[3] "Forrest Gump (1994)"
...

Notes

The script assumes the datasets are properly formatted. Ensure movies.csv and ratings.csv match the expected structure.
Adjust parameters like top_recommendations (default: 10) or k (default: 30) in the IBCF model for different results.
The script filters users and movies with sufficient ratings (e.g., >50 ratings) to improve model performance.
Visualizations require ggplot2; ensure it’s installed to avoid errors.

Troubleshooting

File Not Found: Ensure movies.csv and ratings.csv are in the correct directory or update the file paths.
Package Errors: Install all required packages before running the script.
Memory Issues: If working with large datasets (e.g., MovieLens 10M), ensure sufficient memory or use a smaller dataset (e.g., MovieLens 100K).

License
This project is for educational purposes and uses the MovieLens dataset, which is publicly available under its respective license. Refer to GroupLens for dataset licensing details.
