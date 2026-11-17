# Netflix Movies and TV Shows Analysis

I cleaned and explored the Netflix titles dataset to see what kind of content is on the platform and how it changed over time.

## Dataset

The data comes from the [Netflix dataset on Kaggle](https://www.kaggle.com/datasets/manishamali/netflix-data-analysis) (`netflix_titles.csv`). It has 8,807 titles and 12 columns, including type, title, director, cast, country, date added, release year, rating, duration and genre.

## Data Cleaning

* Checked for duplicate rows (none were found)
* Removed extra spaces from text columns
* Fixed three movies where the duration had been entered in the rating column
* Filled missing director, cast and country values with "Not Specified"
* Filled missing ratings with "Not Rated" and merged NR and UR into the same group
* Kept the 10 titles with no date added instead of dropping them, so they still count in every chart except the ones based on date
* Converted the date column and created year and month columns
* Split duration into a number and a unit (minutes for movies, seasons for TV shows)
* Calculated the gap between release year and the year a title was added, and flagged 14 titles where this gap was negative

No rows were removed, so the cleaned data still has all 8,807 titles.

## What I Looked At

* Movies vs TV shows
* Titles added each year
* Content ratings
* Movies and TV shows added each year
* Top 10 genres
* Median movie length by genre
* Gap between release year and year added

## Key Findings

* Movies make up about 70% of the titles.
* Netflix added the most content around 2019 and 2020.
* TV shows were added more often in later years, but movies stayed the larger group.
* Mature audience ratings are the most common, followed by ratings for teens.
* International Movies, Dramas and Comedies are the most common genres.
* Documentaries and children's movies are usually the shortest, while dramas run the longest.
* Most titles were added within a year of being released.

## Tools

Python, Pandas, NumPy, Matplotlib and Seaborn

## Files

* `EDA_Netflix data analysis` is the notebook with all the cleaning, charts and notes

## How to Run

The notebook was built on Kaggle, so the easiest way is to open it there with the dataset attached and click Run All.

To run it on your own computer, download `netflix_titles.csv` from the Kaggle link above and change the path in the first code cell to:

```python
df = pd.read_csv("netflix_titles.csv")
```
