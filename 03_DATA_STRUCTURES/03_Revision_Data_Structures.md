# 🐍 Python Engineering --- 03. Data Structures --- Revision

> **Purpose:** This is the fast-revision companion to
> `03_Data_Structures.md`.
>
> Use this file when you already understand the detailed chapter and
> want to refresh the complete Data Structures chapter quickly without
> rereading every explanation.

------------------------------------------------------------------------

# 📚 Data Structures at a Glance

``` text
03. Python Data Structures
│
├── list
│   ├── Ordered
│   ├── Mutable
│   ├── Duplicates allowed
│   ├── Indexing
│   ├── Slicing
│   └── append / extend / insert / remove / pop
│
├── tuple
│   ├── Ordered
│   ├── Immutable
│   ├── Duplicates allowed
│   ├── Indexing
│   ├── Slicing
│   └── Packing / Unpacking
│
├── set
│   ├── Unique elements
│   ├── Mutable
│   ├── No positional indexing
│   ├── Membership testing
│   └── Set operations
│
└── dict
    ├── Key → Value
    ├── Mutable
    ├── Unique keys
    ├── Key-based lookup
    └── keys / values / items
```

------------------------------------------------------------------------

# 🧠 01. What Is a Data Structure?

A **data structure** is a way of organizing data so a program can store,
access, modify, search, and process that data effectively.

``` text
Data
 ↓
Choose structure
 ↓
Organize data
 ↓
Perform operations
 ↓
Solve problem
```

The important point is that different structures are optimized for
different kinds of work.

------------------------------------------------------------------------

# 🧩 02. The Four Core Structures

  Structure   Main Idea              Mutable   Duplicates   Positional Access
  ----------- -------------------- --------- ------------ -------------------
  `list`      Ordered collection         Yes          Yes                 Yes
  `tuple`     Fixed sequence              No          Yes                 Yes
  `set`       Unique collection          Yes           No                  No
  `dict`      Key-value mapping          Yes     Keys: No              By key

### Quick Decision

``` text
Need ordered + changeable?
→ list

Need ordered + fixed?
→ tuple

Need unique values?
→ set

Need key → value?
→ dict
```

------------------------------------------------------------------------

# 📋 03. Lists

A list is an **ordered and mutable collection**.

``` python
numbers = [10, 20, 30]

numbers[1] = 99

print(numbers)
```

Output:

``` text
[10, 99, 30]
```

### Remember

``` text
list
 ↓
ordered
 ↓
mutable
 ↓
duplicates allowed
 ↓
indexing supported
```

------------------------------------------------------------------------

# 🔢 04. List Indexing

Python uses zero-based indexing.

``` python
items = ["A", "B", "C"]

print(items[0])   # A
print(items[-1])  # C
```

``` text
A    B    C
0    1    2
-3  -2   -1
```

------------------------------------------------------------------------

# ✂️ 05. List Slicing

Syntax:

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

### Critical rule

``` text
start → included
stop  → excluded
```

------------------------------------------------------------------------

# ➕ 06. `append()` vs `extend()`

``` python
items = [1, 2]

items.append([3, 4])
```

Result:

``` text
[1, 2, [3, 4]]
```

But:

``` python
items = [1, 2]

items.extend([3, 4])
```

Result:

``` text
[1, 2, 3, 4]
```

### Remember

``` text
append(x)
→ add x as ONE element

extend(x)
→ add elements from iterable x
```

------------------------------------------------------------------------

# 📍 07. `insert()`

Adds an element at a specific position.

``` python
numbers = [10, 30]

numbers.insert(1, 20)

print(numbers)
```

Output:

``` text
[10, 20, 30]
```

------------------------------------------------------------------------

# ❌ 08. `remove()` vs `pop()`

``` text
remove(value)
→ removes by VALUE

pop(index)
→ removes by INDEX
→ returns removed value
```

Example:

