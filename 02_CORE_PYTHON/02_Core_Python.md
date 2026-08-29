# 🐍 Python Engineering --- 02. Core Python

> **Goal:** Understand the core Python language features used in
> everyday programming: strings, numbers, Boolean logic, `None`,
> conditional statements, loops, loop control, `range()`, and
> `match / case`.

------------------------------------------------------------------------

# 📚 Chapter Overview

``` text
02. Core Python
│
├── Strings & String Operations
│   ├── Creation & Quotes
│   ├── Escape Sequences
│   ├── Raw Strings
│   ├── Indexing & Negative Indexing
│   ├── Slicing
│   ├── Immutability
│   ├── Concatenation & Repetition
│   ├── String Methods
│   ├── Searching & Checking
│   ├── split() & join()
│   ├── Formatting
│   └── Unicode Basics
│
├── Numbers
│   ├── int
│   ├── float
│   ├── complex
│   ├── Arithmetic
│   ├── Division
│   ├── Floor Division
│   ├── Modulo
│   ├── Exponentiation
│   └── Floating-Point Behaviour
│
├── Boolean & Truthiness
│   ├── True / False
│   ├── Comparisons
│   ├── Truthy / Falsy
│   ├── and / or / not
│   └── Short-Circuit Evaluation
│
├── None
│   ├── None
│   ├── is None
│   └── None vs False / 0 / ""
│
├── Conditional Statements
│   ├── if
│   ├── elif
│   ├── else
│   ├── Nested Conditions
│   ├── Guard Conditions
│   └── Conditional Expressions
│
├── Loops
│   ├── for
│   ├── while
│   ├── Nested Loops
│   └── Loop else
│
├── Loop Control
│   ├── break
│   ├── continue
│   └── pass
│
├── range()
│   ├── range(stop)
│   ├── range(start, stop)
│   ├── range(start, stop, step)
│   └── Reverse Ranges
│
└── match / case
    ├── Literal Patterns
    ├── Multiple Patterns
    ├── Wildcard
    ├── Guards
    └── Structural Patterns
```

------------------------------------------------------------------------

# 🔤 01. Strings

A **string** is an immutable sequence of Unicode characters used to
represent text.

``` python
name = "Biggan"

print(name)
print(type(name))
```

Output:

``` text
Biggan
<class 'str'>
```

Because a string is a sequence, Python allows you to access individual
characters, extract portions, search for text, iterate through
characters, and create new strings from existing ones.

``` text
"Python"

  P   y   t   h   o   n
  0   1   2   3   4   5
```

------------------------------------------------------------------------

# ✍️ 02. Creating Strings

Python supports single, double, and triple quotes.

``` python
single = 'Python'
double = "Python"
triple_single = """Python"""
triple_double = """Python"""
```

Triple-quoted strings can span multiple lines:

``` python
message = """Python
is
powerful"""

print(message)
```

Output:

``` text
Python
is
powerful
```

### Tip

Use the quote style that makes the text easiest to read. Triple quotes
are especially useful for multiline text and docstrings.

------------------------------------------------------------------------

# 🔐 03. Escape Sequences

Escape sequences allow special characters to be represented inside
strings.

  Escape   Meaning
  -------- --------------
  `\n`     New line
  `\t`     Tab
  `\\`     Backslash
  `\'`     Single quote
  `\"`     Double quote

Example:

``` python
print("Hello\nPython")
print("Name:\tBiggan")
```

Output:

``` text
Hello
Python
Name:   Biggan
```

------------------------------------------------------------------------

# 🧱 04. Raw Strings

A raw string treats backslashes mostly as literal characters.

``` python
path = r"C:\Users\Biggan\Projects"

print(path)
```

Output:

``` text
C:\Users\Biggan\Projects
```

Raw strings are useful for Windows paths and regular expressions.

------------------------------------------------------------------------

# 🔢 05. String Indexing

Every character has a zero-based index.

``` python
text = "Python"

print(text[0])
print(text[2])
print(text[5])
```

Output:

``` text
P
t
n
```

### Index structure

``` text
Character:  P   y   t   h   o   n
Index:      0   1   2   3   4   5
```

The first character is always at index `0`.

------------------------------------------------------------------------

# 🔙 06. Negative Indexing

Negative indexes count from the end.

