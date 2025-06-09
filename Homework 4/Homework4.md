# <p align="center"><ins> Homework 4 </ins></p>
## Question 1
###  Code 
```{python}
import copy
def objects(a):
    # The variable a represents a list.
    # You are given a = [1,2,[3,4,5]]
    # The variable b also represents a list.
    # The list b is a copy of list a.
    # Both list a and list b should have the same id address.
    
    # Write the Python statement which will result in list b being a copy of list a, with list a and list b having the same id address.
    b = a #Do this so you can get the same id address and list

    # Assign a shallow copy of the list a to the variable c.
    # (Variable c is a list and is a shallow copy of list a).
    c = copy.copy(a)

    # Assign a deep copy of the list a to the variable d.
    d = copy.deepcopy(a)

    # Assign the id of list a to the variable id_a
    id_a = id(a)

    return b, c, d, id_a
```
## Question 2
### Write a function prime_number(number). This function will return a list of all the prime numbers from 2 up to but not including the variable number.
### Please refer to the sample outputs given below.
### Example 1:
### prime_number(10)
### Output: [2,3,5,7]
### Example 2:
### prime_number(100)
### Output: [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47, 53, 59, 61, 67, 71, 73, 79, 83, 89, 97]
### Example 3:
### prime_number(7)
### Output: [2,3,5]

### Code
```{python}
def prime_number(number):
        listP = []
        for i in range(2, number):
                prime_check = True
                for j in range (2, i):
                        if i % j == 0:
                                prime_check = False
                                break
                if prime_check:
                        listP.append(i)
        return listP
```

### Write a function while_loop(number). The variable number is a string.

*If the character in the string is a number, the function
returns the sum of all integer numbers between 1 and
number inclusive. Please refer to the sample output
below:
Example1:
        while_loop("3")
        Output: 6
        Explanation: 3 + 2 + 1 = 6

*If the character in the string is not a number, (or not an integer
number) the function returns the string "Error". Please refer to the
sample output below:
Example2:
        while_loop("Hello")
        Output: "Error"
        Explanation: Characters in the string are not numbers.
        Hint: You may want to consider using a try statement with an except statement.

*If the character in the string is a number less than one, the function
returns the number zero as a default. Please refer to the sample
output below:
Example3: 
        while_loop("-1")
        Output: 0
        Explanation: The number in the string is less than one. The default of zero is returned. """
#PLEASE COMPLETE THE FOLLOWING PROGRAM.

def while_loop(num):
        #Write your code here
                total = 0
                try:
                        num = int(num) #To make the num to a number, you would do num = int(num)
                        if num >= 1:
                                while num > 0:
                                        total = total + num
                                        num = num -1
                        elif num < 1:
                                total = 0
                except:
                        return "Error"
                return total

```
