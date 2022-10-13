# Task
Query the list of **CITY** names from **STATION** that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.
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
```
SELECT      distinct city
FROM        station
WHERE       city regexp '^[^aeiouAEIOU].*[^aeiouAEIOU]$'
ORDER BY    city;
```