``` text
Character:   P    y    t    h    o    n
Negative:   -6   -5   -4   -3   -2   -1
```

Example:

``` python
text = "Python"

print(text[-1])
print(text[-2])
```

Output:

``` text
n
o
```

### Quick Rule

``` text
-1 → Last character
-2 → Second-last character
```

------------------------------------------------------------------------

# ✂️ 07. String Slicing

Slicing extracts part of a string.

### Syntax

``` python
string[start:stop:step]
```

The `stop` index is **exclusive**.

``` python
text = "Python"

print(text[0:3])
print(text[:3])
print(text[3:])
print(text[::2])
print(text[::-1])
```

Output:

``` text
Pyt
Pyt
hon
Pto
nohtyP
```

### Mental Model

``` text
[start : stop : step]
    │       │      │
    │       │      └── Jump size
    │       └───────── Exclusive endpoint
    └───────────────── Starting index
```

------------------------------------------------------------------------

# 🧊 08. String Immutability

Strings are immutable. You cannot change a character inside an existing
string.

``` python
text = "Python"

# text[0] = "J"
```

The commented statement would raise `TypeError`.

Instead, create a new string:

``` python
text = "J" + text[1:]

print(text)
```

Output:

``` text
Jython
```

### Remember

``` text
String object
     ↓
Cannot mutate in place
     ↓
Create another string
```

------------------------------------------------------------------------

# ➕ 09. Concatenation & Repetition

### Concatenation

Use `+` to join strings.

``` python
first = "G."
last = "Biggan"

full_name = first + " " + last

print(full_name)
```

Output:

``` text
G. Biggan
```

### Repetition

Use `*` to repeat strings.

``` python
print("-" * 20)
print("Python " * 3)
```

------------------------------------------------------------------------

# 📏 10. `len()`

`len()` returns the number of characters in a string.

``` python
text = "Python"

print(len(text))
```

Output:

``` text
6
```

Spaces are also characters:

``` python
print(len("Hello World"))
```

------------------------------------------------------------------------

# 🔍 11. String Membership

Use `in` and `not in` to check whether text occurs inside another
string.

``` python
text = "Python Engineering"

print("Python" in text)
print("Java" in text)
print("Java" not in text)
```

Output:

``` text
True
False
True
```

Membership is case-sensitive:

``` python
print("python" in "Python")
```

Output:

``` text
False
```

------------------------------------------------------------------------

# 🔠 12. Case Conversion

Common methods:

``` text
upper()
lower()
title()
capitalize()
swapcase()
casefold()
```

Example:

``` python
text = "python engineering"

print(text.upper())
print(text.lower())
print(text.title())
print(text.capitalize())
```

Output:

``` text
PYTHON ENGINEERING
python engineering
Python Engineering
Python engineering
```

For case-insensitive comparisons:

``` python
a = "Python"
b = "PYTHON"

print(a.casefold() == b.casefold())
```

Output:

``` text
True
```

------------------------------------------------------------------------

# 🔎 13. Searching & Counting

### `find()`

Returns the first matching index or `-1`.

``` python
text = "Python Programming"

print(text.find("Program"))
print(text.find("Java"))
```

Output:

``` text
7
-1
```

### `index()`

Returns the index but raises `ValueError` if the text is absent.

``` python
print("Python".index("t"))
```

Output:

``` text
2
```

### `count()`

Counts non-overlapping occurrences.

``` python
print("banana".count("a"))
```

Output:

``` text
3
```

### Remember

``` text
find()  → -1 when absent
index() → ValueError when absent
```

------------------------------------------------------------------------

# 🔎 14. String Checking Methods

Useful methods:

``` text
startswith()
endswith()
isalpha()
isdigit()
isalnum()
isspace()
islower()
isupper()
```

Example:

``` python
text = "Python123"

print(text.startswith("Python"))
print(text.endswith("123"))
print(text.isalpha())
print(text.isalnum())
```

Output:

``` text
True
True
False
True
```

`isalpha()` is false because the string contains digits.

------------------------------------------------------------------------

# 🧹 15. `strip()`, `lstrip()`, `rstrip()`

These methods remove characters from the beginning and/or end.

``` python
text = "   Python   "

print(text.strip())
print(text.lstrip())
print(text.rstrip())
```

Output:

