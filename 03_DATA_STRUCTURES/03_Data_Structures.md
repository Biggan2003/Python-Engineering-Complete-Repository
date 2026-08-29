# 🐍 Python Engineering --- 03. Python Data Structures

> **Goal:** Build a strong understanding of Python's built-in data
> structures so you can confidently choose, manipulate, compare, and
> debug the right structure for a given programming problem.
>
> This chapter is written for both **deep learning** and **long-term
> revision**. Every important concept focuses on what it is, why it
> exists, how it works, how to use it, common mistakes, and when it is
> appropriate.

------------------------------------------------------------------------

# 📚 Chapter Overview

``` text
03. Python Data Structures
│
├── Lists & Mutable Collections
│   ├── What is a List?
│   ├── Creating Lists
│   ├── Indexing
│   ├── Negative Indexing
│   ├── Slicing
│   ├── Updating Elements
│   ├── append()
│   ├── extend()
│   ├── insert()
│   ├── remove()
│   ├── pop()
│   ├── clear()
│   ├── sort()
│   ├── sorted()
│   ├── reverse()
│   └── Common List Patterns
│
├── Tuples & Immutable Collections
│   ├── What is a Tuple?
│   ├── Creating Tuples
│   ├── Single-Element Tuples
│   ├── Indexing & Slicing
│   ├── Immutability
│   ├── Packing
│   ├── Unpacking
│   ├── Extended Unpacking
│   └── Tuple Use Cases
│
├── Sets & Unique Collections
│   ├── What is a Set?
│   ├── Creating Sets
│   ├── Uniqueness
│   ├── Membership Testing
│   ├── add()
│   ├── remove()
│   ├── discard()
│   ├── Union
│   ├── Intersection
│   ├── Difference
│   └── Symmetric Difference
│
├── Dictionaries & Key-Value Mapping
│   ├── What is a Dictionary?
│   ├── Key → Value Model
│   ├── Creating Dictionaries
│   ├── Key Lookup
│   ├── get()
│   ├── Adding & Updating
│   ├── pop()
│   ├── keys()
│   ├── values()
│   ├── items()
│   ├── update()
│   └── Nested Dictionaries
│
├── Indexing, Slicing & Unpacking
│   ├── Positive Indexing
│   ├── Negative Indexing
│   ├── Slice Syntax
│   ├── Slice Assignment
│   ├── Tuple Unpacking
│   └── Starred Unpacking
│
├── Nested Data Structures
│   ├── List of Lists
│   ├── List of Dictionaries
│   ├── Dictionary of Lists
│   ├── Dictionary of Dictionaries
│   └── Real-World JSON-Like Data
│
├── Collection Methods
│   ├── Membership
│   ├── len()
│   ├── min()
│   ├── max()
│   ├── sum()
│   ├── sorted()
│   ├── enumerate()
│   └── zip()
│
└── Choosing the Right Data Structure
    ├── list
    ├── tuple
    ├── set
    ├── dict
    ├── Mutability
    ├── Ordering
    ├── Uniqueness
    ├── Lookup Requirements
    └── Performance Intuition
```

------------------------------------------------------------------------

# 🧠 01. What Is a Data Structure?

A **data structure** is a way of organizing data so that a program can
store, access, modify, search, and process that data effectively.

For example, imagine you need to store the names of five students.

You could create five separate variables:

``` python
student1 = "Alice"
student2 = "Bob"
student3 = "Charlie"
student4 = "David"
student5 = "Eva"
```

This works, but it becomes difficult to manage as the amount of data
grows.

A list gives you a structured solution:

``` python
students = ["Alice", "Bob", "Charlie", "David", "Eva"]
```

Now the data is grouped into one object that can be iterated, searched,
modified, sorted, and passed around.

### Mental Model

``` text
Raw Data
   ↓
Choose a structure
   ↓
Organize the data
   ↓
Perform operations efficiently
   ↓
Build useful programs
```

### Why this matters

Choosing the right data structure is not just a syntax decision.

It affects:

-   How easy the code is to understand
-   What operations are possible
-   How the data can be modified
-   How efficiently the program can search or update data
-   How naturally the data represents the real-world problem

------------------------------------------------------------------------

# 🧩 02. Main Built-in Data Structures

Python provides four especially important built-in collection
structures:

``` text
list
tuple
set
dict
```

Their purposes are different.

  Structure   Main Purpose           Mutable   Duplicates   Positional Access
  ----------- -------------------- --------- ------------ -------------------
  `list`      Ordered collection         Yes          Yes                 Yes
  `tuple`     Fixed sequence              No          Yes                 Yes
  `set`       Unique collection          Yes           No                  No
  `dict`      Key-value mapping          Yes     Keys: No              By key

### Quick Decision

``` text
Need an ordered collection that changes?
        ↓
      list

Need an ordered collection that should not change?
        ↓
      tuple

Need unique values?
        ↓
      set

Need key → value relationships?
        ↓
      dict
```

------------------------------------------------------------------------

# 📋 03. Lists

A **list** is an ordered, mutable collection.

``` python
numbers = [10, 20, 30, 40]

print(numbers)
```

Output:

``` text
[10, 20, 30, 40]
```

### What does ordered mean?

Each item has a position.

``` text
Value:   10   20   30   40
Index:    0    1    2    3
```

### What does mutable mean?

You can change the existing list after creating it.

``` python
numbers[1] = 99

print(numbers)
```

Output:

``` text
[10, 99, 30, 40]
```

------------------------------------------------------------------------

# ✍️ 04. Creating Lists

Empty list:

``` python
items = []
```

List with values:

``` python
languages = ["Python", "Java", "C++"]
```

Using `list()`:

``` python
items = list()
```

Converting another iterable:

``` python
letters = list("Python")

print(letters)
```

Output:

``` text
['P', 'y', 't', 'h', 'o', 'n']
```

