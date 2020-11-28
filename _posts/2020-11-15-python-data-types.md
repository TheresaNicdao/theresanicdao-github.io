---
title: Python Data Types
date: "2020-11-15"
categories:
- python
- data-type
tags:
- python
- data-type
header:
  teaser: /assets/images/teasers/python-data-types.png
---

**Data type** is a data classification which tells the compiler/interpreter how the programmer intends to use the data. It defines the set of rules and operations that can be applied to it. The most common data types that exist in majority of programming languages are `integer`, `float`, `character`, `string`, and `boolean`. For this discussion, we will focus on the standard data types in Python programming language. 

## An overview

In Python, there are **5 standard data types** as shown in the diagram below. 

![Python data types](/assets/images/posts/python-data-types.png)


+ If you notice, under **Numeric** data type are the more common types that represent data with numeric value.  
+ Another grouping is the **Sequence** data type which covers all types that have an ordered collection of similar or different data types.  
+ **Boolean** is the typical True or False.  
+ **Dictionary** which is a mapping type, is key-value pair. In other programming languages, it is called hash or map.  
+ **Set** on the other hand, is a very useful data type for mathematical operations like union, intersection, and differences.

The next section will introduce you to each of these data types and how to use them.

![Quick tip](/assets/images/posts/quick-tip.png)
**`type(obj)`** shows the data type of an object
{: .notice--info}

![Quick tip](/assets/images/posts/quick-tip.png)
**`dir(obj)`** shows list of attributes and methods of any object
{: .notice--warning}


***
## TYPE: Numeric 

As mentioned, under this type are the most common data types that are available in almost all programming languages: **integer**, **float**, and **complex**.


**Arithmetic operations can be applied to these types:**
- Addition and Subtration
- Multiplication and Division
- Modulus `%`
- Exponent `**`
- Floor Division `//`


### Integer

+ May contain 0, positive or negative whole number only
+ No limit on how long an int value can be
+ To create an int variable:
```yaml
sample_int = 5
```
+ Leading zeroes in non-zero integers is not allowed, *i.e.* 01, 000123
+ You can use delimiter, but comma is not allowed. Best Practice: Use underscore, *i.e.* 
```yaml
sample_int = 123456 
# is the same as
sample_int = 1_234_456
```
+ Integer can also be binary, octal, or hexadecimal values but I won't dwell on that here


### Float

+ Integer with decimal point
+ To create a float variable:
```yaml
sample_float = 10.29
```
+ You can also use underscore as delimiter just like in int
+ Float has a maximum size depending on your system
  + Float beyond its maximum size is called **INFINITY**, *i.e.* 2e400 is already an infinity number
+ Scientific notation is being used as a shortcut to express floats with many digits
```yaml
sample_float = 10.123_456_789e2
# is the same as 
sample_float = 1012.345_678_9
```

### Complex

+ A number with real and imaginary components
+ To represent an imaginary component, you should use **J** or **j**. Anything else will throw an exception
+ To create a complex variable:
```yaml
sample_complex = 1+2j
```
+ Arithmetics in complex component have different processes - *but I won't discuss them here*

***

## TYPE: Sequence

The three basic sequence types are **string**, **tuple**, and **list**.

**Common Sequence Operations**

| Operation            	| Result                                                             	|
|----------------------	|--------------------------------------------------------------------	|
| x in seq             	| True if x exists in sequence seq                                   	|
| x not in seq         	| True if x does not exist in seq                                    	|
| x + y                	| Concatenate x and y values                                         	|
| x * n                	| Adding x to itself n times                                         	|
| seq[i]               	| Element in index i; -1 means last element index                    	|
| seq[i:j]             	| Slice of seq from index i to j                                     	|
| len(seq)             	| Length of seq                                                      	|
| min(seq)             	| Smallest item in seq                                               	|
| max(seq)             	| Largest item in seq                                                	|
| seq.index(x[,i[,j]]) 	| First occurrence of value x at or after index i and before index j 	|
| seq.count(x)         	| Total number of occurrences of x in seq                            	|

**Common Mutable Sequence Operations**

| Operation        | Result                                      |
|------------------|---------------------------------------------|
| seq[i] = x       | Value of x replacing value in index i       |
| seq[i:j] = it    | Iterable replacing value from index i to j  |
| del seq[i:j]     | Same as seq[i:j] = []                       |
| seq.append(x)    | Append x at the end of seq                  |
| seq.clear()      | Remove all items in seq                     |
| seq.copy()       | Create shallow copy of seq                  |
| seq.extend(it)   | Extends seq with the content of iterable it |
| seq += it        | Same as seq.extend(it)                      |
| seq *= n         | Update seq with its content n times         |
| seq.insert(i, x) | Insert x in index i                         |
| seq.pop(i)       | Remove item in index i and return it        |
| seq.remove(x)    | Remove first item with x value              |
| seq.reverse()    | Reverse the order of items in seq           |

### Strings

+ Strings are *immutable* sequences of Unicode code points
+ In Python, there is no `char` type. It is just a string with length of 1
+ Can be constructed in 3 different ways:

