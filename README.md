# intro-sql
LightHouse Labs Lecture intro to SQL notes

# TOPICS
- [ ] Intro to RDBMS
- [ ] Relational data model
- [ ] DDL vs DML
- [ ] `SELECT` statements
- [ ] Filtering and ordering
- [ ] Joining tabels
- [ ] Grouping records
- [ ] Aggregation functions
- [ ] `LIMIT` and `OFFSET` ?


### RDBMS
  app<===Tcp/HTTP===>Web server/api<==TCP/postgres===>RDBMS(psql)
  https://someurl.com                               postgres://databesename@username
- A program that serves, **and** controls interactions with, one or more _Relational Databases_
- Communicates using a custom protocol (eg. `postgres://` for postgres) that sits on top of TCP
### Structured Data
- The **S** in **SQL** is for _structured_. This means that our data must conform to a _structure_ in order to store it in the database.
- The data itself is stored in **tables** which define things such as field names, data types, and other data constraints
- You are probably familiar with tables already if you've used programs like Excel or Calc
- Tables are made up of **columns** and **rows**
  - Columns are called `fields`
  - Rows are called `records`
- Each table describes an entity (eg. `users`, `products`, `shifts`, `tweets`)
  - The fields represent properties of the entity
  - Each record represents one unique entity
### keys
- In order to reference a particular record in a table, each one is given a unique identifier we call a **Primary Key**
- Other tables can then make reference to a particular record in another table by storing the Primary Keys value
- We call a Primary Key stored in another table a **Foreign Key**
- It is through this Primary Key/Foreign Key relationship that our tables are _related_ to one another

### `JOIN`
- We connect tables together using **JOIN**s
- The tables are joined together using the primary key and foreign key
- There are various types of joins:
  - `INNER JOIN`: The default. Return only records that have matching records in the other table
  - `LEFT JOIN`: Return all records from the "left" table and only those from the other table that match
  - `RIGHT JOIN`: The same as a _LEFT JOIN_, but from the _RIGHT_ instead
  - `FULL OUTER JOIN`: Return all records from both tables
# SQL Challenges

1. list all songs
```sql
-- sql comment
  SELECT * FROM songs;
```

2. list all albums
```sql
  SELECT * FROM albums;
```

3. list the total number of songs
```sql
  SELECT  COUNT(*) AS song_count
    FROM  songs;
```

4. list the songs with a rating over 8
```sql
  SELECT *
  FROM songs
  WHERE rating > 8;
```
5. list all albums from before 2008
```sql
 SELECT *
 FROM albums
 WHERE release_date < 'January 1, 2008';
```
6. list all albums from before 2008 and have a genere of "folk"
```sql
  SELECT *
  FROM albums
  WHERE release_date < 'January 1, 2008'
  AND genre = 'folk';

```
7. List the albums that have genre of "folk" arranged alphabetically by artist and then by release date newest to oldest.
```sql
  SELECT *
  FROM albums
  WHERE genre = 'folk'
  ORDER BY artist_name, release_date asc;
```
8. List all genres only once.
```sql
  SELECT DISTINCT genre
  FROM albums;
```
9. list all albums yet to be released
```sql
  SELECT *
  FROM albums
  WHERE release_date > NOW(); -- issue with dat and time vrs CURRENT_DATE
```
10. list all albums along with their songs.
```sql
  SELECT * 
  FROM albums
  JOIN songs ON albums.id = songs.album_id;
```
11. list all of the albums and how many songs each album has
```sql
  SELECT album_name, COUNT(songs.id) AS num_songs
  FROM albums
  JOIN songs ON albums.id = songs.album_id
  GROUP BY album_name;

```
12. list all albums with more than 10 songs.
```sql
  SELECT album_name, COUNT(songs.id) AS num_songs
  FROM albums
  JOIN songs ON albums.id = songs.album_id
  GROUP BY album_name
  HAVING COUNT(songs.id) > 10;

```
13. list all albums with a average song rating
```sql
  SELECT album_name, artist_name, ROUND(AVG(rating) * 10) / 10 AS average_rating
  FROM albums
  JOIN songs ON albums.id = songs.album_id
  GROUP BY album_name, artist_name;
```
14. list 10 songs only
```sql
SELECT *
FROM songs
LIMIT 10;

```
15. list top 10 songs by raiting
```sql

```
16. OFFSET 
```sql
  SELECT *
  FROM songs
  LIMIT 10
  OFFSET 20;
```
### Useful Links
- [Top 10 Most Popular RDBMSs](https://www.c-sharpcorner.com/article/what-are-the-most-popular-relational-databases/)
- [Another Ranking of DBMSs](https://db-engines.com/en/ranking)
- [SELECT Queries Order of Execution](https://sqlbolt.com/lesson/select_queries_order_of_execution)
- [SQL Joins Visualizer](https://sql-joins.leopard.in.ua/)