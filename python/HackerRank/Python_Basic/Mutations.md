# Task
Read a given string, change the character at a given index and then print the modified string.

# Example
### Input
The first line contains a string, $string$.
The next line contains an integer $position$, the index location and a string $character$, separated by a space.
```
abracadabra
5 k
```
### Output
```
abrackdabra
```
# Solution

```
def mutate_string(string, position, character):
    list_string = list(string)
    list_string[position] = character
    return ''.join(list_string)

if __name__ == '__main__':
    s = input()
    i, c = input().split()
    s_new = mutate_string(s, int(i), c)
    print(s_new)
```