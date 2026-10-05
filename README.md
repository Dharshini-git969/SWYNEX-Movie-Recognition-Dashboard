# 🎬 Movie Recognition & Popularity Analysis Dashboard

## 📌 Project Overview

This project is an interactive Power BI dashboard developed as part of my **SWYNEX Technologies Data Analytics Internship – Task 3**.

The project explores an interesting question:

> **Why do some highly rated movies receive relatively little recognition, while some moderately rated movies become highly popular?**

Using the **MovieLens 25M dataset**, the dashboard analyzes the relationship between movie ratings and the number of ratings received by each movie.

The project focuses on identifying patterns in **movie quality, audience recognition, popularity, genres, and release years** through interactive data visualization.

---

## 🎯 Problem Statement

A high rating does not necessarily mean that a movie is widely recognized.

Some movies receive excellent ratings but have relatively few ratings, while other movies receive a very large number of ratings despite having only moderate ratings.

This project investigates:

- Which movies receive the highest number of ratings?
- Are highly rated movies always highly recognized?
- Can highly rated movies with fewer ratings be considered "Hidden Gems"?
- Which movies become popular despite having moderate ratings?
- How does movie recognition vary across genres?
- How has the number of movies changed over the years?

---

## 📊 Dataset

### MovieLens 25M Dataset

Source: **GroupLens Research**

The MovieLens 25M dataset contains movie ratings and movie metadata collected from MovieLens users.

### Main files used:

- `movies.csv`
- `ratings.csv`

### Additional files available:

- `tags.csv`
- `links.csv`
- `genome-scores.csv`
- `genome-tags.csv`

---

## 🛠️ Tools & Technologies

- **Power BI**
- **Power Query**
- **DAX**
- **Data Cleaning & Transformation**
- **Data Modeling**
- **Interactive Data Visualization**
- **Microsoft Excel / CSV**

---

## 🧹 Data Preparation

The dataset was prepared using Power Query.

### Movie data preparation

The movie dataset was transformed to create:

- Movie ID
- Movie Title
- Genres
- Release Year

The release year was extracted from the movie title and converted into a numeric field.

The `(no genres listed)` category was also handled as `Unknown`.

### Ratings data preparation

The ratings dataset was transformed into:

- User ID
- Movie ID
- Rating
- Rating Date

The original Unix timestamp was converted into a readable date format.

---

## 🏗️ Data Model

The project follows a simplified analytical/star-schema approach.

### Main tables

**Dim Movie**
- Movie ID
- Movie Title
- Genres
- Release Year

**Fact Ratings**
- User ID
- Movie ID
- Rating
- Rating Date

**Dim Genre**
- Movie ID
- Genre

**Movie Analysis**
- Movie ID
- Movie Title
- Genres
- Release Year
- Average Rating
- Rating Count
- Rater Count
- Movie Recognition

Relationships were created between the movie, genre, and ratings data to support interactive filtering.

---

## 📐 Key DAX Measures

### Average Rating

```DAX
Average Rating =
AVERAGE('Fact Ratings'[Rating])
