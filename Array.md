## Program for Array Rotation
arr = [1,2,3,4,5,6,7] <br />
d = 2  (Here, **d** is the number of times user want to rotate the array) <br/>
**Expected Ouput:** arr = [3,4,5,6,7,1,2] <br/>




### Method 1:
- Store the first array in the temp variable
- Shift the rest of the arr[]
- add the temp[] iat the last of the arr[]

```
def rotateArray(arr, d):
  temp = [arr[0], arr[1]]
  for i in range(d):
      arr.pop(0)
      
  arr.extend(temp)

def printArray(arr, size):
  for i in range(size):
    print("% d"% arr[i], end=" ")


arr = [1,2,3,4,5,6,7]

rotateArray(arr, 2)
printArray(arr, 7)
```

### Method 2:
- store the arr[0] in the temp.
- shift the array, arr[0] will become arr[1], arr[1] will become arr[2] and so on.
- set arr[n - 1] = temp   (This will assign the first value of the array at the end)
- Run this function times **d** (Here, **d** is the number of rotations)

```
def rotateLeft(arr, d, size):
  for i in range(d):
    rotateLeftbyOne(arr, size)

def rotateLeftbyOne(arr, size):
  temp = arr[0]
  for i in range(size - 1):
    arr[i] = arr[i + 1]
  arr[size - 1] = temp
 
def printArray(arr, size):
  for i in range(size):
    print("% d"% arr[i], end=" ")


arr = [1, 2, 3, 4, 5, 6, 7]

rotateLeft(arr, 2, 7)
printArray(arr, 7)
```
