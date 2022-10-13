# Task
Query the list of **CITY** names starting with vowels (i.e., a, e, i, o, or u) from **STATION**. Your result cannot contain duplicates.
The **STATION** table is described as follows:

### STATION

| Field       | Type         |  
| :---------- | :----------- |
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude. <br>

# SOLUTION
1.1 แบบสายถึก
```
SELECT 
FROM STATION
WHERE CITY LIKE 'A%' 
   OR CITY LIKE 'E%' 
   OR CITY LIKE 'I%' 
   OR CITY LIKE 'O%' 
   OR CITY LIKE 'U%'
ORDER BY CITY;
```
1.2 ย่อ 1.1 ให้สะอาดขึ้น
```
SELECT distinct city 
FROM station 
WHERE city like '[aeuio]%' 
ORDER BY City;
```
2. แบบหั่นตัวอักษร
```
SELECT DISTINCT CITY
FROM STATION
WHERE UPPER(SUBSTR(CITY, 1, 1)) IN ('A','E','I','O','U');
```
3. แบบใช้ Regex
```
SELECT 
FROM STATION
WHERE CITY REGEXP '^[aeiouAEIOU]'
ORDER BY CITY;
```