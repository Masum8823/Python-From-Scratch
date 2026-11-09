# 32. Chapter Review and Self-Assessment

## 1. Chapter Overview

এই chapter-এ আমরা Python-এর Conditional Statements শিখেছি। Conditional statements ব্যবহার করে program নির্দিষ্ট condition অনুযায়ী সিদ্ধান্ত নিতে পারে।

এই chapter-এর গুরুত্বপূর্ণ বিষয়গুলো:

- Conditions এবং Boolean expressions
- `if`, `else` ও `elif`
- Indentation এবং code blocks
- Nested conditions
- Logical operators
- Truthiness এবং falsy values
- Conditional expressions বা ternary operator
- Membership এবং identity operators
- Chained comparisons
- `match-case`
- Input validation
- Debugging conditional logic
- Practical programs এবং problem-solving techniques

## 2. What Is a Conditional Statement?

**Conditional statement** হলো এমন একটি statement, যার মাধ্যমে condition অনুযায়ী program-এর execution flow নিয়ন্ত্রণ করা হয়।

Example:

```python
age = 20

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Output:

```text
Adult
```

এখানে `age >= 18` True হওয়ায় `if` block execute হয়েছে।

## 3. Boolean Expressions

Boolean expression এমন expression, যার evaluation-এর result `True` অথবা `False` হয়।

Example:

```python
print(10 > 5)
print(10 < 5)
print(10 == 10)
```

Output:

```text
True
False
True
```

Python-এ Boolean values-এর নাম capital letter দিয়ে লেখা হয়: `True` এবং `False`।

## 4. Comparison Operators

Comparison operators দুইটি value-এর মধ্যে তুলনা করে।

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `==` | Equal to | `5 == 5` | `True` |
| `!=` | Not equal to | `5 != 3` | `True` |
| `>` | Greater than | `8 > 5` | `True` |
| `<` | Less than | `3 < 7` | `True` |
| `>=` | Greater than or equal to | `5 >= 5` | `True` |
| `<=` | Less than or equal to | `4 <= 3` | `False` |

মনে রাখবে:

- `=` value assign করে।
- `==` দুইটি value সমান কি না পরীক্ষা করে।

## 5. The if Statement

`if` statement condition True হলে একটি code block execute করে।

Syntax:

```python
if condition:
    # Code to execute
```

Example:

```python
temperature = 38

if temperature > 35:
    print("Hot weather")
```

Output:

```text
Hot weather
```

Condition False হলে `if` block execute হবে না।

## 6. The if-else Statement

`if-else` ব্যবহার করা হয় দুইটি alternative-এর মধ্যে একটি নির্বাচন করতে।

Syntax:

```python
if condition:
    # Runs when condition is True
else:
    # Runs when condition is False
```

Example:

```python
number = 7

if number % 2 == 0:
    print("Even")
else:
    print("Odd")
```

Output:

```text
Odd
```

## 7. The if-elif-else Statement

একাধিক alternative condition পরীক্ষা করতে `if-elif-else` ব্যবহার করা হয়।

Syntax:

```python
if condition1:
    # Block 1
elif condition2:
    # Block 2
elif condition3:
    # Block 3
else:
    # Default block
```

Example:

```python
marks = 75

if marks >= 80:
    print("A")
elif marks >= 60:
    print("B")
elif marks >= 40:
    print("C")
else:
    print("F")
```

Output:

```text
B
```

**Important rule:** প্রথম True condition-এর block execute হয়। এরপর chain-এর বাকি branch-গুলো skip করা হয়।

## 8. Independent if vs if-elif

এই দুইটি structure-এর পার্থক্য exam এবং programming—দুই ক্ষেত্রেই গুরুত্বপূর্ণ।

| Independent `if` | `if-elif` |
|---|---|
| প্রতিটি `if` আলাদাভাবে পরীক্ষা হয়। | একটি chain-এর প্রথম True branch execute হয়। |
| একাধিক block execute হতে পারে। | সর্বোচ্চ একটি branch execute হয়। |
| একাধিক independent rule-এর জন্য উপযুক্ত। | একাধিক alternative-এর মধ্যে একটি বেছে নিতে উপযুক্ত। |

Example:

```python
x = 10

