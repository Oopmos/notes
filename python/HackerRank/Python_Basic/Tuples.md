# Task
* The first line contains an integer, $n$, denoting the number of elements in the tuple. (จำนวนสมาชิกใน turple)
* The second line contains $n$ space-separated integers describing the elements in tuple t. (ข้อมูลภายใน turple)
* Compute and print the result of $hash(t)$.

### Note
* __Must__ change languges to Pypy 3 <br>
$hash(t)$ or hash build-in module have different results depend on languages you used. <br>

### Comment
* Absoulutely __bad__ problem.
* You can skip this problem.

# Example
### Input
```
2
1 2
```
### Output
```
3713081631934410656
```
### Turple will look like these
```
t = (1, 2)
```
# Solution

```
if __name__ == '__main__':
    n = int(input())
    t = tuple(map(int, input().split()))
    print(hash(t))
```