# IMDB-Movie-Visualization-Dashboard
Power BI dashboard visualizes the performance and profitability of the top 250 IMDb-rated movies (1921 – 2022), offering insights into trends such as genres, box office collections, IMDb ratings, and more. The dashboard enables users to explore and analyse movie data interactively through various visualizations and drill-through functionality.

### Data Source
- Dataset: This dataset contains the top 250 rated movies on IMDB as of 2021, providing a snapshot of the most popular and highly rated movies of recent times  
- Source: Kaggle
- URL: https://www.kaggle.com/datasets/rajugc/imdb-top-250-movies-dataset

### Data Columns
The dataset includes the following columns:
-	Rank - Rank of the movie
-	Name - Name of the movie
-	Year - Release year
-	Rating - Rating of the movie
-	Genre - Genre of the movie
-	Certificate - Certificate of the movie
-	Runtime - Total movie run time
-	Tagline - Tagline of the movie
-	Budget - Budget of the movie
-	Box office - Total box office collection across the world
-	Casts - All casts of the movie
-	Directors - Director of the movie
-	Writers - Writer of the movie

### Calculated Columns
•	Profit: Difference between Box Office and Budget values.
DAX Query: Profit = 'IMDB Top 250 Movies'[box_office]-'IMDB Top 250 Movies'[budget]

•	Status: Categorized based on the Profit value:
DAX Query: Status = IF (
    'IMDB Top 250 Movies'[Profit] < 0, 
    "Loss", 
    IF (
        'IMDB Top 250 Movies'[Profit] = 0, 
        "Data Not Available", 
        "Profit"
    )
)

### Data Transformations

-	Data type conversions for columns like Year and Budget.
-	Grouping and categorization of genres and certificates.
-	Formatting and cleaning of the dataset for consistency.

### Dashboard Visualizations

1. Year Slicer
Filter movies by release year (1921–2022).
Analyze data specific to a selected year range.
Dynamic updates across all visualizations based on the selected range.

2. Stacked Column Chart
Understand the distribution of movies by certificate type (e.g., R, PG, G).

3. Pie Chart (Movie Status)
Visualize the proportion of movies based on profitability:
71% of movies made a profit.
16% incurred a loss.
12% had incomplete data.

4. Cards
Display key metrics dynamically based on year filters.
Quickly identify the top-performing movies for any given year range.
Enables comparisons across different time periods.

5. Line Chart
Analyse the relationship between genres, box office collections, and ratings.
Identify which genres tend to perform well financially or have high ratings.

6. Table (Home Page)
Displays detailed information about movies filtered by year.
For example, selecting 2020–2022 shows all movies released during this period, along with their details.

7. Drill-Through Button (Movie Details)
Functionality: Clicking on a movie name in the table and selecting the "Movie Details" button drills through to a detailed second page. Enables in-depth exploration of individual movies for further analysis.
Includes:
-	A table with Director, Writer, Genre, Runtime, Certificate, Year, Cast, Tagline, etc.
-	Cards showing IMDb Rating, Budget, and Box Office.
-	Back button allows navigation to the home page.

### Conclusion
-	Compare trends over time, such as changes in genre popularity, box office earnings, and movie certifications.
-	Identify patterns in movie certifications (e.g., prevalence of R-rated movies in specific years).
-	Assess the overall profitability of movies and spot trends, such as the percentage of profitable vs. non-profitable movies.
-	Quickly determine the most financially successful and highest-rated movies for a selected time period.
-	Analyse how box office performance correlates with IMDb ratings for different genres. Discover which genres tend to have consistent success across both measures.
-	Gain granular insights into movies for specific years. Drill down to view detailed information about any selected movie, including its creative contributors and financial performance.