### Important

A list can contain different object types:

``` python
data = ["Python", 23, True, 3.14]
```

Python allows this, but mixing unrelated types should be intentional.

------------------------------------------------------------------------

# 🔢 05. List Indexing

Indexing accesses an element by its position.

``` python
languages = ["Python", "Java", "C++"]

print(languages[0])
print(languages[1])
print(languages[2])
```

Output:

``` text
Python
Java
C++
```

Python uses **zero-based indexing**.

``` text
First item  → index 0
Second item → index 1
Third item  → index 2
```

------------------------------------------------------------------------

# 🔙 06. Negative Indexing

Negative indexes count from the end.

``` python
languages = ["Python", "Java", "C++"]

print(languages[-1])
print(languages[-2])
```

Output:

``` text
C++
Java
```

Mental model:

``` text
Python   Java   C++
   -3      -2    -1
```

### Tip

Use `-1` when you need the last element without calculating
`len(list) - 1`.

------------------------------------------------------------------------

# ✂️ 07. List Slicing

Slicing extracts a portion of a list.

### Syntax

``` python
list[start:stop:step]
```

Example:

``` python
numbers = [0, 1, 2, 3, 4, 5]

print(numbers[1:4])
```

Output:

``` text
[1, 2, 3]
```

The `stop` index is exclusive.

``` text
start → included
stop  → excluded
```

More examples:

``` python
print(numbers[:3])
print(numbers[3:])
print(numbers[::2])
print(numbers[::-1])
```

------------------------------------------------------------------------

# ✏️ 08. Slice Assignment

Because lists are mutable, slices can also be assigned.

``` python
numbers = [1, 2, 3, 4, 5]

numbers[1:3] = [20, 30]

print(numbers)
```

Output:

``` text
[1, 20, 30, 4, 5]
```

The replacement can even contain a different number of elements:

``` python
numbers[1:3] = [99]

print(numbers)
```

Output:

``` text
[1, 99, 4, 5]
```

This is powerful because slice assignment can replace, remove, or insert
multiple elements.

------------------------------------------------------------------------

# ➕ 09. `append()`

`append()` adds exactly one object to the end of a list.

``` python
numbers = [1, 2, 3]

numbers.append(4)

print(numbers)
```

Output:

``` text
[1, 2, 3, 4]
```

If you append another list:

``` python
numbers.append([5, 6])

print(numbers)
```

Output:

``` text
[1, 2, 3, 4, [5, 6]]
```

The entire `[5, 6]` becomes one element.

------------------------------------------------------------------------

# ➕ 10. `extend()`

`extend()` adds elements from an iterable.

``` python
numbers = [1, 2, 3]

numbers.extend([4, 5])

print(numbers)
```

Output:

``` text
[1, 2, 3, 4, 5]
```

### `append()` vs `extend()`

``` text
append([4, 5])
        ↓
[1, 2, 3, [4, 5]]

extend([4, 5])
        ↓
[1, 2, 3, 4, 5]
```

### Rule

``` text
Add ONE object       → append()
Add iterable's items → extend()
```

------------------------------------------------------------------------

# 📍 11. `insert()`

`insert(index, value)` adds a value at a specific position.

``` python
numbers = [10, 30]

numbers.insert(1, 20)

print(numbers)
```

Output:

``` text
[10, 20, 30]
```

Syntax:

``` python
list.insert(index, value)
```

Use `insert()` when the position matters.

------------------------------------------------------------------------

# ❌ 12. `remove()`

`remove(value)` removes the first matching value.

``` python
numbers = [10, 20, 20, 30]

numbers.remove(20)

print(numbers)
```

Output:

``` text
[10, 20, 30]
```

If the value does not exist, Python raises `ValueError`.

``` python
# numbers.remove(100)
```

### Important

`remove()` works by **value**, not by index.

------------------------------------------------------------------------

# 🗑️ 13. `pop()`

`pop()` removes and returns an element.

``` python
numbers = [10, 20, 30]

value = numbers.pop()

print(value)
print(numbers)
```

Output:

``` text
30
[10, 20]
```

You can provide an index:

``` python
numbers = [10, 20, 30]

value = numbers.pop(1)

print(value)
print(numbers)
```

Output:

``` text
20
[10, 30]
```

### Remember

``` text
remove(value) → remove by value
pop(index)    → remove by index and return it
```

------------------------------------------------------------------------

# 🧹 14. `clear()`

`clear()` removes every element from the list.

``` python
numbers = [10, 20, 30]

numbers.clear()

print(numbers)
```

Output:

``` text
[]
```

The list object still exists; its contents have been removed.

------------------------------------------------------------------------

# 🔎 15. List Membership

Use `in` to test membership.

``` python
languages = ["Python", "Java", "C++"]

print("Python" in languages)
print("Go" in languages)
```

Output:

``` text
True
False
```

Use `not in` when you want the opposite test.

------------------------------------------------------------------------

# 🔢 16. `index()` and `count()`

`index()` finds the first matching position.

``` python
numbers = [10, 20, 30, 20]

print(numbers.index(30))
```

Output:

``` text
2
```

`count()` counts occurrences.

``` python
print(numbers.count(20))
```

Output:

``` text
2
```

If `index()` cannot find the value, it raises `ValueError`.

------------------------------------------------------------------------

# 🔃 17. `sort()`

`sort()` sorts a list **in place**.

``` python
numbers = [40, 10, 30, 20]

numbers.sort()

print(numbers)
```

Output:

``` text
[10, 20, 30, 40]
```

Descending:

``` python
numbers.sort(reverse=True)

print(numbers)
```

Output:

``` text
[40, 30, 20, 10]
```

### Important

`sort()` returns `None`.

``` python
result = numbers.sort()

print(result)
```

Output:

``` text
None
```

------------------------------------------------------------------------

