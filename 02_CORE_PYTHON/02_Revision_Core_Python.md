# 🐍 Python Engineering --- 02. Core Python --- Revision

> **Purpose:** This file is the fast-revision companion to
> `02_Core_Python.md`.
>
> Use this file when you already understand Python and want to refresh
> the complete Core Python chapter quickly.
>
> The explanations are intentionally short, but every major concept
> includes the key behaviour, syntax, and a small example.

------------------------------------------------------------------------

# 📚 Core Python at a Glance

``` text
02. Core Python
│
├── Strings
│   ├── Creation
│   ├── Escape Sequences
│   ├── Raw Strings
│   ├── Indexing
│   ├── Negative Indexing
│   ├── Slicing
│   ├── Immutability
│   ├── Methods
│   ├── split() / join()
│   └── Formatting
│
├── Numbers
│   ├── int
│   ├── float
│   ├── complex
│   ├── Arithmetic Operators
│   ├── /
│   ├── //
│   ├── %
│   └── **
│
├── Boolean & Truthiness
│   ├── True / False
│   ├── bool()
│   ├── Comparisons
│   ├── and
│   ├── or
│   ├── not
│   └── Short-Circuiting
│
├── None
│   ├── None
│   └── is None
│
├── Conditions
│   ├── if
│   ├── elif
│   ├── else
│   ├── Nested Conditions
│   └── Conditional Expression
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
│   └── range(start, stop, step)
│
└── match / case
    ├── Literal Patterns
    ├── Multiple Patterns
    ├── Wildcard
    ├── Guards
    └── Structural Matching
```

------------------------------------------------------------------------

# 🔤 01. Strings

A **string** is an immutable sequence of Unicode characters used to
represent text.

``` python
name = "Python"

print(name)
print(type(name))
```

### Remember

``` text
str
 ↓
Text
 ↓
Ordered sequence of characters
 ↓
Immutable
```

------------------------------------------------------------------------

# ✍️ 02. Creating Strings

Python supports single, double, and triple-quoted strings.

``` python
a = 'Python'
b = "Python"
c = """Python"""
```

Multiline string:

``` python
message = """Python
is
powerful"""
```

### Quick Recall

``` text
'text'     → single quotes
"text"     → double quotes
"""text""" → multiline string
```

------------------------------------------------------------------------

# 🔐 03. Escape Sequences

Escape sequences represent special characters inside strings.

``` python
print("Hello\nPython")
print("Name:\tBiggan")
```

Common escapes:

``` text
\n → new line
\t → tab
\\ → backslash
\' → single quote
\" → double quote
```

------------------------------------------------------------------------

# 🛣️ 04. Raw Strings

Prefix a string with `r` when backslashes should generally be treated
literally.

``` python
path = r"C:\Users\Biggan\Projects"

print(path)
```

Useful for Windows paths and regular expressions.

------------------------------------------------------------------------

# 🔢 05. String Indexing

Strings are zero-indexed sequences.

``` python
text = "Python"

print(text[0])   # P
print(text[2])   # t
print(text[-1])  # n
```

Structure:

``` text
 P   y   t   h   o   n
 0   1   2   3   4   5
```

### Remember

``` text
First character → index 0
Last character  → index len(text) - 1
```

------------------------------------------------------------------------

# 🔙 06. Negative Indexing

Negative indexes count from the end.

``` text
 P    y    t    h    o    n
-6   -5   -4   -3   -2   -1
```

``` python
text = "Python"

print(text[-1])  # n
print(text[-2])  # o
```

------------------------------------------------------------------------

# ✂️ 07. String Slicing

Slicing extracts part of a sequence.

``` python
text = "Python"

print(text[0:3])   # Pyt
print(text[:3])    # Pyt
print(text[3:])    # hon
print(text[::2])   # Pto
print(text[::-1])  # nohtyP
```

Syntax:

``` python
sequence[start:stop:step]
```

### Critical Rule

``` text
start → included
stop  → excluded
```

------------------------------------------------------------------------

# 🧊 08. String Immutability

A string cannot be modified character-by-character after creation.

``` python
text = "Python"

# text[0] = "J"   # TypeError
```

Create a new string instead:

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
String → immutable
List   → mutable
```

------------------------------------------------------------------------

# ➕ 09. String Concatenation & Repetition

Concatenation joins strings:

``` python
first = "G."
last = "Biggan"

