# SQL
SQL = Structured Query Languges
* SQL is case insensitive ตัวอักษรพิมพ์เล็กพิมพ์ใหญ่ไม่มีผล

# SQL Clause
| SQL Clause | Action                                       |  
| :--------- | :------------------------------------------- |
| SELECT     | เลือก column ที่ต้องการ (select columns)         |
| WHERE      | เลือก column ที่ต้องการ (filter rows)            |
| ORDER BY   | เรียงข้อมูลจากน้อยไปมาก หรือมากไปน้อย             |
| GROUP BY   | จับกลุ่มให้ข้อมูล (ใช้ร่วมกับ AGGREGATE FUNCTION)    |
| HAVING     | เลือกกลุ่มที่เราต้องการ (ใช้คู่กับ GROUP BY)           |

# Aggregate Function
| Aggregate Function | Action                                           |
| :----------------- | :----------------------------------------------- | 
| COUNT()            | นับจำนวน rows ใน column ที่กำหนด                   |
| SUM()              | ผลรวมของข้อมูลใน ใน column ที่กำหนด                 |
| MIN() MAX()        | หาค่าน้อยสุด และมากสุดใน column ที่กำหนด              |
| ROUND()            | กำหนดจำนวนทศนิยมให้ข้อมูลที่ต้องการ (ปัดขึ้น)             |
| FLOOR()            | กำหนดจำนวนทศนิยมให้ข้อมูลที่ต้องการ (ปัดลง)             |
| ABS()              | หาค่าสัมบูรณ์ของ column ที่กำหนด                      |
| SQRT()             | หารากที่ 2 ของ column ที่กำหนด                      |
| POWER()            | ยกกำลัง column ที่กำหนด                            |
| LENGTH()           | นับจำนวนตัวอักษรในข้อความ หรือ column ที่กำหนด         |
| REPLACE()          | แทน 'ตัวอักษร' ด้วย 'ตัวอักษร' ใน column ที่กำหนด      |
| CONCAT()           | รวม string เข้าด้วยกัน                               |
| UPPER() LOWER()    | ทำให้เป็นตัวพิมพ์ใหญ่ และพิมพ์เล็กทั้งหมดตามลำดับ          |
| LEFT() RIGHT()     | เลือกตัวอักษรจากทางซ้ายสุด และขวาสุดตามลำดับ           |
| SUBSTR()           | หั่นข้อความใน column ที่กำหนด (กำหนดจุดเริ่ม และจุดสิ้นสุด) |
| REGEXP ''          | ใช้คู่กับ opearators โดยใช้ Regex ช่วย                 |

# การใช้งาน Aggregate Function
### Number
- COUNT(Column)
- SUM(Column)
- MIN(Column), MAX(Column)
- ROUND(Column, จำนวนจุดทศนิยม)
- FLOOR(Column, จำนวนจุดทศนิยม)
- ABS(Column)
- SQRT(Column)
- POWER(Column, เลขยกกำลัง)
### String
- LENGTH(Column)
- REPLACE(Column, ตัวอักษรที่ต้องการเปลี่ยน, ตัวอักษรที่จะใช้เปลี่ยน)
- CONCAT(String1, String2, ...., String_n) ใช้ column ได้
- UPPER(Column), LOWER(Column)
- LEFT(Column, จำนวนตัวอักษรที่ต้องการ), RIGHT(Column, จำนวนตัวอักษรที่ต้องการ)
- SUBSTR(Column, ตำแหน่งคำที่หั่นคำแรก, ตำแหน่งคำที่หั่นตำแหน่งสุดท้าย)

### RECOMEND TO READ!
- Weather_Observation_Station_5.md
- Weather_Observation_Station_6.md
- CASE -> Type_of_Triangle.md