# 🔃 18. `sorted()`

`sorted()` creates a new sorted list.

``` python
numbers = [40, 10, 30, 20]

result = sorted(numbers)

print(result)
print(numbers)
```

Output:

``` text
[10, 20, 30, 40]
[40, 10, 30, 20]
```

### Difference

``` text
sort()
  → modifies existing list

sorted()
  → returns a new sorted list
```

------------------------------------------------------------------------

# 🔄 19. `reverse()`

`reverse()` reverses a list in place.

``` python
numbers = [1, 2, 3, 4]

numbers.reverse()

print(numbers)
```

Output:

``` text
[4, 3, 2, 1]
```

It returns `None`.

If you want a reversed iterator without changing the original list:

``` python
numbers = [1, 2, 3]

for number in reversed(numbers):
    print(number)
```

------------------------------------------------------------------------

# 📊 20. Useful List Functions

``` python
numbers = [10, 20, 30]

print(len(numbers))
print(sum(numbers))
print(min(numbers))
print(max(numbers))
```

Output:

``` text
3
60
10
30
```

These functions are useful for common collection-processing tasks.

------------------------------------------------------------------------

# 🔁 21. Iterating Through Lists

The normal way to process every element is a `for` loop.

``` python
languages = ["Python", "Java", "C++"]

for language in languages:
    print(language)
```

Output:

``` text
Python
Java
C++
```

------------------------------------------------------------------------

# 🔢 22. `enumerate()`

When you need both the index and the value, use `enumerate()`.

``` python
languages = ["Python", "Java", "C++"]

for index, language in enumerate(languages):
    print(index, language)
```

Output:

``` text
0 Python
1 Java
2 C++
```

### Why use it?

Instead of manually writing:

``` python
for i in range(len(languages)):
    print(i, languages[i])
```

use:

``` python
for i, language in enumerate(languages):
    print(i, language)
```

This is cleaner and expresses the intent directly.

------------------------------------------------------------------------

# 📦 23. Tuples

A **tuple** is an ordered, immutable sequence.

``` python
point = (10, 20)

print(point)
print(type(point))
```

Output:

``` text
(10, 20)
<class 'tuple'>
```

A tuple behaves similarly to a list for indexing and iteration, but its
contents cannot be changed in place.

------------------------------------------------------------------------

# ✍️ 24. Creating Tuples

Standard syntax:

``` python
point = (10, 20, 30)
```

Parentheses can often be omitted:

``` python
point = 10, 20, 30
```

Python recognizes the commas as the important part of tuple
construction.

------------------------------------------------------------------------

# 1️⃣ 25. Single-Element Tuple

This is a common beginner mistake.

``` python
value = (10)

print(type(value))
```

Output:

``` text
<class 'int'>
```

A one-element tuple requires a comma:

``` python
value = (10,)

print(type(value))
```

Output:

``` text
<class 'tuple'>
```

### Remember

``` text
(10)  → int
(10,) → tuple
```

------------------------------------------------------------------------

# 🔢 26. Tuple Indexing & Slicing

Tuples support indexing:

``` python
point = (10, 20, 30)

print(point[0])
print(point[-1])
```

Output:

``` text
10
30
```

They also support slicing:

``` python
print(point[1:])
```

Output:

``` text
(20, 30)
```

The result of tuple slicing is another tuple.

------------------------------------------------------------------------

# 🧊 27. Tuple Immutability

You cannot change a tuple element.

``` python
point = (10, 20)

# point[0] = 50
```

The commented statement raises `TypeError`.

### Why is this useful?

Immutability communicates that the collection represents a fixed group
of values.

Examples:

``` python
coordinates = (10.5, 20.3)
rgb = (255, 128, 0)
```

These values often represent a single logical record.

------------------------------------------------------------------------

# 📦 28. Tuple Packing

Packing means putting multiple values into one tuple.

``` python
point = 10, 20, 30

print(point)
```

Output:

``` text
(10, 20, 30)
```

The tuple is created automatically from the comma-separated values.

------------------------------------------------------------------------

# 📤 29. Tuple Unpacking

Unpacking assigns tuple elements to variables.

``` python
point = (10, 20)

x, y = point

print(x)
print(y)
```

Output:

``` text
10
20
```

The number of variables normally needs to match the number of values.

------------------------------------------------------------------------

# ⭐ 30. Extended Unpacking

The starred variable collects remaining values into a list.

``` python
numbers = [1, 2, 3, 4, 5]

first, *middle, last = numbers

print(first)
print(middle)
print(last)
```

Output:

``` text
1
[2, 3, 4]
5
```

### Important

The starred target receives a **list**, even when the source is a tuple.

------------------------------------------------------------------------

# 🔄 31. Variable Swapping

Python can swap values using tuple unpacking.

``` python
a = 10
b = 20

a, b = b, a

print(a, b)
```

Output:

``` text
20 10
```

This is a very common Python idiom.

------------------------------------------------------------------------

# 🟢 32. Sets

A **set** is a mutable collection of unique, hashable elements.

``` python
numbers = {10, 20, 30, 20}

print(numbers)
```

The duplicate `20` is removed.

Conceptually:

``` text
{10, 20, 30, 20}
          ↓
{10, 20, 30}
```

### Why use a set?

Use a set when uniqueness is important or when membership testing is a
major operation.

------------------------------------------------------------------------

# ✍️ 33. Creating Sets

Set with values:

``` python
numbers = {10, 20, 30}
```

Empty set:

``` python
numbers = set()
```

### Important

``` python
{}
```

creates an empty dictionary, not an empty set.

This is one of the most common Python collection mistakes.

------------------------------------------------------------------------

# 🔍 34. Set Membership

Sets are designed for membership testing.

``` python
languages = {"Python", "Java", "C++"}

print("Python" in languages)
print("Go" in languages)
```

Output:

``` text
True
False
```