if x > 5:
    print("A")

if x > 8:
    print("B")
```

Output:

```text
A
B
```

কিন্তু:

```python
x = 10

if x > 5:
    print("A")
elif x > 8:
    print("B")
```

Output:

```text
A
```

কারণ প্রথম condition True।

## 9. Indentation and Code Blocks

Python-এ indentation code block নির্ধারণ করে। সাধারণত প্রতি level-এ চারটি space ব্যবহার করা হয়।

Correct:

```python
if age >= 18:
    print("Adult")
else:
    print("Minor")
```

Incorrect:

```python
if age >= 18:
print("Adult")
```

দ্বিতীয় উদাহরণে indentation error হবে।

## 10. Nested if Statements

একটি `if` block-এর ভেতরে আরেকটি `if` statement থাকলে তাকে nested `if` বলা হয়।

Example:

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Access granted")
    else:
        print("ID required")
else:
    print("Too young")
```

Output:

```text
Access granted
```

Nested condition ব্যবহার করবে যখন একটি condition পূরণ হওয়ার পরে আরেকটি condition পরীক্ষা করা প্রয়োজন।

## 11. Logical Operators

Logical operators এক বা একাধিক condition combine করতে ব্যবহৃত হয়।

| Operator | Meaning | Result |
|---|---|---|
| `and` | সব condition True হতে হবে | `True and False` → `False` |
| `or` | অন্তত একটি condition True হলেই হবে | `True or False` → `True` |
| `not` | Boolean result উল্টে দেয় | `not True` → `False` |

Example:

```python
age = 25
has_id = True

if age >= 18 and has_id:
    print("Eligible")
else:
    print("Not eligible")
```

Output:

```text
Eligible
```

## 12. Truthiness and Falsy Values

Python-এ কিছু value condition হিসেবে ব্যবহার করলে False হিসেবে বিবেচিত হয়। এগুলোকে falsy values বলা হয়।

Common falsy values:

- `False`
- `None`
- `0`
- `0.0`
- `0j`
- `""`
- `[]`
- `()`
- `{}`
- `set()`

সাধারণভাবে, অন্য non-empty values truthy হয়।

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

**Important:** `bool("False")` হলো `True`, কারণ `"False"` একটি non-empty string।

## 13. Conditional Expression (Ternary Operator)

ছোট condition এক লাইনে লিখতে conditional expression ব্যবহার করা যায়।

Syntax:

```python
value_if_true if condition else value_if_false
```

Example:

```python
age = 20
status = "Adult" if age >= 18 else "Minor"

print(status)
```

Output:

```text
Adult
```

ছোট expression-এর জন্য এটি উপযোগী। Complex nested conditional expression ব্যবহার করলে code পড়তে কঠিন হতে পারে।

## 14. Membership Operators

Membership operators কোনো collection বা sequence-এর মধ্যে value আছে কি না পরীক্ষা করে।

| Operator | Meaning |
|---|---|
| `in` | Value উপস্থিত আছে |
| `not in` | Value উপস্থিত নেই |

Example:

```python
fruits = ["apple", "banana", "mango"]

if "banana" in fruits:
    print("Found")
else:
    print("Not found")
```

Output:

```text
Found
```

Dictionary-তে `in` সাধারণত key পরীক্ষা করে, value নয়।

## 15. Identity Operators

Identity operators পরীক্ষা করে দুইটি reference একই object-কে নির্দেশ করছে কি না।

| Operator | Meaning |
|---|---|
| `is` | একই object |
| `is not` | একই object নয় |

Example:

```python
value = None

if value is None:
    print("No value")
```

Output:

```text
No value
```

মনে রাখবে:

- `==` value equality পরীক্ষা করে।
- `is` object identity পরীক্ষা করে।
- `None` পরীক্ষা করতে `is None` বা `is not None` ব্যবহার করবে।

## 16. Chained Comparisons

একাধিক comparison সংক্ষিপ্তভাবে লিখতে chained comparison ব্যবহার করা যায়।

