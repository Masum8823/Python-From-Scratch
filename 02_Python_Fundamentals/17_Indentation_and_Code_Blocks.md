# 17. Indentation and Code Blocks in Python

## 1. Introduction

Python-এ **Indentation** বলতে code line-এর শুরুতে থাকা spaces বা whitespace-কে বোঝায়।

অন্যান্য কিছু programming language-এ code block বোঝাতে `{}` ব্যবহার করা হয়। কিন্তু Python-এ সাধারণত indentation দিয়ে বোঝানো হয় কোন statement কোন block-এর অন্তর্ভুক্ত।

উদাহরণ:

```python
age = 20

if age >= 18:
    print("You are an adult.")
```

Output:

```text
You are an adult.
```

এখানে `print()` statement-টি `if` block-এর ভেতরে রয়েছে, কারণ এর শুরুতে indentation আছে।

Indentation সঠিক না হলে Python `IndentationError` বা `SyntaxError` দিতে পারে।

## 2. What Is Indentation?

Indentation হলো code line-এর শুরুতে এক বা একাধিক space বা tab character ব্যবহার করে code-এর structure প্রকাশ করা।

উদাহরণ:

```python
if True:
    print("Inside the block")

print("Outside the block")
```

Output:

```text
Inside the block
Outside the block
```

এখানে:

- `if True:` একটি condition শুরু করেছে।
- `print("Inside the block")` indentation-এর কারণে `if` block-এর ভেতরে রয়েছে।
- শেষের `print()` একই indentation level-এ নেই, তাই এটি block-এর বাইরে।

### Why Is Indentation Important?

Indentation-এর প্রধান কাজগুলো হলো:

1. Code block নির্ধারণ করা।
2. Program-এর structure বোঝানো।
3. Code readable রাখা।
4. কোন statement কোন condition, loop বা function-এর অংশ, তা স্পষ্ট করা।

## 3. Python Indentation Rules

Python-এ indentation লেখার কিছু গুরুত্বপূর্ণ নিয়ম রয়েছে।

### Rule 1: Use Four Spaces

Python-এর প্রচলিত style হলো প্রতিটি নতুন block-এর জন্য চারটি space ব্যবহার করা।

```python
if True:
    print("Hello")
```

এখানে `print()`-এর আগে চারটি space রয়েছে।

### Rule 2: Keep the Same Indentation Level

একই block-এর statement-গুলোর indentation level একই রাখতে হবে।

সঠিক:

```python
if True:
    print("First statement")
    print("Second statement")
```

ভুল:

```python
# if True:
#     print("First statement")
#   print("Second statement")
```

দ্বিতীয় statement-এর indentation আগেরটির সঙ্গে মেলে না। এটি `IndentationError` তৈরি করতে পারে।

### Rule 3: Use a Colon Before a New Block

`if`, `for`, `while`, `def` এবং `class`-এর মতো compound statement-এর header-এর শেষে সাধারণত colon (`:`) থাকে।

```python
if True:
    print("Condition is true")
```

Colon-এর পরে নতুন block শুরু হয়।

### Rule 4: Do Not Indent Unnecessarily

যে statement কোনো block-এর ভেতরে নয়, সেটিকে অকারণে indent করা উচিত নয়।

সঠিক:

```python
print("Hello")
print("Python")
```

ভুল:

```python
#     print("Hello")
```

সাধারণ script-এর top level-এ এভাবে অপ্রয়োজনীয় indentation দিলে `IndentationError` হতে পারে।

## 4. What Is a Code Block?

**Code Block** হলো এক বা একাধিক statement-এর একটি group, যা একটি নির্দিষ্ট structure-এর অন্তর্ভুক্ত।

Python-এ indentation-এর মাধ্যমে block নির্ধারণ করা হয়।

উদাহরণ:

```python
if True:
    print("Statement 1")
    print("Statement 2")
    print("Statement 3")
```

এখানে তিনটি `print()` statement একই `if` block-এর অংশ।

### Block Structure

```text
if True:
    Statement 1
    Statement 2
    Statement 3

Statement 4
```

- `Statement 1`, `Statement 2` এবং `Statement 3` একই block-এর ভেতরে।
- `Statement 4` block-এর বাইরে।

### Important Note

