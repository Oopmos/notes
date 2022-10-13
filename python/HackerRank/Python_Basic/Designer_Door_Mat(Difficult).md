# Task
Mr. Vincent works in a door mat manufacturing company. One day, he designed a new door mat with the following specifications:

* Mat size must be $n$ X $m$. ($n$ is an odd natural number, and $m$ is 3 times $n$.)
* The design should have 'WELCOME' written in the center.
* The design pattern should only use |, . and - characters.

### Comment
* Difficult problem which required high problem solving skill.
* Code is hard to understand. I don't know what I have done either. :poop:
* Maybe the solution can be improve.

# Example
### Input and Output
```
    n=7, m=21
    Size: 7 x 21 
    ---------.|.---------
    ------.|..|..|.------
    ---.|..|..|..|..|.---
    -------WELCOME-------
    ---.|..|..|..|..|.---
    ------.|..|..|.------
    ---------.|.---------
    
    n=11, m=33
    Size: 11 x 33
    ---------------.|.---------------
    ------------.|..|..|.------------
    ---------.|..|..|..|..|.---------
    ------.|..|..|..|..|..|..|.------
    ---.|..|..|..|..|..|..|..|..|.---
    -------------WELCOME-------------
    ---.|..|..|..|..|..|..|..|..|.---
    ------.|..|..|..|..|..|..|.------
    ---------.|..|..|..|..|.---------
    ------------.|..|..|.------------
    ---------------.|.---------------
```
# Solution

```
if __name__ == '__main__':
    n, m = input().split()
    width = int(m)
    height = int(n)
    middle_width = int(width/2)
    
    top_height = int((height-1)/2)
    for i in range(top_height):
        
        for j in range(width-(3*2*i)-2):
            
            if j==middle_width-1-(3*i):

                for k in range(1+i*2):
                    print(".|.", end='')
                    
            else:
                print('-', end='')
                
        print()
        
    word_length = len("WELCOME")
    count_word_from_middle = int(word_length/2)
    for j in range(width-len("WELCOME")+1):

        if j==middle_width-count_word_from_middle:
            print("WELCOME", end='')

        else:
            print('-', end='')

    print()        
            
    for i in range(top_height):
        
        for j in range(width-(3*2*(top_height-1-i))-2):
            
            if j==middle_width-1-(3*(top_height-1-i)):
                
                for k in range(1+(top_height-1-i)*2):
                    print(".|.", end='')
                    
            else:
                print('-', end='')
                
        print()
```