``` python
numbers = [10, 20, 30]

numbers.remove(20)

value = numbers.pop(1)
```

### Tip

Use `remove()` when you know the value.

Use `pop()` when you need the removed item or know its position.

------------------------------------------------------------------------

# 🧹 09. `clear()`

Removes all elements from the list.

``` python
numbers = [1, 2, 3]

numbers.clear()

print(numbers)
```

Output:

``` text
[]
```

------------------------------------------------------------------------

# 🔎 10. `index()` and `count()`

``` python
numbers = [10, 20, 20, 30]

print(numbers.index(20))
print(numbers.count(20))
```

Output:

``` text
1
2
```

``` text
index() → first matching position
count() → number of occurrences
```

------------------------------------------------------------------------

# 🔃 11. `sort()` vs `sorted()`

`sort()` changes the existing list.

``` python
numbers = [30, 10, 20]

numbers.sort()

print(numbers)
```

`sorted()` creates a new sorted result.

``` python
numbers = [30, 10, 20]

result = sorted(numbers)

print(result)
print(numbers)
```

### Remember

``` text
sort()
→ in-place
→ returns None

sorted()
→ new result
→ original remains unchanged
```

------------------------------------------------------------------------

# 🔄 12. `reverse()`

Reverses a list in place.

``` python
numbers = [1, 2, 3]

numbers.reverse()

print(numbers)
```

Output:

``` text
[3, 2, 1]
```

For a non-mutating reversed iterator:

``` python
reversed(numbers)
```

------------------------------------------------------------------------

# 📦 13. Tuples

A tuple is an **ordered and immutable sequence**.

``` python
point = (10, 20)
```

``` text
tuple
 ↓
ordered
 ↓
immutable
 ↓
duplicates allowed
 ↓
indexing supported
```

Use tuples for values that logically represent a fixed group.

------------------------------------------------------------------------

# 1️⃣ 14. Single-Element Tuple

``` python
value = (10)

print(type(value))
```

This is an `int`.

Correct:

``` python
value = (10,)

print(type(value))
```

This is a `tuple`.

### Rule

``` text
(10)  → int
(10,) → tuple
```

The comma creates the one-element tuple.

------------------------------------------------------------------------

# 🧊 15. Tuple Immutability

Tuple elements cannot be replaced.

``` python
point = (10, 20)

# point[0] = 50
```

This raises `TypeError`.

However, a tuple can contain a mutable object:

``` python
data = ([1, 2], 3)

data[0].append(4)

print(data)
```

The tuple itself remains structurally fixed, while the nested list can
change.

------------------------------------------------------------------------

# 📦 16. Packing & Unpacking

Packing:

``` python
point = 10, 20
```

Unpacking:

``` python
x, y = point

print(x)
print(y)
```

Output:

``` text
10
20
```

Python assigns the values according to their positions.

------------------------------------------------------------------------

# ⭐ 17. Extended Unpacking

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

The starred variable collects the remaining values into a list.

------------------------------------------------------------------------

# 🔄 18. Variable Swapping

Python supports direct swapping:

``` python
a = 10
b = 20

a, b = b, a
```

No temporary variable is required.

------------------------------------------------------------------------

# 🟢 19. Sets

A set is a **mutable collection of unique hashable elements**.

``` python
numbers = {1, 2, 2, 3}

print(numbers)
```

Conceptually:

``` text
{1, 2, 2, 3}
       ↓
{1, 2, 3}
```

### Remember

``` text
set
 ↓
unique
 ↓
no positional indexing
 ↓
fast average membership
```

------------------------------------------------------------------------

# ✍️ 20. Creating an Empty Set

This is wrong for an empty set:

``` python
items = {}
```

It creates an empty dictionary.

Correct:

``` python
items = set()
```

### Important Interview Trap

``` text
{}      → empty dict
set()   → empty set
```

------------------------------------------------------------------------

# 🔍 21. Set Membership

``` python
languages = {"Python", "Java", "C++"}

print("Python" in languages)
```

