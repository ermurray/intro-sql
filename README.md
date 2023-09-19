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

# SQL Challenges

1. list all songs
```sql
-- sql comment

```

2. list all albums
```sql
```

3. list the total number of songs
```sql
```

4. list the songs with a rating over 8
```sql

```
5. list all albums from before 2008
```sql

```
6. list all albums from before 2008 and have a genere of "folk"
```sql

```
7. List the albums that have genre of "folk" arranged alphabetically by artist and then by release date newest to oldest.
```sql
```
8. List all genres only once.
```sql

```
9. list all albums yet to be released
```sql

```
10. list all albums along with their songs.
```sql

```
11. list all of the albums and how many songs each album has
```sql

```
12. list all albums with more than 10 songs.
```sql

```
13. list all albums with a average song rating
```sql

```
14. list 10 songs only
```sql

```
15. list top 10 songs by raiting
```sql

```
16. OFFSET 
```sql
```
### Useful Links
- [Top 10 Most Popular RDBMSs](https://www.c-sharpcorner.com/article/what-are-the-most-popular-relational-databases/)
- [Another Ranking of DBMSs](https://db-engines.com/en/ranking)
- [SELECT Queries Order of Execution](https://sqlbolt.com/lesson/select_queries_order_of_execution)
- [SQL Joins Visualizer](https://sql-joins.leopard.in.ua/)