# 🐍 Python Engineering — 01. Python Foundation

> **Goal:** Build a strong Python foundation that a complete beginner can understand and that an experienced Python developer can revisit years later.

---

# 📚 Chapter Overview

```text
Python Foundation
│
├── What is Python?
├── Why Python?
├── Python Installation & Environment
├── Python Interpreter
├── Python Execution Model
├── Python Syntax
├── Indentation
├── Comments & Docstrings
├── Statements & Expressions
├── Variables & Assignment
├── Naming Rules
├── Dynamic Typing
├── Built-in Data Types
├── Type Checking
├── Type Conversion
├── Input & Output
├── print()
├── input()
├── Operators
├── Operator Precedence
├── f-Strings
├── Python Keywords
├── Built-in Functions
├── Truthiness
├── Errors & Exceptions
├── Debugging Basics
├── Coding Style
└── Foundation Revision
```

---

# 🎯 01. What is Python?

Python is a **high-level, general-purpose programming language**.

### What does "high-level" mean?

A high-level language hides many low-level computer details from the programmer. You can work with variables, functions, objects, files, and data structures without manually controlling CPU registers or raw memory addresses for normal programming tasks.

### What does "general-purpose" mean?

Python is not designed for only one type of application. It can be used for:

- Web and backend development
- Automation and scripting
- Data analysis
- Data Engineering
- Artificial Intelligence and Machine Learning
- Testing
- Scientific computing
- DevOps and tooling

### Example

```python
print("Hello, Python!")
```

### Output

```text
Hello, Python!
```

Here, `print()` is a Python built-in function that writes the supplied value to standard output.

### 🧠 Quick Recall

```text
Python
  ↓
High-Level
  ↓
General-Purpose
  ↓
Readable Syntax
  ↓
Many Application Domains
```

---

# 🚀 02. Why Learn Python?

Python is popular because its syntax is relatively readable and its ecosystem is extremely large.

### Major strengths

- **Readable syntax** → code is comparatively easy to understand.
- **Large ecosystem** → many libraries and frameworks are available.
- **Rapid development** → many tasks require relatively little code.
- **Automation** → repetitive tasks can be automated.
- **AI/ML** → Python has a very strong machine-learning ecosystem.
- **Data Engineering** → Python is widely used for data processing and pipelines.
- **Backend Development** → frameworks such as Django and FastAPI support server-side applications.
- **Testing** → Python has mature testing tools.
- **Community** → extensive documentation, packages, tutorials, and community support.

### Example

```python
name = "Biggan"
age = 23

print(f"My name is {name} and I am {age} years old.")
```

The example shows how Python can store information in variables and produce readable output using an f-string.

---

# 🐍 03. Python Installation & Environment

Before writing Python programs, you need a Python implementation installed on your machine.

Check the installed version:

```bash
python --version
```

On systems where `python3` is used:

```bash
python3 --version
```

On Windows, you can also use:

```powershell
py --version
```

Example:

```text
Python 3.x.x
```

### Why check the version?

Python has multiple versions, and projects may depend on particular language features or package versions. Knowing exactly which interpreter you are using is an important debugging habit.

### 💡 Tip

If Python works in one terminal but not another, check which Python executable and version each terminal is actually using.

---

# ⚙️ 04. Python Interpreter

The **Python interpreter/runtime** is the software environment responsible for processing and executing Python programs.

For a beginner, think of it like this:

```text
Your Python Code
       ↓
Python Interpreter / Runtime
       ↓
Program Execution
       ↓
Output / Result
```

Example:

```python
print("Hello")
```

Python processes this instruction and sends the text to standard output.

### 🔬 A little deeper

The exact execution process depends on the Python implementation. In the commonly used **CPython** implementation, Python source code is compiled into bytecode and then executed by the Python runtime.

You do not need to memorize the internal details yet. The important foundation is understanding that the `.py` source code must be processed by a Python implementation before the program can execute.

---

# 🧠 05. Python Execution Model

A Python source file normally uses the `.py` extension.

Example:

```text
hello.py
```

Run it:

```bash
python hello.py
```

A simplified CPython execution pipeline is:

```text
Python Source Code
        ↓
Tokenization / Parsing
        ↓
Compilation
        ↓
Bytecode
        ↓
Python Runtime
        ↓
Execution
        ↓
Output
```

### What is bytecode?

Bytecode is an intermediate representation of Python instructions. It is not the same as native CPU machine code.

The runtime executes this intermediate representation.

### 💡 Tip

At foundation level, remember:

```text
.py file
   ↓
Python implementation
   ↓
Execution
   ↓
Result
```

The internal details become more important later when studying Python internals.

---

# ✍️ 06. Python Syntax

**Syntax means the rules that determine how valid Python code must be written.**

Just like a natural language has grammar rules, Python has syntax rules.

If Python cannot parse your code according to those rules, it raises a syntax-related error.

### Example

```python
name = "Biggan"

print(name)
```

Here:

```text
name
 ↓
Identifier / Variable Name

"Biggan"
 ↓
String Value

print(name)
 ↓
Function Call
```

