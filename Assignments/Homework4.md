# <p align="center"><ins> Homework 4 </ins></p>
## **<ins> Code </ins>**
```{python}
#I pledge my honor that I have abided by the Stevens Honors System. - Deep Shah
import math

def calculate():
    a=3
    b=4

    # Add a and b then assign the sum to variable c
    c = a + b
    print(c)

    # Subtract c by 1 then divide this result by 5.0 and assign this final result to the variable q
    q = (c - 1)/5.0
    print (q)



    # Assign the type of the variable q to a new variable type_q
    type_q = type(q)
    print (type_q)

    return c,q,type_q


def string_formating():

    math_pi = 3.141592653589793

    # Format the variable math_pi as a string with 6 decimal places and assign it to variable string_pi
    math_pi = 3.141592653589793
    string_pi = "{:.6f}".format(math_pi) #The f indicates that you're formatting a floating-point number. The .6 specifies the number of decimal places to display. 
    #So :.6f means "format the number as a float with 6 digits after the decimal point."

    print (string_pi)

    ####
    large_number= 100000000

    # Format large_number to be a string and assign it to the variable comma_string. The contents of comma_string
    # should have the appropriate commas. (Comma separator). Example; 1000 should be "1,000"
    large_number = 100000000
    comma_string = "{:,}".format(large_number) #This code is used to format the large number with commas; notes you need to indicate the {:,} for commas
    print (comma_string)

    # Format large_number to be a string and assign it to the variable exp_string. The contents of exp_string
    # should be exponent notation (with two decimal places).
    large_number = 100000000
    exp_string = "{:.2e}".format(large_number) #This code does the exp_string operation, where it makes the number in exponentation notation like 1.00e+8. 
    #{:.2e}: This is used to indicate that it should be two decimal places and e represents the exponentation notation. The colon inside the curly braces indicates that a format specification follows
    print (exp_string)

    ####
    small_number =13

    # Format small_number to be a string and assign it to the variable center_string. 
    # The format for center_string should be Center aligned with a width of 10.
    small_number = 13
    center_string = "{: ^10}".format(small_number) #When you place ^ in the format specification, it tells Python to center-align the content within the specified width.
    print (center_string) 

    # Format small_number to be a string and assign it to the variable left_string.
    # The format for left_string should be Left aligned with a width of 10.
    left_string = "{: <10}".format(small_number)
    print (left_string)

    return string_pi,comma_string,exp_string,center_string,left_string


def build_in():
    #### Use the math library for the following questions.
    # Assign the number pi to the variable math_pi
    math_pi = math.pi
    print(math_pi)

    # Assign the Euler's number (e) to the variable math_e
    math_e = math.e
    print(math_e)

    # Assign the sine of pi (sin(pi)) to the variable sin_pi
    sin_pi = math.sin(math.pi)
    print (sin_pi)

    # Assign the square root of 2 to the variable square_root_2
    square_root_2 = math.sqrt(2)
    print (square_root_2)

    # Assign the absolute value of -2 to the variable abs_2
    # (Please use the built-in Python function for absolute value)
    abs_2 = abs(-2)
    print(abs_2)

    return math_pi,math_e,sin_pi,square_root_2,abs_2



def set_op():
    S1 = {1, 2, 3, 4}
    S2 = {3, 4, 5, 6}

    # Add 0 to set S1
    S1.add((0))
    print (S1)

    # Assign the union of S1 and S2 to the variable union_s
    union_s = S1 | S2
    print (union_s)

    # Assign the sum of all items in union_s to the variable sum_s
    sum_s = sum((union_s))
    print (sum_s)

    return S1,union_s,sum_s


calculate()
string_formating()
build_in()
set_op()
```