``` text
Python
Python
   Python
```

`strip()` does not remove whitespace from the middle.

------------------------------------------------------------------------

# 🔄 16. `replace()`

`replace()` returns a new string with matching text replaced.

``` python
text = "I like Java"

new_text = text.replace("Java", "Python")

print(new_text)
```

Output:

``` text
I like Python
```

Because strings are immutable, the original object is not modified in
place.

------------------------------------------------------------------------

# ✂️ 17. `split()`

`split()` divides a string into a list.

``` python
text = "Python is powerful"

words = text.split()

print(words)
```

Output:

``` text
['Python', 'is', 'powerful']
```

Custom separator:

``` python
data = "apple,banana,mango"

print(data.split(","))
```

Output:

``` text
['apple', 'banana', 'mango']
```

------------------------------------------------------------------------

# 🔗 18. `join()`

`join()` combines strings using a separator.

``` python
words = ["Python", "is", "powerful"]

sentence = " ".join(words)

print(sentence)
```

Output:

``` text
Python is powerful
```

### Important

The elements must be strings.

``` python
numbers = ["10", "20", "30"]

print("-".join(numbers))
```

Mental model:

``` text
split()
String → List of strings

join()
Iterable of strings → String
```

------------------------------------------------------------------------

# 🎨 19. String Formatting

The most common modern approach is an f-string.

``` python
name = "Biggan"
age = 23

print(f"My name is {name} and I am {age} years old.")
```

Expressions can be embedded:

``` python
a = 10
b = 20

print(f"Sum = {a + b}")
```

Number formatting:

``` python
price = 99.98765

print(f"{price:.2f}")
```

Output:

``` text
99.99
```

------------------------------------------------------------------------

# 🌍 20. Unicode Basics

Python `str` represents Unicode text.

``` python
text = "Python — বাংলা — 日本語"

print(text)
```

A single string can contain characters from different writing systems.

Encoding becomes important when converting between text and raw bytes;
that topic belongs to a later chapter.

------------------------------------------------------------------------

# 🔢 21. Numbers

Python's core numeric types are:

``` text
int
float
complex
```

Example:

``` python
integer_value = 10
float_value = 10.5
complex_value = 2 + 3j
```

------------------------------------------------------------------------

# ➕ 22. Arithmetic Operators

  Operator   Meaning          Example
  ---------- ---------------- -----------
  `+`        Addition         `10 + 3`
  `-`        Subtraction      `10 - 3`
  `*`        Multiplication   `10 * 3`
  `/`        True division    `10 / 3`
  `//`       Floor division   `10 // 3`
  `%`        Remainder        `10 % 3`
  `**`       Exponentiation   `10 ** 3`

Example:

``` python
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a // b)
print(a % b)
print(a ** b)
```

------------------------------------------------------------------------

# ➗ 23. True Division `/`

`/` performs true division and normally returns a float.

``` python
print(10 / 2)
print(10 / 3)
```

Output:

``` text
5.0
3.3333333333333335
```

Even `10 / 2` produces `5.0`, not integer `5`.

------------------------------------------------------------------------

# ⬇️ 24. Floor Division `//`

`//` performs floor division.

``` python
print(10 // 3)
```

Output:

``` text
3
```

With negative values:

``` python
print(-10 // 3)
```

Output:

``` text
-4
```

This happens because floor means rounding toward negative infinity:

``` text
-10 / 3 ≈ -3.333...
floor → -4
```

------------------------------------------------------------------------

# 🧮 25. Modulo `%`

`%` returns the remainder associated with division.

``` python
print(10 % 3)
```

Output:

``` text
1
```

Because:

``` text
10 = 3 × 3 + 1
```

Common use:

``` python
number = 10

if number % 2 == 0:
    print("Even")
```

------------------------------------------------------------------------

# ⚡ 26. Exponentiation `**`

Use `**` for powers.

``` python
print(2 ** 3)
```

Output:

``` text
8
```

Fractional powers can represent roots:

``` python
print(25 ** 0.5)
```

Output:

``` text
5.0
```

------------------------------------------------------------------------

# 🎯 27. Floating-Point Behaviour

Floating-point arithmetic is approximate.

``` python
print(0.1 + 0.2)
```

You may see:

``` text
0.30000000000000004
```

This happens because many decimal fractions cannot be represented
exactly in binary floating-point format.

