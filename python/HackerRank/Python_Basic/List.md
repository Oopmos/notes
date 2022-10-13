# Task
Consider a list (list = []). You can perform the following commands:

1. insert i e: Insert integer e at position $i$.
2. print: Print the list.
3. remove e: Delete the first occurrence of integer $e$.
4. append e: Insert integer $e$ at the end of the list.
5. sort: Sort the list.
6. pop: Pop the last element from the list.
7. reverse: Reverse the list.

Initialize your list and read in the value of $n$ followed by $n$ lines of commands where each command will be of the 7 types listed above. Iterate through each command in order and perform the corresponding operation on your list.

# Example
### Input
```
12
insert 0 5
insert 1 10
insert 0 6
print
remove 6
append 9
append 1
sort
print
pop
reverse
print
```
### Output
```
[6, 5, 10]
[1, 5, 9, 10]
[9, 5, 1]
```
# Solution

```
if __name__ == '__main__':
    N = int(input())
    l = []
    
    for j in range(N):
        command = input().split()
        
        if command[0]=="insert":
            i = int(command[1])
            e = int(command[2])
            l.insert(i, e)

        elif command[0]=="print":
            print(l)
   
        elif command[0]=="remove":
            e = int(command[1])
            l.remove(e)
            
        elif command[0]=="append":
            e = int(command[1])
            l.append(e)
        
        elif command[0]=="sort":
            l.sort()
        
        elif command[0]=="pop":
            l.pop()
        
        elif command[0]=="reverse":
            l.reverse()
```