### Incorrect Example

```python
# if True
#     print("Hello")
```

The `if` statement needs a colon and a properly indented body.

Correct:

```python
if True:
    print("Hello")
```

### 🧠 Remember

```text
Syntax = Rules for writing valid Python code
```

---

# 📐 07. Indentation

**Indentation means the whitespace placed at the beginning of a line.**

In Python, indentation is not only a visual formatting choice. It is part of Python's syntax and is used to define the structure of code blocks.

For example:

```python
age = 23

if age >= 18:
    print("Adult")
    print("Age requirement satisfied")
```

Both `print()` statements belong to the `if` block because they are indented to the same level.

### Visual structure

```text
if condition:
│
├── indented statement
└── indented statement
```

### ❌ Incorrect

```python
age = 23

if age >= 18:
print("Adult")
```

Python cannot understand the intended block correctly.

### ✅ Correct

```python
age = 23

if age >= 18:
    print("Adult")
```

### Why does Python use indentation?

Many programming languages use braces such as `{}` to define blocks.

Python instead uses indentation. This forces the visual structure of the code to match its logical structure.

```text
Other languages:

if (condition) {
    statement;
}


Python:

if condition:
    statement
```

### Recommended style

Use **4 spaces** for one indentation level.

```python
if condition:
    statement
```

### 💡 Tip

Configure your editor so that pressing Tab inserts spaces consistently. Avoid randomly mixing tabs and spaces.

---

# 💬 08. Comments & Docstrings

A **comment** is text written for programmers rather than for normal program execution.

A normal single-line comment begins with `#`.

```python
# Store the student's age
age = 23
```

Python ignores the comment as executable code.

## Inline Comment

```python
age = 23  # Student age
```

## Docstring

A **docstring** is documentation written inside a module, function, class, or method.

```python
def greet():
    """Return a greeting message."""
    return "Hello"
```

A function's docstring can be inspected:

```python
print(greet.__doc__)
```

### Why are comments useful?

Good comments explain things that are not obvious from the code itself.

Less useful:

```python
age = 23  # Set age to 23
```

More useful:

```python
# API returns age as text, so convert it before numeric comparison.
age = int(age)
```

### 💡 Tip

Prefer clear variable/function names first. Use comments to explain **why**, assumptions, or non-obvious decisions.

---

# 🧱 09. Statements

A **statement** is an instruction that forms part of a Python program.

Example:

```python
name = "Biggan"
age = 23

print(name)
print(age)
```

Examples of statements include:

```text
Assignment
if statement
for statement
while statement
function definition
class definition
import statement
return statement
```

Statements are the building blocks that tell the program what to do.

---

# 🧮 10. Expressions

An **expression** is code that Python can evaluate to produce a value.

Example:

```python
10 + 20
```

Result:

```text
30
```

Another example:

```python
age = 23

result = age + 10
```

Here:

```python
age + 10
```

is an expression that produces the value `33`.

### Mental Model

```text
Expression
    ↓
Python evaluates it
    ↓
A value is produced
```

This concept becomes extremely important later with conditions, functions, comprehensions, and advanced Python.

---

# 📦 11. Variables & Assignment

A Python variable is best understood as a **name bound to an object**.

For beginners, think of a variable as a name that lets you refer to a value.

```python
name = "Biggan"
age = 23
height = 5.8
```

Conceptually:

```text
name ───────► "Biggan"

age ────────► 23

height ─────► 5.8
```

Python does not require a separate variable declaration such as:

```text
int age;
```

Instead:

```python
age = 23
```

creates or updates a binding between the name `age` and an object.

### Important idea

The name itself does not permanently have a type. The object has a type.

---

# 🔄 12. Variable Reassignment

A variable can later be bound to another object.

```python
age = 23

print(age)

age = 24

print(age)
```

Output:

```text
23
24
```

Conceptually:

```text
First:
age ───► 23

Later:
age ───► 24
```

The name `age` now refers to the new object.

### 🧠 Remember

```text
Variable Name
      ↓
Object Reference

Reassignment
      ↓
Same name
      ↓
Different object
```

---

# 🧠 13. Dynamic Typing

Python is a **dynamically typed language**.

This means type information is associated with runtime objects, and a name can be rebound to objects of different types during execution.

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

The name `value` first refers to an integer object and later refers to a string object.

### Visual model

```text
value ───► 100
           int


value ───► "Python"
           str
```

### Does dynamic typing mean Python has no types?

**No.**

Python has a strong object/type system. The important difference is that you generally do not have to declare the type of a variable before assigning a value.

### Example comparison

Python:

```python
value = 10
value = "Python"
```

The name can be rebound.

### 💡 Tip

Dynamic typing is convenient, but it also means you must understand the types of the objects flowing through your program.

---

# 🔍 14. `type()`

The built-in `type()` function helps you inspect the type of an object.

```python
name = "Biggan"
age = 23
height = 5.8

print(type(name))
print(type(age))
print(type(height))
```

Output:

```text
<class 'str'>
<class 'int'>
<class 'float'>
```

### Why is `type()` useful?