For precision-sensitive comparisons, use a tolerance:

``` python
a = 0.1 + 0.2
b = 0.3

print(abs(a - b) < 1e-9)
```

For exact decimal arithmetic, use the `decimal` module when appropriate.

------------------------------------------------------------------------

# 🧰 28. Useful Numeric Functions

``` python
print(abs(-10))
print(round(3.14159, 2))
print(min(10, 20, 5))
print(max(10, 20, 5))
print(sum([10, 20, 30]))
```

Output:

``` text
10
3.14
5
20
60
```

------------------------------------------------------------------------

# 🟢 29. Boolean Values

Python has two Boolean values:

``` python
True
False
```

Comparisons normally produce Boolean results:

``` python
age = 23

print(age >= 18)
print(age == 23)
print(age != 30)
```

Output:

``` text
True
True
True
```

------------------------------------------------------------------------

# 🧠 30. Truthiness

Python can evaluate objects in Boolean contexts.

Common falsy values:

``` text
False
None
0
0.0
0j
""
[]
()
{}
set()
```

Example:

``` python
name = ""

if name:
    print("Name exists")
else:
    print("Name is empty")
```

Output:

``` text
Name is empty
```

### Mental Model

``` text
Object
  ↓
Boolean Context
  ↓
Truthy / Falsy
```

------------------------------------------------------------------------

# 🧪 31. `bool()`

`bool()` converts a value to its Boolean interpretation.

``` python
print(bool(1))
print(bool(0))
print(bool("Python"))
print(bool(""))
print(bool([]))
print(bool([1, 2]))
```

Output:

``` text
True
False
True
False
False
True
```

------------------------------------------------------------------------

# 🔗 32. `and`

`and` evaluates operands from left to right.

``` python
age = 23
has_id = True

print(age >= 18 and has_id)
```

Output:

``` text
True
```

Important: `and` returns an operand, not necessarily a Boolean.

``` python
result = "Python" and "Engineering"

print(result)
```

Output:

``` text
Engineering
```

------------------------------------------------------------------------

# 🔗 33. `or`

`or` returns the first truthy operand, or the final operand if none is
truthy.

``` python
name = ""

result = name or "Unknown"

print(result)
```

Output:

``` text
Unknown
```

This is useful for fallback values:

``` python
display_name = user_name or "Anonymous"
```

------------------------------------------------------------------------

# 🔄 34. `not`

`not` reverses Boolean interpretation.

``` python
is_logged_in = False

print(not is_logged_in)
```

Output:

``` text
True
```

------------------------------------------------------------------------

# ⚡ 35. Short-Circuit Evaluation

Python can stop evaluating `and` / `or` before checking every operand.

### `and`

``` python
False and expensive_operation()
```

The second operand does not need to execute.

### `or`

``` python
True or expensive_operation()
```

The second operand does not need to execute.

Practical example:

``` python
user = None

if user and user.is_active:
    print("Active user")
```

If `user` is `None`, Python does not evaluate `user.is_active`.

------------------------------------------------------------------------

# ⚪ 36. `None`

`None` represents the absence of a meaningful value.

``` python
result = None

print(result)
print(type(result))
```

Output:

``` text
None
<class 'NoneType'>
```

Check it using identity:

``` python
if result is None:
    print("No result")
```

Prefer:

``` python
value is None
value is not None
```

over:

``` python
value == None
```

------------------------------------------------------------------------

# 🆚 37. `None` vs `False` vs `0` vs `""`

These values can all be falsy, but they have different meanings.

``` text
None  → No meaningful value
False → Logical false
0     → Numeric zero
""    → Empty string
```

If you need to distinguish them, use an explicit check rather than
relying only on truthiness.

------------------------------------------------------------------------

# 🧭 38. Conditional Statements

Conditional statements allow a program to choose different paths.

``` python
age = 23

if age >= 18:
    print("Adult")
```

Mental model:

``` text
Condition
    ↓
Truthy?
 /    \
Yes    No
 ↓      ↓
Run    Skip
block  block
```

------------------------------------------------------------------------

# 🔀 39. `if ... else`

``` python
age = 16

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Output:

``` text
Minor
```

`else` provides the alternative path when the `if` condition is falsy.

------------------------------------------------------------------------

# 🔀 40. `if ... elif ... else`

Use `elif` for multiple conditions.

``` python
marks = 82