Output:

``` text
True
```

Sets are particularly useful when membership testing is frequent.

------------------------------------------------------------------------

# ➕ 22. `add()`

Adds one element.

``` python
numbers = {1, 2}

numbers.add(3)

print(numbers)
```

Adding an existing element does not create a duplicate.

------------------------------------------------------------------------

# ❌ 23. `remove()` vs `discard()`

``` text
remove(x)
→ raises KeyError if x is absent

discard(x)
→ silently does nothing if x is absent
```

Example:

``` python
numbers = {1, 2, 3}

numbers.discard(100)
```

No exception occurs.

------------------------------------------------------------------------

# 🔗 24. Set Operations

Union:

``` python
a | b
```

All unique elements from both sets.

Intersection:

``` python
a & b
```

Only common elements.

Difference:

``` python
a - b
```

Elements in `a` but not `b`.

Symmetric difference:

``` python
a ^ b
```

Elements in either set, but not both.

### Mental Model

``` text
A ∪ B → everything
A ∩ B → common
A - B → A only
A ^ B → unique to either side
```

------------------------------------------------------------------------

# 🗂️ 25. Dictionaries

A dictionary stores data as:

``` text
key → value
```

Example:

``` python
student = {
    "name": "Alice",
    "age": 23,
    "department": "CSE"
}
```

Think of it as labelled data rather than position-based data.

------------------------------------------------------------------------

# 🔑 26. Dictionary Keys

Keys must be hashable.

Valid examples:

``` python
data = {
    "name": "Alice",
    1: "One",
    (10, 20): "Point"
}
```

Lists and sets cannot normally be keys because they are unhashable.

Keys must be unique:

``` python
data = {
    "name": "Alice",
    "name": "Bob"
}
```

The later value replaces the earlier one.

------------------------------------------------------------------------

# 🔎 27. Dictionary Lookup

``` python
student = {
    "name": "Alice",
    "age": 23
}

print(student["name"])
```

Output:

``` text
Alice
```

Missing key:

``` python
# student["email"]
```

raises `KeyError`.

------------------------------------------------------------------------

# 🛡️ 28. `dict[key]` vs `dict.get()`

``` python
student = {
    "name": "Alice"
}

print(student["email"])
```

This raises `KeyError`.

Instead:

``` python
print(student.get("email"))
```

returns:

``` text
None
```

Or provide a default:

``` python
print(student.get("email", "Not provided"))
```

### Remember

``` text
data[key]
→ strict lookup

data.get(key)
→ safe lookup with optional default
```

------------------------------------------------------------------------

# ✏️ 29. Adding & Updating Dictionary Values

Same syntax performs two different operations depending on whether the
key exists.

``` python
student["age"] = 23
```

If `"age"` is new:

``` text
ADD
```

If `"age"` already exists:

``` text
UPDATE
```

------------------------------------------------------------------------

# 🔄 30. `update()`

Adds or updates multiple key-value pairs.

``` python
student.update({
    "age": 24,
    "city": "Chennai"
})
```

Useful when several dictionary values need to be changed at once.

------------------------------------------------------------------------

# 🗑️ 31. Dictionary `pop()`

Removes a key and returns its value.

``` python
student = {
    "name": "Alice",
    "age": 23
}

age = student.pop("age")

print(age)
```

Output:

``` text
23
```

------------------------------------------------------------------------

# 🔑 32. `keys()`, `values()`, `items()`

``` python
student = {
    "name": "Alice",
    "age": 23
}

student.keys()
student.values()
student.items()
```

Use `items()` when you need both key and value:

``` python
for key, value in student.items():
    print(key, value)
```

------------------------------------------------------------------------

# 🔄 33. Dictionary Iteration

Direct iteration:

``` python
for key in student:
    print(key)
```

Values:

``` python
for value in student.values():
    print(value)
```

Key + value:

``` python
for key, value in student.items():
    print(key, value)
```

