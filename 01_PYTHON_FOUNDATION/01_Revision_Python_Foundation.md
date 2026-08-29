# 🐍 Python Engineering — 01. Python Foundation Revision

> **Purpose:** A compact, scan-friendly revision guide for quickly recalling the complete Python Foundation chapter.
>
> **Rule:** If a concept is unfamiliar, return to `01_Python_Foundation.md` for the full explanation.

---

# 📚 Foundation at a Glance

```text
Python Foundation
│
├── Python & Execution
├── Syntax & Indentation
├── Comments & Docstrings
├── Statements & Expressions
├── Variables & Assignment
├── Dynamic Typing
├── Built-in Data Types
├── Type Checking & Conversion
├── Input & Output
├── Operators
├── Operator Precedence
├── f-Strings
├── Truthiness
├── Keywords & Naming
├── Built-in Functions
├── Unpacking
├── Functions — Basic Foundation
├── Imports — Basic Foundation
├── Errors & Exceptions
├── Debugging
└── Python Style
```

---

# 🐍 01. What is Python?

```text
Python
  ↓
High-Level
  ↓
General-Purpose
  ↓
Readable Syntax
  ↓
Large Ecosystem
```

**Quick Definition:** Python is a high-level, general-purpose programming language used for web development, automation, data processing, AI/ML, Data Engineering, testing, scripting, and many other areas.

### Remember

```python
print("Hello, Python!")
```

`print()` writes output to standard output.

---

# ⚙️ 02. Python Execution

A simplified CPython model:

```text
Source Code
    ↓
Parsing / Compilation
    ↓
Bytecode
    ↓
Python Runtime
    ↓
Execution
    ↓
Result
```

Run a Python file:

```bash
python program.py
```

Check Python version:

```bash
python --version
```

Windows alternative:

```powershell
py --version
```

---

# ✍️ 03. Syntax

**Syntax = the rules Python uses to understand valid code.**

Correct:

```python
if True:
    print("Hello")
```

Incorrect:

```python
# if True
#     print("Hello")
```

### Quick Rule

```text
Valid Python code
      ↓
Follows Python syntax
```

---

# 📐 04. Indentation

**Indentation defines the structure of Python code blocks.**

Python uses indentation instead of `{}` for ordinary block structure.

```python
if age >= 18:
    print("Adult")
```

The indented statement belongs to the `if` block.

### Recommended

```text
1 indentation level = 4 spaces
```

### Common mistake

```python
if True:
print("Hello")
```

Correct:

```python
if True:
    print("Hello")
```

### Remember

```text
Header
  ↓
:
  ↓
Indented Block
```

---

# 💬 05. Comments & Docstrings

### Comment

```python
# This is a comment
age = 23
```

### Inline Comment

```python
age = 23  # Student age
```

### Docstring

```python
def greet():
    """Return a greeting."""
    return "Hello"
```

### Quick Rule

```text
Comment   → Explanation for programmers
Docstring → Documentation associated with code
```

---

# 🧱 06. Statements vs Expressions

### Statement

An instruction that forms part of a program.

```python
age = 23
print(age)
```

### Expression

Code that evaluates to a value.

```python
10 + 20
```

Result:

```text
30
```

### Remember

```text
Statement  → Performs an instruction
Expression → Produces / evaluates to a value
```

---

# 📦 07. Variables

A Python variable is best understood as a **name bound to an object**.

```python
name = "Biggan"
age = 23
```

Conceptually:

```text
name ───► "Biggan"
age  ───► 23
```

### Reassignment

```python
age = 23
age = 24
```

Now:

```text
age ───► 24
```

### Key Rule

Python does not require a traditional variable declaration such as:

```text
int age;
```

Instead:

```python
age = 23
```

creates or updates a name-to-object binding.

---

# 🧠 08. Dynamic Typing

Python is dynamically typed.

A name can be rebound to objects of different types:

```python
value = 100
print(type(value))

value = "Python"
print(type(value))
```

Output:

```text
<class 'int'>
<class 'str'>
```

### Mental Model

```text
value ───► 100
           int

value ───► "Python"
           str
```

### Important

```text
Dynamic typing
≠
No types
```

Python objects still have types.

---

# 🔍 09. `type()`

Use `type()` to inspect an object's type.

```python
name = "Biggan"
age = 23
price = 99.99

print(type(name))
print(type(age))
print(type(price))
```

Output:

```text
<class 'str'>
<class 'int'>
<class 'float'>
```

### Quick Recall

```python
type(value)
```

→ tells you the object's type.

---

# 🧪 10. Basic Built-in Types

