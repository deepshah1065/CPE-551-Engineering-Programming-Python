# <p align="center"><ins> Homework 2 </ins></p>
## **<ins> Code </ins>**
### This reviews tuples, basic operations, and function calls.
```{python}
def tuple():

    # Assign the first element of the tuple "t1" to the variable x.
    t1 = (13, 100, 99, 100, 999)
    x = t1[0]
    print(x)

    # Assign the next to the last element of the tuple "t1" to the
    # variable y. For the given tuple, the next to the last element
    # is 100.
    y = t1[-2]
    print(y)

    # Determine the index of 2 in the tuple "t2" by using the index
    # method for tuples. Assign the result to the variable z.
    
    t2 = (55, 777, 54, 6, 76, 101, 1, 2, 8679, 98, 123, 98, 98)
    z = t2.index(2)    
    print(z)

    # Determine the number of times 98 occurs in the tuple "t2" by
    # using the count method for tuples. Assign the result to
    # the variable f.
    f = t2.count(98)
    print(f)

    # Determine the sum of all the numbers in the tuple "t2" and
    # assign the result to the variable m.
    m = sum(t2)
    print(m)

    # Determine the maximum number of all the numbers
    # in the tuple "t2" and assign the result to the variable n.
    n = max(t2)
    print(n)


    return x, y, z, f, m, n


tuple()
```
