# Task
You are given a string $S$ and width $w$.
Your task is to wrap the string into a paragraph of width $w$.

### Returns

string: a single string with newline characters ('\n') where the breaks should be

# Example
### Input
```
ABCDEFGHIJKLIMNOQRSTUVWXYZ
4
```
### Output
```
ABCD
EFGH
IJKL
IMNO
QRST
UVWX
YZ
```
# Solution

```
import textwrap

def wrap(string, max_width):
    list_string = []
    list_string.extend(string[i:i+max_width] for i in range(0, len(string), max_width))    
    return '\n'.join(list_string)

if __name__ == '__main__':
    string, max_width = input(), int(input())
    result = wrap(string, max_width)
    print(result)
```
หลักการทำงานของฟังก์ชัน
1. สร้าง list รองรับชุดตัวอักษรตามความยาวที่ต้องการ
2. ใช้ list comprehension ในการเพิ่มสตริงที่หั่นด้วยตัวดำเนินการ $i$ ที่ใช้ for loop โดยเริ่มที่ตำแหน่ง 0 และจบตำแหน่งตามความยาวของ string โดยจะเพิ่มสเต็ปตามความยาวที่กำหนดเพื่อกันไม่ให้ไปดำเนินการตัวอักษรที่หั่นมาใส่ list แล้ว
3. return string ที่เกิดจากการนำ list ที่เก็บชุดตัวอักษรที่ต้องการนำมารวมกัน โดยคั่นระหว่างสมาชิกใน list ด้วยการเว้นบรรทัด '\n'
4. นำ string ที่ได้เก็บใส่ตัวแปร result และนำมา print