Do not use indexing:

``` python
# languages[0]
```

A set does not provide positional indexing.

------------------------------------------------------------------------

# ➕ 35. `add()`

`add()` inserts one element.

``` python
languages = {"Python", "Java"}

languages.add("C++")

print(languages)
```

Adding an element that already exists does not create a duplicate.

------------------------------------------------------------------------

# ❌ 36. Set `remove()`

`remove()` deletes an element.

``` python
numbers = {10, 20, 30}

numbers.remove(20)

print(numbers)
```

If the element is missing, `remove()` raises `KeyError`.

------------------------------------------------------------------------

# 🛡️ 37. Set `discard()`

`discard()` also removes an element, but it does not raise an error if
the element is absent.

``` python
numbers = {10, 20, 30}

numbers.discard(100)

print(numbers)
```

No exception occurs.

### Difference

``` text
remove(x)
  → error if x is absent

discard(x)
  → safely does nothing if x is absent
```

------------------------------------------------------------------------

# 🔗 38. Set Union

Union combines unique elements from both sets.

``` python
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)
```

Output:

``` text
{1, 2, 3, 4, 5}
```

Equivalent method:

``` python
a.union(b)
```

Mathematical notation:

``` text
A ∪ B
```

------------------------------------------------------------------------

# 🔗 39. Set Intersection

Intersection contains elements common to both sets.

``` python
a = {1, 2, 3}
b = {2, 3, 4}

print(a & b)
```

Output:

``` text
{2, 3}
```

Equivalent method:

``` python
a.intersection(b)
```

Mathematical notation:

``` text
A ∩ B
```

------------------------------------------------------------------------

# ➖ 40. Set Difference

Difference contains elements that exist in the left set but not the
right set.

``` python
a = {1, 2, 3}
b = {2, 3, 4}

print(a - b)
```

Output:

``` text
{1}
```

The direction matters:

``` text
A - B
```

is different from:

``` text
B - A
```

------------------------------------------------------------------------

# 🔄 41. Symmetric Difference

Symmetric difference contains values that exist in either set but not
both.

``` python
a = {1, 2, 3}
b = {2, 3, 4}

print(a ^ b)
```

Output:

``` text
{1, 4}
```

Mental model:

``` text
Common values → removed
Unique values  → kept
```

------------------------------------------------------------------------

# 🗂️ 42. Dictionaries

A **dictionary** stores data as **key-value pairs**.

``` python
student = {
    "name": "Alice",
    "age": 23,
    "department": "CSE"
}
```

Mental model:

``` text
Key            Value
────────────────────────
"name"      →  "Alice"
"age"       →  23
"department"→  "CSE"
```

### Why use a dictionary?

Suppose you have:

``` python
student = ["Alice", 23, "CSE"]
```

You need to remember:

``` text
0 → name
1 → age
2 → department
```

A dictionary makes the meaning explicit:

``` python
student = {
    "name": "Alice",
    "age": 23,
    "department": "CSE"
}
```

Now you can access data by meaningful keys.

------------------------------------------------------------------------

# 🔑 43. Dictionary Keys

Dictionary keys must be **hashable**.

Common examples:

``` python
data = {
    "name": "Alice",
    1: "One",
    (10, 20): "Point"
}
```

Common unhashable objects:

``` text
list
dict
set
```

These cannot normally be used as dictionary keys.

Keys must also be unique.

``` python
data = {
    "name": "Alice",
    "name": "Bob"
}

print(data)
```

Output:

``` text
{'name': 'Bob'}
```

The later assignment replaces the earlier value.

------------------------------------------------------------------------

# 🔎 44. Dictionary Lookup

Use the key inside square brackets.

``` python
student = {
    "name": "Alice",
    "age": 23
}

print(student["name"])
print(student["age"])
```

Output:

``` text
Alice
23
```

If the key does not exist:

``` python
# student["email"]
```

Python raises `KeyError`.

------------------------------------------------------------------------

# 🛡️ 45. `dict.get()`

`get()` is useful when a key may be missing.

``` python
student = {
    "name": "Alice"
}

print(student.get("email"))
```

Output:

``` text
None
```

You can provide a default:

``` python
print(student.get("email", "Not provided"))
```

Output:

``` text
Not provided
```

### Compare

``` text
dict[key]
  → raises KeyError if missing

dict.get(key)
  → returns None/default if missing
```

------------------------------------------------------------------------

# ✏️ 46. Adding & Updating Dictionary Values

Assigning to a new key adds it:

``` python
student = {
    "name": "Alice"
}

student["age"] = 23

print(student)
```

Assigning to an existing key updates it:

``` python
student["age"] = 24
```

So the same syntax handles both operations:

``` text
new key      → add
existing key → update
```

------------------------------------------------------------------------

# 🔄 47. `update()`

`update()` adds or replaces multiple key-value pairs.

``` python
student = {
    "name": "Alice",
    "age": 23
}

student.update({
    "age": 24,
    "city": "Chennai"
})

print(student)
```

The `age` value is replaced and `city` is added.

------------------------------------------------------------------------

# 🗑️ 48. Dictionary `pop()`

`pop(key)` removes a key-value pair and returns the value.

``` python
student = {
    "name": "Alice",
    "age": 23
}

age = student.pop("age")

print(age)
print(student)
```

Output:

``` text
23
{'name': 'Alice'}
```

------------------------------------------------------------------------

# 🔑 49. `keys()`, `values()`, `items()`

``` python
student = {
    "name": "Alice",
    "age": 23
}

print(student.keys())
print(student.values())
print(student.items())
```

These methods provide dynamic view objects.

The most common use is iteration:

``` python
for key, value in student.items():
    print(key, value)
```

------------------------------------------------------------------------

# 🔄 50. Dictionary Iteration

Iterating directly over a dictionary gives keys.