### Remember

``` text
for x in dict
→ keys

dict.values()
→ values

dict.items()
→ key + value
```

------------------------------------------------------------------------

# 🧩 34. Nested Data Structures

Collections can contain other collections.

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

Structure:

``` text
list
 ↓
dict
 ↓
list
```

Access:

``` python
students[0]["marks"][1]
```

Output:

``` text
90
```

------------------------------------------------------------------------

# 🔢 35. List of Lists

``` python
matrix = [
    [1, 2, 3],
    [4, 5, 6]
]

print(matrix[1][2])
```

Output:

``` text
6
```

Common use cases:

``` text
matrices
grids
tables
game boards
```

------------------------------------------------------------------------

# 🗂️ 36. Dictionary of Lists

``` python
courses = {
    "Python": ["Alice", "Bob"],
    "Java": ["Charlie"]
}
```

One key maps to multiple values.

------------------------------------------------------------------------

# 🗂️ 37. Dictionary of Dictionaries

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

This is common for structured application data and JSON-like objects.

------------------------------------------------------------------------

# 🔢 38. `enumerate()`

Use `enumerate()` when you need both index and value.

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

### Remember

``` text
enumerate(iterable)
→ index + item
```

------------------------------------------------------------------------

# 🔗 39. `zip()`

Use `zip()` to process corresponding values from multiple iterables.

``` python
names = ["Alice", "Bob"]
marks = [90, 80]

for name, mark in zip(names, marks):
    print(name, mark)
```

Output:

``` text
Alice 90
Bob 80
```

### Remember

``` text
enumerate()
→ index + item

zip()
→ item + corresponding item
```

------------------------------------------------------------------------

# 🧬 40. Mutability

Mutable objects can be changed after creation.

``` text
list
set
dict
```

Immutable objects cannot be changed in place.

``` text
tuple
str
int
float
bool
None
```

### Core idea

``` text
Mutable
→ existing object can change

Immutable
→ modification creates/requires another object
```

------------------------------------------------------------------------

# 🧬 41. Aliasing

Two variables can reference the same object.

``` python
a = [1, 2, 3]
b = a

b.append(4)

print(a)
```

Output:

``` text
[1, 2, 3, 4]
```

Why?

``` text
a ─────┐
       ↓
     [list]
       ↑
b ─────┘
```

`a` and `b` are different names for the same list object.

------------------------------------------------------------------------

# 🆚 42. `==` vs `is`

`==` compares values.

`is` compares identity.

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

### Remember

``` text
== → same value?
is → same object?
```

------------------------------------------------------------------------

# 📋 43. Shallow Copy

A shallow copy creates a new outer object but nested objects may still
be shared.

``` python
original = [[1, 2], [3, 4]]

copy_value = original.copy()

copy_value[0].append(99)
```

The nested list is shared, so both structures can observe the change.

``` text
Shallow copy
     ↓
new outer object
     +
shared nested objects
```

------------------------------------------------------------------------

# 🧬 44. Deep Copy

A deep copy recursively copies nested objects.

``` python
import copy

original = [[1, 2], [3, 4]]

copy_value = copy.deepcopy(original)

copy_value[0].append(99)
```

Now the nested structures are independent.

``` text
Deep copy
    ↓
new outer object
    +
new nested objects
```

------------------------------------------------------------------------

# #️⃣ 45. Hashability

Hashable objects can be used as:

``` text
dictionary keys
set elements
```

Examples:

``` python
{
    "name": "Alice",
    (1, 2): "point"
}
```

A list cannot be used as a dictionary key:

``` python
# data[[1, 2]] = "value"
```

because lists are unhashable.

------------------------------------------------------------------------

# ⚙️ 46. Performance Intuition

Typical average-case behaviour:

  Operation          List      Set     Dict
  -------------- -------- -------- --------
  Index access       O(1)      N/A      N/A
  Membership         O(n)   O(1)\*   O(1)\*
  Key lookup          N/A      N/A   O(1)\*
  Append           O(1)\*   O(1)\*   O(1)\*

