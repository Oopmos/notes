# Task
Given the participants' score sheet for your University Sports Day, you are required to find the runner-up score. You are given $n$ scores. Store them in a list and find the score of the runner-up. > __Print Second_highest score__

The first line contains $n$. The second line contains an array $A[]$ of $n$ integers each separated by a space.


# Example
### Input
```
5
2 3 6 6 5
```
### Output
```
5
```
# Solution

```
if __name__ == '__main__':
    n = int(input())
    arr = map(int, input().split())
    
    highest = -100
    second_highest = 0
    
    for i in arr:
        if i>highest:
            second_highest = highest
            highest = i
            
        elif second_highest<i<highest:
            second_highest = i
            
    print(second_highest)
```