| Option       	  | Notes |
|----------------	| ----- |
| Single quotes 	|  - If string has special characters except double quotes, you need to escape it using backslash<br>- If string has both single and double quotes, you need to escape the quotes that are the same with the enclosing quotes, else it will fail |
| Double quotes 	|  - If string has special characters aside from double quotes, you need not to escape it<br>- If string has double quotes, you need to escape it<br>- If string has both single and double quotes, you need to escape the quotes that are the same with the enclosing quotes, else it will fail |
| Triple quotes 	|  - May span multiple lines<br>- All associated whitespace will be included in the string literal<br>- If string has both single and double quotes, you can use triple quotes to not worry about escaping characters<br>- *However*, if the string starts or ends with a single or double quotes, we need to use the quotes that differ from starting or ending one<br>- It is also being used for docstring and multi-line comments 	|

```yaml
str_in_single_q = 'This is a string using "single" quotes'

str_in_double_q = "This is a string using 'double' quotes"

str_in_triple_q = "This is
                  a string using
                  'triple quotes'"
```  

+ Aside from the common sequence methods, here are some additional operations that can be done to a string:

| Operation | Result |
|-|-|
| str.capitalize() | Self-explanatory |
| str.islower()<br>str.isupper() | Self-explanatory |
| str.lower()<br>str.upper() | Self-explanatory |
| str.encode(encoding="utf-8", errors="strict") | - Return an encoded version of the string as a bytes object<br>- Default encoding is 'utf-8'<br>- Default for errors is 'strict' (will raise UnicodeError) |
| str.format() | - Perform a string formatting operation |
| str.join(*iterable*) | - Return a string which is the concatenation of the strings in iterable<br>- The separator between elements is the string providing this method |
| str.lstrip(char) | - Return a copy of the string with leading characters removed<br>- The chars argument is a string specifying the set of characters to be removed<br>- If omitted or None, the chars argument defaults to removing whitespace<br>- The chars argument is not a prefix; rather, all combinations of its values are stripped |
| str.removeprefix(prefix,/)<br>str.removesuffix(suffix, /) | Self-explanatory |
| str.replace(old, new, [,count]) | - Return a copy of the string with all occurrences of substring old replaced by new<br>- If the optional argument count is given, only the first count occurrences are replaced |
| str.rstrip([chars]) | - Return a copy of the string with trailing characters removed<br>- The chars argument is a string specifying the set of characters to be removed<br>- If omitted or None, the chars argument defaults to removing whitespace<br>- The chars argument is not a suffix; rather, all combinations of its values are stripped |
| str.strip([chars]) | - Same with rstrip() except that is is removing leading and trailing characters |
| str.split(sep=None, maxsplit=-1) | - Return a list of the words in the string, using sep as the delimiter string<br>- If maxsplit is given, at most maxsplit splits are done (thus, the list will have at most maxsplit+1 elements) |

### Tuples

+ Tuples are immutable sequences used to store collections of heterogenous data
+ Can be constructed in different ways:

| Option                             | Result        |
|------------------------------------|---------------|
| A pair of parenthesis              | tup = (a,b)   |
| Trailing comma for singleton tuple | tup = a,      |
| Separating items with comma        | tup = a, b, c |
| Built-in method                    | tup = tuple(*iterable*) |

+ Tuples implement all the *common sequence operations*
+ However, since tuples are immutable, we cannot modify its value
+ But we can delete a tuple using `del()` method
+ For heterogenous data where access by name is clearer than access by index, *collections.namedtuple()* might be more appropriate compared to the simple tuple

### Lists

+ Lists are mutable sequences used to store collections of homogenous items
+ Can be constructed in different ways:

| Option                                          | Result                            |
|-------------------------------------------------|-----------------------------------|
| A pair of square bracket denoting an empty list | lst = []                          |
| Square bracket, separating items with commas    | lst = [1, 2, ['a', 'b']]          |
| Using list comprehension                        | lst = [item for item in iterable] |
| Built-in method                                 | lst = list()                      |

+ Lists implement both common and mutable sequence operations
+ Aside from those, Lists also have the following operations:

| Operation                            | Result |
|--------------------------------------|------- |
| sort(*, key=None, reverse=False)     | - This method sorts the list in place, using only < comparisons between items<br>- Has two keyword-only arguments:<br>  1. key - specifies a function of one argument that is used to extract a comparison key from each list element<br>  2. reverse - If set to True, then the list elements are sorted as if each comparison were reversed |

+ List can contain unlimited data depending on your computer's memory

## TYPE: Boolean

+ By default, an object is considered true unless its class defines either a __bool__() method that returns `False` or a __len__() method that returns zero
+ The following are the built-in objects considered as `False`:

| Object                        | Value          |
|-------------------------------|----------------|
| Constants defined to be False | None, False    |
| Zero of any numeric type      | 0, 0.0, 0j     |
| Empty sequence or collection  | '', (), [], {} |

+ Boolean operations:

