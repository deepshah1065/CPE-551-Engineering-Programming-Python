# <p align="center"><ins> Homework 1 </ins></p>
## **<ins> Code </ins>**
### Python Core Object Types

#### This reviews numbers and basic operations.
```{python}
def number():
    # Write the value 4 to the power of 5 and assign it to variable x.
    x = 4 ** 5
    print (x)
    
    # Write the value x divided by 3 and assign it to variable y.
    y = x / 3
    print(y)
    
    return x, y
```
#### This reviews numbers, strings, and basic operations.
```{python}
def strings():
    # Assign a string "stevens" to a variable stevens.
    stevens = "stevens"

    # Repeat variable stevens 7 times and assign it to variable stevens_7.
    stevens_7 = stevens * 7
    print(stevens_7)

    # Determine the length of stevens_7
    length = len(stevens_7)
    print(length)
    
    # Concatenate variable stevens with string " is great" and assign it to variable great.
    great = stevens + " is great"
    print(great)

    # Use string slicing to replace "great" with "good" in variable great and assign it to a new variable good.
    good = great.replace("great", "good",)
    print(good)

    return stevens, stevens_7, length, great, good
```
#### This reviews basic operations with lists.
```{python}
def list_1D():

    s = " hoboken,is,awesome,i,like,it "
    
    #Using list slicing, remove the whitespace characters on both side and assign it to a new variable hoboken.
    hoboken = s.strip() 
    print(hoboken)

    # Split variable hoboken on a delimiter(comma) into a list of substrings and assign it to a new variable hoboken_list.
    hoboken_list = s.strip().split(',') 
    print(hoboken_list)

    # Get the first item in the hoboken_list and assign it to a new variable hoboken_first_item.
    hoboken_first_item = hoboken_list[0]
    print(hoboken_first_item)

    l=[2,3,4,1,5,6,9,10,15,12,13,-2,-6,0,0]

    # Inplace sort list l (use .sort() ).
    l.sort() #This would sort the list in ascending order.
    
    # Get the 4th to 10th item in sorted list l and assign them to a new list new_l.
    new_l = l[3:10] 
    print (new_l)
    return hoboken,hoboken_list, hoboken_first_item, l, new_l

def list_2D():
    # Create a 3 x 3 matrix A as nested list such that
    #   first row is [1, 4, 5]
    #   second row is [6, 10, 11]
    #   third row is [12, 17, 38]
    A = [[1, 4, 5], [6, 10, 11], [12, 17, 38]]
    print(A)

    # Collect the items in the last column of matrix A using list comprehension (with a for loop) and assign it to a new variable last_column.
    last_column = [i[2] for i in A]
    print(last_column)

    # Using indexing, get the item at the last row and last column of A and assign this item to a new variable a.
    a = A[2][2]
    print(a)
    # Using indexing, get the item at row 2 and column 1 of A and assign this item to a new variable b.
    b = A[1][0]
    print(b)
    return A, last_column, a, b
```
#### This reviews basic operations with dictionaries and function calls.
```{python}
def dictionary():
    # Create a dictionary named fruit_dict that maps:
    #   "fruit" => "apple"
    #   "quantity" => 18
    #   "color" => "red"
    fruit_dict = {"fruit": "apple", "quantity": 18, "color": "red"}

    # Get the item in dictionary fruit_dict that the key "fruit" maps to. Assign this item to the variable f.
    f = fruit_dict["fruit"]
    print(f)

    # Increase the value that key "quantity" maps to by 1.
    fruit_dict["quantity"] += 1
    return fruit_dict, f

def dictionary_nested():
    # Create a nested dictionary Grace where:
    #   "name" => {"first_name" => "Grace", "last_name" => "Hopper"} (a dictionary)
    #   "jobs" => ["scientist", "engineer"] (a list)
    #   "age" => 85
    Grace = {"name": {"first_name": "Grace", "last_name": "Hopper"},
             "jobs": ["scientist", "engineer"],
             "age": 85}
    # Get the value of key "last_name" from the subdictionary of key "name" in dictionary Grace. (aka."Hopper")
    last_name = Grace["name"]["last_name"]
    print (last_name)
    # Add "programmer" to the list that key "jobs" maps to.
    Grace["jobs"].append("programmer")
    print(Grace["jobs"])

    # Get the third item in the list that key "job" maps to. (This is the item  you recently added).
    job = Grace["jobs"][2]
    print(job)

    return Grace, last_name, job

number()
strings()
list_1D()
list_2D()
dictionary()
dictionary_nested()
```