`*` means typical average-case behaviour.

### Key idea

``` text
Need repeated membership checks?
→ Consider set

Need repeated key lookup?
→ Consider dict

Need positional access?
→ Consider list / tuple
```

------------------------------------------------------------------------

# 🎯 47. Choosing the Right Structure

``` text
Need order?
│
├── Yes + mutable
│      → list
│
└── Yes + immutable
       → tuple


Need uniqueness?
│
└── Yes
       → set


Need key → value mapping?
│
└── Yes
       → dict
```

### Practical rule

Do not choose a collection only because its syntax is familiar.

Choose based on:

``` text
Required operations
+
Ordering requirements
+
Mutation requirements
+
Duplicate requirements
+
Lookup requirements
+
Performance requirements
```

------------------------------------------------------------------------

# 🧠 48. Most Important Comparisons

### List vs Tuple

``` text
list
→ mutable

tuple
→ immutable
```

Both support ordering, indexing, and slicing.

------------------------------------------------------------------------

### List vs Set

``` text
list
→ ordered
→ duplicates allowed
→ indexing

set
→ unique
→ no positional indexing
→ membership-focused
```

------------------------------------------------------------------------

### Set vs Dictionary

``` text
set
→ stores unique values

dict
→ stores key → value relationships
```

Both rely on hash-based organization.

------------------------------------------------------------------------

### `append()` vs `extend()`

``` text
append(x)
→ one element

extend(x)
→ elements from iterable
```

------------------------------------------------------------------------

### `remove()` vs `pop()`

``` text
remove(value)
→ remove by value

pop(index)
→ remove by index + return value
```

------------------------------------------------------------------------

### `sort()` vs `sorted()`

``` text
sort()
→ modifies list

sorted()
→ creates sorted result
```

------------------------------------------------------------------------

### `==` vs `is`

``` text
== → value equality
is → object identity
```

------------------------------------------------------------------------

# 🚨 49. Common Mistakes

``` python
# Empty set
items = set()

# NOT {}
```

``` python
# One-element tuple
value = (10,)

# NOT (10)
```

``` python
# Dictionary safe lookup
value = data.get("missing")
```

``` python
# Same object
b = a

# Independent shallow outer list
b = a.copy()
```

``` python
# Value comparison
a == b

# Identity comparison
a is b
```

``` python
# Set removal
numbers.discard(value)
```

when absence is acceptable.

------------------------------------------------------------------------

# 🎤 50. Interview Quick Fire

``` text
Q: What is a list?
A: An ordered, mutable collection.

Q: What is a tuple?
A: An ordered, immutable sequence.

Q: What is a set?
A: A mutable collection of unique hashable elements.

Q: What is a dictionary?
A: A mutable mapping of unique keys to values.

Q: Can a set contain duplicate values?
A: No.

Q: Can a list contain duplicates?
A: Yes.

Q: Can a tuple contain duplicates?
A: Yes.

Q: Can a dictionary have duplicate keys?
A: No.

Q: What is the difference between append() and extend()?
A: append adds one object; extend adds elements from an iterable.

Q: What is the difference between remove() and pop()?
A: remove uses a value; pop uses an index and returns the removed value.

Q: What is the difference between sort() and sorted()?
A: sort modifies a list in place; sorted returns a new sorted result.

Q: Why is {} not an empty set?
A: {} creates an empty dictionary.

Q: How do you create an empty set?
A: set().

Q: Why is (10,) different from (10)?
A: The comma creates the tuple.

Q: What does dict.get() help with?
A: It allows safe lookup when a key may be missing.

Q: What does enumerate() provide?
A: Index and item.

Q: What does zip() provide?
A: Corresponding elements from multiple iterables.

Q: What is aliasing?
A: Multiple variables referencing the same object.

Q: What is shallow copy?
A: New outer object with potentially shared nested objects.

Q: What is deep copy?
A: Recursive copying of nested objects.

Q: What does hashable mean?
A: An object can provide a stable hash suitable for hash-based structures.
```