Python-এ `{}` দিয়ে সাধারণ code block তৈরি করা হয় না। তবে dictionary এবং set-এর মতো data structure-এ `{}` ব্যবহার হয়।

উদাহরণ:

```python
student = {
    "name": "Masum",
    "department": "CSE"
}
```

এখানে `{}` একটি dictionary তৈরি করেছে; এটি `if` বা `for`-এর code block নয়।

## 5. Indentation in Conditional Statements

Conditional statement-এর মধ্যে `if`, `elif` এবং `else` ব্যবহার করলে indentation খুব গুরুত্বপূর্ণ।

উদাহরণ:

```python
marks = 85

if marks >= 80:
    print("Grade A+")

elif marks >= 70:
    print("Grade A")

else:
    print("Other Grade")
```

Output:

```text
Grade A+
```

এখানে:

- `if`, `elif` এবং `else` একই indentation level-এ রয়েছে।
- প্রতিটি branch-এর ভেতরের statement চারটি space দিয়ে indent করা হয়েছে।
- `marks >= 80` সত্য হওয়ায় প্রথম block execute হয়েছে।

### Nested Conditional Blocks

একটি `if` block-এর ভেতরে আরেকটি `if` block থাকতে পারে। একে nested conditional বলা হয়।

```python
age = 22
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
    else:
        print("ID required")
else:
    print("Underage")
```

Output:

```text
Entry allowed
```

এখানে indentation দেখে সহজেই বোঝা যায় কোন `else` কোন `if`-এর সঙ্গে সম্পর্কিত।

## 6. Indentation in Loops

`for` এবং `while` loop-এর body-ও indentation দিয়ে নির্ধারিত হয়।

### For Loop

```python
for i in range(3):
    print("Hello")
    print(i)

print("Loop finished")
```

Output:

```text
Hello
0
Hello
1
Hello
2
Loop finished
```

প্রথম দুটি `print()` loop-এর ভেতরে রয়েছে, তাই প্রতিটি iteration-এ execute হয়েছে। শেষের `print()` loop-এর বাইরে, তাই loop শেষ হওয়ার পরে একবার execute হয়েছে।

### While Loop

```python
count = 1

while count <= 3:
    print(count)
    count += 1

print("Done")
```

Output:

```text
1
2
3
Done
```

এখানে `print(count)` এবং `count += 1` loop-এর body-এর অংশ।

**মনে রাখবে:** Indentation ঠিক থাকলেও loop-এর condition কখনো false না হলে infinite loop হতে পারে।

## 7. Indentation in Functions

Function-এর body-ও indentation দিয়ে নির্ধারিত হয়।

```python
def greet():
    print("Hello")
    print("Welcome to Python")

greet()
```

Output:

```text
Hello
Welcome to Python
```

এখানে:

- `def greet():` function define করেছে।
- দুটি `print()` function body-এর অংশ।
- `greet()` indentation ছাড়া লেখা হয়েছে, তাই এটি top-level statement।

### Function with Return

```python
def add(a, b):
    result = a + b
    return result

answer = add(10, 5)
print(answer)
```

Output:

```text
15
```

`result = a + b` এবং `return result` একই function block-এর অংশ।

## 8. Nested Code Blocks

একটি block-এর ভেতরে আরেকটি block থাকলে তাকে nested block বলা হয়।

উদাহরণ:

```python
for i in range(2):
    print("Outer loop:", i)

    for j in range(2):
        print("Inner loop:", j)

print("Finished")
```

Output:

```text
Outer loop: 0
Inner loop: 0
Inner loop: 1
Outer loop: 1
Inner loop: 0
Inner loop: 1
Finished
```

### Understanding the Indentation Levels

```text
Level 0: for i in range(2):
    Level 1: print("Outer loop:", i)
    Level 1: for j in range(2):
        Level 2: print("Inner loop:", j)

Level 0: print("Finished")
```

ব্যাখ্যা:

- Level 0 হলো top-level code।
- Level 1 হলো outer loop-এর body।
- Level 2 হলো inner loop-এর body।

Nested block-এ প্রতিটি নতুন level সঠিকভাবে indent করা অত্যন্ত গুরুত্বপূর্ণ।

## 9. Indentation with `try`, `except`, and Other Blocks

Python-এর বিভিন্ন compound statement-এ indentation ব্যবহার হয়।

### Exception Handling