Example:

```python
age = 25

if 18 <= age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

Output:

```text
Eligible
```

এটি নিচের expression-এর সমতুল্য:

```python
if age >= 18 and age <= 60:
    print("Eligible")
```

## 17. Match-Case Statement

`match-case` Python 3.10 বা তার পরবর্তী version-এ পাওয়া যায়। নির্দিষ্ট value বা pattern অনুযায়ী action নির্বাচন করতে এটি ব্যবহার করা যায়।

Example:

```python
choice = 2

match choice:
    case 1:
        print("One")
    case 2:
        print("Two")
    case 3:
        print("Three")
    case _:
        print("Invalid choice")
```

Output:

```text
Two
```

এখানে `case _` হলো catch-all pattern। আগের কোনো case match না করলে এটি ব্যবহার হয়।

## 18. Operator Precedence in Conditions

একটি expression-এ একাধিক operator থাকলে precedence নির্ধারণ করে কোন operator আগে evaluate হবে।

Conditional logic-এর জন্য গুরুত্বপূর্ণ order:

1. Arithmetic ও অন্যান্য expression evaluation
2. Comparison, membership ও identity operations
3. `not`
4. `and`
5. `or`

Example:

```python
result = True or False and False
print(result)
```

Output:

```text
True
```

কারণ `and`-এর precedence `or`-এর চেয়ে বেশি। তাই expression-টি এভাবে evaluate হয়:

```python
True or (False and False)
```

Complex condition পরিষ্কার করতে parentheses ব্যবহার করা ভালো।

## 19. Input Validation

Input validation নিশ্চিত করে user-এর input গ্রহণযোগ্য কি না।

Example:

```python
marks = float(input("Enter marks: "))

if marks < 0 or marks > 100:
    print("Invalid marks")
elif marks >= 40:
    print("Pass")
else:
    print("Fail")
```

এখানে marks 0–100-এর বাইরে হলে Invalid marks দেখানো হয়।

তবে non-numeric text দিলে `float()` থেকে `ValueError` হতে পারে। সেটি সামলাতে পরবর্তী chapter-এ `try-except` শিখবে।

## 20. Debugging Conditional Logic

Debugging হলো program-এর ভুল বা unexpected behavior খুঁজে বের করে ঠিক করার প্রক্রিয়া।

সাধারণ logical error:

```python
marks = 90

if marks >= 40:
    print("Pass")
elif marks >= 80:
    print("A")
```

Output:

```text
Pass
```

এখানে প্রথম condition True হওয়ায় `A` branch-এ পৌঁছায় না।

সঠিক version:

```python
marks = 90

if marks >= 80:
    print("A")
elif marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Debugging-এর সময়:

1. Variable-এর value পরীক্ষা করবে।
2. প্রতিটি condition True নাকি False দেখবে।
3. Condition-এর order যাচাই করবে।
4. Boundary value দিয়ে test করবে।
5. Code পরিবর্তনের পরে আবার পরীক্ষা করবে।

## 21. Common Mistakes and Their Solutions

| Mistake | Correct approach |
|---|---|
| `if x = 5:` | `if x == 5:` |
| `if age >= 18 or age <= 60:` দিয়ে range পরীক্ষা | `if age >= 18 and age <= 60:` |
| বড় threshold-এর পরে ছোট threshold পরীক্ষা | প্রয়োজন অনুযায়ী বড় threshold আগে পরীক্ষা |
| `if choice == "yes" or "y":` | `if choice == "yes" or choice == "y":` |
| String equality-তে `is` ব্যবহার | `==` ব্যবহার |
| `if`-এর পরে colon বাদ দেওয়া | `if condition:` |
| Block-এ ভুল indentation | সঠিক indentation ব্যবহার |
| Boundary value বাদ দেওয়া | সীমানার value-ও পরীক্ষা |
| Invalid numeric input পরীক্ষা না করা | প্রয়োজন হলে `try-except` ব্যবহার |

## 22. Important Syntax Cheat Sheet

### Simple if