``` python
student = {
    "name": "Alice",
    "age": 23
}

for key in student:
    print(key)
```

Output:

``` text
name
age
```

For values:

``` python
for value in student.values():
    print(value)
```

For both:

``` python
for key, value in student.items():
    print(key, value)
```

------------------------------------------------------------------------

# 🧩 51. Nested Data Structures

Real-world data is often more complex than a single list or dictionary.

Python allows structures to contain other structures.

Example:

``` python
students = [
    {
        "name": "Alice",
        "marks": [85, 90, 88]
    },
    {
        "name": "Bob",
        "marks": [70, 75, 80]
    }
]
```

Here:

``` text
students
   ↓
list
   ↓
dictionary
   ↓
list of marks
```

Accessing nested data:

``` python
print(students[0]["name"])
print(students[0]["marks"][1])
```

Output:

``` text
Alice
90
```

------------------------------------------------------------------------

# 📋 52. List of Lists

A list can contain other lists.

``` python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
```

Access:

``` python
print(matrix[1][2])
```

Output:

``` text
6
```

Mental model:

``` text
matrix
  │
  ├── row 0 → [1, 2, 3]
  ├── row 1 → [4, 5, 6]
  └── row 2 → [7, 8, 9]
```

This pattern is common for grids and tabular data.

------------------------------------------------------------------------

# 🗂️ 53. Dictionary of Lists

``` python
courses = {
    "Python": ["Alice", "Bob"],
    "Java": ["Charlie", "David"]
}
```

Access:

``` python
print(courses["Python"])
print(courses["Python"][0])
```

Output:

``` text
['Alice', 'Bob']
Alice
```

This is useful when one key maps to multiple related values.

------------------------------------------------------------------------

# 🗂️ 54. Dictionary of Dictionaries

``` python
users = {
    "alice": {
        "age": 23,
        "role": "developer"
    },
    "bob": {
        "age": 25,
        "role": "designer"
    }
}
```

Access:

``` python
print(users["alice"]["role"])
```

Output:

``` text
developer
```

This resembles JSON and is extremely common in APIs and configuration
data.

------------------------------------------------------------------------

# 🔗 55. `zip()`

`zip()` combines corresponding elements from multiple iterables.

``` python
names = ["Alice", "Bob", "Charlie"]
marks = [90, 80, 85]

for name, mark in zip(names, marks):
    print(name, mark)
```

Output:

``` text
Alice 90
Bob 80
Charlie 85
```

### Mental Model

``` text
names       marks
  │           │
  ├─ Alice ─ 90
  ├─ Bob   ─ 80
  └─ Charlie─ 85
```

`zip()` stops when the shortest iterable is exhausted.

------------------------------------------------------------------------

# 🧠 56. `enumerate()` vs `zip()`

Use `enumerate()` when you need:

``` text
index + item
```

Example:

``` python
for index, item in enumerate(items):
    ...
```

Use `zip()` when you need:

``` text
item from collection A + item from collection B
```

Example:

``` python
for name, mark in zip(names, marks):
    ...
```

------------------------------------------------------------------------

# 🧊 57. Mutability

Mutability means whether an existing object can be changed after
creation.

Common mutable objects:

``` text
list
set
dict
```

Common immutable objects:

``` text
tuple
str
int
float
bool
None
```

Example:

``` python
numbers = [1, 2, 3]

numbers.append(4)
```

The existing list changed.

But:

``` python
text = "Python"

# text[0] = "J"
```

is invalid because strings are immutable.

------------------------------------------------------------------------

# 🧬 58. Aliasing

Two variables can refer to the same object.

``` python
a = [1, 2, 3]
b = a

b.append(4)

print(a)
print(b)
```

Output:

``` text
[1, 2, 3, 4]
[1, 2, 3, 4]
```

Why?

``` text
a ─────┐
       ↓
   [1, 2, 3]
       ↑
b ─────┘
```

`a` and `b` are two names pointing to the same list object.

------------------------------------------------------------------------

# 🆚 59. Equality vs Identity

`==` compares values.

`is` compares object identity.

``` python
a = [1, 2]
b = [1, 2]

print(a == b)
print(a is b)
```

Output:

``` text
True
False
```

The lists contain equal values but are different objects.

### Remember

``` text
== → "Do these objects have equal values?"
is → "Are these the exact same object?"
```

------------------------------------------------------------------------

# 📋 60. Shallow Copy

A shallow copy creates a new outer collection but keeps references to
nested objects.

``` python
original = [[1, 2], [3, 4]]

copy_value = original.copy()

copy_value[0].append(99)

print(original)
print(copy_value)
```

Output:

``` text
[[1, 2, 99], [3, 4]]
[[1, 2, 99], [3, 4]]
```

Why?

``` text
original ──→ outer list A
                 │
                 ├──→ inner list 1
                 └──→ inner list 2

copy ─────→ outer list B
                 │
                 ├──→ same inner list 1
                 └──→ same inner list 2
```

------------------------------------------------------------------------

# 🧬 61. Deep Copy

A deep copy recursively copies nested objects.

``` python
import copy

original = [[1, 2], [3, 4]]

copy_value = copy.deepcopy(original)

copy_value[0].append(99)

print(original)
print(copy_value)
```

Output:

``` text
[[1, 2], [3, 4]]
[[1, 2, 99], [3, 4]]
```

### Mental Model

``` text
Shallow copy → new outer object, shared nested objects
Deep copy    → recursively independent objects
```

Use deep copying deliberately; copying complex object graphs can be
expensive and sometimes unnecessary.

------------------------------------------------------------------------

# #️⃣ 62. Hashability

A hashable object has a hash value that remains stable during its
lifetime and can be used by hash-based structures.

Dictionary keys and set elements must be hashable.

Valid examples:

``` python
data = {
    "name": "Alice",
    42: "answer",
    (1, 2): "point"
}
```

