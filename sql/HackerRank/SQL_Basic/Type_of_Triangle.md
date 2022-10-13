# Task
Write a query identifying the type of each record in the **TRIANGLES** table using its three side lengths. Output one of the following statements for each record in the table:

- Equilateral: It's a triangle with 3 sides of equal length.
- Isosceles: It's a triangle with 2 sides of equal length.
- Scalene: It's a triangle with 3 sides of differing lengths.
- Not A Triangle: The given values of A, B, and C don't form a triangle.

### TRIANGLES

| Column | Type     |  
| :----- | :------- |
| A      | Integer  |
| B      | integer  |
| C      | Integer  |

Each row in the table denotes the lengths of each of a triangle's three sides.

### Sample Input

| A   | B   | C   | 
| :-- | :-- | :-- |
| 20  | 20  | 23  |
| 20  | 20  | 20  |
| 20  | 21  | 22  |
| 15  | 15  | 30  |

### Sample Output
```
Isosceles
Equilateral
Scalene
Not A Triangle
```

### Sample Explansion

- Values in the tuple $(20, 20, 23)$ form an Isosceles triangle, because $A \equiv B$.
- Values in the tuple $(20, 20, 20)$ form an Equilateral triangle, because $A \equiv B \equiv C$.
- Values in the tuple $(20, 21, 22)$ form a Scalene triangle, because $A \neq B \neq C$.
- Values in the tuple $(15, 15, 30)$ cannot form a triangle because the combined value of sides $A$ and $B$ is not larger than that of side $C$.

# SOLUTION
```
SELECT
    CASE
        WHEN a+b<=c OR a+c<=b OR b+c<=a THEN 'Not A Triangle'
        WHEN a=b AND b=c                THEN 'Equilateral'
        WHEN a=b OR a=c OR b=c          THEN 'Isosceles'
        ELSE 'Scalene'
    END
FROM triangles;
```