if marks >= 90:
    grade = "A+"
elif marks >= 80:
    grade = "A"
elif marks >= 70:
    grade = "B"
else:
    grade = "C"

print(grade)
```

Output:

``` text
A
```

Python checks conditions from top to bottom and executes the first
matching branch.

------------------------------------------------------------------------

# 🪆 41. Nested Conditions

A condition can contain another condition.

``` python
age = 23
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
```

Sometimes this is clearer:

``` python
if age >= 18 and has_id:
    print("Entry allowed")
```

Prefer the structure that makes the business rule easiest to understand.

------------------------------------------------------------------------

# 🎯 42. Guard Conditions

A guard handles an invalid or special case early.

``` python
def process_age(age):
    if age < 0:
        return "Invalid age"

    return "Valid age"
```

Guard conditions reduce unnecessary nesting and are common in
professional code.

------------------------------------------------------------------------

# 🧮 43. Conditional Expression

Syntax:

``` python
value_if_true if condition else value_if_false
```

Example:

``` python
age = 23

status = "Adult" if age >= 18 else "Minor"

print(status)
```

Output:

``` text
Adult
```

Use this when the expression remains easy to read.

------------------------------------------------------------------------

# 🔁 44. `for` Loop

A `for` loop iterates over an iterable.

``` python
for character in "Python":
    print(character)
```

Output:

``` text
P
y
t
h
o
n
```

Mental model:

``` text
Iterable
   ↓
Get next item
   ↓
Run body
   ↓
Repeat
   ↓
Stop when exhausted
```

------------------------------------------------------------------------

# 📦 45. Iterating Over Collections

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

The loop variable receives one item at a time.

------------------------------------------------------------------------

# 🔢 46. `range(stop)`

`range()` represents an arithmetic progression of integers.

``` python
for i in range(5):
    print(i)
```

Output:

``` text
0
1
2
3
4
```

The `stop` value is exclusive.

------------------------------------------------------------------------

# 🔢 47. `range(start, stop)`

``` python
for i in range(2, 7):
    print(i)
```

Output:

``` text
2
3
4
5
6
```

Remember:

``` text
start → included
stop  → excluded
```

------------------------------------------------------------------------

# 🔢 48. `range(start, stop, step)`

``` python
for i in range(0, 10, 2):
    print(i)
```

Output:

``` text
0
2
4
6
8
```

Reverse:

``` python
for i in range(5, 0, -1):
    print(i)
```

Output:

``` text
5
4
3
2
1
```

------------------------------------------------------------------------

# 🔄 49. `while` Loop

A `while` loop repeats while its condition is truthy.

``` python
count = 1

while count <= 5:
    print(count)
    count += 1
```

Output:

``` text
1
2
3
4
5
```

Mental model:

``` text
Check
  ↓
Truthy?
  ↓ yes
Run body
  ↓
Update state
  ↓
Check again
```

------------------------------------------------------------------------

# ⚠️ 50. Infinite `while` Loops

A loop becomes infinite if its condition never becomes falsy.

Problem:

``` python
count = 1

# while count <= 5:
#     print(count)
```

`count` never changes.

Correct:

``` python
count = 1

while count <= 5:
    print(count)
    count += 1
```

### Always ask

``` text
What changes the loop condition?
```

------------------------------------------------------------------------

# 🪆 51. Nested Loops

A loop can contain another loop.

``` python
for i in range(3):
    for j in range(2):
        print(i, j)
```

Output:

``` text
0 0
0 1
1 0
1 1
2 0
2 1
```

The inner loop runs completely for each outer-loop iteration.

------------------------------------------------------------------------

# 🛑 52. `break`

`break` immediately exits the nearest enclosing loop.

``` python
for number in range(10):
    if number == 5:
        break

    print(number)
```

Output:

``` text
0
1
2
3
4
```

------------------------------------------------------------------------

# ⏭️ 53. `continue`

`continue` skips the remaining body of the current iteration and moves
to the next iteration.

``` python
for number in range(5):
    if number == 2:
        continue

    print(number)
```

Output:

``` text
0
1
3
4
```

------------------------------------------------------------------------

# 💤 54. `pass`

`pass` does nothing. It is a placeholder statement.

``` python
def future_feature():
    pass
