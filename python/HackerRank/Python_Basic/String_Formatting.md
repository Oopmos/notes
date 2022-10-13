# Task
Given an integer, $n$, print the following values for each integer $i$ from $1$ to $n$:

1. Decimal
2. Octal
3. Hexadecimal (capitalized)
4. Binary

### Prints

The four values must be printed on a single line in the order specified above for each $i$ from $1$ to $number$. Each value should be space-padded to match the width of the binary value of $number$ and the values should be separated by a single space.
# Example
### Input
```
17
```
### Output
```
    1     1     1     1
    2     2     2    10
    3     3     3    11
    4     4     4   100
    5     5     5   101
    6     6     6   110
    7     7     7   111
    8    10     8  1000
    9    11     9  1001
   10    12     A  1010
   11    13     B  1011
   12    14     C  1100
   13    15     D  1101
   14    16     E  1110
   15    17     F  1111
   16    20    10 10000
   17    21    11 10001
```
# Solution

```
def print_formatted(number):
    for i in range(number):
        
        octal = oct(i+1)
        hexadecimal = hex(i+1)
        binary = bin(i+1)
        last_binary = bin(number)
        last_binary = last_binary[2:]

        first_value = str(i+1)
        second_value = octal[2:]
        third_value = hexadecimal[2:]
        fourth_value = binary[2:]
        width = len(last_binary)
        
        print((first_value.rjust(width)), (second_value.rjust(width)), (third_value.rjust(width).upper()), (fourth_value.rjust(width)))

if __name__ == '__main__':
    n = int(input())
    print_formatted(n)
```