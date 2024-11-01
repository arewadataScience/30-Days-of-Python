<div align="center">
  <h1> Python Programming for Data Science: Module 5 - Lists, Tuples and Sets</h1>
  <a class="header-badge" target="_blank" href="https://www.linkedin.com/in/asabeneh/">
  <img src="https://img.shields.io/badge/style--5eba00.svg?label=LinkedIn&logo=linkedin&style=social">
  </a>
  <a class="header-badge" target="_blank" href="https://twitter.com/Asabeneh">
  <img alt="Twitter Follow" src="https://img.shields.io/twitter/follow/asabeneh?style=social">
  </a>

<sub>Author:
<a href="https://www.linkedin.com/in/asabeneh/" target="_blank">Asabeneh Yetayeh</a><br>
<small> Second Edition: July - 2021</small>
</sub>

</div>

[<< Module 4](../04_Module_Strings/04_strings.md) | [Module 6 >>](../06_Module_Dictionaries/06_dictionaries.md)

![30DaysOfPython](../images/30DaysOfPython_banner3@2x.png)

- [Module 5](#module-5)
  - [Lists](#lists)
    - [How to Create a List](#how-to-create-a-list)
    - [Accessing List Items Using Positive Indexing](#accessing-list-items-using-positive-indexing)
    - [Accessing List Items Using Negative Indexing](#accessing-list-items-using-negative-indexing)
    - [Unpacking List Items](#unpacking-list-items)
    - [Slicing Items from a List](#slicing-items-from-a-list)
    - [Modifying Lists](#modifying-lists)
    - [Checking Items in a List](#checking-items-in-a-list)
    - [Adding Items to a List](#adding-items-to-a-list)
    - [Inserting Items into a List](#inserting-items-into-a-list)
    - [Removing Items from a List](#removing-items-from-a-list)
    - [Removing Items Using Pop](#removing-items-using-pop)
    - [Removing Items Using Del](#removing-items-using-del)
    - [Clearing List Items](#clearing-list-items)
    - [Copying a List](#copying-a-list)
    - [Joining Lists](#joining-lists)
    - [Counting Items in a List](#counting-items-in-a-list)
    - [Finding Index of an Item](#finding-index-of-an-item)
    - [Reversing a List](#reversing-a-list)
    - [Sorting List Items](#sorting-list-items)
  - [💻 Exercises: Day 5](#-exercises-day-5)
    - [Exercises: Level 1](#exercises-level-1)
    - [Exercises: Level 2](#exercises-level-2)

# Module 5

## Lists

There are four collection data types in Python :

- List: is a collection which is ordered and changeable(modifiable). Allows duplicate members.
- Tuple: is a collection which is ordered and unchangeable or unmodifiable(immutable). Allows duplicate members.
- Set: is a collection which is unordered, un-indexed and unmodifiable, but we can add new items to the set. Duplicate members are not allowed.
- Dictionary: is a collection which is unordered, changeable(modifiable) and indexed. No duplicate members.

A list is collection of different data types which is ordered and modifiable(mutable). A list can be empty or it may have different data type items.

### How to Create a List

In Python we can create lists in two ways:

- Using list built-in function

```py
# syntax
lst = list()
```

```py
empty_list = list() # this is an empty list, no item in the list
print(len(empty_list)) # 0
```

- Using square brackets, []

```py
# syntax
lst = []
```

```py
empty_list = [] # this is an empty list, no item in the list
print(len(empty_list)) # 0
```

Lists with initial values. We use _len()_ to find the length of a list.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']                     # list of fruits
vegetables = ['Tomato', 'Potato', 'Cabbage','Onion', 'Carrot']      # list of vegetables
animal_products = ['milk', 'meat', 'butter', 'yoghurt']             # list of animal products
web_techs = ['HTML', 'CSS', 'JS', 'React','Redux', 'Node', 'MongDB'] # list of web technologies
countries = ['Finland', 'Estonia', 'Denmark', 'Sweden', 'Norway']

# Print the lists and its length
print('Fruits:', fruits)
print('Number of fruits:', len(fruits))
print('Vegetables:', vegetables)
print('Number of vegetables:', len(vegetables))
print('Animal products:',animal_products)
print('Number of animal products:', len(animal_products))
print('Web technologies:', web_techs)
print('Number of web technologies:', len(web_techs))
print('Countries:', countries)
print('Number of countries:', len(countries))
```

```sh
output
Fruits: ['banana', 'orange', 'mango', 'lemon']
Number of fruits: 4
Vegetables: ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
Number of vegetables: 5
Animal products: ['milk', 'meat', 'butter', 'yoghurt']
Number of animal products: 4
Web technologies: ['HTML', 'CSS', 'JS', 'React', 'Redux', 'Node', 'MongDB']
Number of web technologies: 7
Countries: ['Finland', 'Estonia', 'Denmark', 'Sweden', 'Norway']
Number of countries: 5
```

- Lists can have items of different data types

```py
 lst = ['Asabeneh', 250, True, {'country':'Finland', 'city':'Helsinki'}] # list containing different data types
```

### Accessing List Items Using Positive Indexing

We access each item in a list using their index. A list index starts from 0. The picture below shows clearly where the index starts
![List index](../images/list_index.png)

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
first_fruit = fruits[0] # we are accessing the first item using its index
print(first_fruit)      # banana
second_fruit = fruits[1]
print(second_fruit)     # orange
last_fruit = fruits[3]
print(last_fruit) # lemon
# Last index
last_index = len(fruits) - 1
last_fruit = fruits[last_index]
```

### Accessing List Items Using Negative Indexing

Negative indexing means beginning from the end, -1 refers to the last item, -2 refers to the second last item.

![List negative indexing](../images/list_negative_indexing.png)

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
first_fruit = fruits[-4]
last_fruit = fruits[-1]
second_last = fruits[-2]
print(first_fruit)      # banana
print(last_fruit)       # lemon
print(second_last)      # mango
```

### Unpacking List Items

```py
lst = ['item1','item2','item3', 'item4', 'item5']
first_item, second_item, third_item, *rest = lst
print(first_item)     # item1
print(second_item)    # item2
print(third_item)     # item3
print(rest)           # ['item4', 'item5']

```

```py
# First Example
fruits = ['banana', 'orange', 'mango', 'lemon','lime','apple']
first_fruit, second_fruit, third_fruit, *rest = fruits 
print(first_fruit)     # banana
print(second_fruit)    # orange
print(third_fruit)     # mango
print(rest)           # ['lemon','lime','apple']
# Second Example about unpacking list
first, second, third,*rest, tenth = [1,2,3,4,5,6,7,8,9,10]
print(first)          # 1
print(second)         # 2
print(third)          # 3
print(rest)           # [4,5,6,7,8,9]
print(tenth)          # 10
# Third Example about unpacking list
countries = ['Germany', 'France','Belgium','Sweden','Denmark','Finland','Norway','Iceland','Estonia']
gr, fr, bg, sw, *scandic, es = countries
print(gr)
print(fr)
print(bg)
print(sw)
print(scandic)
print(es)
```

### Slicing Items from a List

- Positive Indexing: We can specify a range of positive indexes by specifying the start, end and step, the return value will be a new list. (default values for start = 0, end = len(lst) - 1 (last item), step = 1)

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
all_fruits = fruits[0:4] # it returns all the fruits
# this will also give the same result as the one above
all_fruits = fruits[0:] # if we don't set where to stop it takes all the rest
orange_and_mango = fruits[1:3] # it does not include the first index
orange_mango_lemon = fruits[1:]
orange_and_lemon = fruits[::2] # here we used a 3rd argument, step. It will take every 2cnd item - ['banana', 'mango']
```

- Negative Indexing: We can specify a range of negative indexes by specifying the start, end and step, the return value will be a new list.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
all_fruits = fruits[-4:] # it returns all the fruits
orange_and_mango = fruits[-3:-1] # it does not include the last index,['orange', 'mango']
orange_mango_lemon = fruits[-3:] # this will give starting from -3 to the end,['orange', 'mango', 'lemon']
reverse_fruits = fruits[::-1] # a negative step will take the list in reverse order,['lemon', 'mango', 'orange', 'banana']
```

### Modifying Lists

List is a mutable or modifiable ordered collection of items. Lets modify the fruit list.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits[0] = 'avocado'
print(fruits)       #  ['avocado', 'orange', 'mango', 'lemon']
fruits[1] = 'apple'
print(fruits)       #  ['avocado', 'apple', 'mango', 'lemon']
last_index = len(fruits) - 1
fruits[last_index] = 'lime'
print(fruits)        #  ['avocado', 'apple', 'mango', 'lime']
```

### Checking Items in a List

Checking an item if it is a member of a list using *in* operator. See the example below.

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
does_exist = 'banana' in fruits
print(does_exist)  # True
does_exist = 'lime' in fruits
print(does_exist)  # False
```

### Adding Items to a List

To add item to the end of an existing list we use the method *append()*.

```py
# syntax
lst = list()
lst.append(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.append('apple')
print(fruits)           # ['banana', 'orange', 'mango', 'lemon', 'apple']
fruits.append('lime')   # ['banana', 'orange', 'mango', 'lemon', 'apple', 'lime']
print(fruits)
```

### Inserting Items into a List

We can use *insert()* method to insert a single item at a specified index in a list. Note that other items are shifted to the right. The *insert()* methods takes two arguments:index and an item to insert.

```py
# syntax
lst = ['item1', 'item2']
lst.insert(index, item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.insert(2, 'apple') # insert apple between orange and mango
print(fruits)           # ['banana', 'orange', 'apple', 'mango', 'lemon']
fruits.insert(3, 'lime')   # ['banana', 'orange', 'apple', 'lime', 'mango', 'lemon']
print(fruits)
```

### Removing Items from a List

The remove method removes a specified item from a list

```py
# syntax
lst = ['item1', 'item2']
lst.remove(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon', 'banana']
fruits.remove('banana')
print(fruits)  # ['orange', 'mango', 'lemon', 'banana'] - this method removes the first occurrence of the item in the list
fruits.remove('lemon')
print(fruits)  # ['orange', 'mango', 'banana']
```

### Removing Items Using Pop

The *pop()* method removes the specified index, (or the last item if index is not specified):

```py
# syntax
lst = ['item1', 'item2']
lst.pop()       # last item
lst.pop(index)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.pop()
print(fruits)       # ['banana', 'orange', 'mango']

fruits.pop(0)
print(fruits)       # ['orange', 'mango']
```

### Removing Items Using Del

The *del* keyword removes the specified index and it can also be used to delete items within index range. It can also delete the list completely

```py
# syntax
lst = ['item1', 'item2']
del lst[index] # only a single item
del lst        # to delete the list completely
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon', 'kiwi', 'lime']
del fruits[0]
print(fruits)       # ['orange', 'mango', 'lemon', 'kiwi', 'lime']
del fruits[1]
print(fruits)       # ['orange', 'lemon', 'kiwi', 'lime']
del fruits[1:3]     # this deletes items between given indexes, so it does not delete the item with index 3!
print(fruits)       # ['orange', 'lime']
del fruits
print(fruits)       # This should give: NameError: name 'fruits' is not defined
```

### Clearing List Items

The *clear()* method empties the list:

```py
# syntax
lst = ['item1', 'item2']
lst.clear()
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.clear()
print(fruits)       # []
```

### Copying a List

It is possible to copy a list by reassigning it to a new variable in the following way: list2 = list1. Now, list2 is a reference of list1, any changes we make in list2 will also modify the original, list1. But there are lots of case in which we do not like to modify the original instead we like to have a different copy. One of way of avoiding the problem above is using _copy()_.

```py
# syntax
lst = ['item1', 'item2']
lst_copy = lst.copy()
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits_copy = fruits.copy()
print(fruits_copy)       # ['banana', 'orange', 'mango', 'lemon']
```

### Joining Lists

There are several ways to join, or concatenate, two or more lists in Python.

- Plus Operator (+)

```py
# syntax
list3 = list1 + list2
```

```py
positive_numbers = [1, 2, 3, 4, 5]
zero = [0]
negative_numbers = [-5,-4,-3,-2,-1]
integers = negative_numbers + zero + positive_numbers
print(integers) # [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
fruits = ['banana', 'orange', 'mango', 'lemon']
vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
fruits_and_vegetables = fruits + vegetables
print(fruits_and_vegetables ) # ['banana', 'orange', 'mango', 'lemon', 'Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
```

- Joining using extend() method
  The *extend()* method allows to append list in a list. See the example below.

```py
# syntax
list1 = ['item1', 'item2']
list2 = ['item3', 'item4', 'item5']
list1.extend(list2)
```

```py
num1 = [0, 1, 2, 3]
num2= [4, 5, 6]
num1.extend(num2)
print('Numbers:', num1) # Numbers: [0, 1, 2, 3, 4, 5, 6]
negative_numbers = [-5,-4,-3,-2,-1]
positive_numbers = [1, 2, 3,4,5]
zero = [0]

negative_numbers.extend(zero)
negative_numbers.extend(positive_numbers)
print('Integers:', negative_numbers) # Integers: [-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5]
fruits = ['banana', 'orange', 'mango', 'lemon']
vegetables = ['Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
fruits.extend(vegetables)
print('Fruits and vegetables:', fruits ) # Fruits and vegetables: ['banana', 'orange', 'mango', 'lemon', 'Tomato', 'Potato', 'Cabbage', 'Onion', 'Carrot']
```

### Counting Items in a List

The *count()* method returns the number of times an item appears in a list:

```py
# syntax
lst = ['item1', 'item2']
lst.count(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
print(fruits.count('orange'))   # 1
ages = [22, 19, 24, 25, 26, 24, 25, 24]
print(ages.count(24))           # 3
```

### Finding Index of an Item

The *index()* method returns the index of an item in the list:

```py
# syntax
lst = ['item1', 'item2']
lst.index(item)
```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
print(fruits.index('orange'))   # 1
ages = [22, 19, 24, 25, 26, 24, 25, 24]
print(ages.index(24))           # 2, the first occurrence
```

### Reversing a List

The *reverse()* method reverses the order of a list.

```py
# syntax
lst = ['item1', 'item2']
lst.reverse()

```

```py
fruits = ['banana', 'orange', 'mango', 'lemon']
fruits.reverse()
print(fruits) # ['lemon', 'mango', 'orange', 'banana']
ages = [22, 19, 24, 25, 26, 24, 25, 24]
ages.reverse()
print(ages) # [24, 25, 24, 26, 25, 24, 19, 22]
```

### Sorting List Items

To sort lists we can use _sort()_ method or _sorted()_ built-in functions. The _sort()_ method reorders the list items in ascending order and modifies the original list. If an argument of _sort()_ method reverse is equal to true, it will arrange the list in descending order.

- sort(): this method modifies the original list

  ```py
  # syntax
  lst = ['item1', 'item2']
  lst.sort()                # ascending
  lst.sort(reverse=True)    # descending
  ```

  **Example:**

  ```py
  fruits = ['banana', 'orange', 'mango', 'lemon']
  fruits.sort()
  print(fruits)             # sorted in alphabetical order, ['banana', 'lemon', 'mango', 'orange']
  fruits.sort(reverse=True)
  print(fruits) # ['orange', 'mango', 'lemon', 'banana']
  ages = [22, 19, 24, 25, 26, 24, 25, 24]
  ages.sort()
  print(ages) #  [19, 22, 24, 24, 24, 25, 25, 26]
 
  ages.sort(reverse=True)
  print(ages) #  [26, 25, 25, 24, 24, 24, 22, 19]
  ```

  sorted(): returns the ordered list without modifying the original list
  **Example:**

  ```py
  fruits = ['banana', 'orange', 'mango', 'lemon']
  print(sorted(fruits))   # ['banana', 'lemon', 'mango', 'orange']
  # Reverse order
  fruits = ['banana', 'orange', 'mango', 'lemon']
  fruits = sorted(fruits,reverse=True)
  print(fruits)     # ['orange', 'mango', 'lemon', 'banana']
  ```

🌕 You are diligent and you have already achieved quite a lot. You have just completed day 5 challenges and you are 5 steps a head in to your way to greatness. Now do some exercises for your brain and muscles.

## 💻 Exercises: Module 5

### Exercises: Level 1

1. Declare an empty list
2. Declare a list with more than 5 items
3. Find the length of your list
4. Get the first item, the middle item and the last item of the list
5. Declare a list called mixed_data_types, put your(name, age, height, marital status, address)
6. Declare a list variable named it_companies and assign initial values Facebook, Google, Microsoft, Apple, IBM, Oracle and Amazon.
7. Print the list using _print()_
8. Print the number of companies in the list
9. Print the first, middle and last company
10. Print the list after modifying one of the companies
11. Add an IT company to it_companies
12. Insert an IT company in the middle of the companies list
13. Change one of the it_companies names to uppercase (IBM excluded!)
14. Join the it_companies with a string '#;&nbsp; '
15. Check if a certain company exists in the it_companies list.
16. Sort the list using sort() method
17. Reverse the list in descending order using reverse() method
18. Slice out the first 3 companies from the list
19. Slice out the last 3 companies from the list
20. Slice out the middle IT company or companies from the list
21. Remove the first IT company from the list
22. Remove the middle IT company or companies from the list
23. Remove the last IT company from the list
24. Remove all IT companies from the list
25. Destroy the IT companies list
26. Join the following lists:

    ```py
    front_end = ['HTML', 'CSS', 'JS', 'React', 'Redux']
    back_end = ['Node','Express', 'MongoDB']
    ```

27. After joining the lists in question 26. Copy the joined list and assign it to a variable full_stack, then insert Python and SQL after Redux.

### Exercises: Level 2

1. The following is a list of 10 students ages:

```sh
ages = [19, 22, 19, 24, 20, 25, 26, 24, 25, 24]
```

- Sort the list and find the min and max age
- Add the min age and the max age again to the list
- Find the median age (one middle item or two middle items divided by two)
- Find the average age (sum of all items divided by their number )
- Find the range of the ages (max minus min)
- Compare the value of (min - average) and (max - average), use _abs()_ method

1. Find the middle country(ies) in the [countries list](https://github.com/Asabeneh/30-Days-Of-Python/tree/master/data/countries.py)
1. Divide the countries list into two equal lists if it is even if not one more country for the first half.
1. ['China', 'Russia', 'USA', 'Finland', 'Sweden', 'Norway', 'Denmark']. Unpack the first three countries and the rest as scandic countries.



## Tuples

A tuple is a collection of different data types which is ordered and unchangeable (immutable). Tuples are written with round brackets, (). Once a tuple is created, we cannot change its values. We cannot use add, insert, remove methods in a tuple because it is not modifiable (mutable). Unlike list, tuple has few methods. Methods related to tuples:

- tuple(): to create an empty tuple
- count(): to count the number of a specified item in a tuple
- index(): to find the index of a specified item in a tuple
- + operator: to join two or more tuples and to create a new tuple

### Creating a Tuple

- Empty tuple: Creating an empty tuple
  
  ```py
  # syntax
  empty_tuple = ()
  # or using the tuple constructor
  empty_tuple = tuple()
  ```

- Tuple with initial values
  
  ```py
  # syntax
  tpl = ('item1', 'item2','item3')
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  ```

### Tuple length

We use the _len()_ method to get the length of a tuple.

```py
# syntax
tpl = ('item1', 'item2', 'item3')
len(tpl)
```

### Accessing Tuple Items

- Positive Indexing
  Similar to the list data type we use positive or negative indexing to access tuple items.
  ![Accessing tuple items](../images/tuples_index.png)

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3')
  first_item = tpl[0]
  second_item = tpl[1]
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  first_fruit = fruits[0]
  second_fruit = fruits[1]
  last_index =len(fruits) - 1
  last_fruit = fruits[las_index]
  ```

- Negative indexing
  Negative indexing means beginning from the end, -1 refers to the last item, -2 refers to the second last and the negative of the list/tuple length refers to the first item.
  ![Tuple Negative indexing](../images/tuple_negative_indexing.png)

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3','item4')
  first_item = tpl[-4]
  second_item = tpl[-3]
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  first_fruit = fruits[-4]
  second_fruit = fruits[-3]
  last_fruit = fruits[-1]
  ```

### Slicing tuples

We can slice out a sub-tuple by specifying a range of indexes where to start and where to end in the tuple, the return value will be a new tuple with the specified items.

- Range of Positive Indexes

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3','item4')
  all_items = tpl[0:4]         # all items
  all_items = tpl[0:]         # all items
  middle_two_items = tpl[1:3]  # does not include item at index 3
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  all_fruits = fruits[0:4]    # all items
  all_fruits= fruits[0:]      # all items
  orange_mango = fruits[1:3]  # doesn't include item at index 3
  orange_to_the_rest = fruits[1:]
  ```

- Range of Negative Indexes

  ```py
  # Syntax
  tpl = ('item1', 'item2', 'item3','item4')
  all_items = tpl[-4:]         # all items
  middle_two_items = tpl[-3:-1]  # does not include item at index 3 (-1)
  ```

  ```py
  fruits = ('banana', 'orange', 'mango', 'lemon')
  all_fruits = fruits[-4:]    # all items
  orange_mango = fruits[-3:-1]  # doesn't include item at index 3
  orange_to_the_rest = fruits[-3:]
  ```

### Changing Tuples to Lists

We can change tuples to lists and lists to tuples. Tuple is immutable if we want to modify a tuple we should change it to a list.

```py
# Syntax
tpl = ('item1', 'item2', 'item3','item4')
lst = list(tpl)
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
fruits = list(fruits)
fruits[0] = 'apple'
print(fruits)     # ['apple', 'orange', 'mango', 'lemon']
fruits = tuple(fruits)
print(fruits)     # ('apple', 'orange', 'mango', 'lemon')
```

### Checking an Item in a Tuple

We can check if an item exists or not in a tuple using _in_, it returns a boolean.

```py
# Syntax
tpl = ('item1', 'item2', 'item3','item4')
'item2' in tpl # True
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
print('orange' in fruits) # True
print('apple' in fruits) # False
fruits[0] = 'apple' # TypeError: 'tuple' object does not support item assignment
```

### Joining Tuples

We can join two or more tuples using + operator

```py
# syntax
tpl1 = ('item1', 'item2', 'item3')
tpl2 = ('item4', 'item5','item6')
tpl3 = tpl1 + tpl2
```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
vegetables = ('Tomato', 'Potato', 'Cabbage','Onion', 'Carrot')
fruits_and_vegetables = fruits + vegetables
```

### Deleting Tuples

It is not possible to remove a single item in a tuple but it is possible to delete the tuple itself using _del_.

```py
# syntax
tpl1 = ('item1', 'item2', 'item3')
del tpl1

```

```py
fruits = ('banana', 'orange', 'mango', 'lemon')
del fruits
```

🌕 You are so brave, you made it to this far. You have just completed day 6 challenges and you are 6 steps a head in to your way to greatness. Now do some exercises for your brain and for your muscle.

## 💻 Tuple Exercises

### Tuple Exercises: Level 1

1. Create an empty tuple
2. Create a tuple containing names of your sisters and your brothers (imaginary siblings are fine)
3. Join brothers and sisters tuples and assign it to siblings
4. How many siblings do you have?
5. Modify the siblings tuple and add the name of your father and mother and assign it to family_members

### Tuple Exercises: Level 2

1. Unpack siblings and parents from family_members
1. Create fruits, vegetables and animal products tuples. Join the three tuples and assign it to a variable called food_stuff_tp.
1. Change the about food_stuff_tp  tuple to a food_stuff_lt list
1. Slice out the middle item or items from the food_stuff_tp tuple or food_stuff_lt list.
1. Slice out the first three items and the last three items from food_staff_lt list
1. Delete the food_staff_tp tuple completely
1. Check if an item exists in  tuple:

- Check if 'Estonia' is a nordic country
- Check if 'Iceland' is a nordic country

  ```py
  nordic_countries = ('Denmark', 'Finland','Iceland', 'Norway', 'Sweden')
  ```


## Sets

Set is a collection of items. Let me take you back to your elementary or high school Mathematics lesson. The Mathematics definition of a set can be applied also in Python. Set is a collection of unordered and un-indexed distinct elements. In Python set is used to store unique items, and it is possible to find the _union_, _intersection_, _difference_, _symmetric difference_, _subset_, _super set_ and _disjoint set_ among sets.

### Creating a Set

We use the _set()_ built-in function.

- Creating an empty set

```py
# syntax
st = set()
```

- Creating a set with initial items

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
```

**Example:**

```py
# syntax
fruits = {'banana', 'orange', 'mango', 'lemon'}
```

### Getting Set's Length

We use **len()** method to find the length of a set.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
len(st)
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
len(fruits)
```

### Accessing Items in a Set

We use loops to access items. We will see this in loop section

### Checking an Item

To check if an item exist in a list we use _in_ membership operator.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
print("Does set st contain item3? ", 'item3' in st) # Does set st contain item3? True
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
print('mango' in fruits ) # True
```

### Adding Items to a Set

Once a set is created we cannot change any items and we can also add additional items.

- Add one item using _add()_

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
st.add('item5')
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.add('lime')
```

- Add multiple items using _update()_
  The _update()_ allows to add multiple items to a set. The _update()_ takes a list argument.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
st.update(['item5','item6','item7'])
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = ('tomato', 'potato', 'cabbage','onion', 'carrot')
fruits.update(vegetables)
```

### Removing Items from a Set

We can remove an item from a set using _remove()_ method. If the item is not found _remove()_ method will raise errors, so it is good to check if the item exist in the given set. However, _discard()_ method doesn't raise any errors.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
st.remove('item2')
```

The pop() methods remove a random item from a list and it returns the removed item.

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.pop()  # removes a random item from the set

```

If we are interested in the removed item.

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
removed_item = fruits.pop() 
```

### Clearing Items in a Set

If we want to clear or empty the set we use _clear_ method.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
st.clear()
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
fruits.clear()
print(fruits) # set()
```

### Deleting a Set

If we want to delete the set itself we use _del_ operator.

```py
# syntax
st = {'item1', 'item2', 'item3', 'item4'}
del st
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
del fruits
```

### Converting List to Set

We can convert list to set and set to list. Converting list to set removes duplicates and only unique items will be reserved.

```py
# syntax
lst = ['item1', 'item2', 'item3', 'item4', 'item1']
st = set(lst)  # {'item2', 'item4', 'item1', 'item3'} - the order is random, because sets in general are unordered
```

**Example:**

```py
fruits = ['banana', 'orange', 'mango', 'lemon','orange', 'banana']
fruits = set(fruits) # {'mango', 'lemon', 'banana', 'orange'}
```

### Joining Sets

We can join two sets using the _union()_ or _update()_ method.

- Union
  This method returns a new set

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item5', 'item6', 'item7', 'item8'}
st3 = st1.union(st2)
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = {'tomato', 'potato', 'cabbage','onion', 'carrot'}
print(fruits.union(vegetables)) # {'lemon', 'carrot', 'tomato', 'banana', 'mango', 'orange', 'cabbage', 'potato', 'onion'}
```

- Update
  This method inserts a set into a given set

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item5', 'item6', 'item7', 'item8'}
st1.update(st2) # st2 contents are added to st1
```

**Example:**

```py
fruits = {'banana', 'orange', 'mango', 'lemon'}
vegetables = {'tomato', 'potato', 'cabbage','onion', 'carrot'}
fruits.update(vegetables)
print(fruits) # {'lemon', 'carrot', 'tomato', 'banana', 'mango', 'orange', 'cabbage', 'potato', 'onion'}
```

### Finding Intersection Items

Intersection returns a set of items which are in both the sets. See the example

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item3', 'item2'}
st1.intersection(st2) # {'item3', 'item2'}
```

**Example:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.intersection(even_numbers) # {0, 2, 4, 6, 8, 10}

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.intersection(dragon)     # {'o', 'n'}
```

### Checking Subset and Super Set

A set can be a subset or super set of other sets:

- Subset: _issubset()_
- Super set: _issuperset_

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.issubset(st1) # True
st1.issuperset(st2) # True
```

**Example:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.issubset(even_numbers) # False, because it is a super set
whole_numbers.issuperset(even_numbers) # True

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.issubset(dragon)     # False
```

### Checking the Difference Between Two Sets

It returns the difference between two sets.

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.difference(st1) # set()
st1.difference(st2) # {'item1', 'item4'} => st1\st2
```

**Example:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
even_numbers = {0, 2, 4, 6, 8, 10}
whole_numbers.difference(even_numbers) # {1, 3, 5, 7, 9}

python = {'p', 'y', 't', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.difference(dragon)     # {'p', 'y', 't'}  - the result is unordered (characteristic of sets)
dragon.difference(python)     # {'d', 'r', 'a', 'g'}
```

### Finding Symmetric Difference Between Two Sets

It returns the symmetric difference between two sets. It means that it returns a set that contains all items from both sets, except items that are present in both sets, mathematically: (A\B) ∪ (B\A)

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
# it means (A\B)∪(B\A)
st2.symmetric_difference(st1) # {'item1', 'item4'}
```

**Example:**

```py
whole_numbers = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
some_numbers = {1, 2, 3, 4, 5}
whole_numbers.symmetric_difference(some_numbers) # {0, 6, 7, 8, 9, 10}

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.symmetric_difference(dragon)  # {'r', 't', 'p', 'y', 'g', 'a', 'd', 'h'}
```

### Joining Sets

If two sets do not have a common item or items we call them disjoint sets. We can check if two sets are joint or disjoint using _isdisjoint()_ method.

```py
# syntax
st1 = {'item1', 'item2', 'item3', 'item4'}
st2 = {'item2', 'item3'}
st2.isdisjoint(st1) # False
```

**Example:**

```py
even_numbers = {0, 2, 4 ,6, 8}
odd_numbers = {1, 3, 5, 7, 9}
even_numbers.isdisjoint(odd_numbers) # True, because no common item

python = {'p', 'y', 't', 'h', 'o','n'}
dragon = {'d', 'r', 'a', 'g', 'o','n'}
python.isdisjoint(dragon)  # False, there are common items {'o', 'n'}
```

🌕 You are a rising star . You have just completed day 7 challenges and you are 7 steps ahead in to your way to greatness. Now do some exercises for your brain and muscles.

## 💻 Sets Exercises

```py
# sets
it_companies = {'Facebook', 'Google', 'Microsoft', 'Apple', 'IBM', 'Oracle', 'Amazon'}
A = {19, 22, 24, 20, 25, 26}
B = {19, 22, 20, 25, 26, 24, 28, 27}
age = [22, 19, 24, 25, 26, 24, 25, 24]
```

### Sets Exercises: Level 1

1. Find the length of the set it_companies
2. Add 'Twitter' to it_companies
3. Insert multiple IT companies at once to the set it_companies
4. Remove one of the companies from the set it_companies
5. What is the difference between remove and discard

### Sets Exercises: Level 2

1. Join A and B
1. Find A intersection B
1. Is A subset of B
1. Are A and B disjoint sets
1. Join A with B and B with A
1. What is the symmetric difference between A and B
1. Delete the sets completely

### Sets Exercises: Level 3

1. Convert the ages to a set and compare the length of the list and the set, which one is bigger?
1. Explain the difference between the following data types: string, list, tuple and set
2. _I am a teacher and I love to inspire and teach people._ How many unique words have been used in the sentence? Use the split methods and set to get the unique words.



🎉 CONGRATULATIONS ! 🎉

[<< Module 4](../04_Module_Strings/04_strings.md) | [Module 6 >>](../06_Module_Dictionaries/06_dictionaries.md)