| Type | Example | Meaning |
|---|---|---|
| `str` | `"Python"` | Text |
| `int` | `23` | Integer |
| `float` | `23.5` | Floating-point number |
| `complex` | `2 + 3j` | Complex number |
| `bool` | `True` | Boolean |
| `NoneType` | `None` | Absence of a meaningful value |

Collections such as:

```text
list
tuple
set
dict
```

will be studied in the Data Structures chapter.

---

# 🔤 11. `str`

Strings represent text.

```python
name = "Python"
```

Other quoting forms:

```python
single = 'Python'
double = "Python"
multi_line = """Python
is
great"""
```

### Important

Strings are **immutable**.

```python
name = "Python"

name = name + " Engineering"
```

The original string is not modified in place; the name is rebound to a new string.

---

# 🔢 12. `int`

Integers represent whole numbers.

```python
age = 23
count = -10
large_number = 12345678901234567890
```

Python integers support arbitrarily large integer values, limited mainly by available memory.

---

# 🔢 13. `float`

Floating-point numbers represent approximate real numbers.

```python
price = 99.99
```

### Important floating-point behaviour

```python
print(0.1 + 0.2)
```

Possible output:

```text
0.30000000000000004
```

This occurs because binary floating-point representation cannot represent every decimal fraction exactly.

### Remember

```text
float ≠ exact decimal arithmetic
```

---

# 🧮 14. `complex`

Python represents complex numbers using `j`.

```python
number = 2 + 3j

print(number.real)
print(number.imag)
```

Output:

```text
2.0
3.0
```

Mental model:

```text
2 + 3j
│   │
│   └── Imaginary part
└────── Real part
```

---

# 🟢 15. `bool`

Boolean values:

```python
True
False
```

Example:

```python
is_logged_in = True
```

Comparisons also produce Boolean results:

```python
age = 23

print(age >= 18)
```

Output:

```text
True
```

---

# ⚪ 16. `None`

`None` represents the absence of a meaningful value.

```python
result = None
```

Type:

```python
print(type(result))
```

Output:

```text
<class 'NoneType'>
```

### Correct check

```python
if result is None:
    print("No result")
```

### Remember

```text
None
≠
0
≠
""
≠
False
```

---

# 🔄 17. Type Conversion

Common conversion functions:

```python
int()
float()
str()
bool()
complex()
```

Examples:

```python
age = int("23")
price = float("99.99")
number = str(100)
flag = bool(1)
value = complex(2, 3)
```

### Invalid conversion

```python
# int("Python")
```

Raises:

```text
ValueError
```

### Mental Model

```text
Existing Value
      ↓
Conversion Function
      ↓
Converted Value
```

---

# ⌨️ 18. `input()`

`input()` reads a line from standard input and returns a string.

```python
name = input("Enter your name: ")
```

If the user enters:

```text
Biggan
```

then:

```python
name == "Biggan"
```

### Critical Rule

```python
age = input("Enter age: ")
```

Even if the user enters:

```text
23
```

the result is:

```python
"23"
```

not:

```python
23
```

Convert when necessary:

```python
age = int(input("Enter age: "))
```

---

# 🖨️ 19. `print()`

Basic:

```python
print("Hello")
```

Multiple values:

```python
name = "Biggan"
age = 23

print(name, age)
```

### `sep`

```python
print("Python", "Java", "C++", sep=" | ")
```

Output:

```text
Python | Java | C++
```

### `end`

```python
print("Hello", end=" ")
print("Python")
```

Output:

```text
Hello Python
```

### Quick Recall

```text
print()
├── sep → separator between arguments
└── end → ending after output
```

---

# 🔤 20. f-Strings

Syntax:

```python
f"Text {expression}"
```

Example:

```python
name = "Biggan"
age = 23

print(f"My name is {name} and I am {age} years old.")
```

Expression:

```python
a = 10
b = 20

print(f"Sum = {a + b}")
```

Number formatting:

```python
price = 99.98765

print(f"{price:.2f}")
```

Output:

```text
99.99
```

### Remember

```text
f"Hello {name}"
```

→ insert the value/expression inside `{}`.

---

# ➕ 21. Arithmetic Operators

| Operator | Meaning | Example |
|---|---|---|
| `+` | Addition | `10 + 3` |
| `-` | Subtraction | `10 - 3` |
| `*` | Multiplication | `10 * 3` |
| `/` | Division | `10 / 3` |
| `//` | Floor division | `10 // 3` |
| `%` | Remainder | `10 % 3` |
| `**` | Power | `10 ** 3` |

Example:

