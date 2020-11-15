---
title: What Can Python Data Types Do?
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

**Built-in Data Types**

+ Numeric
    + Integer
    + Float
    + Complex Number
+ Sequence
    + String
    + Tuple
    + List
+ Dictionary
+ Set
+ Boolean

***

**How to check the data type of a variable?**

Use **`type()`** method   


## Numeric Types

> Represent data with numeric value

### Integer
+ `int`
+ Represented by int class
+ May contain positive or negative whole number only
+ No limit on how long an int value can be

### Float
+ `float`
+ Represeneted by float class
+ Real number with decimal points

### Complex
+ `complex`
+ Represented by complex class
+ Specified as `(real part) + (imaginary part) j` , i.e. **-2+3j**
+ Has some built-in accessors

***

## Sequence Type

Ordered collection of similar of different data types

### String
+ `str`
+  Represented by str class
+ Array of bytes representing Unicode characters
+ In Python, there is no `char` type. It is just a string with length of 1
+ Strings should be in a *single*, *double*, or *triple* quote

  **Using Quotes in Strings**

    Single quote
    + If string has apostrophe or other special characters, you need to escape it using backslash
        ```
        str = 'Hello world, it\'s me'
        ```

    + If string has double quotes, no need to escape it
        ```
        str = 'He replied "hi" to me'
        ```

    + If string has both single and double quote, you need to escape the quotes that are the same with the enclosing quotes, else it will fail
        ```
        str = 'She said, "Oh, it\'s you again."'
        ```

  <br/>
  Double quote
    + If string has any special character aside from double quotes, you need not to escape it
        ```
        str = "Hello world, it's me"
        ```

    + If string has double quotes, you need to escape it
        ```
        str = "She said, \"Oh hello\""
        ```

    + If string has both single and double quote, you need to escape the quotes that are the same with the enclosing quotes, else it will fail
        ```
        str = "She said, \"Oh, it's you again.\""
        ```

  <br/>
  Triple quote
    + If string has both single and double quotes, you can use triple quotes to not worry about escaping characters
    + *However*, if the string starts or ends with a single or double quotes, we need to use the quotes that differ from starting or ending one    
        ```
        str = '''She said, "Oh, it's you again."'''
        ```

    + If string has multi-line, use triple quote. It is interpreted the same with using `\n` but it is more readable
        ```
        str = '''Hello
              World'''
        ```
    + It is also being used for docstring and multi-line comments
        ```
        def test():
          """ This is a doctring. """
        ```

  **Accessing Elements in a String**

    + Individual characters in a string can be accessed through their index
    + Can use positive index if starting from the first character
    + Can use negative index if starting from the last character, where `-1` means the last character
        ```
        str = 'Python tutorial'
        
        char1 = str[0]
        char15 = str[-1]
        ```

  **Getting Length of String**

    + Use `len()` method


### List
+ `[]`
+ Like an array

  **Operations in List**
  
    Creating list
    ```
    # Empty list
    lst = []

    # With initial values
    lst = [1, 'hello', 3.5]
    
    # Multi-dimensional list
    lst = [[1,2], ['hello'], [3.5, 'world]]
    ```

    Accessing element
    ```
    lst = [1, 'hello', 3.5]

    # Access first element
    lst[0]

    # Access last element
    lst[-1]
    ```    

    Get size of list
    ```
    lst = [1, 'hello', 3.5]

    list_size = len(lst)
    ```  

    Adding to list
    ```
    lst = [1, 'hello', 3.5]

    # Add at the end of the list - one element at a time
    lst.append('world')

    # Add at a desired position in the list - passing index position and the value to be added
    lst.insert(2, 'world')

    # Add at the end of the list - multiple elements
    lst.extend([8, 2, 1])

    ```  

    Removing element from list
    ```
    lst = [1, 'hello', 3.5]

    # Remove an element with the given value
    lst.remove(1)

    # Remove and return the last element
    val = lst.pop()

    # Remove all elements from the list
    lst.clear()
    ```

    Slicing a list
    ```
    # Print elements from beginning to a range use
    sliced_lst = lst[:index]

    # Print elements from end-use
    sliced_lst = lst[:-index]

    # Print elements from specific index to end-use
    sliced_lst = lst[index:]

    # Print elements within ranges
    sliced_lst = lst[start_index:end_index]

    # Print the whole list
    sliced_lst = lst[:]

    # Print the whole list in reverse order
    sliced_lst = lst[::-1]
    ```

    Sort, Reverse, Copy a list
    ```
    # Sort a list - default is ascending
    lst.sort()
    lst.sort(reverse=True)

    # Reverse order of elements
    lst.reverse()

    # Copy a list - changes in new list will not affect the orig list
    # considering there is no nested element
    copied_lst = lst.copy()

    # Deep copy of a list
    # Use copy library
    import copy
    copied_list = copy.deepcopy(lst)
    ```

