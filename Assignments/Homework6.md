# <p align="center"><ins> Homework 6 </ins></p>
## Question 1
### Give a list of numbers, write a function with lambda and filter to return the even numbers of the list.
### Note: This function should use Lambda. 

### Example 1:
### Input: [1, 2, 3, 4, 5, 6]
### Output: [2, 4, 6]

### Example 2:
### Input:[10,10,10,20,21,20]
### Output: [10, 10, 10, 20, 20]

### Example 3:
### Input: []
### Output: []

## Code
```{python}
def filter_even(lst):
    #Your code here, should use lambda and filter
    ans = list(filter((lambda x: x % 2 == 0), lst)) #x just represents each individual element in the list
    #x % 2 == 0 would result in checking what values in the list are even values
    return ans        
```

## Question 2 
### Give a list of numbers, write a function with lambda and reduce to return the product (multiple result) of numbers.
### Note: This function should use Lambda. 

### Example 1:
### Input: [1, 2, 3, 4, 5, 6]
### Output: 720

### Example 2:
### Input:[7,8,9,10]
### Output: 5040

### Example 3:
### Input: [100,200,300]
### Output: 6000000

## Code
```{python}
from functools import reduce
def reduce_function(lst):
    #Your code here, should use lambda and reduce
    ans = reduce(lambda x, y: x * y, lst) #Since we need a value, there should be list at the beginning of it.
    return ans
```

## Question 3 
### Give a string number as Num, representing a larger number. An integer is considered a great integer if it satisfies all of the following conditions:
### 1.The integer is a substring of length 4 of Num.
### 2.The integer consists of a unique number repeated 4 times.
### Returns the largest great integer as a string. Returns an empty string "" if no such integer exists.

### Example 1:
### Input: "8999921111116"
### Output: "9999"
### Explanation: There are two great integers in Num: "9999" and "1111". "9999" is the largest one.

### Example 2:
### Input:"6498888132"
### Output: "8888"
### Explanation: "8888" is the only great integer.

### Example 3:
### Input: "89454648126"
### Output: ""
### Explanation: There is no integer of length 4 consisting of only one unique digit. Therefore, great integers do not exist.

```{python}
def largestGoodInteger(Num):
    ans = "" #ans would be represented as largest great integer
    
    for i in range(len(Num) - 3): #len(Num) - 3: We subtract 3 to make sure we stop at the last valid starting index for a 4-character substring.
        substring = Num[i: i + 4] #This creates a substring that slices from [i, i+1], determing character that have a length of 4.
        if substring [0] == substring [1] == substring [2] == substring[3]:
            if substring > ans:
                ans = substring #ans is updating its value with the larger string
    if ans == "": #This is just returning an empty string for when you have an empty string 
        return ""
    return ans
```