name = first + " " + last
```

Repetition duplicates a string:

``` python
print("Python " * 3)
```

Output:

``` text
Python Python Python
```

------------------------------------------------------------------------

# 🔍 10. String Membership

Use `in` and `not in` to test whether text exists inside another string.

``` python
text = "Python Engineering"

print("Python" in text)  # True
print("Java" in text)    # False
```

Membership is case-sensitive.

``` python
print("python" in "Python")  # False
```

------------------------------------------------------------------------

# 📏 11. `len()`

`len()` returns the number of characters.

``` python
text = "Python"

print(len(text))
```

Output:

``` text
6
```

Spaces also count as characters.

------------------------------------------------------------------------

# 🔠 12. Common String Methods

``` python
text = "python engineering"

print(text.upper())
print(text.lower())
print(text.title())
print(text.capitalize())
```

Quick recall:

``` text
upper()      → uppercase
lower()      → lowercase
title()      → Title Case
capitalize() → First character uppercase
```

------------------------------------------------------------------------

# 🔎 13. Searching Strings

``` python
text = "Python Programming"

print(text.find("Program"))
print(text.count("m"))
```

Important difference:

``` text
find()  → returns index or -1
index() → returns index or raises ValueError
```

------------------------------------------------------------------------

# 🧪 14. String Checking Methods

``` python
text = "Python123"

print(text.startswith("Python"))
print(text.endswith("123"))
print(text.isalpha())
print(text.isalnum())
```

Common methods:

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

------------------------------------------------------------------------

# 🧹 15. `strip()`

Remove leading/trailing whitespace:

``` python
text = "   Python   "

print(text.strip())
```

Output:

``` text
Python
```

Related:

``` text
strip()  → both sides
lstrip() → left side
rstrip() → right side
```

------------------------------------------------------------------------

# 🔄 16. `replace()`

Returns a new string with matching text replaced.

``` python
text = "I like Java"

new_text = text.replace("Java", "Python")

print(new_text)
```

Output:

``` text
I like Python
```

The original string is unchanged because strings are immutable.

------------------------------------------------------------------------

# ✂️ 17. `split()`

`split()` converts a string into a list of strings.

``` python
text = "Python is powerful"

words = text.split()

print(words)
```

Output:

``` text
['Python', 'is', 'powerful']
```

------------------------------------------------------------------------

# 🔗 18. `join()`

`join()` combines strings into one string.

``` python
words = ["Python", "is", "powerful"]

sentence = " ".join(words)

print(sentence)
```

Output:

``` text
Python is powerful
```

### Mental Model

``` text
split() → String → List
join()  → List/Iterable of strings → String
```

------------------------------------------------------------------------

# 🎨 19. f-Strings

f-strings allow expressions to be embedded directly inside strings.

``` python
name = "Biggan"
age = 23

print(f"My name is {name} and I am {age}.")
```

Expressions are allowed:

``` python
a = 10
b = 20

print(f"Sum = {a + b}")
```

Formatting:

``` python
price = 99.98765

print(f"{price:.2f}")
```

Output:

``` text
99.99
```

------------------------------------------------------------------------

# 🔢 20. Numbers

Python's main built-in numeric types:

``` text
int
float
complex
```

Examples:

``` python
a = 10
b = 10.5
c = 2 + 3j
```

------------------------------------------------------------------------

# ➕ 21. Arithmetic Operators

``` python
a = 10
b = 3