```

### Critical Difference

``` text
break    → Exit loop
continue → Skip current iteration
pass     → Do nothing
```

------------------------------------------------------------------------

# 🔄 55. Loop `else`

Python allows an `else` block after a loop.

The loop `else` executes when the loop completes normally without
`break`.

``` python
for number in range(5):
    print(number)
else:
    print("Loop completed")
```

Output:

``` text
0
1
2
3
4
Loop completed
```

With `break`:

``` python
for number in range(5):
    if number == 2:
        break
else:
    print("Loop completed")
```

The `else` block does not run because `break` terminated the loop.

------------------------------------------------------------------------

# 🔎 56. Search Pattern

A common use of loop `else` is searching.

``` python
numbers = [10, 20, 30, 40]
target = 30

for number in numbers:
    if number == target:
        print("Found")
        break
else:
    print("Not found")
```

Output:

``` text
Found
```

------------------------------------------------------------------------

# ➕ 57. Accumulator Pattern

An accumulator gradually builds a result.

``` python
total = 0

for number in [10, 20, 30]:
    total += number

print(total)
```

Output:

``` text
60
```

Mental model:

``` text
0
 ↓ +10
10
 ↓ +20
30
 ↓ +30
60
```

This pattern is fundamental in data processing.

------------------------------------------------------------------------

# 📊 58. Counting Pattern

Use a counter to count matching items.

``` python
count = 0

for number in [10, 20, 30, 40]:
    if number > 20:
        count += 1

print(count)
```

Output:

``` text
2
```

------------------------------------------------------------------------

# 🧩 59. `match / case`

Python's `match / case` statement provides structural pattern matching.

``` python
command = "start"

match command:
    case "start":
        print("Starting")
    case "stop":
        print("Stopping")
    case _:
        print("Unknown command")
```

Output:

``` text
Starting
```

Mental model:

``` text
Value
  ↓
match
  ↓
Try patterns
  ↓
First matching case
  ↓
Execute block
```

------------------------------------------------------------------------

# 🔹 60. Literal Patterns

``` python
status = 404

match status:
    case 200:
        print("Success")
    case 404:
        print("Not Found")
    case 500:
        print("Server Error")
    case _:
        print("Other")
```

Output:

``` text
Not Found
```

------------------------------------------------------------------------

# 🔗 61. Multiple Patterns with `|`

Use `|` when multiple patterns should use the same branch.

``` python
command = "quit"

match command:
    case "quit" | "exit":
        print("Program will stop")
    case "start":
        print("Program will start")
    case _:
        print("Unknown command")
```

Output:

``` text
Program will stop
```

------------------------------------------------------------------------

# 🃏 62. Wildcard `_`

`case _:` matches anything not matched by earlier cases.

``` python
value = "unknown"

match value:
    case "python":
        print("Python")
    case _:
        print("Something else")
```

Output:

``` text
Something else
```

------------------------------------------------------------------------

# 🛡️ 63. Guards

A guard adds an additional condition to a pattern.

``` python
number = 15

match number:
    case n if n > 10:
        print("Greater than 10")
    case _:
        print("10 or less")
```

Output:

``` text
Greater than 10
```

The pattern must match and the guard must also be true.

------------------------------------------------------------------------

# 🧩 64. Structural Pattern Matching

`match` can inspect the structure of a value.

``` python
point = (0, 5)

match point:
    case (0, 0):
        print("Origin")
    case (0, y):
        print(f"On Y-axis at {y}")
    case (x, 0):
        print(f"On X-axis at {x}")
    case (x, y):
        print(f"Point: ({x}, {y})")
```

Output:

``` text
On Y-axis at 5
```

Here, `(0, y)` matches a two-item tuple whose first item is `0` and
binds the second item to `y`.

------------------------------------------------------------------------

# 🆚 65. `if` vs `match`

Use `if` when the decision is primarily based on arbitrary Boolean
conditions.

``` python
if age >= 18:
    ...
```

Use `match` when the problem naturally involves matching a value or
structure against patterns.

``` python
match command:
    case "start":
        ...
    case "stop":
        ...
```

### Quick Rule

``` text
Condition-based decision → if / elif / else
Pattern-based decision   → match / case
```

------------------------------------------------------------------------

# 🧪 66. Combined Core Python Example

``` python
name = input("Enter your name: ")
age = int(input("Enter your age: "))