It is extremely useful while learning and debugging because it allows you to verify what kind of object you are working with.

Example:

```python
age = input("Enter age: ")

print(type(age))
```

You may expect a number, but `input()` gives you a string.

---

# 🧪 15. Built-in Data Types

Python provides many built-in data types.

Important types include:

```text
str
int
float
complex
bool
NoneType

list
tuple
set
dict

range

bytes
bytearray
frozenset
```

At foundation level, first understand the basic scalar types:

```text
str
int
float
complex
bool
NoneType
```

Collections such as `list`, `tuple`, `set`, and `dict` will be covered deeply in the Data Structures chapter.

---

# 🔤 16. String — `str`

A string represents text.

```python
name = "Biggan"

print(name)
print(type(name))
```

Output:

```text
Biggan
<class 'str'>
```

Python supports different quoting styles:

```python
single = 'Python'
double = "Python"
multi_line = """Python
is
awesome"""
```

### Important property

Strings are **immutable**.

That means an existing string object cannot be changed in place. String operations create new string objects.

Example:

```python
name = "Python"

name = name + " Engineering"

print(name)
```

The original string is not modified in place; the name is rebound to a new string.

Detailed string operations will be covered in `02_CORE_PYTHON`.

---

# 🔢 17. Integer — `int`

`int` represents whole numbers.

```python
age = 23

print(age)
print(type(age))
```

Output:

```text
23
<class 'int'>
```

Python integers can represent arbitrarily large integers, limited mainly by available memory.

Example:

```python
large_number = 123456789012345678901234567890

print(large_number)
```

---

# 🔢 18. Float — `float`

`float` represents floating-point numbers.

```python
price = 99.99

print(price)
print(type(price))
```

Output:

```text
99.99
<class 'float'>
```

### ⚠️ Important

Floating-point numbers use binary floating-point representation, so some decimal values cannot be represented exactly.

Example:

```python
result = 0.1 + 0.2

print(result)
```

You may get:

```text
0.30000000000000004
```

This is a consequence of floating-point representation, not a Python arithmetic bug.

For financial calculations requiring exact decimal behaviour, later learn about the `decimal` module.

---

# 🧮 19. Complex — `complex`

Python supports complex numbers using `j` for the imaginary component.

```python
number = 2 + 3j

print(number)
print(number.real)
print(number.imag)
print(type(number))
```

Output:

```text
(2+3j)
2.0
3.0
<class 'complex'>
```

Conceptually:

```text
2 + 3j
│   │
│   └── Imaginary part
└────── Real part
```

Complex numbers are useful in mathematical, scientific, and engineering applications.

---

# 🟢 20. Boolean — `bool`

Boolean values represent logical truth values:

```python
True
False
```

Example:

```python
is_logged_in = True

print(is_logged_in)
print(type(is_logged_in))
```

Output:

```text
True
<class 'bool'>
```

Boolean values are often produced by comparisons.

```python
age = 23

is_adult = age >= 18

print(is_adult)
```

Output:

```text
True
```

Later, these Boolean results become the foundation of conditional statements.

---

# ⚪ 21. None — `NoneType`

`None` is a special singleton object commonly used to represent **absence of a meaningful value**.

```python
result = None

print(result)
print(type(result))
```

Output:

```text
None
<class 'NoneType'>
```

A function that does not explicitly return a value returns `None`.

```python
def log_message():
    print("Message logged")


result = log_message()

print(result)
```

Output:

```text
Message logged
None
```

### Correct comparison

Prefer:

```python
if result is None:
    print("No result")
```

over:

```python
if result == None:
    print("No result")
```

### 🧠 Remember

```text
None
 ↓
Absence of a meaningful value
```

It is not the same thing as:

```text
0
""
False
```

---

# 📋 22. Basic Data Type Table

| Type | Example | Meaning |
|---|---|---|
| `str` | `"Python"` | Text |
| `int` | `23` | Integer |
| `float` | `23.5` | Floating-point number |
| `complex` | `2 + 3j` | Complex number |
| `bool` | `True` | Boolean value |
| `NoneType` | `None` | Absence of meaningful value |

---

# 🔄 23. Type Conversion

**Type conversion** means creating a value of another type from an existing value when that conversion is valid.

Common conversion functions:

```text
int()
float()
str()
bool()
complex()
```

## String → Integer

```python
age = "23"

age = int(age)

print(age)
print(type(age))
```

Output:

```text
23
<class 'int'>
```

## Integer → Float

```python
number = 10

number = float(number)

print(number)
```

Output:

```text
10.0
```

## Number → String

```python
age = 23

message = "Age: " + str(age)

print(message)
```

## String → Float

```python
price = "99.99"

price = float(price)

print(price)
```

## Invalid Conversion

```python
# int("Python")
```

This raises:

```text
ValueError
```

### Mental Model

```text
Original Value
      ↓
Conversion Function
      ↓
New Value / Object
```

### 💡 Tip

Never assume every value can be converted to every type. The actual content must be valid for the target type.

---

# ⌨️ 24. User Input

