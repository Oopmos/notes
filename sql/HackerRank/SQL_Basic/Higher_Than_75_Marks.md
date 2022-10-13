# Task
Query the Name of any student in **STUDENTS** who scored higher than 75 Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

### Input Format

| Column      | Type         |  
| :---------- | :----------- |
| ID          | Integer      |
| Name        | String       |
| Marks       | Integer      |

The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.

### Sample Input

| ID | Name         | Marks |   
| :- | :----------- | :---- |
| 1  | Ashley       | 81    |
| 2  | Samantha     | 75    |
| 3  | Julia        | 76    |
| 4  | Belvet       | 84    |

### Sample Output
```
Ashley
Julia
Belvet
```

# SOLUTION
1. ใช้ SUBSTR()
```
SELECT name
FROM students
WHERE marks > 75
ORDER BY SUBSTR(name, -3, 3), id;
```
2. ใช้ RIGHT()
```
SELECT name
FROM students
WHERE marks > 75
ORDER BY RIGHT(name, 3), id;
```

### Explansion
โจทย์อยากให้แสดงชื่อคนที่มีคะแนนมากกว่า 75 คะแนนโดย
1. เรียงตามตัวอักษร 3 ตัวท้ายของชื่อ
2. หากตัวอักษรตัวท้าย 3 ตัวซ้ำทุกตัว ให้เรียงตามเลข ID