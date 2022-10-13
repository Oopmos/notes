# Task
Given the names and grades for each student in a class of N students, store them in a nested list and print the name(s) of any student(s) having the second lowest grade.

__Note__: If there are multiple students with the second lowest grade, order their names alphabetically and print each name on a new line.

# Example
### Input
```
5
Harry
37.21
Berry
37.21
Tina
37.2
Akriti
41
Harsh
39
```
### Output
```
Berry
Harry
```
# Solution

```
if __name__ == '__main__':
    n = int(input())
    dict_grade = {}
    for _ in range(n):
        name = input()
        dict_grade[name] = float(input())
        
    list_name = list(dict_grade.keys())    
    list_grade = list(dict_grade.values())

    # find second lowest grade      
    lowest = 100
    second_lowest = 101
    for _ in range(n):
        if list_grade[_]<lowest:
            second_lowest = lowest
            lowest = list_grade[_]
        elif lowest<list_grade[_]<second_lowest:
            second_lowest = list_grade[_]
    
    # use second lowest grade to track index of name then print sorted name
    second_lowest_name = []        
    for _ in range (n):
        if list_grade[_]==second_lowest:
            second_lowest_name.append(list_name[_])
    second_lowest_name.sort()
    [print(_) for _ in second_lowest_name]
```