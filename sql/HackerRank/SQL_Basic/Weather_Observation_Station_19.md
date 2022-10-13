# Task
Consider $P_1(a,c)$ and $P_2(b,d)$ to be two points on a 2D plane where $(a,b)$ are the respective minimum and maximum values of Northern Latitude (LAT_N) and $(c,d)$ are the respective minimum and maximum values of Western Longitude (LONG_W) in **STATION**.

Query the **Euclidean Distance** between points $P_1$ and $P_2$ and format your answer to display  decimal digits.

### Euclidean Distance
**Two dimensions** <br>
In the Euclidean plane, let point $p$ have Cartesian coordinates $(p_1,p_2)$ and let point $q$ have coordinates $(q_1,q_2)$. Then the distance between $p$ and $q$ is given by: <br>

$d(p,q)=\sqrt{(q_1 - p_1)^2 + (q_2 - p_2)^2}$

In this problem:

$d(P_1,P_2)=\sqrt{(b - a)^2 + (d - c)^2}$

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
SELECT ROUND( SQRT( POWER( MAX(lat_n)-MIN(lat_n), 2 ) +
                   POWER( MAX(long_w)-MIN(long_w), 2 ) ), 4 )
FROM station;
```