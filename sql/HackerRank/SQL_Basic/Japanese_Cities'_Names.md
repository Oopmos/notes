# Task
Query the names of all the Japanese cities in the **CITY** table. The **COUNTRYCODE** for Japan is **JPN**. <br>
The **CITY** table is described as follows:

### CITY

| Field       | Type         |  
| :---------- | :----------- |
| ID          | NUMBER       |
| NAME        | VARCHAR2(17) |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT    | VARCHAR2(20) |
| POPULATION  | NUMBER       |

# SOLUTION
```
SELECT NAME
FROM CITY
WHERE COUNTRYCODE="JPN";
```