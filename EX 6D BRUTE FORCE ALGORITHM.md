# EX 6D BRUTE FORCE ALGORITHM
## DATE: 06/05/2025
## AIM:
To write a python program using brute force method of searching for the given substring in the main string.




## Algorithm
1. Loop through the main string from index 0 to len(main) - len(sub).

2. For each index i, compare the substring of main[i:i+len(sub)] with the target substring.

3. If all characters match, return the index i as the match position.

4. If no match is found after the loop, return -1.

## Program:
```
/*
To implement the program using brute force method of searching for the given substring in the main string.


Developed by: LAVANYA S
Register Number: 212223230112
*/

def match(string,sub):
    l = len(string)
    ls = len(sub)
    ## start = sub[0]

    ########### Add your code here #######
    for i in range(l-ls+1):
        j=0
        while j<ls and string[i+j]==sub[j]:
            j+=1
        if j==ls:
            print("Found at index",i)
    return -1

str1=input()
str2=input()

```

## Output:
![image](https://github.com/user-attachments/assets/cc66f926-091a-40a5-b3b2-4a9dcfc06da3)



## Result:
Thus the above program was executed successfully for searching the substring at respective index.
