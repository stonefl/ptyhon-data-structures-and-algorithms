# Introduction

Python contains many built-in data types. These include four numeric types(`int`, `float`, `complex`, `bool`), four sequence types (`str`, `list`, `tuple`, `range`), one mapping type (`dict`), and two set types (`set`, `fronzenset`). It is also possible to create user-defined objects, such as functions or classes. We will starts with string in this chapter and the remaining built-in types in the next chapters.

# String

In Python, strings are **immutable** text sequence objects, with each character representing an element in the sequence. Python does not have specific data type for characters, so characters are represented as a string with a single element. 

## Build strings

You can build strings through the following ways.
```python
>>> s1 = 'welcome to Python'
>>> s2 = "welcome to Python"
>>> s3 = str('welcome to Python')
>>> s4 = str("welcome to Python")
>>> s5 = s1
>>> 
>>> print(s1 == s2)
True
>>> print(s1 is s2)
False
>>> print(s3 == s4)
True
>>> print(s3 is s4)
False
>>> print(s1 is s5)
True
```

## Concatenation and repeatition

`+` operator is used to concatenate strings and `*` is used to repeat.

```python
>>> 3 * 'un' + 'ium' # 3 times 'un', followed by 'ium'
'unununium'
```
Two or more _string literals_ next to each other are automatically concatenated. Please note, this only works with two literals, not with variables or expressions.

```python
>>> 'Py' 'thon'
'Python'
```
## Indexing and slicing

String can be indexed with the first character having index of 0. Indices can be negative numbers, starting from -1, reprenting the last character.

```python
>>> s ='Welcome'
>>>
>>> s[0]
'W'
>>> s[1]
'e'
>>> s[-1]
'e'
>>> s[-2]
'm'
```

String can be sliced with syntax `s[start:end]` or `s[start:end:step]` to get a substring. **Note:** `start` index and `end` index are optional. If omitted, the default value of `start` is 0, and the default value of `end` is the last index of the string.

```python
>>> s = 'Welcome'
>>> s[1:3]
'el'
>>> s[:6]
'Welcom'
>>> s[:6:2]
'Wlo'
>>> s[::-1]
'emocleW'
```

## Functions work on strings

|  **FUNCTION**  |  **DESCRIPTION**    |
| ----       | ----            |
| ord()      |   returns the ASCII code of a **character**.   |
| chr()      |   returns a character represented by a ASCII number  |
| len()      |  returns length of the string |
| max()      |  returns character having highest ASCII value |
| min()      |  returns character having lowest ASCII value |

```python
>>> ord('A')
65
>>> chr(97)
'a'
>>> len("Python")
6
>>> max("Python")
'y'
>>> min("Python")
'P'
```

## Membership operators

You can use `in`  and `not in`  operators to check existence of a string in another string. They are also known as membership operator.

```python
>>> s = "Welcome"
>>> "come" in s
True
>>> "Wel" not in s
False
```



## String methods

String class in python has various inbuilt methods which allows to check for different types of strings.



### Methods testing strings

The following table lists the built-in methods that allow to check for different types of strings.

| **METHOD** |	**DESCRIPTION** |
| ----       | ----             |
|isalnum()	| Return true if all characters in the string are alphanumeric and there is at least one character|
|isalpha()	|Return true if all characters in the string are alphabetic and there is at least one character|
|isascii() | Return true if the string is empty or all characters in the string are ASCII |
|isdecimal() | Return true if all characters in the string are decimal characters and there is at least one character |
|isdigit()	|Return true if all characters in the string are digits and there is at least one character |
|isnumeric()	|Return true if all characters in the string are numeric characters, and there is at least one character |
|isidentifier()	| Return true if the string is a valid identifier according to the language definition |
|islower()	| Return true if all cased characters in the string are lowercase and there is at least one cased character|
|isupper() |Return true if all cased characters in the string are uppercase and there is at least one cased character |
|isspace()	| Return true if there are only whitespace characters in the string and there is at least one character|
|istitle()	| Return true if the string is a titlecased string and there is at least one character|


```python
>>> "OK123".isalnum()
True
>>> "Welcome".isalpha()
True
>>> "97".isascii()
True
>>> "97".isdecimal()
True
>>> "97".isdigit()
True
>>> "97".isnumeric()
True
>>> "97".isidentifier()
False
>>> "welcome".islower()
True
>>> "WELCOME".isupper()
True
>>> " ".isspace()
True
>>> "Welcome".istitle()
True
```

### Methods searching for substrings

|**METHOD**|	**DESCRIPTION**|
| ----       | ----             |
|count(sub:str[, start:int[, end:int]]):int | Returns number of occurrences of substring _sub_, optionally, in the range of [_start_, _end_] |
|endswith(suffix:str[, start:int[, end:int]]):bool | Returns True if strings ends with substring _suffix_, optionally, in the range of [_start_, _end_]|
|startswith(prefix:str[, start:int[, end:int]]):bool | Returns True if strings starts with substring _prefix_, optionally, in the range of [_start_, _end_]|

|find(s1): int	|Returns lowest index from where s1 starts in the string, if string not found returns -1|
|rfind(s1): int	|Returns highest index from where s1 starts in the string, if string not found returns -1|



### Methods converting strings

|**METHOD ** |	**DESCRIPTION**|
| ----       | ----             |
|capitalize(): str |	Returns a copy of this string with only the first character capitalized.|
|casefold(): str |	Return a casefolded copy of the string.Casefolding is similar to lowercasing but more aggressive.|
|lower(): str	|Return string by converting every character to lowercase|
|upper(): str	|Return string by converting every character to uppercase|
|title(): str	|This function return string by capitalizing first letter of every word in the string|
|swapcase(): str	|Return a string in which the lowercase letter is converted to uppercase and uppercase to lowercase|
|replace(old:str, new:str): str	|This function returns new string by replacing the occurrence of old string with new string|


### Methods padding strings
|**METHOD ** |	**DESCRIPTION**|
| ----       | ----             |
|center(width:int[, fillchar:str]):str |Return centered in a string of length width. Padding is done using the specified fillchar |





# References:

Python Documentation:
https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str

The Python Guru:
https://thepythonguru.com/python-strings/

Packet Book - Hands-On Data Structures and Algortihms with Python
https://subscription.packtpub.com/book/application_development/9781788995573/1/ch01lvl1sec14/overview-of-data-types-and-objects