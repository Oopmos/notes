# Task
Query the two cities in **STATION** with the shortest and longest **CITY** names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically. <br>
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

### SAMPLE INPUT
For example, CITY has five entries: DEF, ABC, PQRS, TUVW and XYZ.

### Sample Output
```
ABC 3
PQRS 4
```

# SOLUTION
```
SELECT CITY, LENGTH(CITY)
FROM STATION
ORDER BY LENGTH(CITY) ASC, CITY
LIMIT 1;


SELECT CITY, LENGTH(CITY)
FROM STATION
ORDER BY LENGTH(CITY) DESC, CITY
LIMIT 1;
```

### Explanation
ทำด้วยการ 2 query
1. หาเมืองที่มีตัวอักษรน้อยที่สุดโดยเรียงตามตัวอักษร A-Z
2. หาเมืองที่มีตัวอักษรมากที่สุดโดยเรียงตามตัวอักษร A-Z

โดยจะใช้ LENGHT() เพื่อหาความยาวของตัวอักษร จากนั้นสั่งให้เรียงตามจำนวนน้อยที่สุด และมากที่สุด จากนั้นเรียงตัวอักษร A-Z ลำดับสุดท้ายให้แสดงแค่ 1 ค่าที่เป็น MIN และ MAX ตามลำดับ
