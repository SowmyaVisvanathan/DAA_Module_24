# EX 6D BRUTE FORCE ALGORITHM
## DATE: 17-05-25
## AIM:
To write a python program using brute force method of searching for the given substring in the main string.

## Algorithm
1. Input two strings:
   - string: main string
   - sub: substring to search
2. Loop through main string from index 0 to len(string) - len(sub).
3. Compare substring: At each position i, check if string[i : i+len(sub)] == sub.
4. If match found, print the index i.

## Program:
```
/*
To implement the program using brute force method of searching for the given substring in the main string.


Developed by: Sowmya V
Register Number: 212222110045
*/

def match(string,sub):
    l = len(string)
    ls = len(sub)
    start = sub[0]
    for i in range(l-ls+1):
        if string[i:i+ls]==sub:
            print(f"Found at index {i}")

str1=input()
str2=input()
```

## Output:
![image](https://github.com/user-attachments/assets/6b2bb82c-84be-46ed-9ed7-36bafa97fd5b)

## Result:
Thus the above program was executed successfully for searching the substring at respective index.