| Object  | Value                                |
|---------|--------------------------------------|
| x or y  | If x is false, then y, else x        |
| x and y | If x is false, then x, else y        |
| not x   | If x is false, then True, else False |


## TYPE: Dictionary

+ The only mapping type in Python
+ Dictionary is a mutable object
+ Can be constructed in different ways:

| Option                                                  | Result                           |
|---------------------------------------------------------|----------------------------------|
| A pair of curly braces denotes an empty dict            | dct = {}                         |
| A comma-separated list of key:value pairs within braces | dct = {'a':1, 'b':2}             |
| Using dict comprehension                                | dct = {x:x**2 for x in iterable} |
| Built-in method                                         | dct = dict()                     |

+ Dictionary keys should be hashable objects
+ The following are the supported Dictionary operations:

| Operation                 | Result                                                                           |
|---------------------------|----------------------------------------------------------------------------------|
| list(dct)                 | Return list all keys                                                             |
| len(dct)                  | Return number of items                                                           |
| dct[k]                    | Return item in key k                                                             |
| dct[k] = val              | Set value of key k                                                               |
| del dct[k]                | Remove dct[k]                                                                    |
| k in dct                  | Return True if k is a key in dct                                                 |
| k not in dct              | Return True if k is not a key in dct                                             |
| iter(dct)                 | Return an iterator over the keys of dct                                          |
| clear()                   | Remove all items of dct                                                          |
| copy()                    | Create shallow copy of dct                                                       |
| get(k, *None*)            | Return value of key k, else default value                                        |
| items()                   | Return a view of all items (key, value) of dct                                   |
| keys()                    | Return a view of all keys of dct                                                 |
| values()                  | Return a view of all values of all keys in dct                                   |
| pop(k, [, *default*])     | Pop key if k exists in dct, else return default value                            |
| popitem()                 | Pop the last item in dct                                                         |
| reversed(d)               | Return reverse iterator over keys of dct                                         |
| setdefault(k, [,default]) | Return k value if k exists, else set default as k's value and return it          |
| update(other_dct)         | Update dct with key-value pair from the other dct, overwriting the existing keys |

    
## TYPE: Set

+ Set is an ordered collection of distinct hashable objects
+ It is used for the following cases:
  - Membership testing
  - Removing duplicates from a sequence
  - Computing mathematical operations - union, intersection, difference
+ Set does not record element position of order of insertion
+ Set does not support the following:
  - Indexing
  - Slicing
  - Other sequence-like behaviour
+ Set support the following operations:
  - x in set()
  - len(set)
  - for x in set()
+ There are two built-in types of set:

| Type      | Definition                                                                       |
|-----------|----------------------------------------------------------------------------------|
| Set       | - Mutable, thus has no hash value, and cannot be assigned as key in dictionaries |
| Frozenset | - Immutable and hashable, so it can be set as key in dictionaries                |

+ There are many ways to construct a set:

| Option                                           | Result                                               |
|--------------------------------------------------|------------------------------------------------------|
| A comma-separated list of elements within braces | st = {1,2,3}                                         |
| Set comprehension                                | st = {x for x in 'abracadabra' where x not 'abc'}    |
| Type constructor                                 | st = set([iterable])<br>fset = frozenset([iterable]) |

+ Both set and frozenset provide the following operations:

| Operation                              | Result                                                                     |
|----------------------------------------|----------------------------------------------------------------------------|
| len(st)                                | Return length of st                                                        |
| x in st                                | Return True if x exists in st                                              |
| x not in st                            | Return True if x does not exist in st                                      |
| isdisjoint(other_st)                   | Return True if st does not have common element with the other_st           |
| issubset(other_st)                     | Test whether every element in the st is in other                           |
| issuperset(other_st)                   | Test whether every element in other_st is in the st                        |
| union(*other_st)                       | Return a new set with elements from the set and all others                 |
| intersection(*other_st)                | Return a new set with elements common to the set and all others            |
| difference(*other_st)                  | Return a new set with elements in the set that are not in the others       |
| symmetric_difference(*other_st)        | Return a new set with elements in either the set or other but not both     |
| copy()                                 | Return a shallow copy of st                                                |
| update(*other_st)                      | Update the set, adding elements from all others                            |
| intersection_update(*other_st)         | Update the set, keeping only elements found in it and all others           |
| difference_update(*other_st)           | Update the set, removing elements found in others                          |
| symmetric_difference_update(*other_st) | Update the set, keeping only elements found in either set, but not in both |
| add(x)                                 | Add element x to st                                                        |
| remove(x)                              | Remove element x from st                                                   |
| discard(x)                             | Remove element x from st if it exists                                      |
| pop()                                  | Remove and return an arbitrary element from the set                        |
| clear()                                | Remove all elements from the set                                           |

***


**References**
: [Python Data Types](https://www.geeksforgeeks.org/python-data-types/)
: [Python Docs](https://docs.python.org/3/library/stdtypes.html#:~:text=There%20are%20three%20basic%20sequence,%2C%20tuples%2C%20and%20range%20objects.)
: [Teaser Image](https://www.educba.com/python-variable-types/)