Invalid examples:

``` python
# data[[1, 2]] = "list"
# data[{1, 2}] = "set"
```

Lists and sets are mutable and therefore unhashable.

------------------------------------------------------------------------

# ⚙️ 63. Why Hashing Matters

Hashing allows dictionaries and sets to perform efficient average-case
lookup.

Conceptually:

``` text
Key / Element
      ↓
    hash()
      ↓
Hash-based structure
      ↓
Locate candidate position
      ↓
Compare
      ↓
Result
```

You do not need to implement the hash table yourself to use dictionaries
and sets, but understanding this model helps explain their performance.

------------------------------------------------------------------------

# 📊 64. Basic Complexity Intuition

Typical average-case behaviour:

  Operation                 List      Set                Dict
  --------------------- -------- -------- -------------------
  Index access              O(1)      N/A                 N/A
  Membership                O(n)   O(1)\*              O(1)\*
  Append                  O(1)\*   O(1)\*              O(1)\*
  Search by value           O(n)   O(1)\*   Key lookup O(1)\*
  Insert at beginning       O(n)      N/A              O(1)\*

`*` indicates typical average-case behaviour rather than an
unconditional guarantee.

### Why should you care?

Imagine checking whether a value exists millions of times.

A list may require scanning many elements:

``` text
O(n)
```

A set is designed for much faster average membership testing:

``` text
O(1)
```

The correct structure can therefore have a major impact on program
performance.

------------------------------------------------------------------------

# 🧠 65. Choosing a List

Use a list when:

-   Order matters
-   Duplicates are allowed
-   You need indexing
-   You need to modify elements
-   You frequently append items

Example:

``` python
tasks = [
    "Study Python",
    "Practice coding",
    "Build project"
]
```

A task list naturally maps to a Python list.

------------------------------------------------------------------------

# 🧠 66. Choosing a Tuple

Use a tuple when:

-   The values represent a fixed group
-   Immutability is desirable
-   Positional access is useful
-   The object may be used as a dictionary key when all elements are
    hashable

Example:

``` python
coordinates = (28.61, 77.20)
```

The coordinate pair represents one fixed logical value.

------------------------------------------------------------------------

# 🧠 67. Choosing a Set

Use a set when:

-   Duplicate values should disappear
-   Membership testing is important
-   Set mathematics is useful
-   Ordering is not the primary requirement

Example:

``` python
visited_pages = {
    "home",
    "about",
    "contact"
}
```

If the same page is visited multiple times, the set still contains only
one entry.

------------------------------------------------------------------------

# 🧠 68. Choosing a Dictionary

Use a dictionary when:

-   Data has meaningful keys
-   You need key-based lookup
-   Each key maps to a value
-   You are representing structured records

Example:

``` python
user = {
    "id": 101,
    "name": "Alice",
    "role": "developer"
}
```

The dictionary is much clearer than storing these values in arbitrary
positions.

------------------------------------------------------------------------

# 🆚 69. List vs Tuple vs Set vs Dictionary

  Requirement                  Best Starting Choice
  ---------------------------- ----------------------
  Ordered mutable collection   `list`
  Fixed ordered collection     `tuple`
  Unique collection            `set`
  Key-value mapping            `dict`
  Index-based access           `list` / `tuple`
  Fast average membership      `set`
  Fast average key lookup      `dict`
  Duplicate values required    `list` / `tuple`
  Unique values required       `set`

### Important

There is no universally "best" data structure.

The right choice depends on:

``` text
Data relationship
      +
Required operations
      +
Mutation requirements
      +
Performance requirements
```

------------------------------------------------------------------------

# 🧪 70. Practical Example --- Student Data

Suppose we need to represent student records.

``` python
students = [
    {
        "name": "Alice",
        "department": "CSE",
        "marks": [85, 90, 88]
    },
    {
        "name": "Bob",
        "department": "ECE",
        "marks": [70, 75, 80]
    },
    {
        "name": "Charlie",
        "department": "CSE",
        "marks": [92, 95, 90]
    }
]
```

This structure uses:

``` text
list
  ↓
dictionary
  ↓
list
```

Calculate an average:

``` python
for student in students:
    average = sum(student["marks"]) / len(student["marks"])

    print(
        f"{student['name']}: "
        f"{average:.2f}"
    )
```

Possible output:

``` text
Alice: 87.67
Bob: 75.00
Charlie: 92.33
```

This is a realistic example of how Python data structures combine in
applications.

------------------------------------------------------------------------

# 🔎 71. Practical Example --- Remove Duplicates

Suppose:

``` python
numbers = [10, 20, 10, 30, 20, 40]
```

If order is not important:

``` python
unique_numbers = set(numbers)

print(unique_numbers)
```

If you need to preserve the original order while removing duplicates:

``` python
unique_numbers = list(dict.fromkeys(numbers))

print(unique_numbers)
```

Output:

``` text
[10, 20, 30, 40]
```

The important lesson is that the data structure should match the
requirement.

------------------------------------------------------------------------

# 📊 72. Practical Example --- Frequency Counting

Count how many times each value occurs.

``` python
words = [
    "python",
    "java",
    "python",
    "c++",
    "python",
    "java"
]

counts = {}

for word in words:
    counts[word] = counts.get(word, 0) + 1

print(counts)
```

Output:

``` text
{'python': 3, 'java': 2, 'c++': 1}
```

This is one of the most important dictionary patterns in programming.

------------------------------------------------------------------------

# 🗂️ 73. Practical Example --- Grouping

Group students by department.

``` python
students = [
    {"name": "Alice", "department": "CSE"},
    {"name": "Bob", "department": "ECE"},
    {"name": "Charlie", "department": "CSE"}
]

groups = {}

for student in students:
    department = student["department"]

    groups.setdefault(department, []).append(
        student["name"]
    )

print(groups)
```