```python
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

---

# 📝 22. Assignment Operators

Basic:

```python
x = 10
```

Compound:

```python
x += 5
x -= 2
x *= 2
x /= 2
x //= 2
x %= 2
x **= 2
```

Example:

```python
x = 10
x += 5
```

Conceptually:

```python
x = x + 5
```

---

# ⚖️ 23. Comparison Operators

```text
==  Equal
!=  Not equal
>   Greater than
<   Less than
>=  Greater than or equal
<=  Less than or equal
```

Example:

```python
age = 23

print(age >= 18)
print(age == 23)
print(age != 20)
```

Comparison results are normally Boolean:

```text
True
False
```

---

# 🧠 24. Logical Operators

```text
and
or
not
```

### `and`

Both conditions must be truthy.

```python
age = 23
has_id = True

print(age >= 18 and has_id)
```

### `or`

At least one condition must be truthy.

```python
is_admin = False
is_owner = True

print(is_admin or is_owner)
```

### `not`

Reverses truth value.

```python
has_id = True

print(not has_id)
```

### Important

`and` and `or` use short-circuit evaluation and can return an operand rather than a Boolean.

```python
result = "" or "Python"

print(result)
```

Output:

```text
Python
```

---

# 🔍 25. Membership Operators

```text
in
not in
```

Example:

```python
language = "Python"

print("P" in language)
print("Java" in language)
print("Java" not in language)
```

Output:

```text
True
False
True
```

### Quick Meaning

```text
in     → Is it contained?
not in → Is it not contained?
```

---

# 🆔 26. Identity Operators

```text
is
is not
```

They test **object identity**, not general value equality.

Example:

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)
print(a is b)
```

Output:

```text
True
False
```

### Critical Difference

```text
== → Equality
is → Same object?
```

Use:

```python
value is None
```

for `None` checks.

---

# 📐 27. Operator Precedence

When multiple operators appear in one expression, precedence determines which operations are evaluated first.

Example:

```python
10 + 2 * 3
```

Multiplication happens first:

```text
2 * 3 = 6
10 + 6 = 16
```

Therefore:

```python
print(10 + 2 * 3)
```

Output:

```text
16
```

### Simplified order

```text
()
 ↓
**
 ↓
+x, -x
 ↓
*, /, //, %
 ↓
+, -
 ↓
Comparisons
 ↓
not
 ↓
and
 ↓
or
```

### Best Practice

Use parentheses when they make the intended calculation clearer:

```python
result = (10 + 2) * 3
```

---

# 🧠 28. Truthiness

Python evaluates objects in Boolean contexts.

Common falsy values:

```text
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

```python
name = ""

if name:
    print("Name exists")
else:
    print("Name is empty")
```

Output:

```text
Name is empty
```

### Quick Rule

```text
Empty / zero-like values → commonly falsy
Non-empty / non-zero objects → commonly truthy
```

---

# 🔗 29. Chained Comparisons

Python allows:

```python
18 <= age <= 60
```

instead of:

```python
18 <= age and age <= 60
```

Example:

```python
score = 75

if 40 <= score <= 100:
    print("Valid range")
```

This is both valid and readable Python.

---

# 📦 30. Multiple Assignment

Python allows:

```python
a, b, c = 10, 20, 30
```

Output:

```python
print(a, b, c)
```

```text
10 20 30
```

---

# 🔄 31. Variable Swapping

Python can swap values without a temporary variable:

```python
a = 10
b = 20

a, b = b, a
```

Result:

```text
a → 20
b → 10
```

---

# 📦 32. Unpacking

```python
numbers = [10, 20, 30]

a, b, c = numbers
```

Result:

```text
a → 10
b → 20
c → 30
```

### Extended Unpacking

```python
numbers = [1, 2, 3, 4, 5]

first, *middle, last = numbers
```

Result:

```text
first  → 1
middle → [2, 3, 4]
last   → 5
```

---

# 🔑 33. Python Keywords

Keywords are reserved words with special meaning in Python syntax.

Examples:

```text
False
None
True
and
as
assert
async
await
break
case
class
continue
def
del
elif
else
except
finally
for
from
global
if
import
in
is
lambda
match
nonlocal
not
or
pass
raise
return
try
while
with
yield
```

Check the actual keyword list:

```python
import keyword

