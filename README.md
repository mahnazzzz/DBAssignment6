
## Excercise 1

In the `classicmodels` database, write a query that picks out those customers who are in the same city as office of their sales representative.

```sh
select  officeAndCustomersT.customerNumber
from officeAndCustomersT
group by customerNumber
order by customers.city DESC;

SELECT 
    c.customerNumber, c.city, o.officeCode, o.city
   FROM
    employees AS e
        INNER JOIN
    offices AS o ON e.officeCode=o.officeCode
    INNER JOIN customers as c ON c.city= o.city
GROUP BY c.customerNumber;
```


## Exercise 2
Change the database schema so that the query from exercise get better performance. 
create Index on city in customers

### Befor 
![alt text]()

## Exercise 3
We want to find out how much each office has sold and the max single payment for each office. Write two queries which give this information

a) using grouping<br>
b) using windowing

### a
```sh
SELECT 
    e.officeCode, SUM(od.priceEach) AS totalPaid, max(p.amount) as maximumPrice
   FROM
    orderdetails as od
    INNER JOIN
    orders AS o ON o.orderNumber = od.orderNumber
    INNER JOIN  
    customers AS c ON c.customerNumber= o.customerNumber
    INNER JOIN
    payments AS p ON p.customerNumber= o.customerNumber
    INNER JOIN
    employees AS e ON c.salesRepEmployeeNumber = e.employeeNumber   
GROUP BY e.officeCode;
```
### b
```sh
SELECT 
    e.officeCode ,  
    sum(p.amount) OVER (PARTITION BY e.officeCode) as totalAmountPerOffice,
    sum(od.quantityOrdered)  OVER (PARTITION BY e.officeCode) as amountOFOrder
   FROM
    orderdetails as od
    INNER JOIN
    orders AS o ON o.orderNumber = od.orderNumber
    INNER JOIN  
    customers AS c ON c.customerNumber= o.customerNumber
    INNER JOIN
    payments AS p ON p.customerNumber= o.customerNumber
    INNER JOIN
    employees AS e ON c.salesRepEmployeeNumber = e.employeeNumber ;  
```

## Exercise 4
In the stackexchange forum for coffee (coffee.stackexchange.com), write a query which return the displayName and title of all posts which with the word `grounds`in the title.



## Exercise 5
Add a full text index to the `posts` table and change the query from exercise 4 so it no longer scans the entire `posts` table. 