Conceptually:

``` text
CSE → Alice, Charlie
ECE → Bob
```

Later, the `collections` module will provide specialized tools for
patterns like this.

------------------------------------------------------------------------

# 🚨 74. Common Mistakes

## Mistake 1 --- Using `{}` for an empty set

Wrong:

``` python
items = {}
```

This creates a dictionary.

Correct:

``` python
items = set()
```

------------------------------------------------------------------------

## Mistake 2 --- Confusing `append()` and `extend()`

``` python
items = [1, 2]

items.append([3, 4])
```

Result:

``` text
[1, 2, [3, 4]]
```

Whereas:

``` python
items = [1, 2]

items.extend([3, 4])
```

Result:

``` text
[1, 2, 3, 4]
```

------------------------------------------------------------------------

## Mistake 3 --- Expecting `sort()` to return a list

Wrong:

``` python
result = numbers.sort()
```

`result` becomes `None`.

Correct:

``` python
numbers.sort()
```

or:

``` python
result = sorted(numbers)
```

------------------------------------------------------------------------

## Mistake 4 --- Using `is` for value comparison

Usually:

``` python
a == b
```

means compare values.

``` python
a is b
```

means compare identity.

Do not replace `==` with `is`.

------------------------------------------------------------------------

## Mistake 5 --- Forgetting dictionary missing-key behaviour

``` python
data["missing"]
```

raises `KeyError`.

Use:

``` python
data.get("missing")
```

when absence is expected.

------------------------------------------------------------------------

## Mistake 6 --- Accidentally creating an alias

``` python
a = [1, 2, 3]
b = a
```

Both variables reference the same list.

If you need a separate outer list:

``` python
b = a.copy()
```

------------------------------------------------------------------------

## Mistake 7 --- Using a list as a dictionary key

This fails because lists are unhashable:

``` python
# data[[1, 2]] = "value"
```

A tuple may work:

``` python
data[(1, 2)] = "value"
```

provided all tuple elements are hashable.

------------------------------------------------------------------------

## Mistake 8 --- Assuming sets are indexable

Wrong:

``` python
# numbers[0]
```

A set has no positional indexing.

------------------------------------------------------------------------

## Mistake 9 --- Modifying a collection while iterating over it

This can produce unexpected behaviour.

Prefer building a new collection or iterating over an appropriate
copy/snapshot when modification is necessary.

------------------------------------------------------------------------

# 🎤 75. Interview Perspective

### Q1. What is the difference between a list and a tuple?

``` text
list  → mutable
tuple → immutable
```

Both are ordered sequences.

------------------------------------------------------------------------

### Q2. What is the difference between `append()` and `extend()`?

``` text
append(x) → adds x as one element
extend(x) → adds elements from iterable x
```

------------------------------------------------------------------------

### Q3. What is the difference between `remove()` and `pop()`?

``` text
remove(value) → removes by value
pop(index)    → removes and returns by index
```

------------------------------------------------------------------------

### Q4. What is the difference between `sort()` and `sorted()`?

``` text
sort()    → modifies list in place
sorted()  → returns a new sorted list
```

------------------------------------------------------------------------

### Q5. Why can a tuple be a dictionary key but a list cannot?

A tuple can be hashable when all of its elements are hashable. A list is
mutable and unhashable.

------------------------------------------------------------------------

### Q6. Why are sets useful?

They provide uniqueness and efficient average-case membership testing.

------------------------------------------------------------------------

### Q7. Difference between `remove()` and `discard()` for sets?

``` text
remove()  → raises KeyError if missing
discard() → does nothing if missing
```

------------------------------------------------------------------------

### Q8. What happens when a dictionary key does not exist?

``` python
data["missing"]
```

raises `KeyError`.

``` python
data.get("missing")
```

returns `None` by default.

------------------------------------------------------------------------

### Q9. What is aliasing?

Aliasing occurs when multiple variables reference the same object.

------------------------------------------------------------------------

### Q10. Difference between `==` and `is`?

``` text
== → equality of values
is → identity of objects
```

------------------------------------------------------------------------

### Q11. What is shallow copy?

A new outer object is created while nested objects may remain shared.

------------------------------------------------------------------------

### Q12. What is deep copy?

Nested objects are recursively copied to create an independent object
graph.

------------------------------------------------------------------------

### Q13. What does `enumerate()` provide?

An index and the corresponding item during iteration.

------------------------------------------------------------------------

### Q14. What does `zip()` provide?

It combines corresponding elements from multiple iterables.

------------------------------------------------------------------------

### Q15. What is hashability?

Hashability means an object can provide a stable hash value suitable for
hash-based structures such as dictionaries and sets.

------------------------------------------------------------------------

# 📊 76. Quick Reference Table

  Concept            Quick Recall
  ------------------ ---------------------------
  `list`             Ordered + mutable
  `tuple`            Ordered + immutable
  `set`              Unique elements
  `dict`             Key → value mapping
  `append()`         Add one object
  `extend()`         Add iterable's elements
  `insert()`         Add at position
  `remove()`         Remove by value
  `pop()`            Remove + return
  `clear()`          Remove all elements
  `sort()`           Sort list in place
  `sorted()`         Return sorted result
  `reverse()`        Reverse list in place
  `add()`            Add set element
  `discard()`        Safe set removal
  `union()`          Combine unique values
  `intersection()`   Common values
  `difference()`     Left-only values
  `get()`            Safe dictionary lookup
  `update()`         Add/update multiple pairs
  `keys()`           Dictionary keys
  `values()`         Dictionary values
  `items()`          Key-value pairs
  `enumerate()`      Index + item
  `zip()`            Pair corresponding items
  `==`               Value equality
  `is`               Object identity
  `.copy()`          Shallow copy
  `deepcopy()`       Recursive copy

------------------------------------------------------------------------