------------------------------------------------------------------------

# ⚡ 51. One-Minute Revision Map

``` text
                    DATA STRUCTURES
                           │
          ┌────────────────┼────────────────┐
          ↓                ↓                ↓
        LIST             TUPLE            SET
          │                │                │
      ordered          ordered          unique
      mutable          immutable        mutable
      duplicates        duplicates       no duplicates
      indexing          indexing         no indexing
          │                │                │
          └────────────────┼────────────────┘
                           │
                           ↓
                         DICT
                           │
                      key → value
                           │
                    unique keys
                           │
                      fast lookup


OBJECT BEHAVIOUR
      │
      ├── Mutable
      ├── Immutable
      ├── Aliasing
      ├── Equality
      ├── Identity
      ├── Shallow Copy
      ├── Deep Copy
      └── Hashability


ITERATION HELPERS
      │
      ├── enumerate()
      │      ↓
      │   index + item
      │
      └── zip()
             ↓
       corresponding items
```

------------------------------------------------------------------------

# ✅ 52. Revision Checklist

``` text
FOUNDATIONS
☐ Understand what a data structure is
☐ Understand why structure choice matters
☐ Understand mutable vs immutable
☐ Understand hashability

LIST
☐ Creation
☐ Indexing
☐ Negative indexing
☐ Slicing
☐ Mutation
☐ append()
☐ extend()
☐ insert()
☐ remove()
☐ pop()
☐ clear()
☐ index()
☐ count()
☐ sort()
☐ sorted()
☐ reverse()

TUPLE
☐ Creation
☐ Single-element tuple
☐ Indexing
☐ Slicing
☐ Immutability
☐ Packing
☐ Unpacking
☐ Extended unpacking
☐ Swapping

SET
☐ Creation
☐ Empty set
☐ Uniqueness
☐ Membership
☐ add()
☐ remove()
☐ discard()
☐ Union
☐ Intersection
☐ Difference
☐ Symmetric difference

DICT
☐ Creation
☐ Key-value mapping
☐ Key lookup
☐ get()
☐ Add
☐ Update
☐ update()
☐ pop()
☐ keys()
☐ values()
☐ items()
☐ Iteration

NESTED STRUCTURES
☐ List of lists
☐ List of dictionaries
☐ Dictionary of lists
☐ Dictionary of dictionaries

OBJECT BEHAVIOUR
☐ Aliasing
☐ == vs is
☐ Shallow copy
☐ Deep copy
☐ Hashability

ITERATION
☐ enumerate()
☐ zip()

SELECTION
☐ Know when to use list
☐ Know when to use tuple
☐ Know when to use set
☐ Know when to use dict
```

------------------------------------------------------------------------

# 🎯 Final Recall

``` text
list
→ ordered + mutable + duplicates

tuple
→ ordered + immutable + duplicates

set
→ unique + hash-based membership

dict
→ key → value mapping

append()
→ add one object

extend()
→ add iterable's elements

remove()
→ remove by value

pop()
→ remove + return by index

sort()
→ modify list

sorted()
→ return sorted result

==
→ compare values

is
→ compare identity

enumerate()
→ index + item

zip()
→ corresponding items

shallow copy
→ new outer object + shared nested references

deep copy
→ recursively independent nested objects
```

------------------------------------------------------------------------

# 🚀 Next Chapter

``` text
01. Python Foundation
        ↓
02. Core Python
        ↓
03. Python Data Structures
        ↓
03. Revision — Data Structures
        ↓
04. Functions
```

> **Detailed learning:** `03_Data_Structures.md`
>
> **Fast revision:** `03_Revision_Data_Structures.md`
>
> **Next:** `04_Functions.md`