print(a + b)   # 13
print(a - b)   # 7
print(a * b)   # 30
print(a / b)   # 3.333...
print(a // b)  # 3
print(a % b)   # 1
print(a ** b)  # 1000
```

Quick recall:

``` text
+  → addition
-  → subtraction
*  → multiplication
/  → true division
// → floor division
%  → remainder
** → exponentiation
```

------------------------------------------------------------------------

# ➗ 22. `/` vs `//`

True division:

``` python
10 / 3
# 3.333333...
```

Floor division:

``` python
10 // 3
# 3
```

Important:

``` python
-10 // 3
# -4
```

Floor division moves toward negative infinity, not simply toward zero.

------------------------------------------------------------------------

# 🧮 23. Modulo `%`

Modulo returns the remainder.

``` python
10 % 3
# 1
```

Common use:

``` python
number = 10

if number % 2 == 0:
    print("Even")
```

### Pattern

``` text
number % 2 == 0 → even
number % 2 != 0 → odd
```

------------------------------------------------------------------------

# ⚡ 24. Exponentiation `**`

Use `**` for powers.

``` python
print(2 ** 3)
# 8

print(25 ** 0.5)
# 5.0
```

------------------------------------------------------------------------

# 🎯 25. Floating-Point Precision

Floating-point numbers are stored approximately.

``` python
print(0.1 + 0.2)
```

The result may be:

``` text
0.30000000000000004
```

This is a representation issue, not ordinary arithmetic failure.

For tolerant comparison:

``` python
a = 0.1 + 0.2
b = 0.3

print(abs(a - b) < 1e-9)
```

------------------------------------------------------------------------

# 🟢 26. Boolean Values

Python has exactly two Boolean objects:

``` python
True
False
```

Comparisons produce Boolean results.

``` python
age = 23

print(age >= 18)  # True
print(age == 23)  # True
print(age != 30)  # True
```

------------------------------------------------------------------------

# 🧠 27. Truthiness

Python evaluates objects as truthy or falsy in Boolean contexts.

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

------------------------------------------------------------------------

# 🧪 28. `bool()`

`bool()` returns the truth value of an object.

``` python
print(bool(1))       # True
print(bool(0))       # False
print(bool("Python"))# True
print(bool(""))      # False
print(bool([]))      # False
print(bool([1]))     # True
```

------------------------------------------------------------------------

# 🔗 29. `and`

`and` evaluates from left to right and short-circuits when the result is
known.

``` python
age = 23
has_id = True

print(age >= 18 and has_id)
```

Important:

``` python
result = "Python" and "Engineering"

print(result)
```

Output:

``` text
Engineering
```

`and` returns operands, not necessarily `True` or `False`.

------------------------------------------------------------------------

# 🔗 30. `or`

`or` returns the first truthy operand.

``` python
name = ""

result = name or "Unknown"

print(result)
```

Output:

``` text
Unknown
```

Common pattern:

``` python
display_name = user_name or "Anonymous"
```

------------------------------------------------------------------------

# 🔄 31. `not`

`not` reverses Boolean truth.

``` python
is_logged_in = False

print(not is_logged_in)
```

Output:

``` text
True
```

------------------------------------------------------------------------

# ⚡ 32. Short-Circuit Evaluation

Python may stop evaluating `and` / `or` before reaching every operand.

``` python
user = None

if user and user.is_active:
    print("Active")
```

Because `user` is falsy, Python does not need to evaluate:

``` python
user.is_active
```

This is useful for safe conditional access and efficient logic.

------------------------------------------------------------------------

# ⚪ 33. `None`

`None` represents the absence of a meaningful value.

``` python
result = None

print(type(result))
```

Output:

``` text
<class 'NoneType'>
```

Use identity checks:

``` python
if result is None:
    print("No result")
```

Preferred:

``` text
is None
is not None
```

------------------------------------------------------------------------

# 🆚 34. `None` vs `False` vs `0` vs `""`

All can be falsy, but their meanings differ.

``` text
None  → no meaningful value
False → logical false
0     → numeric zero
""    → empty string
```

Do not confuse truthiness with semantic meaning.

------------------------------------------------------------------------

# 🧭 35. `if`

`if` executes a block when its condition is truthy.

``` python
age = 23

if age >= 18:
    print("Adult")
```

Structure:

``` text
if condition:
    indented block
```

------------------------------------------------------------------------

# 🔀 36. `if ... else`

``` python
age = 16

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

`else` handles the alternative path when the `if` condition is falsy.

------------------------------------------------------------------------

# 🔀 37. `if ... elif ... else`

Use `elif` for multiple mutually exclusive branches.

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
```

Python checks from top to bottom and executes the first matching branch.

------------------------------------------------------------------------

# 🪆 38. Nested Conditions

A condition can contain another condition.

``` python
age = 23
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
```

Often this can be simplified:

``` python
if age >= 18 and has_id:
    print("Entry allowed")
```

------------------------------------------------------------------------

# 🎯 39. Conditional Expression

One-line conditional expression:

``` python
status = "Adult" if age >= 18 else "Minor"
```

Structure:

``` python
true_value if condition else false_value
```

Use it only when the expression remains readable.

------------------------------------------------------------------------

# 🔁 40. `for` Loop

A `for` loop iterates over an iterable.

``` python
for character in "Python":
    print(character)
```

The loop receives one item at a time.

``` text
Iterable
   ↓
Next item
   ↓
Execute body
   ↓
Next item
   ↓
Stop when exhausted
```

------------------------------------------------------------------------

# 🔄 41. `while` Loop

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

### Critical Rule

A `while` loop usually needs state that eventually makes the condition
false.

------------------------------------------------------------------------

# 🪆 42. Nested Loops

One loop can contain another.

``` python
for i in range(3):
    for j in range(2):
        print(i, j)
```

The inner loop completes for every outer-loop iteration.

------------------------------------------------------------------------

# 🛑 43. `break`

`break` immediately exits the nearest loop.

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

# ⏭️ 44. `continue`

`continue` skips the rest of the current iteration.

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

# 💤 45. `pass`

`pass` performs no operation.

``` python
def future_feature():
    pass
```

Use it as a placeholder when Python requires a statement.

``` text
break    → exit loop
continue → next iteration
pass     → do nothing
```

------------------------------------------------------------------------

# 🔄 46. Loop `else`

A loop's `else` runs when the loop finishes normally without `break`.

``` python
for number in range(5):
    print(number)
else:
    print("Completed")
```

If `break` executes, the loop `else` does not run.

This is especially useful for search operations.

------------------------------------------------------------------------

# 🔢 47. `range(stop)`

``` python
for i in range(5):
    print(i)
```

Produces:

``` text
0 1 2 3 4
```

`stop` is exclusive.

------------------------------------------------------------------------

# 🔢 48. `range(start, stop)`

``` python
for i in range(2, 7):
    print(i)
```

Produces:

``` text
2 3 4 5 6
```

------------------------------------------------------------------------

# 🔢 49. `range(start, stop, step)`

``` python
for i in range(0, 10, 2):
    print(i)
```

Produces:

``` text
0 2 4 6 8
```

Reverse:

``` python
for i in range(5, 0, -1):
    print(i)
```

Produces:

``` text
5 4 3 2 1
```

### Remember

``` text
range(start, stop, step)
                    ↑
               direction
```

------------------------------------------------------------------------

# 🧩 50. `match / case`

`match / case` performs structural pattern matching.

``` python
command = "start"

match command:
    case "start":
        print("Starting")
    case "stop":
        print("Stopping")
    case _:
        print("Unknown")
```

It is especially useful when matching values or structures against known
patterns.

------------------------------------------------------------------------

# 🔹 51. Multiple Patterns

Use `|` to combine patterns.

``` python
command = "exit"

match command:
    case "quit" | "exit":
        print("Stopping")
    case "start":
        print("Starting")
    case _:
        print("Unknown")
```

------------------------------------------------------------------------

# 🃏 52. Wildcard `_`

`case _` acts as a fallback pattern.

``` python
value = "unknown"

match value:
    case "python":
        print("Python")
    case _:
        print("Other")
```

------------------------------------------------------------------------

# 🛡️ 53. Guards

A guard adds a condition to a pattern.

``` python
number = 15

match number:
    case n if n > 10:
        print("Greater than 10")
    case _:
        print("10 or less")
```

The pattern must match and the guard must also be true.

------------------------------------------------------------------------

# 🧩 54. Structural Matching

`match` can match the structure of values.

``` python
point = (0, 5)

match point:
    case (0, 0):
        print("Origin")
    case (0, y):
        print(f"Y-axis: {y}")
    case (x, 0):
        print(f"X-axis: {x}")
    case (x, y):
        print(f"Point: {x}, {y}")
```

Output:

``` text
Y-axis: 5
```

------------------------------------------------------------------------

# 🆚 55. `if` vs `match`

Use `if` when the decision is based on Boolean conditions:

``` python
if age >= 18:
    ...
```

Use `match` when the problem naturally involves patterns:

``` python
match command:
    case "start":
        ...
    case "stop":
        ...
```

### Quick Rule

``` text
Condition-based logic → if / elif / else
Pattern-based logic   → match / case
```

------------------------------------------------------------------------

# 🧠 56. Core Python Rules to Remember

``` text
STRING
→ Immutable Unicode sequence

INDEXING
→ Starts at 0

SLICING
→ stop is exclusive

INPUT
→ Always returns str

/
→ True division

//
→ Floor division

%
→ Remainder

**
→ Power

TRUTHINESS
→ Objects can behave as True/False in Boolean contexts

and
→ First falsy operand, otherwise last operand

or
→ First truthy operand, otherwise last operand

not
→ Reverses truth value

None
→ Absence of meaningful value

None CHECK
→ is None

for
→ Iterate over an iterable

while
→ Repeat while condition is truthy

break
→ Exit loop

continue
→ Skip current iteration

pass
→ Do nothing

range()
→ stop is exclusive

LOOP ELSE
→ Runs when loop ends without break

match / case
→ Structural pattern matching
```

------------------------------------------------------------------------

# 🚨 57. Most Common Mistakes

``` python
# Wrong: input() is not automatically numeric
age = input("Age: ")
# age + 1

# Correct
age = int(input("Age: "))
```

``` python
# Wrong: strings are immutable
# text[0] = "J"

# Correct: create a new string
text = "J" + text[1:]
```

``` python
# / and // are different
10 / 3    # 3.333...
10 // 3   # 3
```

``` python
# Equality vs identity
a == b    # same value?
a is b    # same object?
```

``` python
# None check
value is None
```

``` python
# Loop control
break       # exit
continue    # skip iteration
pass        # placeholder
```

------------------------------------------------------------------------

# 🎤 58. Interview Quick Fire

``` text
Q: Are strings mutable?
A: No. Strings are immutable.

Q: What does input() return?
A: str.

Q: What is the difference between / and //?
A: / performs true division; // performs floor division.

Q: What does % return?
A: The remainder associated with division.

Q: What are falsy values?
A: Values such as False, None, 0, 0.0, "", [], (), {}, and set().

Q: Why use is None?
A: None is a singleton object and identity is the appropriate test.

Q: Difference between break and continue?
A: break exits the loop; continue skips the current iteration.

Q: What does pass do?
A: Nothing; it is a placeholder statement.

Q: When does loop else execute?
A: When the loop completes without break.

Q: Is range() a list?
A: No. range() returns a range object representing an integer progression.

Q: What is match/case?
A: Python's structural pattern matching feature.
```

------------------------------------------------------------------------

# ⚡ 59. One-Minute Revision Map

``` text
                    CORE PYTHON
                         │
        ┌────────────────┼────────────────┐
        ↓                ↓                ↓
     STRINGS          NUMBERS          BOOLEAN
        │                │                │
   index/slice       int/float/        True/False
   methods           complex           truthiness
   split/join        / // % **          and/or/not
   f-string
        │
        ├───────────────┐
        ↓               ↓
      NONE           CONDITIONS
        │               │
     is None        if/elif/else
                        │
                        ↓
                     LOOPS
                        │
             ┌──────────┼──────────┐
             ↓          ↓          ↓
            for       while      control
                                  │
                          break/continue/pass
                                  │
                                  ↓
                               range()
                                  │
                                  ↓
                             match/case
```

------------------------------------------------------------------------

# ✅ 60. Revision Checklist

``` text
☐ Strings
☐ String indexing
☐ Negative indexing
☐ Slicing
☐ String immutability
☐ String methods
☐ split()
☐ join()
☐ f-strings

☐ int
☐ float
☐ complex
☐ /
☐ //
☐ %
☐ **

☐ True / False
☐ Truthiness
☐ bool()
☐ and
☐ or
☐ not
☐ Short-circuit evaluation

☐ None
☐ is None

☐ if
☐ elif
☐ else
☐ Conditional expression
☐ Nested conditions

☐ for
☐ while
☐ Nested loops
☐ break
☐ continue
☐ pass
☐ Loop else

☐ range(stop)
☐ range(start, stop)
☐ range(start, stop, step)
☐ Reverse range

☐ match
☐ case
☐ Multiple patterns
☐ Wildcard
☐ Guards
☐ Structural matching
```

------------------------------------------------------------------------

# 🎯 Final Recall

``` text
If you can explain these without opening the detailed chapter,
you have successfully revised Core Python:

String → immutable text sequence
Number → int / float / complex
Boolean → truthiness + logical operators
None → absence of meaningful value
if → conditional execution
for → iteration
while → condition-controlled repetition
break → exit
continue → skip
pass → placeholder
range → integer progression
match → pattern matching
```

> **Detailed learning:** `02_Core_Python.md`
>
> **Fast revision:** `02_Revision_Core_Python.md`
>
> **Next chapter:** `03_Data_Structures.md`