print(keyword.kwlist)
```

### Remember

Do not use keywords as normal variable names.

---

# 📝 34. Naming Rules

Identifiers:

```text
✓ Can contain letters
✓ Can contain digits
✓ Can contain underscores
✓ Are case-sensitive
✗ Cannot start with a digit
✗ Cannot be keywords
```

Valid:

```python
name = "Biggan"
student_age = 23
value2 = 100
_private_value = 10
```

Invalid:

```python
# 2value = 20
# student-age = 23
# class = "Python"
```

---

# 📐 35. Naming Conventions

| Item | Convention | Example |
|---|---|---|
| Variable | `snake_case` | `student_name` |
| Function | `snake_case` | `calculate_total()` |
| Class | `PascalCase` | `StudentProfile` |
| Constant | `UPPER_CASE` | `MAX_SIZE` |
| Internal name | `_leading_underscore` | `_value` |

### Why?

Good names communicate intent.

Bad:

```python
x = 4500
```

Better:

```python
monthly_salary = 4500
```

---

# 🔤 36. Case Sensitivity

Python treats different capitalization as different names.

```python
name = "Biggan"
Name = "Rahim"
```

These are two separate identifiers.

```python
print(name)
print(Name)
```

Output:

```text
Biggan
Rahim
```

### Tip

Avoid names that differ only by capitalization because they are easy to confuse.

---

# 🧰 37. Important Built-in Functions

Common built-ins:

```text
print()
input()
len()
type()
id()
abs()
round()
sum()
min()
max()
sorted()
range()
enumerate()
zip()
map()
filter()
```

Example:

```python
numbers = [10, 20, 30]

print(len(numbers))
print(sum(numbers))
print(min(numbers))
print(max(numbers))
```

Output:

```text
3
60
10
30
```

---

# 🆔 38. `id()`

`id()` returns an integer identifying an object for the duration of that object's lifetime.

```python
value = "Python"

print(id(value))
```

Do not memorize the actual number because it is runtime-dependent.

### Quick Recall

```text
type() → What type is this object?
id()   → Which identity does this object have?
is     → Are these references to the same object?
==     → Are these values equal?
```

---

# 🔄 39. Basic Function Structure

A function is a reusable unit of logic.

```python
def greet(name):
    return f"Hello, {name}"


message = greet("Biggan")

print(message)
```

### Terms

```text
greet       → Function name
name        → Parameter
"Biggan"    → Argument
return      → Sends result back
message     → Receives returned value
```

Detailed functions are covered later.

---

# 📦 40. Basic Import

Python modules provide reusable functionality.

```python
import math

print(math.sqrt(25))
```

Output:

```text
5.0
```

Specific import:

```python
from math import sqrt

print(sqrt(25))
```

### Quick Recall

```text
Module
  ↓
Reusable Python code
  ↓
import
  ↓
Use functionality
```

---

# 🧪 41. Interactive Mode / REPL

Start:

```bash
python
```

Then:

```python
>>> 10 + 20
30

>>> print("Hello")
Hello
```

Useful for:

```text
Quick experiments
Small calculations
Testing ideas
Exploring behaviour
```

Exit:

```python
exit()
```

### Remember

```text
REPL   → Experiment
Script → Build
```

---

# 🚨 42. Common Errors

| Error | Meaning |
|---|---|
| `SyntaxError` | Python cannot parse the code |
| `IndentationError` | Block indentation is invalid |
| `NameError` | Name is not defined |
| `TypeError` | Operation/function received an inappropriate type |
| `ValueError` | Value is invalid for the operation |
| `ZeroDivisionError` | Division by zero |
| `IndexError` | Sequence index does not exist |
| `KeyError` | Dictionary key does not exist |

### Example

```python
# int("Python")
```

→ `ValueError`

```python
# "Age: " + 23
```

→ `TypeError`

---

# 🧠 43. Reading a Traceback

When an error occurs:

```text
Error
  ↓
Read Traceback
  ↓
Find File
  ↓
Find Line
  ↓
Read Exception Type
  ↓
Read Error Message
  ↓
Inspect Values
  ↓
Fix Cause
  ↓
Run Again
```

### Professional habit

Do not immediately copy the error into a search engine.

First ask:

```text
What happened?
Why did it happen?
Where did it happen?
What value/type caused it?
How can I fix the actual cause?
```

---

# 🧪 44. `assert`

Use `assert` to check assumptions during development.

```python
age = 23

assert age >= 18
```

If the condition is false:

```text
AssertionError
```

### Important

Do not use `assert` as a replacement for security checks or mandatory runtime validation because assertions can be disabled.

---

# 📏 45. PEP 8 Foundation

PEP 8 is Python's widely used style guide.

Remember:

```text
4-space indentation
snake_case variables/functions
PascalCase classes
UPPER_CASE constants
Readable spacing
Clear structure
```

Example:

```python
def calculate_total(price, quantity):
    return price * quantity