### Tuple
+ `()`
+ Like a list but *immutable* - meaning cannot be modified once it is created

  **Operations in List**

    Creating a Tuple
    ```
    # Empty tuple
    tuple = ()

    # With initial values
    tuple = ('hello', 'world')

    # From a list
    lst = [1, 2, 3]
    tuple = tuple(lst)

    # From built-in function
    tuple = tuple('hello')

    # With nested tuples
    tuple1 = (1, 2)
    tuple2 = ('hello', 'world')
    tuple3 = (tuple1, tuple2)
    ```

    Accesing element
    ```
    tuple = (1, ('hello', 'world'), 3)

    # Access first element
    tuple[0]

    # Access last element
    tuple[-1]

    # Acces nested element
    tuple[1][0]
    ```

    Deleting a tuple
    ```
    # Since tuple is immutable, we cannot delete an element only, but the whole tuple
    del(tuple)
    ```

***

## Dictionary
+ {}
+ Key-value pair

  **Operations in List**

    Creating dictionary
    ```
    # Empty dictionary
    dct = {}

    # With initial values
    dct = {
      'key1' : 1,
      'key2' : 2
    }
    ```

    Accessing element
    ```
    # Using key - may result to KeyError if the key doesn't exist
    val = dct['key1']

    # Using get - safer since it can have a default value
    val = dct.get('key1)
    val = dct.get('key1', None)

    # Get all keys
    keys = dct.keys()

    # Get all values
    vals = dct.values()

    # Get all key-value pairs in tuple
    pairs = dct.items()
    ```

    Add element
    ```
    # Add new key-value pair
    dct['new_key'] = 'new_value'

    # Add elements from another dictionary
    dct.update(other_dct)
    ```

    Removing element
    ```
    # Remove a key
    del dct['key1]

    # Remove and return key's value
    val = dct.pop('key1')

    # Remove all items
    dct.clear()

    # Remove the whole dictionary
    del dct
    ```
    
## Set
+ set()
+ Unordered collection, iterable, mutable, and has no duplicate

  **Operations in List**

    Creating set
    ```
    # Empty dictionary
    st = set()

    # With initial values
    st = set(1,2,3)

    # From a list
    lst = [1,2,1,3]
    st = set(lst)
    ```

    Accessing element
    ```
    # Since it is unordered, there is no indexing
    # Can use loop
    for i in st:
      print(i)

    # Use in keyword
    val = 1
    if val in st:
      print(val)
    ```

    Adding element
    ```
    # Add one element at a time
    st = set(1,2,3)
    st.add(4)

    # Add multiple elements
    st.update([4,5,6])
    ```

    Removing element
    ```
    # Use built-in remove() - will produce error if the element doesnt exist
    st.remove(1)

    # Use discard() - set will remain unchanged if element doesnt exist
    st.discard(1)

    # Remove all elements
    st.clear()
    ```

    Union, Difference, Intersection
    ```
    set1 = set(1,2,3)
    set2 = set(3,4,5)

    # Get union of 2 or more sets
    set1.uniion(set2)

    # Return the difference between sets as a new set
    set3 = set1.difference(set2)

    # Remove all elements of another set from a list
    set1.difference_update(set2)

    # Get intersection of 2 sets as a new set
    set3 = set1.intersection(set2)

    # Returns True if 2 sets have null intersetion
    set1.isdisjoint(set2)

    # Returns True if another set contains a set
    set1.issubset(set2)

    # Returnds True if a set contains another set
    set1.issuperset(set2)
    ```

## Boolean
+ Either *True* or *False*




References:
: [Teaser Image](https://www.educba.com/python-variable-types/)
: [Python Data Types](https://www.geeksforgeeks.org/python-data-types/)