# Keanu crack the matrix

In this problem we were given a n x n matrix, where n is the length of the message.
The diagonal elements were the ascii codes of the message subtraced from the keys respectively.
To extract the keys, we used the following script:

```python
arr = [[ .....]] # 2d array encrypted message

keys = []
keys.append(arr[0][1] +2)
b = -37
for i in range(1,len(arr)):
    keys.append(arr[i][0]-b)
    b-=len(arr)
print(keys)
res = ""
for i in range(len(keys)):
    res += chr((keys[i] - arr[i][i]))
print(res)

```
