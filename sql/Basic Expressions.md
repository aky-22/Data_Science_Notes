Database'e göre farklı işlem fonksiyonları varmış.


```sql
SELECT title, (domestic_sales + international_sales) / 1000000
AS Total_sales_in_millions
FROM movies
INNER JOIN boxoffice
ON id = movie_id;
```


```sql
SELECT title, rating * 10 AS rating_percent
FROM movies
INNER JOIN boxoffice
ON id = movie_id;
```


```sql
SELECT title AS rating_percent
FROM movies
WHERE year % 2 = 0;
```