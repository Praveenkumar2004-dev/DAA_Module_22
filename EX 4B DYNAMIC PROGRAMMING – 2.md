# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..

## Algorithm:
1. Create a table lookup to store lengths of matching characters.
2. Compare each character of X with each character of Y.
3. If characters match, update the lookup value and track the maximum length and ending position.
4. After filling the table, the longest common substring is found at the tracked position.
5. Extract and print the substring from X using the recorded indices.  

## Program:

```
Developed by: Praveen Kumar S
Register Number: 212222230108
```

```py
def LCS(X, Y, m, n):
    maxLength = 0
    endingIndex = m
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]

X = input()
Y = input()
m = len(X)
n = len(Y)
print('The longest common substring is', LCS(X, Y, m, n))
```

## Output:

![22b](https://github.com/user-attachments/assets/0af9fbaf-24f2-4bee-bb03-88d27caf577f)


## Result:

Thus the program was executed successfully for finding the longest common substring .