The `input()` function reads a line of text from standard input and returns it as a string.

```python
name = input("Enter your name: ")

print("Hello", name)
```

If the user enters:

```text
Biggan
```

then `name` contains:

```python
"Biggan"
```

### Why is `input()` important?

It allows a program to receive information from the person running it instead of using only hard-coded values.

---

# ⚠️ 25. `input()` Returns a String

This is one of the most important beginner concepts.

Suppose the user enters:

```text
23
```

You might visually see a number, but `input()` returns:

```python
"23"
```

which is a string.

Example:

```python
age = input("Enter your age: ")

print(type(age))
```

Output:

```text
<class 'str'>
```

### Integer Input

```python
age = int(input("Enter your age: "))

print(age)
print(type(age))
```

### Float Input

```python
price = float(input("Enter price: "))

print(price)
print(type(price))
```

### Mental Model

```text
Keyboard
   ↓
input()
   ↓
String
   ↓
Convert if necessary
   ↓
int / float / etc.
```

---

# 🖨️ 26. `print()`

`print()` writes one or more values to standard output.

Basic examples:

```python
print("Hello")
print(100)
print(True)
```

## Multiple Values

```python
name = "Biggan"
age = 23

print(name, age)
```

Output:

```text
Biggan 23
```

By default, multiple arguments are separated by a space.

## `sep`

You can change the separator:

```python
print("Python", "Java", "C++", sep=" | ")
```

Output:

```text
Python | Java | C++
```

## `end`

By default, `print()` ends with a newline.

```python
print("Hello")
print("Python")
```

Output:

```text
Hello
Python
```

You can change the ending:

```python
print("Hello", end=" ")
print("Python")
```

Output:

```text
Hello Python
```

### 💡 Tip

`print()` is excellent for learning and simple debugging. For larger applications, structured logging is usually preferable for diagnostic messages.

---

# 🔤 27. f-Strings

An **f-string** is a formatted string literal that allows expressions to be embedded directly inside `{}`.

### Syntax

```python
f"Text {expression}"
```

### Example

```python
name = "Biggan"
age = 23

print(f"My name is {name} and I am {age} years old.")
```

Output:

```text
My name is Biggan and I am 23 years old.
```

## Expression Inside f-String

```python
a = 10
b = 20

print(f"Sum = {a + b}")
```

Output:

```text
Sum = 30
```

## Number Formatting

```python
price = 99.98765

print(f"{price:.2f}")
```

Output:

```text
99.99
```

### Why use f-strings?

They make dynamic strings easier to read than manually concatenating many pieces.

---

# ➕ 28. Assignment Operators

The basic assignment operator is:

```python
=
```

Example:

```python
x = 10
```

Python also supports compound assignment operators:

```text
+=
-=
*=
/=
//=
%=
**=
```

Example:

```python
x = 10

x += 5
print(x)

x -= 2
print(x)

x *= 2
print(x)
```

The statement:

```python
x += 5
```

is conceptually similar to:

```python
x = x + 5
```

for ordinary numeric examples.

---

# ⚖️ 29. Comparison Operators

Comparison operators compare values and produce a Boolean result.

| Operator | Meaning |
|---|---|
| `==` | Equal |
| `!=` | Not Equal |
| `>` | Greater Than |
| `<` | Less Than |
| `>=` | Greater Than or Equal |
| `<=` | Less Than or Equal |

Example:

```python
a = 10
b = 20

print(a == b)
print(a != b)
print(a < b)
print(a > b)
print(a <= b)
print(a >= b)
```

### Real-world example

```python
age = 23

is_adult = age >= 18

print(is_adult)
```

Output:

```text
True
```

The Boolean result can then be used by an `if` statement.

---

# 🧠 30. Logical Operators

Logical operators combine or modify conditions.

Python provides:

```text
and
or
not
```

## `and`

Both operands must be truthy for the overall result to be truthy.

```python
age = 23
has_id = True

print(age >= 18 and has_id)
```

## `or`

The result is truthy when at least one operand is truthy.

```python
is_admin = False
is_owner = True

print(is_admin or is_owner)
```

## `not`

`not` reverses the truth value.

```python
has_id = True

print(not has_id)
```

### Mental Model

```text
A and B
   ↓
Both conditions matter

A or B
   ↓
At least one can be true

not A
   ↓
Reverse the truth value
```

### Important

`and` and `or` use **short-circuit evaluation** and return one of their operands, not necessarily a Boolean object.

Example:

```python
result = "" or "Python"

print(result)
```

Output:

```text
Python
```

This behaviour becomes very useful later.

---

# 🔍 31. Membership Operators

Membership operators check whether a value is contained inside another object.

Python provides:

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

For strings, membership checks whether a character or substring occurs inside the string.

Later, membership will also be important with lists, sets, dictionaries, and other containers.

---

# 🆔 32. Identity Operators

Identity operators test whether two references point to the **same object**.

Python provides:

```text
is
is not
```

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

### Why?

The values are equal:

```text
[1, 2, 3] == [1, 2, 3]
```

But the two list objects are separate objects:

