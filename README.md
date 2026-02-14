## Project Overview
This project analyzes best selling books from 2023 to 2025 using MySQL.
The dataset includes book title, author, rating, reviews count, price, print length, publishing date, genre, and year.

The three yearly datasets were merged into one structured table to enable comprehensive analysis and trend comparison.

## Project Objectives

etermine total books per year

Identify the highest-rated book overall

Find the most reviewed (most popular) book

Determine the most expensive book

Analyze the most popular genre

## Tools Used
MySQL (Aggregation, GROUP BY, ORDER BY, UNION, Subqueries)

## Data Preparation

Three separate tables:

best_selling_books_2023

best_selling_books_2024

best_selling_books_2025

Were combined into one master table:

```sql
CREATE TABLE best_selling_books_all (
    id INT AUTO_INCREMENT PRIMARY KEY,
    book_name TEXT,
    author TEXT,
    rating DECIMAL(2,1),
    reviews_count INT,
    form TEXT,
    price DOUBLE,
    print_length INT,
    publishing_date DATE,
    genre TEXT,
    year INT
);
```
## Key Analysis Queries

### 1. Total Books Per Year

```sql
SELECT year, COUNT(*) AS total_books
FROM best_selling_books_all
GROUP BY year
ORDER BY year;
```

### 2. Highest Rated Book Overall

```sql
SELECT book_name, author, rating, year
FROM best_selling_books_all
ORDER BY rating DESC
LIMIT 1;
```

### 3. Most Reviewed Book (Most Popular)

```sql
SELECT book_name, author, reviews_count, year
FROM best_selling_books_all
ORDER BY reviews_count DESC
LIMIT 1;
```

### 4. Most Expensive Book

```sql
SELECT book_name, author, price, year
FROM best_selling_books_all
ORDER BY price DESC
LIMIT 1;
```
### 5. Most Popular Genre

```sql
SELECT genre, COUNT(*) AS total_books
FROM best_selling_books_all
GROUP BY genre
ORDER BY total_books DESC;

```

## Insights

Identified the top-performing book based on rating.

Determined the most popular book using review count.

Analyzed genre trends across multiple years.

## Skills Demonstrated
Data Cleaning

Table Merging (UNION & INSERT INTO SELECT)

Aggregation Functions (COUNT, MAX, AVG, SUM)

Subqueries

Sorting & Grouping

Database Structuring

## Conclusion
This project demonstrates practical SQL skills in data merging, analysis, and performance comparison across multiple datasets. It highlights the ability to extract meaningful insights from structured data using MySQL.













