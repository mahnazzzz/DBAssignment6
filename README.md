
## Excercise 1

In the `classicmodels` database, write a query that picks out those customers who are in the same city as office of their sales representative.

### Hand-in:
Insert into the readme file: the query and the graphical execution plan which can be obtained from the query. Explain what is the main performance problem for this query. Do not try to optimize the database for this query (yet).

### Review:
* Are you able to use the query?
* Do you have the same explanation?
* If you find the explanation good or bad - say so, and be constructive.

## Exercise 2
Change the database schema so that the query from exercise get better performance. 

### Hand-in:
Explain in the readme file what changes you did, if you changed the query or the schema. Insert a new graphical execution plan, and point out in the readme file why this new one is better.

### Review:
* Are you able to reproduce the speedup?
* Do you agree with the explanation?
* If you find the explanation good or bad - say so, and be constructive.

## Exercise 3
We want to find out how much each office has sold and the max single payment for each office. Write two queries which give this information

a) using grouping<br>
b) using windowing

For each of the two solutions, check its graphical execution plan.

### Hand-in:
The two queries and the graphical execution plans. Explain any differences and try to explain why there is or is not any difference.

### Review:
* Are you able to reproduce the difference?
* Do you agree with the explanation?
* If you find the explanation good or bad - say so, and be constructive.

## Exercise 4
In the stackexchange forum for coffee (coffee.stackexchange.com), write a query which return the displayName and title of all posts which with the word `grounds`in the title.

> If you want to challenge yourself a bit, use the ubuntu stackexchange instead, and search for `grep` rather than `grounds` in this and exercise 5.