```text
a ─────► [1, 2, 3]

b ─────► [1, 2, 3]
```

### Critical Difference

```text
==
 ↓
Do the objects compare equal?

is
 ↓
Are these references pointing to the same object?
```

### 💡 Tip

Use `is` primarily for identity checks, especially:

```python
value is None
```

Do not use `is` as a general replacement for `==`.

---

# 📊 33. Operator Categories

Python operators can be grouped by the type of operation they perform.

```text
Python Operators
│
├── Arithmetic
│   ├── +
│   ├── -
│   ├── *
│   ├── /
│   ├── //
│   ├── %
│   └── **
│
├── Assignment
│   ├── =
│   ├── +=
│   ├── -=
│   ├── *=
│   └── ...
│
├── Comparison
│   ├── ==
│   ├── !=
│   ├── >
│   ├── <
│   ├── >=
│   └── <=
│
├── Logical
│   ├── and
│   ├── or
│   └── not
│
├── Membership
│   ├── in
│   └── not in
│
└── Identity
    ├── is
    └── is not
```

Understanding these categories makes Python expressions much easier to read.

---

# 📐 34. Operator Precedence

When an expression contains multiple operators, Python needs a rule for deciding **which operation should be evaluated first**.

That rule is called **operator precedence**.

Consider:

```python
result = 10 + 2 * 3
```

A beginner might read it from left to right:

```text
10 + 2 = 12
12 * 3 = 36
```

But Python does not evaluate it that way.

Multiplication has higher precedence than addition:

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

### Common Precedence Order

A simplified order from higher to lower precedence is:

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

### Parentheses Override Normal Precedence

If you want addition to happen first:

```python
result = (10 + 2) * 3

print(result)
```

Output:

```text
36
```

Python first evaluates:

```text
10 + 2
   ↓
  12
```

Then:

```text
12 * 3
   ↓
  36
```

### Why is precedence necessary?

Without precedence rules, expressions containing multiple operators would be ambiguous.

For example:

```python
10 + 2 * 3
```

must have one deterministic interpretation.

### 💡 Best Practice

You do not need to memorize every precedence rule immediately.

When an expression becomes difficult to read, use parentheses to make the intended order explicit:

```python
total = (price * quantity) + shipping
```

Readable code is more important than showing off operator knowledge.

---

# 🔑 35. Python Keywords

Keywords are reserved words that have special meaning in Python's grammar.

Examples include:

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

You cannot normally use a keyword as a variable name.

Incorrect:

```python
# class = "Python"
```

Check the keywords supported by your installed Python version:

```python
import keyword

print(keyword.kwlist)
```

### 💡 Tip

The keyword list can change between Python versions. `keyword.kwlist` checks the actual interpreter you are running.

---

# 🧰 36. Built-in Functions

Python provides many functions that are available without importing a module first.

Important examples:

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

### 💡 Tip

Do not try to memorize every built-in function at once. Understand the most common ones and learn others naturally through practice.

---

# 🆔 37. `id()`

`id()` returns an integer that identifies an object for the duration of that object's lifetime.

```python
name = "Python"

print(id(name))
```

The exact number is runtime-dependent, so you should not expect the same number every time you run the program.

### Remember

```text
==  → Equality
is  → Identity
id() → Identity-related integer
```

---

# 📦 38. Multiple Assignment

Python allows multiple names to be assigned in one statement.

```python
a, b, c = 10, 20, 30

print(a)
print(b)
print(c)
```

Output:

```text
10
20
30
```

This is useful when several related values are available together.

---

# 🔄 39. Variable Swapping

Python allows variables to exchange their references without requiring a temporary variable.

```python
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```

Output:

```text
20
10
```

Conceptually:

```text
Before:
a → 10
b → 20

After:
a → 20
b → 10
```

This works because Python supports multiple assignment and unpacking.

---

# 📦 40. Unpacking

Unpacking means assigning values from an iterable to multiple names.

```python
numbers = [10, 20, 30]

a, b, c = numbers

print(a)
print(b)
print(c)
```

Output:

```text
10
20
30
```

Python expects the number of values to match the number of target names unless extended unpacking is used.

---

# ⭐ 41. Starred Unpacking

The `*` operator can collect multiple remaining values into a list.

```python
numbers = [1, 2, 3, 4, 5]

first, *middle, last = numbers

print(first)
print(middle)
print(last)
```

Output:

```text
1
[2, 3, 4]
5
```

Conceptually:

```text
first  → 1
middle → [2, 3, 4]
last   → 5
```

This becomes especially useful when processing variable-length data.

---

# 🔗 42. Chained Comparison

Python allows several comparisons to be written as a chain.

```python
age = 23

print(18 <= age <= 60)
```

This is conceptually equivalent to:

```python
18 <= age and age <= 60
```

The chained form is often easier to read.

### Example

```python
score = 75

if 40 <= score <= 100:
    print("Valid passing-range score")
```

---

# 🧠 43. Truthiness

Python often needs to decide whether an object should be treated as **true or false in a Boolean context**.

For example:

```python
if "Python":
    print("This string is truthy")
```

