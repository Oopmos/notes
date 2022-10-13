# Task
The included code stub will read an integer, $n$, from STDIN.

Without using any string methods, try to print the following:
$123...n$

Note that "$...$" represents the consecutive values in between.

# Example
### Input
```
n = 5
```
### Output
```
12345
```
# Solution

```
if __name__ == '__main__':
    n = int(input())
    [print(i+1, end="") for i in range(n)] 
```