# <p align="center"><ins> Homework 5 </ins></p>
## Question 1
### Given a list of numbers, write a function to find the maximum number in the list. Do Not Use the built-in Python function max. Note: For the purpose of this problem, we define that an empty list will return None. 
### NOTE: DO NOT USE THE PYTHON FUNCTION max. WRITE your program using a loop. 

### Example 1:
### Input: [10, 5, 20, 15, 25]
### Output: 25

### Example 2:
### Input: [10,10,10]
### Output: 10

### Example 3:
### Input: []
### Output: None

## Code
```{python}
def find_maximum(numbers):
    if not numbers:
        return None
    maximumnumber = numbers[0] #This sets maximumnumber to first number of a list
    for i in numbers: 
        if i > maximumnumber:
            maximumnumber = i #This updates maximumnumber if i is greater than maximumnumber
    return maximumnumber        
```

## Question 2 
### Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses. Write a function named generateParenthesis that takes an integer as an input and returns a list of strings as an output. Note that you can define a function inside a function if necessary.

### Example 1:
### Input: 0
### Output: ['']

### Example 2:
### Input: 1
### Output: ['()']

### Example 3:
### Input: 2
### Output: ['(())', '()()']

### Example 4:
### Input: 3
### Output: ['((()))', '(()())', '(())()', '()(())', '()()()'])

## Code
```{python}
def generateParenthesis(n):
    def generate(p, left, right, parenthesis): #setting parameters for the generate function 
        if left == 0 and right == 0:
            parenthesis.append(p) 
            return
        if left > 0:
            generate(p + "(", left - 1, right, parenthesis)
        if right > left:
            generate(p + ")", left, right - 1, parenthesis)
        
    result = []
    generate("", n, n, result)
    return result
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