A string containing text is truthy.

An empty string is falsy:

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

### Common falsy values

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

Most other ordinary objects are truthy unless their type defines different Boolean behaviour.

### Why is truthiness useful?

It allows concise checks:

```python
if users:
    print("Users are available")
```

instead of always writing:

```python
if len(users) > 0:
    print("Users are available")
```

---

# 🧱 44. Python Block Structure

A Python block is a group of statements that belong together structurally.

A colon `:` introduces a block/suite in constructs such as:

```text
if
for
while
def
class
try
with
```

Example:

```python
if condition:
    statement
    statement
```

Function:

```python
def greet():
    print("Hello")
```

Loop:

```python
for number in range(5):
    print(number)
```

### Mental Model

```text
Header
  ↓
:
  ↓
Indented Block
  ↓
Statements
```

This is why indentation is fundamental to Python syntax.

---

# 🔄 45. Basic Function Foundation

A **function** is a reusable unit of code designed to perform a task.

The complete function topic will be covered later, but you should understand the basic structure now.

```python
def greet(name):
    return f"Hello, {name}"


message = greet("Biggan")

print(message)
```

### What is happening?

```text
def
 ↓
Function Definition

greet
 ↓
Function Name

name
 ↓
Parameter

"Biggan"
 ↓
Argument

return
 ↓
Send result back

message
 ↓
Receives returned value
```

Functions help reduce duplication and organize programs into reusable pieces.

---

# 📦 46. Import Foundation

Python programs can use functionality from modules.

Example:

```python
import math

print(math.sqrt(25))
```

Output:

```text
5.0
```

You can also import a specific name:

```python
from math import sqrt

print(sqrt(25))
```

### What is a module?

A module is a Python file containing reusable code.

### Why use modules?

Large programs become easier to maintain when related functionality is separated into logical modules.

Modules and packages will be studied deeply in:

```text
06_MODULES_PACKAGES_FILES
```

---

# 🧪 47. Interactive Mode

Python can be used interactively from a terminal.

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

This is useful for:

- Quick experiments
- Testing syntax
- Checking small expressions
- Exploring library behaviour

Exit:

```python
exit()
```

---

# 📁 48. Script vs Interactive Mode

## Interactive Mode

```text
Command
   ↓
Immediate Evaluation
   ↓
Result
```

Useful for:

- Learning
- Quick experiments
- Small calculations
- Testing ideas

## Script Mode

```text
program.py
    ↓
python program.py
    ↓
Program Execution
```

Useful for:

- Reusable programs
- Automation
- Projects
- Applications
- Version control

### 🧠 Remember

```text
REPL   → Experiment
Script → Build
```

---

# 🧹 49. Python Coding Style

Readable code is easier to understand, debug, review, and maintain.

### Good

```python
student_name = "Biggan"
student_age = 23

if student_age >= 18:
    print("Adult")
```

### Poor

```python
x="Biggan"
y=23
if y>=18: print("Adult")
```

The second code may work, but the first communicates intent much more clearly.

### 💡 Tip

Professional Python development is not only about making code run. It is also about making the code understandable to the next person who reads it.

---

# 📏 50. PEP 8 Foundation

**PEP 8** is Python's widely used style guide.

Important ideas include:

```text
Readable Code
Consistent Naming
4-Space Indentation
Reasonable Line Length
Clear Imports
Consistent Whitespace
```

Example:

```python
def calculate_total(price, quantity):
    return price * quantity
```

### Why does style matter?

A consistent style reduces cognitive load. When every developer follows similar conventions, the reader can focus on the program's logic instead of constantly interpreting formatting choices.

---

# 🚨 51. Common Python Errors

Errors are not just failures. They are information about what Python detected while processing your program.

## `SyntaxError`

Python cannot parse the code according to its grammar.

```python
# if True
#     print("Hello")
```

Correct:

```python
if True:
    print("Hello")
```

---

## `IndentationError`

The indentation does not follow Python's block structure.

```python
if True:
# print("Hello")
```

Correct:

```python
if True:
    print("Hello")
```

---

## `NameError`

You try to use a name that has not been defined in the current scope.

```python
# print(username)
```

---

## `TypeError`

An operation or function call receives an inappropriate type.

```python
# "Age: " + 23
```

Correct:

```python
"Age: " + str(23)
```

---

## `ValueError`

The type is acceptable, but the specific value is not valid for the operation.

```python
# int("Python")
```

---

## `ZeroDivisionError`

A number is divided by zero.

```python
# print(10 / 0)
```

---

## `IndexError`

A sequence is accessed using an index that does not exist.

```python
numbers = [10, 20, 30]

# print(numbers[10])
```

---

## `KeyError`

A dictionary is accessed with a key that does not exist.

```python
data = {"name": "Biggan"}

# print(data["age"])
```

---

# 🧠 52. Debugging Basics

**Debugging** means systematically finding and fixing the cause of incorrect program behaviour.

When Python gives you a traceback, do not randomly change lines.

Use a structured process:

