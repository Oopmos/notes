# Task
You are given a string. Split the string on a " " (space) delimiter and join using a - hyphen.

### Tip
```
>>> a = "this is a string"
>>> a = a.split(" ") # a is converted to a list of strings. 
>>> print a
['this', 'is', 'a', 'string']
```
Joining a string is simple:
```
>>> a = "-".join(a)
>>> print a
this-is-a-string 
```

# Example
### Input
```
this is a string   
```
### Output
```
this-is-a-string
```
# Solution

```
def split_and_join(line):
    return "-".join(line.split())
    
if __name__ == '__main__':
    line = input()
    result = split_and_join(line)
    print(result)
```