```python
if condition:
    statement
```

### if-else

```python
if condition:
    statement1
else:
    statement2
```

### if-elif-else

```python
if condition1:
    statement1
elif condition2:
    statement2
else:
    statement3
```

### Nested if

```python
if condition1:
    if condition2:
        statement
```

### Logical conditions

```python
if condition1 and condition2:
    statement

if condition1 or condition2:
    statement

if not condition:
    statement
```

### Chained comparison

```python
if lower <= value <= upper:
    statement
```

### Membership

```python
if value in collection:
    statement
```

### Conditional expression

```python
result = value1 if condition else value2
```

### Match-case

```python
match value:
    case pattern1:
        statement1
    case pattern2:
        statement2
    case _:
        default_statement
```

## 23. Final Output Prediction Test

নিজে solve করার চেষ্টা করবে।

### Question 1

```python
x = 10

if x >= 10:
    print("A")
elif x > 5:
    print("B")
else:
    print("C")
```

### Question 2

```python
x = 5

if x > 0 and x < 5:
    print("A")
else:
    print("B")
```

### Question 3

```python
age = 17

if age >= 18 or age <= 60:
    print("Eligible")
else:
    print("Not eligible")
```

### Question 4

```python
x = 0

if x:
    print("A")
else:
    print("B")
```

### Question 5

```python
x = 7

print(5 < x < 10)
```

### Question 6

```python
choice = "2"

match choice:
    case "1":
        print("One")
    case "2":
        print("Two")
    case _:
        print("Other")
```

### Answer Key

| Question | Output | Reason |
|---:|---|---|
| 1 | `A` | প্রথম condition True |
| 2 | `B` | `x < 5` False |
| 3 | `Eligible` | `age <= 60` True |
| 4 | `B` | Zero falsy |
| 5 | `True` | 5 < 7 < 10 |
| 6 | `Two` | String `"2"`-এর সঙ্গে `"2"` match করে |

## 24. Final Self-Assessment

প্রতিটি statement-এর পাশে নিজের প্রস্তুতি যাচাই করো।

- [ ] Boolean expressions ও comparison operators বুঝি।
- [ ] `if`, `elif`, `else` সঠিকভাবে ব্যবহার করতে পারি।
- [ ] Independent `if` ও `if-elif`-এর পার্থক্য বুঝি।
- [ ] Nested conditions লিখতে পারি।
- [ ] Logical operators ব্যবহার করতে পারি।
- [ ] Truthy ও falsy values শনাক্ত করতে পারি।
- [ ] Conditional expression লিখতে পারি।
- [ ] Membership ও identity operators-এর পার্থক্য বুঝি।
- [ ] Chained comparisons ব্যবহার করতে পারি।
- [ ] `match-case` দিয়ে value match করতে পারি।
- [ ] Input validation-এর basic logic লিখতে পারি।
- [ ] Conditional logic debug করতে পারি।
- [ ] Practical conditional programs নিজে তৈরি করতে পারি।
- [ ] Output prediction exercises solve করতে পারি।

## 25. Chapter Completion Checklist

Chapter 06 সম্পূর্ণ শেষ করার আগে:

1. সব topic file একবার revise করবে।
2. প্রতিটি code example নিজে run করবে।
3. Output prediction questions-এর উত্তর code run করার আগে লিখবে।
4. Programming exercises-এর অন্তত beginner ও intermediate level নিজে solve করবে।
5. ভুল হওয়া question-গুলো আবার practice করবে।
6. প্রয়োজন হলে নিজের দুর্বল topic-এর notes পুনরায় পড়বে।

## 26. Final Advice

Conditional statements হলো programming-এর decision-making foundation। পরবর্তী সময়ে loops, functions, algorithms এবং real-world applications-এও এই concepts বারবার ব্যবহার করবে।

শুধু syntax মুখস্থ না করে condition কেন True বা False হচ্ছে এবং কোন block execute হচ্ছে—সেটি বুঝে code লিখবে।

**Chapter 06 Completed: Conditional Statements**

**Next Chapter:** Chapter 07 — Loops & Iteration
