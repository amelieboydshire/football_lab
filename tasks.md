# Football Matches - Tasks

Each of the questions/tasks below can be answered using a `SELECT` query. When you find a solution copy it into the code block under the question before pushing your solution to GitHub.

1) Find all the matches from 2017.

```sql
SELECT * from matches WHERE season = 2017



```

2) Find all the matches featuring Barcelona.

```sql
SELECT * FROM matches WHERE hometeam = 'Barcelona' OR awayteam = 'Barcelona';


```

3) What are the names of the Scottish divisions included?

```sql
SELECT name FROM divisions WHERE country = 'Scotland';


```

4) Find the value of the `code` for the `Bundesliga` division. Use that code to find out how many matches Freiburg have played in that division. HINT: You will need to query both tables

```sql
SELECT code FROM divisions WHERE name = 'Bundesliga';
SELECT COUNT(*) FROM matches WHERE division_code = 'D1' and (hometeam = 'Freiburg' or awayteam = 'Freiburg');



```

5) Find the teams which include the word "City" in their name. 
```sql
SELECT hometeam FROM matches WHERE hometeam LIKE '%City%' GROUP BY hometeam;

```

6) How many different teams have played in matches recorded in a French division?

```sql
SELECT code FROM divisions WHERE country = 'France';
SELECT COUNT(DISTINCT team) AS different_teams_count
FROM (
    SELECT hometeam AS team FROM matches WHERE division_code IN ('F1', 'F2')
    
    UNION
    
    SELECT awayteam AS team FROM matches WHERE division_code IN ('F1', 'F2')
) AS all_teams;


```

7) Have Huddersfield played Swansea in any of the recorded matches?

```sql
<!-- Copy solution here -->


```

8) How many draws were there in the `Eredivisie` between 2010 and 2015?

```sql
<!-- Copy solution here -->


```

9) Select the matches played in the Premier League in order of total goals scored from highest to lowest. When two matches have the same total the match with more home goals should come first.

```sql
<!-- Copy solution here -->


```

10) In which division and which season were the most goals scored?

```sql
<!-- Copy solution here -->


```

### Useful Resources

- [Filtering results](https://www.w3schools.com/sql/sql_where.asp)
- [Ordering results](https://www.w3schools.com/sql/sql_orderby.asp)
- [Grouping results](https://www.w3schools.com/sql/sql_groupby.asp)