print(f"\nHello, {name}!")

if age < 0:
    print("Invalid age")
elif age >= 18:
    print("You are an adult")
else:
    print("You are a minor")

for number in range(1, 6):
    if number % 2 == 0:
        print(f"{number} is even")
    else:
        print(f"{number} is odd")

command = "start"

match command:
    case "start":
        print("System starting...")
    case "stop":
        print("System stopping...")
    case _:
        print("Unknown command")
```

This single program combines:

``` text
input()
int()
str
int
f-string
if / elif / else
for
range()
%
Boolean logic
match / case
```

------------------------------------------------------------------------

# 🚨 67. Common Mistakes

### 1. Forgetting zero-based indexing

``` python
text = "Python"

# text[6]
```

The last index is `5`.

### 2. Forgetting that slicing excludes `stop`

``` python
print("Python"[0:2])
```

Output:

``` text
Py
```

### 3. Trying to mutate a string

``` python
text = "Python"

# text[0] = "J"
```

Strings are immutable.

### 4. Treating `input()` as numeric

``` python
age = input("Age: ")

# age + 10
```

Convert first:

``` python
age = int(input("Age: "))
```

### 5. Confusing `/` and `//`

``` python
10 / 3   # 3.333...
10 // 3  # 3
```

### 6. Using `is` for normal equality

``` text
== → Equality
is → Identity
```

### 7. Forgetting to update a `while` loop

``` python
count = 1

# while count <= 5:
#     print(count)
```

### 8. Confusing loop controls

``` text
break    → Exit loop
continue → Skip current iteration
pass     → Do nothing
```

### 9. Expecting `range()` to include `stop`

``` python
range(5)
```

produces:

``` text
0 1 2 3 4
```

### 10. Forgetting the fallback case

``` python
case _:
```

is useful when unmatched values need a default branch.

------------------------------------------------------------------------

# 🎤 68. Interview Perspective

### Q1. Are strings mutable?

No. Python strings are immutable.

### Q2. Difference between `find()` and `index()`?

``` text
find()  → -1 if absent
index() → ValueError if absent
```

### Q3. What does `input()` return?

`str`.

### Q4. Difference between `/` and `//`?

``` text
/  → True division
// → Floor division
```

### Q5. What does `%` do?

It returns the remainder associated with division.

### Q6. What is truthiness?

The Boolean interpretation of an object in a Boolean context.

### Q7. What is short-circuit evaluation?

Python stops evaluating `and` / `or` operands once the final result is
already determined.

### Q8. Difference between `break` and `continue`?

``` text
break    → exits the loop
continue → skips the current iteration
```

### Q9. What does `pass` do?

Nothing; it is a placeholder statement.

### Q10. What is special about loop `else`?

It runs when the loop completes normally without `break`.

### Q11. What is `range()`?

A range object representing an arithmetic progression of integers.

### Q12. What is `match / case`?

Python's structural pattern matching feature, introduced in Python 3.10.

------------------------------------------------------------------------

# 📊 69. Core Python Quick Reference

  Concept       Quick Recall
  ------------- ------------------------------------
  String        Immutable Unicode text sequence
  Indexing      Access by position
  Slicing       Extract a sequence portion
  `len()`       Number of characters/items
  `upper()`     Uppercase
  `lower()`     Lowercase
  `strip()`     Remove leading/trailing whitespace
  `split()`     String → list
  `join()`      Strings → string
  `replace()`   Return replaced string
  `find()`      Position or `-1`
  `count()`     Count occurrences
  `int`         Integer
  `float`       Floating-point
  `complex`     Complex number
  `/`           True division
  `//`          Floor division
  `%`           Remainder
  `**`          Exponentiation
  `bool`        `True` / `False`
  Truthiness    Boolean interpretation
  `and`         Logical AND / short-circuit
  `or`          Logical OR / short-circuit
  `not`         Logical negation
  `None`        No meaningful value
  `if`          Conditional branch
  `elif`        Additional branch
  `else`        Alternative branch
  `for`         Iterate over iterable
  `while`       Repeat while truthy
  `break`       Exit loop
  `continue`    Skip current iteration
  `pass`        Do nothing
  `range()`     Integer progression
  `match`       Pattern matching
  `case _`      Wildcard / fallback