```

### Goal

```text
Readable
   ↓
Maintainable
   ↓
Reviewable
   ↓
Professional
```

---

# 🧪 46. Foundation Practice

Run this program:

```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
marks = float(input("Enter your marks: "))

is_adult = age >= 18
is_passed = marks >= 40

print("\n--- Student Information ---")
print(f"Name: {name}")
print(f"Age: {age}")
print(f"Marks: {marks}")
print(f"Adult: {is_adult}")
print(f"Passed: {is_passed}")
```

### Then experiment

```text
☐ Change the name
☐ Change the age
☐ Change the marks
☐ Add another variable
☐ Add arithmetic
☐ Add a comparison
☐ Intentionally create a TypeError
☐ Read the traceback
☐ Fix the error
☐ Run again
```

---

# 🧠 47. One-Minute Mental Model

```text
PYTHON
│
├── Code
│   ├── Syntax
│   ├── Statements
│   ├── Expressions
│   └── Indentation
│
├── Names
│   ├── Variables
│   ├── Assignment
│   └── Dynamic Typing
│
├── Objects
│   ├── str
│   ├── int
│   ├── float
│   ├── complex
│   ├── bool
│   └── None
│
├── Interaction
│   ├── input()
│   └── print()
│
├── Operations
│   ├── Arithmetic
│   ├── Assignment
│   ├── Comparison
│   ├── Logical
│   ├── Membership
│   └── Identity
│
├── Language Rules
│   ├── Precedence
│   ├── Keywords
│   ├── Naming
│   └── Truthiness
│
└── Reliability
    ├── Errors
    ├── Tracebacks
    ├── Debugging
    └── Style
```

---

# 🎯 48. Must-Remember Rules

```text
1. Python uses indentation to define block structure.

2. Variables are names bound to objects.

3. Python is dynamically typed.

4. input() returns str.

5. type() tells you an object's type.

6. None represents absence of a meaningful value.

7. == checks equality.

8. is checks object identity.

9. Strings are immutable.

10. Floating-point arithmetic is approximate.

11. f-strings format values directly inside strings.

12. Operator precedence determines evaluation order.

13. Parentheses can make evaluation order explicit.

14. Truthiness controls behaviour in Boolean contexts.

15. and/or use short-circuit evaluation.

16. Keywords are reserved by Python's syntax.

17. Read the traceback before trying to fix an error.

18. Good naming makes code easier to understand.

19. Assertions are for development assumptions, not mandatory validation.

20. Readable code is part of professional Python development.
```

---

# 🎤 49. Interview Flash Revision

### What is Python?

```text
High-level + General-purpose programming language
```

### What is dynamic typing?

```text
Names can be rebound to objects of different types at runtime.
```

### What is a variable?

```text
A name bound to an object.
```

### `=` vs `==`

```text
=   → Assignment
==  → Equality comparison
```

### `==` vs `is`

```text
==  → Equality
is  → Identity
```

### What does `input()` return?

```text
str
```

### What is `None`?

```text
A singleton representing absence of a meaningful value.
```

### What is indentation?

```text
Leading whitespace used to define Python block structure.
```

### What is an f-string?

```text
A formatted string literal that embeds expressions using {}.
```

### What is truthiness?

```text
The way an object behaves when evaluated in a Boolean context.
```

---

# 🏁 Foundation Complete

If you can quickly explain these concepts without looking at the main chapter:

```text
Python
Syntax
Indentation
Statements
Expressions
Variables
Objects
Dynamic Typing
Data Types
Type Conversion
input()
print()
f-Strings
Operators
Precedence
Truthiness
Keywords
Functions
Imports
Errors
Tracebacks
Debugging
PEP 8
```

then you have a solid Python Foundation.

---

# 🚀 Next Chapter

```text
01. Python Foundation
          │
          ▼
02. Core Python
          │
          ├── Strings & String Operations
          ├── Numbers
          ├── Boolean & Truthiness
          ├── None
          ├── Conditional Statements
          ├── for / while Loops
          ├── break / continue / pass
          ├── range()
          └── match / case
```

**Next → `02_CORE_PYTHON/02_Core_Python.md`**

---

# 🐍 Final Rule

```text
Don't just read.
      ↓
Understand.
      ↓
Write.
      ↓
Run.
      ↓
Experiment.
      ↓
Break.
      ↓
Read the error.
      ↓
Debug.
      ↓
Practice.
      ↓
Build.
      ↓
Revise.
```

> **Python becomes a skill when you stop only reading code and start actively working with it.**