```python
try:
    number = int("abc")
except ValueError:
    print("Invalid number")
```

Output:

```text
Invalid number
```

`try` এবং `except` একই indentation level-এ রয়েছে। তাদের body indent করা হয়েছে।

### Class Definition

```python
class Student:
    def greet(self):
        print("Hello, student")

student = Student()
student.greet()
```

Output:

```text
Hello, student
```

এখানে:

- `def greet(self):` class block-এর ভেতরে।
- `print()` method-এর body-এর ভেতরে।
- Object তৈরি এবং method call top-level-এ রয়েছে।

## 10. Spaces vs Tabs

Indentation দেওয়ার জন্য Python-এ spaces এবং tabs ব্যবহার করা যায়। কিন্তু একই code block-এ দুটো মিশিয়ে ব্যবহার করা উচিত নয়।

### Recommended Practice

**প্রতিটি indentation level-এর জন্য চারটি space ব্যবহার করো।**

সঠিক:

```python
if True:
    print("Hello")
```

সমস্যাজনক:

```python
# একই block-এ spaces ও tabs মিশিয়ে লেখা
```

Spaces এবং tabs মিশিয়ে ফেললে `TabError` বা indentation-সংক্রান্ত সমস্যা হতে পারে।

VS Code-এ সাধারণত Tab key চাপলে spaces insert করার ব্যবস্থা করা যায়। তাই editor-এর indentation settings ঠিক রাখা ভালো।

## 11. Common Indentation Errors

### Error 1: Expected an Indented Block

ভুল:

```python
# if True:
# print("Hello")
```

সমস্যা: `if`-এর body indent করা হয়নি।

সঠিক:

```python
if True:
    print("Hello")
```

### Error 2: Unexpected Indentation

ভুল:

```python
#     print("Hello")
```

সমস্যা: top-level statement অকারণে indent করা হয়েছে।

সঠিক:

```python
print("Hello")
```

### Error 3: Inconsistent Indentation

ভুল:

```python
# if True:
#     print("First")
#   print("Second")
```

সমস্যা: একই block-এর statement-গুলোর indentation level এক নয়।

সঠিক:

```python
if True:
    print("First")
    print("Second")
```

### Error 4: Missing Colon

ভুল:

```python
# if True
#     print("Hello")
```

সমস্যা: `if` header-এর শেষে colon নেই। এটি `SyntaxError` তৈরি করবে।

সঠিক:

```python
if True:
    print("Hello")
```

### Error 5: Wrong Block Placement

ভুল:

```python
age = 16

if age >= 18:
    print("Adult")

    print("Program finished")
```

এই code-টি syntax-এর দিক থেকে valid, কিন্তু `Program finished` statement-টি `if` block-এর ভেতরে আছে। তাই `age` ১৮-এর কম হলে এটি execute হবে না।

যদি statement-টি সবসময় execute করাতে চাও:

```python
age = 16

if age >= 18:
    print("Adult")

print("Program finished")
```

Output:

```text
Program finished
```

এখানে code syntactically valid হলেও indentation-এর কারণে execution behavior পরিবর্তিত হতে পারে।

## 12. The `pass` Statement

কখনো block তৈরি করতে হয়, কিন্তু আপাতত তার ভেতরে কোনো কাজ লিখতে হয় না। তখন `pass` ব্যবহার করা যায়।

```python
if True:
    pass

print("Program continues")
```

Output:

```text
Program continues
```

`pass` কোনো কাজ করে না; এটি একটি placeholder statement।

Function-এর ক্ষেত্রেও ব্যবহার করা যায়:

```python
def future_function():
    pass
```

এভাবে function-এর structure তৈরি করে পরে implementation যোগ করা যায়।

## 13. Indentation and Readability

সঠিক indentation code পড়া, বোঝা এবং maintain করা সহজ করে।

কম readable:

```python
if True:
 print("First")
 if True:
  print("Second")
```

যদিও এখানে indentation level ধারাবাহিক, তবে চারটি space-এর প্রচলিত style অনুসরণ করা হয়নি।

আরও readable:

```python
if True:
    print("First")

    if True:
        print("Second")
```

এখানে indentation-এর প্রতিটি level স্পষ্ট।

### Best Practices