```text
Error
  ↓
Read Traceback
  ↓
Find File
  ↓
Find Line
  ↓
Identify Exception Type
  ↓
Understand Error Message
  ↓
Inspect Variables / Values
  ↓
Form a Hypothesis
  ↓
Make a Small Fix
  ↓
Run Again
  ↓
Verify
```

### Example

```python
age = "23"

# print(age + 10)
```

The problem is:

```text
str + int
```

If numeric addition is intended:

```python
age = int(age)

print(age + 10)
```

### 💡 Professional Tip

Do not blindly copy a solution from the internet. First understand:

```text
What happened?
Why did it happen?
Where did it happen?
What change fixes the cause?
```

---

# 🧪 53. `assert`

`assert` is useful for checking assumptions during development.

```python
age = 23

assert age >= 18
```

If the condition is false, Python raises `AssertionError`.

Example:

```python
age = 15

# assert age >= 18
```

### Important

`assert` is not a general replacement for user-input validation or security checks because assertions can be disabled when Python is run with optimization.

Use explicit validation when a condition must always be enforced.

---

# 📝 54. Python Naming Rules

A Python identifier generally:

- Can contain letters, digits, and underscores.
- Cannot start with a digit.
- Is case-sensitive.
- Cannot be a reserved keyword.

### Valid

```python
name = "Biggan"
student_age = 23
_private_value = 10
value2 = 20
```

### Invalid

```python
# 2value = 20
# student-age = 23
# class = "Python"
```

### Why naming rules exist

Python needs a predictable way to distinguish identifiers from numbers, operators, keywords, and other syntax elements.

---

# 📐 55. Naming Conventions

Python commonly follows these naming conventions:

| Item | Convention | Example |
|---|---|---|
| Variable | `snake_case` | `student_name` |
| Function | `snake_case` | `calculate_total()` |
| Class | `PascalCase` | `StudentProfile` |
| Constant | `UPPER_CASE` | `MAX_SIZE` |
| Internal name | `_leading_underscore` | `_value` |

### Why does naming matter?

A meaningful name communicates the purpose of a value.

Compare:

```python
x = 4500
```

with:

```python
monthly_salary = 4500
```

The second version tells the reader what `4500` represents without requiring them to inspect other code.

---

# 🔤 56. Case Sensitivity

Python is case-sensitive.

That means:

```python
name = "Biggan"
Name = "Rahim"
```

creates two different names.

```python
print(name)
print(Name)
```

Output:

```text
Biggan
Rahim
```

### 💡 Tip

Although this is legal, avoid creating names that differ only by capitalization because they are easy for humans to confuse.

---

# 🔬 57. Foundation Learning Experiment

Do not only read Python. Experiment with it.

Start:

```python
name = "Biggan"
age = 23

print(f"My name is {name}")
print(f"I am {age} years old.")
```

Now deliberately change the program:

```text
1. Change the name.
2. Change the age.
3. Add another variable.
4. Add an arithmetic expression.
5. Convert a string to an integer.
6. Intentionally create a TypeError.
7. Read the traceback.
8. Fix the error.
9. Run the program again.
```

### Learning Cycle

```text
Understand
    ↓
Write Code
    ↓
Run Code
    ↓
Experiment
    ↓
Break Code
    ↓
Read Error
    ↓
Debug
    ↓
Understand
    ↓
Practice
```

---

# 🎯 58. Complete Foundation Example

This small program combines several foundation concepts.

```python
# Get user information
name = input("Enter your name: ")
age = int(input("Enter your age: "))
marks = float(input("Enter your marks: "))

# Calculate Boolean conditions
is_adult = age >= 18
is_passed = marks >= 40

# Display the result
print("\n--- Student Information ---")

print(f"Name: {name}")
print(f"Age: {age}")
print(f"Marks: {marks}")
print(f"Adult: {is_adult}")
print(f"Passed: {is_passed}")
```

### Step-by-step flow

```text
User enters name
      ↓
input() returns str
      ↓
User enters age
      ↓
int() converts str → int
      ↓
User enters marks
      ↓
float() converts str → float
      ↓
Comparisons produce Boolean values
      ↓
f-string formats the output
      ↓
print() displays the result
```

This connects:

```text
input()
variables
type conversion
comparison
Boolean
f-string
print()
comments
```

---

# 🎤 59. Interview Foundation Questions

## Q1. What is Python?

Python is a high-level, general-purpose programming language with readable syntax and a large ecosystem.

## Q2. Is Python dynamically typed?

Yes. Python is dynamically typed; names can be rebound to objects of different types during execution.

## Q3. What is a variable?

A variable is a name bound to an object.

## Q4. What does `type()` do?

It returns the type of an object.

## Q5. What does `input()` return?

`input()` reads a line and returns it as a string.

## Q6. Difference between `=` and `==`?

```text
=  → Assignment
== → Equality comparison
```

## Q7. Difference between `==` and `is`?

```text
== → Equality / value comparison
is → Object identity comparison
```

## Q8. What is `None`?

`None` is a special singleton object commonly used to represent the absence of a meaningful value.

## Q9. What is indentation?

Indentation is the leading whitespace used by Python to define the structure of code blocks.

