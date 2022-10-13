# Cheat Sheet FOR ME
### String Manipulation <br>
```python
string = "Hello World!"
```

1. เปลี่ยนตัวอักษรพิมพ์ใหญ่เป็นพิมพ์เล็ก
```python
string.lower()
# hello world!
```

2. เปลี่ยนตัวอักษรพิมพ์เล็กเป็นพิมพ์ใหญ่
```python
string.upper()
# HELLO WORLD!
```

3. เปลี่ยนตัวอักษรพิมพ์ใหญ่เป็นพิมพ์เล็ก และเปลี่ยนตัวอักษรพิมพ์เล็กเป็นพิมพ์ใหญ่
```python
string.swapcase()
# hELLO wORLD!
```

4. ทำให้ตัวอักษรตัวแรกเป็นพิมพ์ใหญ่
```python
string.capitalize()
```

5. เลือกตัวอักษรบางตัวจากกลุ่มตัวอักษร
```python
string[2:5]
# ll0

string[:5]
# Hello

string[6:]
# World!

[start index : end index but not included]
```

6. แยกคำที่มีการเว้นวรรค โดยนำคำที่แยกไปใส่ใน list
```python
list_string = string.split()
# list_string = ["Hello", "World!"]
```

7. รวมคำจาก list สามารถกำหนดตัวอักษรที่มาคั่นระหว่างคำได้
```python
list_string = ["Hello", "World!"]

join_string = '-'.join(list_string)
# join_string = Hello-World!

join_string = ''.join(list_string)
# join_string = HelloWorld!
```

8. หาคำที่กำหนด
```python
หาจากซ้ายไปขวา
string.find(H)
# 1

หาจากขวาไปซ้าย
string.rfind(l)
# 3

* ถ้าหาด้วยกลุ่มคำแนะนำไปดู Find_a_string.md ใน HackerRank\Python_Basic
```

9. จัดตำแหน่งตัวอักษร
```python
width = 20

print 'HackerRank'.ljust(width,'-')
# HackerRank----------

print 'HackerRank'.center(width,'-')
# -----HackerRank-----

print 'HackerRank'.center(width)
#      HackerRank

print 'HackerRank'.rjust(width,'-')
# ----------HackerRank
```