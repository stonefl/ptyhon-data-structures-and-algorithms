



Some articles:
<https://www.codingame.com/playgrounds/500/advanced-python-features>

https://towardsdatascience.com/5-advanced-features-of-python-and-how-to-use-them-73bffa373c84

https://sahandsaba.com/thirty-python-language-features-and-tricks-you-may-not-know.html

https://www.asmeurer.com/python3-presentation/slides.html#1





# Multiple Assignment

The first line contains a multiple assignment: the variables a and b simultaneously get the new values 0 and 1. On the last line this is used again, demonstrating that the expressions on the right-hand side are all evaluated first before any of the assignments take place. The right-hand side expressions are evaluated from the left to the right.

```
>>> a,b = 0,1
>>> while a < 30:
...     print(a, end=',')
...     a, b = b, a+b
...
0,1,1,2,3,5,8,13,21,
```

# List Comprehensions






# Unpacking





# Generator







# Positional and Keyword Arguments




# 4.7.5. Lambda Expressions


# Sequence Operations

## Repeatition




## Slicing




## Concatenate




# Built-in Functions https://docs.python.org/3/library/functions.html

## all()
## any()



## `enumerate()` Function

Return an enumerate object. iterable must be a sequence, an iterator, or some other object which supports iteration. The __next__() method of the iterator returned by enumerate() returns a tuple containing a count (from start which defaults to 0) and the values obtained from iterating over iterable.



Equivalent to:

```
def enumerate(sequence, start=0):
    n = start
    for elem in sequence:
        yield n, elem
        n += 1
```































