# Book-Recommender-Collaborative-Filtering
This notebook implements a collaborative filtering-based book recommendation system. It leverages user ratings to find books similar to ones a user has enjoyed or is looking for.
Collaborative Filtering-Based Book Recommendation System
This notebook implements a collaborative filtering-based book recommendation system. It leverages user ratings to find books similar to ones a user has enjoyed or is looking for.

# Project Overview
The project involves the following key steps:

1. Data Acquisition and Preparation: Three datasets (books, users, and ratings) are loaded. These datasets undergo cleaning, including renaming columns, selecting relevant features, and merging them into a single comprehensive DataFrame.

2. Filtering and Feature Engineering: To ensure the quality of recommendations, the data is filtered. Only users who have rated more than 200 books and books that have received at least 50 ratings are considered. This focuses on active users and popular books, reducing data sparsity and noise.

3. User-Item Matrix Creation: A pivot table is constructed with book titles as rows, user IDs as columns, and ratings as values. This matrix effectively represents the interaction between users and books. Missing ratings are filled with zeros to indicate no rating.

4. Model Training: The pivot table is converted into a sparse matrix for efficient handling of large datasets. A NearestNeighbors model from scikit-learn, utilizing a brute-force algorithm and cosine similarity, is then trained on this sparse matrix. This model is adept at identifying items (books) that are most 'similar' to a given item based on their rating patterns.

5. Recommendation Generation: A function is developed to take a book title as input, locate its position within the pivot table, and then use the trained NearestNeighbors model to identify and return the top 5 most similar books. The system generates recommendations based on the collective rating behavior of users, suggesting books that users with similar tastes have also enjoyed.

# How to Use
To get recommendations for a specific book, use the recommend_book function:
> **recommend_book("Your Book Title Here")** 
Replace "Your Book Title Here" with the exact title of the book you want recommendations for.

*** Example Recommendation
For example, if you search for 'Harry Potter and the Chamber of Secrets (Book 2)', the system might recommend:

Harry Potter and the Goblet of Fire (Book 4)
Harry Potter and the Prisoner of Azkaban (Book 3)
Harry Potter and the Sorcerer's Stone (Book 1) ***
Exclusive
The Cradle Will Fall
