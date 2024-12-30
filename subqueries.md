SQL subqueries are: nested SELECT statements within another SQL statement.
```
Example: General subquery
Lets say your company has a list of all Sales Associates, with data on the revenue that each Associate brings in, and their individual salary. Times are tight, and you now want to find out which of your Associates are costing the company more than the average revenue brought per Associate.

First, you would need to calculate the average revenue all the Associates are generating:
```
```
SELECT AVG(revenue_generated)
FROM slaes_associates
```
 then using that result, we can then compare the costs of each of the Associates against that value. To use it as a subquery, we can just write it straight into the WHERE clause of the query:
```
SELECT *
FROM sales_associates
WHERE salary >
   (SELECT AVG(revenue_generated) FROM slaes_associates);
```
