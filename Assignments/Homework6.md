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
### Given a string, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases. Note: For the purpose of this problem, we define empty string as valid palindrome. Write a function named isPalindrome that takes a string as an input and returns a bool as an output.

### Hint: refer to the following example on how to reverse a string.
### Code
```{python}
>>> S = "abc"
>>> S[::-1]
```
### Output
### 'cba'

### Example 1:
### Input: "A man, a plan, a canal: Panama"
### Output: true

### Explanation:
### After removing non-alphanumeric charactors and ignoring cases, the input is: amanaplanacanalPanama which reads the same as backward and forward, so it is true.

### Example 2:
### Input: "race a car"
### Output: false

### Explanation:
### After removing non-alphanumeric charactors and ignoring cases, the input is: raceacar which does not read the same as backward and forward, so it is false.

```{python}
def isPalindrome(x):
    filter_text = ''.join(char.lower() for char in x if char.isalnum()) #This filters the word to remove the non-alphanumeric charactors and ignoring cases as shown below. This also makes the characters lower case. 
    #To remove the non-alphanumeric charactors and ignoring cases, you can use use the code: 
    # clean_text = ''.join(char for char in text if char.isalnum())
    return filter_text == filter_text[::-1] #This will output whether this is true, resulting in a palindrome and false for which does not read the same as backward and forward
```