# 🧠 77. One-Minute Revision

``` text
LIST
│
├── Ordered
├── Mutable
├── Duplicates allowed
├── Indexing
├── Slicing
├── append()
├── extend()
├── insert()
├── remove()
├── pop()
├── sort()
└── reverse()

TUPLE
│
├── Ordered
├── Immutable
├── Duplicates allowed
├── Indexing
├── Slicing
└── Unpacking

SET
│
├── Unique
├── Mutable
├── Hash-based membership
├── No positional indexing
├── add()
├── remove()
├── discard()
├── union()
├── intersection()
├── difference()
└── symmetric difference

DICT
│
├── Key → Value
├── Mutable
├── Unique keys
├── Hash-based lookup
├── get()
├── update()
├── pop()
├── keys()
├── values()
└── items()

OBJECT BEHAVIOUR
│
├── Mutable vs Immutable
├── Aliasing
├── Equality vs Identity
├── Shallow Copy
├── Deep Copy
└── Hashability

ITERATION
│
├── for
├── enumerate()
└── zip()
```

------------------------------------------------------------------------

# 🧪 78. Practice Checklist

``` text
FOUNDATIONS
☐ Understand what a data structure is
☐ Understand why data structures matter
☐ Understand ordered vs unordered collections
☐ Understand mutable vs immutable objects
☐ Understand hashable vs unhashable objects

LISTS
☐ Create lists
☐ Index lists
☐ Use negative indexes
☐ Slice lists
☐ Modify list elements
☐ Use append()
☐ Use extend()
☐ Use insert()
☐ Use remove()
☐ Use pop()
☐ Use clear()
☐ Use index()
☐ Use count()
☐ Use sort()
☐ Use sorted()
☐ Use reverse()
☐ Iterate through lists
☐ Use enumerate()

TUPLES
☐ Create tuples
☐ Create single-element tuples
☐ Index tuples
☐ Slice tuples
☐ Understand immutability
☐ Understand packing
☐ Understand unpacking
☐ Use extended unpacking
☐ Swap variables

SETS
☐ Create sets
☐ Create an empty set
☐ Understand uniqueness
☐ Test membership
☐ Use add()
☐ Use remove()
☐ Use discard()
☐ Use union
☐ Use intersection
☐ Use difference
☐ Use symmetric difference

DICTIONARIES
☐ Create dictionaries
☐ Understand key-value mapping
☐ Access values by key
☐ Handle missing keys
☐ Use get()
☐ Add values
☐ Update values
☐ Use update()
☐ Use pop()
☐ Iterate over keys
☐ Iterate over values
☐ Iterate over items()
☐ Build nested dictionaries

NESTED STRUCTURES
☐ List of lists
☐ List of dictionaries
☐ Dictionary of lists
☐ Dictionary of dictionaries
☐ Access deeply nested data

OBJECT BEHAVIOUR
☐ Aliasing
☐ Identity
☐ Equality
☐ Shallow copy
☐ Deep copy
☐ Hashability

ITERATION
☐ enumerate()
☐ zip()

SELECTION
☐ Choose list when order and mutation matter
☐ Choose tuple for fixed sequences
☐ Choose set for uniqueness
☐ Choose dict for key-value relationships
```

------------------------------------------------------------------------

# 🎯 79. Data Structures Completion Test

Before moving to the next chapter, you should be able to explain these
without simply memorizing syntax:

``` text
1. What is a data structure?

2. Why does the choice of data structure matter?

3. Why is a list mutable?

4. Why is a tuple immutable?

5. What is the difference between append() and extend()?

6. What is the difference between remove() and pop()?

7. What is the difference between sort() and sorted()?

8. Why is {} an empty dictionary instead of an empty set?

9. Why can sets not be indexed?

10. What is the difference between remove() and discard() for sets?

11. What are union, intersection, and difference?

12. What is a dictionary and why is key-based access useful?

13. What happens when a dictionary key is missing?

14. What is the difference between dict[key] and dict.get(key)?

15. Why must dictionary keys be hashable?

16. What is aliasing?

17. What is the difference between == and is?

18. What is a shallow copy?

19. What is a deep copy?

20. What does enumerate() do?

21. What does zip() do?

22. When should you use a list?

23. When should you use a tuple?

24. When should you use a set?

25. When should you use a dictionary?

26. How can multiple data structures be combined to represent real-world data?
```

------------------------------------------------------------------------

# 🚀 Next Chapter

``` text
01. Python Foundation
          │
          ▼
02. Core Python
          │
          ▼
03. Python Data Structures
          │
          ▼
04. Functions
          │
          ├── What Is a Function?
          ├── Defining Functions
          ├── Parameters & Arguments
          ├── Return Values
          ├── Positional Arguments
          ├── Keyword Arguments
          ├── Default Arguments
          ├── *args
          ├── **kwargs
          ├── Positional-Only Parameters
          ├── Keyword-Only Parameters
          ├── Scope
          ├── LEGB Rule
          ├── Global & Nonlocal
          ├── Lambda Functions
          ├── Higher-Order Functions
          ├── Closures
          └── Recursion
```

------------------------------------------------------------------------

# 🐍 Final Data Structure Rule

> **Do not choose a data structure because you know its syntax. Choose
> it because its behaviour matches the problem.**

``` text
Understand the data
        ↓
Understand required operations
        ↓
Ask whether order matters
        ↓
Ask whether mutation is required
        ↓
Ask whether duplicates are allowed
        ↓
Ask whether key-based lookup is required
        ↓
Consider performance
        ↓
Choose the structure
        ↓
Implement
        ↓
Test
        ↓
Profile and optimize when necessary
```

A professional Python engineer does not merely know how to write:

``` python
[]
()
{}
set()
```

They understand **what each structure represents, what operations it
supports, how it behaves, and why one structure is a better choice than
another for a particular problem.**
