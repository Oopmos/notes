# Task
The provided code stub will read in a dictionary containing key/value pairs of name:[marks] for a list of students. Print the average of the marks array for the student name provided, showing 2 places after the decimal.

* $2 \le n \le 10$
* $0 \le marks[i] \le 100$
* length of mark array $=3$

# Example
### Input
```
3
Krishna 67 68 69
Arjun 70 98 63
Malika 52 56 60
Malika
```
### Output
```
56.00
```
# Solution

```
if __name__ == '__main__':
    n = int(input())
    student_marks = {}
    for _ in range(n):
        name, *line = input().split()
        scores = list(map(float, line))
        student_marks[name] = scores
    query_name = input()
    
    
    marks = (student_marks[query_name])
    total = 0
    for i in range(3):
        total += marks[i]
        
    avg = total/3
    print("{:.2f}".format(avg))
```