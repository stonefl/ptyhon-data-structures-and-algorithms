---
title: String
---
# String

In Python, strings are **immutable** text sequence objects, with each character representing an element in the sequence. Python does not have specific data type for characters, so characters are represented as a string with a single element. 

## Build strings

Strings can be created through the following ways.
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
Two or more **_string literals_** next to each other are automatically concatenated. Please note, this only works with two literals, not with variables or expressions.

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

String can be sliced through syntax `s[start:end]` or `s[start:end:step]`. **Note:** `start` index and `end` index are optional. If omitted, the default value of `start` is 0, and the default value of `end` is the last index of the string.

```python
>>> s = 'Welcome'
>>> s[1:3]
'el'
>>> s[:6]
'Welcom'
>>> s[:6:2]
'Wlo'
>>> s[::-1] #reverse the string
'emocleW'
```

## Functions on strings

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

`in`  and `not in`  operators can be used  to check existence of a string in another string. They are also known as membership operators.

```python
>>> s = "Welcome"
>>> "come" in s
True
>>> "Wel" not in s
False
```

## String methods

String class in python has various built-in methods which can be categorized to the following groups.

### Methods testing string types

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
|count(sub [, start [, end]) | Returns number of occurrences of substring _sub_, optionally, in the range of [_start_, _end_] |
|endswith(suffix [, start [, end]]) | Returns True if strings ends with substring _suffix_, optionally, in the range of [_start_, _end_]|
|startswith(prefix [, start [, end]]) | Returns True if strings starts with substring _prefix_, optionally, in the range of [_start_, _end_]|
|find(sub[, start[, end]])	| Returns lowest index from where _sub_ starts in the string within the rangle of [_start_, _end_], if substring not found returns -1|
|index(sub[,start[,end]])	| Like find(), but raise `ValueError` when the substring is not found.|
|rfind(sub[, start[, end]])	|Return the highest index in the string where substring _sub_ is found, such that sub is contained within `s[start:end]`. Optional arguments start and end are interpreted as in slice notation. Return -1 on failure.|
|rindex(sub[, start[, end]])	| Like rfind() but raises `ValueError` when the substring sub is not found.|
```python
>>> s = "Welcome to Python"
>>> s.count("o")
3
>>> s.count("o", 7, -1)
2
>>>
>>> s.endswith("on")
True
>>> s.startswith("wel")
False
>>> s.find("come")
3
>>> s.index("become")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: substring not found
>>> s.rfind("o")
15
>>> s.rindex("a")
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: substring not found
```

### Methods converting strings

|**METHOD ** |	**DESCRIPTION**|
| ----       | ----             |
|capitalize() |	Returns a copy of this string with only the first character capitalized.|
|casefold() |	Return a casefolded copy of the string. Casefolding is similar to lowercasing but more aggressive.|
|lower() | Return string by converting every character to lowercase|
|upper()	| Return string by converting every character to uppercase|
|title()	|This function return string by capitalizing first letter of every word in the string|
|swapcase()	| Return a string in which the lowercase letter is converted to uppercase and uppercase to lowercase|
|replace(old, new[, count])	|Return a copy of the string with all occurrences of substring old replaced by new.|


```python
>>> s = "welCOME to python"
>>> s.capitalize()
'Welcome to python'
>>> s.casefold()
'welcome to python'
>>> s.lower()
'welcome to python'
>>> s.upper()
'WELCOME TO PYTHON'
>>> s.title()
'Welcome To Python'
>>> s.swapcase()
'WELcome TO PYTHON'
>>> s.replace('python', 'java')
'welCOME to java'
```

### Methods padding/formatting strings

|**METHOD ** |	**DESCRIPTION**|
| ----       | ----             |
| expandtabs(tabsize=8) | Return a copy of the string where all tab characters are replaced by one or more spaces, depending on the current column and the given tab size. |
| center(width [, fillchar]) |Returns centered in a string of length _width_. Padding is done using the specified _fillchar_ |
| ljust(width[, fillchar]) | Return the string left justified in a string of length _width_. Padding is done using the specified _fillchar_ |
| rjust(width[, fillchar]) | Return the string right justified in a string of length _width_. Padding is done using the specified _fillchar_ |
| zfill(width) | Return a copy of the string left filled with ASCII `0` digits to make a string of length _width_. A leading sign prefix (`+`/`-`) is handled by inserting the padding after the sign character rather than before.  |
| format(*args, *\*kwargs) | Perform a string formatting operation. The string on which this method is called can contain literal text or replacement fields delimited by braces {} |

```python
>>> '01\t012\t0123\t01234'.expandtabs()
'01      012     0123    01234'
>>> '01\t012\t0123\t01234'.expandtabs(4)
'01  012 0123    01234'
>>>
>>> s = 'Welcome to Python'
>>> s.center(30, '@')
'@@@@@@Welcome to Python@@@@@@@'
>>> s.ljust(30, '#')
'Welcome to Python#############'
>>> s.rjust(30)
'             Welcome to Python'
>>> s.zfill(30)
'0000000000000Welcome to Python'
>>> "42".zfill(5)
'00042'
>>> "-42".zfill(5)
'-0042'
>>> "The sum of 1 + 2 is {0}".format(1+2)
'The sum of 1 + 2 is 3'
```

### Methods operating strings
|**METHOD ** |	**DESCRIPTION**|
| ----       | ----             |
|join(iterable) | Return a string which is the concatenation of the strings in iterable. A `TypeError` will be raised if there are any non-string values in iterable |
|lstrip([chars]) | Return a copy of the string with leading characters removed. The chars argument is a string specifying the set of characters to be removed.|
|rstrip([chars]) | Return a copy of the string with trailing characters removed. The chars argument is a string specifying the set of characters to be removed.  |
|strip([chars]) | Return a copy of the string with the leading and trailing characters removed. The chars argument is a string specifying the set of characters to be removed.  |
|partition(sep) | Split the string at the first occurrence of sep, and return a 3-tuple containing the part before the separator, the separator itself, and the part after the separator. |
|rpartition(sep) | Split the string at the last occurrence of sep, and return a 3-tuple containing the part before the separator, the separator itself, and the part after the separator. |
|split(sep=None, maxsplit=-1) | Return a list of the words in the string, using _sep_ as the delimiter string. |
|rsplit(sep=None, maxsplit=-1) | Return a list of the words in the string, using sep as the delimiter string. |
|split(sep=None, maxsplit=-1) | Return a list of the words in the string, using _sep_ as the delimiter string. |
|splitlines([keepends]) | Return a list of the lines in the string, breaking at line boundaries. |
|maketrans(x[, y[, z]]) | returns a translation table that maps each character in the x into the character at the same position in the y string. This table is usable for `str.translate()`. |
|translate(table) | Return a copy of the string in which each character has been mapped through the given translation table. |


```python
>>> test = ['1', '2', '3']
>>> "<".join(test)
'1<2<3'
>>> '   spacious   '.lstrip()
'spacious   '
>>> 'www.example.com'.lstrip('cmowz.')
'example.com'
>>>
>>> '   spacious   '.rstrip()
'   spacious'
>>> 'mississippi'.rstrip('ipz')
'mississ'

>>> '   spacious   '.strip()
'spacious'
>>> 'www.example.com'.strip('cmowz.')
'example'
>>> s = "Welcome to Python"
>>> s.partition('o')
('Welc', 'o', 'me to Python')
>>> s.partition('x')
('Welcome to Python', '', '')
>>> s.rpartition('o')
('Welcome to Pyth', 'o', 'n')
>>> '1,2,3'.split(',')
['1', '2', '3']
>>> '1,2,3'.split(',', maxsplit=1)
['1', '2,3']
>>> '1,2,,3,'.split(',')
['1', '2', '', '3', '']
>>> ''.split('\n')
['']
>>> 'Two lines\n'.split('\n')
['Two lines', '']
>>> '1,2,3'.rsplit(',', maxsplit=1)
['1,2', '3']
>>> 'ab c\n\nde fg\rkl\r\n'.splitlines()
['ab c', '', 'de fg', 'kl']
>>> 'ab c\n\nde fg\rkl\r\n'.splitlines(keepends=True)
['ab c\n', '\n', 'de fg\r', 'kl\r\n']
>>> "".splitlines() #compare to split('\n')
[]
>>> "One line\n".splitlines() #compare to split('\n')
['One line']


>>> intab = "aeiou"
>>> outtab = "12345"
>>> trantab = str.maketrans(intab, outtab)
>>> trantab
{97: 49, 101: 50, 105: 51, 111: 52, 117: 53}
>>> s = "This is a testing string."
>>> print(s.translate(trantab))
Th3s 3s 1 t2st3ng str3ng.
```



# References:



Python Documentation:
https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str

The Python Guru:
https://thepythonguru.com/python-strings/

Packet Book - Hands-On Data Structures and Algortihms with Python
https://subscription.packtpub.com/book/application_development/9781788995573/1/ch01lvl1sec14/overview-of-data-types-and-objects