# Problem

Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

- Not A Triangle: The given values of A, B, and C don't form a triangle.
- Equilateral: It's a triangle with sides of equal length.
- Isosceles: It's a triangle with sides of equal length.
- Scalene: It's a triangle with sides of differing lengths. Input Format
- The TRIANGLES table is described as follows:

Each row in the table denotes the lengths of each of a triangle's three sides.

**Sample Input**

| A | B | C |
|---|---|---|
|20 |20 |23 |
|20 |20 |20 |
|20 |21 |22 |
|13 |14 |30 |

**Sample Output**

- Isosceles
- Equilateral
- Scalene
- Not A Triangle




# Solution

```sql
SELECT
  CASE 
    WHEN A + B <= C or A + C <= B or B + C <= A THEN 'Not A Triangle'
    WHEN A = B and B = C THEN 'Equilateral'
    WHEN A = B or A = C or B = C THEN 'Isosceles'
    WHEN A <> B and B <> C THEN 'Scalene'
  END TRINGLE_TYPE
FROM TRIANGLES;
```

