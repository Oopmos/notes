# Task
You are given the firstname and lastname of a person on two different lines. Your task is to read them and print the following:
```
Hello firstname lastname! You just delved into python.
```

# Example
### Input
```
Ross
Taylor
```
### Output
```
Hello Ross Taylor! You just delved into python.
```

# Solution

```
def print_full_name(first, last):

    '''
    # Nomal Way
    print("Hello " + first + " " + last + "! You just delved into python.")
    # or
    print("Hello",first,last + "! You just delved into python.")
    
    # Use .format
    print("Hello {} {}! You just delved into python.".format(first, last))
    # or
    print("Hello {0} {1}! You just delved into python.".format(first, last))
    '''
    
    #Python 3.6+
    print(f"Hello {first} {last}! You just delved into python.")
    
if __name__ == '__main__':
    first_name = input()
    last_name = input()
    print_full_name(first_name, last_name)
```