------------------------------------------------------------------------

# 🧠 70. One-Minute Revision

``` text
STRINGS
│
├── Immutable
├── Unicode
├── Indexing
├── Negative Indexing
├── Slicing
├── Concatenation
├── Repetition
├── Membership
├── Searching
├── Checking
├── split()
├── join()
├── replace()
└── Formatting

NUMBERS
│
├── int
├── float
├── complex
├── +
├── -
├── *
├── /
├── //
├── %
└── **

BOOLEAN
│
├── True
├── False
├── Truthiness
├── and
├── or
├── not
└── Short-Circuiting

NONE
│
├── None
├── is None
└── No Meaningful Value

CONTROL FLOW
│
├── if
├── elif
├── else
├── for
├── while
├── break
├── continue
└── pass

RANGE
│
├── range(stop)
├── range(start, stop)
└── range(start, stop, step)

MATCHING
│
├── match
├── case
├── |
├── _
└── Guards
```

------------------------------------------------------------------------

# 🧪 71. Practice Checklist

``` text
STRINGS
☐ Create strings
☐ Use quote styles
☐ Escape sequences
☐ Raw strings
☐ Indexing
☐ Negative indexing
☐ Slicing
☐ Reverse strings
☐ Immutability
☐ Concatenation
☐ Repetition
☐ Membership
☐ Case methods
☐ Search methods
☐ Checking methods
☐ strip()
☐ replace()
☐ split()
☐ join()
☐ f-strings
☐ Unicode basics

NUMBERS
☐ int
☐ float
☐ complex
☐ Arithmetic
☐ True division
☐ Floor division
☐ Modulo
☐ Exponentiation
☐ Floating-point behaviour

BOOLEAN
☐ True / False
☐ Comparisons
☐ Truthiness
☐ bool()
☐ and
☐ or
☐ not
☐ Short-circuit evaluation

NONE
☐ None
☐ is None
☐ None vs False
☐ None vs 0
☐ None vs ""

CONDITIONALS
☐ if
☐ elif
☐ else
☐ Nested conditions
☐ Guard conditions
☐ Conditional expressions

LOOPS
☐ for
☐ while
☐ Nested loops
☐ break
☐ continue
☐ pass
☐ Loop else
☐ Search pattern
☐ Counting pattern
☐ Accumulator pattern

RANGE
☐ range(stop)
☐ range(start, stop)
☐ range(start, stop, step)
☐ Positive step
☐ Negative step

MATCH
☐ match
☐ case
☐ Literal patterns
☐ Multiple patterns
☐ Wildcard
☐ Guards
☐ Structural patterns
```

------------------------------------------------------------------------

# 🎯 72. Core Python Completion Test

Before moving to Data Structures, make sure you can explain:

``` text
1. Why are strings immutable?

2. How does zero-based indexing work?

3. Why is the slicing stop index exclusive?

4. What does input() return?

5. What is the difference between / and //?

6. What does % represent?

7. Why can 0.1 + 0.2 produce an unexpected decimal representation?

8. What are truthy and falsy values?

9. How does short-circuit evaluation work?

10. Why should None normally be checked with is?

11. What is the difference between if, elif, and else?

12. What is the difference between for and while?

13. What is the difference between break, continue, and pass?

14. How does range(start, stop, step) work?

15. What does loop else mean?

16. What is an accumulator pattern?

17. What is a search pattern?

18. When is match/case more natural than if/elif?
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
03. Data Structures
          │
          ├── Lists
          ├── Tuples
          ├── Sets
          ├── Dictionaries
          ├── Mutability
          ├── Hashing
          ├── Nested Structures
          ├── Iteration
          ├── Comprehensions
          └── Practical Data Processing
```

**Next → `03_DATA_STRUCTURES/03_Data_Structures.md`**

------------------------------------------------------------------------

# 🐍 Final Core Python Rule

> **Do not memorize syntax without understanding behaviour.**

``` text
Syntax
  ↓
Meaning
  ↓
Behaviour
  ↓
Experiment
  ↓
Debug
  ↓
Practice
  ↓
Build
  ↓
Recall
```

Core Python is where Python starts feeling like a real programming
language rather than a collection of syntax rules.