## Q10. What is dynamic typing?

It means type information is associated with runtime objects and a name can be rebound to objects of different types.

---

# 📊 60. Foundation Quick Reference

| Concept | Quick Recall |
|---|---|
| Python | High-level, general-purpose language |
| Interpreter / Runtime | Processes and executes Python code |
| Syntax | Rules for valid Python code |
| Indentation | Defines code block structure |
| Comment | Programmer-facing explanation |
| Docstring | Documentation attached to code objects |
| Variable | Name bound to an object |
| Dynamic Typing | Names can reference different object types |
| `type()` | Inspect object type |
| `id()` | Object identity-related integer |
| `input()` | Reads a line and returns `str` |
| `print()` | Writes values to standard output |
| `str` | Text |
| `int` | Integer |
| `float` | Floating-point number |
| `complex` | Complex number |
| `bool` | `True` / `False` |
| `None` | Absence of meaningful value |
| `int()` | Integer conversion |
| `float()` | Float conversion |
| `str()` | String conversion |
| `bool()` | Boolean conversion |
| `=` | Assignment |
| `==` | Equality |
| `is` | Identity |
| `in` | Membership |
| `and` | Logical AND |
| `or` | Logical OR |
| `not` | Logical negation |
| `f""` | Formatted string literal |
| `range()` | Creates a range object |
| `import` | Imports module functionality |

---

# 🧠 61. One-Minute Revision

```text
PYTHON FOUNDATION
│
├── Python
│   ├── High-Level
│   ├── General-Purpose
│   └── Readable
│
├── Syntax
│   ├── Statements
│   ├── Expressions
│   └── Indentation
│
├── Variables
│   ├── Names
│   ├── Assignment
│   ├── Reassignment
│   └── Dynamic Typing
│
├── Data Types
│   ├── str
│   ├── int
│   ├── float
│   ├── complex
│   ├── bool
│   └── NoneType
│
├── Type Conversion
│   ├── int()
│   ├── float()
│   ├── str()
│   ├── bool()
│   └── complex()
│
├── Input / Output
│   ├── input()
│   └── print()
│
├── Operators
│   ├── Arithmetic
│   ├── Assignment
│   ├── Comparison
│   ├── Logical
│   ├── Membership
│   └── Identity
│
├── Formatting
│   └── f-string
│
├── Language
│   ├── Keywords
│   └── Built-in Functions
│
└── Debugging
    ├── Traceback
    ├── Error Type
    ├── Error Location
    └── Fix & Test
```

---

# 🧪 62. Foundation Practice Checklist

```text
☑ Hello World
☑ Python Installation
☑ Python Interpreter
☑ Python Execution Model
☑ Syntax
☑ Indentation
☑ Comments
☑ Docstrings
☑ Statements
☑ Expressions

☑ Variables
☑ Assignment
☑ Reassignment
☑ Multiple Assignment
☑ Variable Swapping
☑ Unpacking
☑ Starred Unpacking

☑ String
☑ Integer
☑ Float
☑ Complex
☑ Boolean
☑ None

☑ type()
☑ id()
☑ int()
☑ float()
☑ str()
☑ bool()

☑ input()
☑ print()
☑ sep
☑ end
☑ f-string

☑ Arithmetic Operators
☑ Assignment Operators
☑ Comparison Operators
☑ Logical Operators
☑ Membership Operators
☑ Identity Operators
☑ Operator Precedence

☑ Truthiness
☑ Keywords
☑ Naming Rules
☑ Naming Conventions
☑ Case Sensitivity
☑ Basic Import
☑ Basic Function Structure

☑ SyntaxError
☑ IndentationError
☑ NameError
☑ TypeError
☑ ValueError
☑ ZeroDivisionError
☑ IndexError
☑ KeyError

☑ Traceback Reading
☑ Basic Debugging
☑ assert
☑ PEP 8 Foundation
```

---

# 🚀 63. Foundation Completion

If you can comfortably understand this flow:

```text
Input
  ↓
Variable
  ↓
Object / Value
  ↓
Type
  ↓
Conversion
  ↓
Expression
  ↓
Operator
  ↓
Condition
  ↓
Function
  ↓
Output
  ↓
Error
  ↓
Debug
```

then your Python Foundation is ready for the next level.

The goal is not to memorize every line. The goal is to understand the relationships between these concepts.

---

# 📚 Next Chapter

```text
01. Python Foundation
          │
          ▼
02. Core Python
          │
          ▼
03. Data Structures
          │
          ▼
04. Functions
          │
          ▼
05. OOP
```

**Next → `02_CORE_PYTHON/02_Core_Python.md`**

---

# 🎯 Final Foundation Rule

> **Don't just memorize Python. Understand the behaviour, write the code, run it, break it, read the error, fix it, and repeat.**

```text
Understand
    ↓
Code
    ↓
Run
    ↓
Experiment
    ↓
Break
    ↓
Debug
    ↓
Understand Internals
    ↓
Practice
    ↓
Build
    ↓
Revise
```

# 🐍 Python Foundation — Completed
