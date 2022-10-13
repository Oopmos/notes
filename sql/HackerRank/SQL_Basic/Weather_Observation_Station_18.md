# Task
Consider $P_1(a,b)$ and $P_2(c,d)$ to be two points on a 2D plane.

- $a$ happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
- $b$ happens to equal the minimum value in Western Longitude (LONG_W in STATION).
- $c$ happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
- $d$ happens to equal the maximum value in Western Longitude (LONG_W in STATION).

Query the **Manhattan Distance** between points $P_1$ and $P_2$ and round it to a scale of  decimal places.

### Manhattan Distance
The distance between two points measured along axes at right angles. In a plane with $P_1$ at $(x_1, y_1)$ and $P_2$ at $(x_2, y_2)$, it is $|x_1 - x_2| + |y_1 - y_2|$.

### STATION

| Field       | Type         |  
| :---------- | :----------- |
| ID          | NUMBER       |
| CITY        | VARCHAR2(21) |
| STATE       | VARCHAR2(2)  |
| LAT_N       | NUMBER       |
| LONG_W      | NUMBER       |

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

# SOLUTION
```
SELECT  ROUND( ABS( MIN(lat_n) - MAX(lat_n) ) + 
              ABS( MIN(long_w) - MAX(long_w) ), 4 )
FROM station;
```