1. প্রতি block-এ চারটি space ব্যবহার করো।
2. Spaces ও tabs মিশিয়ে ব্যবহার কোরো না।
3. একই block-এর statement একই indentation level-এ রাখো।
4. Nested block-এ প্রতিটি level-এর জন্য অতিরিক্ত চারটি space ব্যবহার করো।
5. `if`, `for`, `while`, `def` এবং `class`-এর মতো compound statement-এর পরে colon দাও।
6. প্রয়োজন হলে blank line দিয়ে code-এর আলাদা অংশগুলো পৃথক করো।
7. VS Code-এর formatter ও indentation settings ব্যবহার করো।

## 14. Practical Example: Student Result System

```python
student_name = "Masum"
marks = 85

if marks >= 80:
    grade = "A+"
elif marks >= 70:
    grade = "A"
elif marks >= 60:
    grade = "B"
else:
    grade = "F"

print("Student:", student_name)
print("Marks:", marks)
print("Grade:", grade)
```

Output:

```text
Student: Masum
Marks: 85
Grade: A+
```

এখানে `if`, `elif` এবং `else`-এর body-গুলো indentation দিয়ে আলাদা করা হয়েছে। Condition অনুযায়ী একটি branch execute হবে।

## 15. Practice Exercises

### Exercise 1: Fix the Indentation

নিচের code-টি সঠিকভাবে indent করো:

```python
# if True:
# print("Python")
# print("Programming")
```

Expected output:

```text
Python
Programming
```

### Exercise 2: Predict the Output

```python
for i in range(3):
    print(i)

print("Finished")
```

প্রতিটি statement কতবার execute হবে, তা ব্যাখ্যা করো।

### Exercise 3: Nested Conditions

নিচের code-টির indentation ঠিক করো:

```python
# age = 20
# if age >= 18:
# print("Adult")
# if age >= 21:
# print("Eligible for this condition")
```

### Exercise 4: Function Block

একটি `greet()` function লেখো, যা দুটি message print করবে। তারপর function-টি call করো।

### Exercise 5: Find the Problem

```python
age = 15

if age >= 18:
    print("Adult")
    print("Eligible")

print("Program ended")
```

প্রশ্ন:

1. কোন statement-গুলো `if` block-এর ভেতরে?
2. কোন statement সবসময় execute হবে?
3. `age = 20` করলে output কী হবে?

### Exercise 6: Nested Loop

দুটি nested `for` loop ব্যবহার করে নিচের output তৈরি করো:

```text
i = 0, j = 0
i = 0, j = 1
i = 1, j = 0
i = 1, j = 1
```

## 16. Quick Revision

| Term | Meaning |
|---|---|
| Indentation | Code line-এর শুরুতে spaces বা tabs |
| Code Block | একই structure-এর অন্তর্ভুক্ত statement-এর group |
| Nested Block | একটি block-এর ভেতরে আরেকটি block |
| Four Spaces | Python-এর প্রচলিত indentation style |
| `IndentationError` | Indentation সঠিক না হলে হতে পারে |
| `SyntaxError` | Code-এর syntax ভুল হলে হয় |
| `pass` | কোনো কাজ না করে placeholder হিসেবে থাকা statement |

## 17. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Python-এ indentation code-এর structure নির্ধারণ করে।
- Code block-এর statement-গুলো সঠিক indentation level-এ লিখতে হয়।
- Python-এর প্রচলিত style হলো প্রতি level-এ চারটি space।
- `if`, `elif`, `else`, `for`, `while`, `def`, `class` এবং `try`-এর মতো statement-এ indentation গুরুত্বপূর্ণ।
- Nested block-এ প্রতিটি level আলাদাভাবে indent করতে হয়।
- Spaces এবং tabs মিশিয়ে ব্যবহার করা উচিত নয়।
- `IndentationError` এবং `SyntaxError`-এর কারণ বুঝে code ঠিক করতে হয়।
- `pass` একটি empty block-এর placeholder হিসেবে ব্যবহার করা যায়।

## 18. Next Topic

পরবর্তী ফাইল: [`18_Case_Sensitivity_and_Whitespace.md`](18_Case_Sensitivity_and_Whitespace.md)

সেখানে Python-এর case sensitivity, whitespace, spaces, blank lines এবং এগুলো কীভাবে code-এর meaning ও readability-কে প্রভাবিত করে, তা আলোচনা করা হবে।