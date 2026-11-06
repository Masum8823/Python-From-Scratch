# 03. Conditions and Boolean Expressions

## 1. Introduction

Python-এ conditional statements ব্যবহার করে decision নেওয়ার জন্য condition তৈরি করতে হয়।

একটি condition সাধারণত যাচাই করে কোনো statement সত্য নাকি মিথ্যা। Python-এ এই ফলাফল প্রকাশ করার জন্য Boolean values `True` এবং `False` ব্যবহার করা হয়।

Example:

```python
print(10 > 5)
print(10 < 5)
```

Output:

```text
True
False
```

প্রথম expression সত্য, তাই `True` এসেছে। দ্বিতীয় expression মিথ্যা, তাই `False` এসেছে।

এই chapter-এ আমরা শিখব:

- Condition কী
- Boolean data type কী
- Boolean expression কী
- Comparison দিয়ে condition তৈরি করা
- Variable ব্যবহার করে condition তৈরি করা
- Logical expression
- Condition কীভাবে evaluate হয়
- Common mistakes এবং practice exercises

## 2. What Is a Condition?

**Condition** হলো এমন একটি expression, যা যাচাই করে কোনো নির্দিষ্ট শর্ত পূরণ হয়েছে কি না।

উদাহরণ:

```python
age = 20

age >= 18
```

এখানে `age >= 18` হলো condition।

যেহেতু `age`-এর value 20, তাই:

```python
20 >= 18
```

এর ফলাফল `True`।

আরেকটি উদাহরণ:

```python
age = 15

print(age >= 18)
```

Output:

```text
False
```

কারণ 15, 18-এর চেয়ে বড় বা সমান নয়।

### Important Point

Condition কোনো variable-এর value পরিবর্তন করে না। এটি শুধু যাচাই করে এবং একটি result দেয়।

```python
number = 10

result = number > 5

print(result)
print(number)
```

Output:

```text
True
10
```

এখানে `number > 5` যাচাই করে result `result` variable-এ রাখা হয়েছে। মূল `number`-এর value অপরিবর্তিত রয়েছে।

## 3. What Is Boolean Data Type?

Python-এর **Boolean data type** দুটি value ধারণ করে:

- `True`
- `False`

Python-এ এদের data type হলো `bool`।

Example:

```python
is_student = True
is_graduated = False

print(is_student)
print(is_graduated)

print(type(is_student))
print(type(is_graduated))
```

Output:

```text
True
False
<class 'bool'>
<class 'bool'>
```

### Boolean Values-এর ব্যবহার

Boolean values সাধারণত decision-making, comparison, validation এবং logical operations-এ ব্যবহৃত হয়।

```python
is_logged_in = True

if is_logged_in:
    print("Welcome back!")
```

Output:

```text
Welcome back!
```

এখানে `is_logged_in`-এর value `True`, তাই `if` block execute হয়েছে।

### Important Rule

Python-এ Boolean literals-এর প্রথম অক্ষর capital:

```python
True
False
```

এগুলো ভুল:

```python
true
false
```

`true` ও `false` Python-এর Boolean literals নয়। এগুলো আলাদা identifier হিসেবে বিবেচিত হয় এবং আগে define না করা থাকলে `NameError` হবে।

## 4. What Is a Boolean Expression?

**Boolean Expression** হলো এমন একটি expression, যার evaluation-এর result Boolean value—`True` অথবা `False`।

উদাহরণ:

```python
print(8 > 3)
print(8 == 3)
print(10 != 5)
```

Output:

```text
True
False
True
```

এখানে প্রতিটি expression-এর result হলো Boolean value।

### More Examples

| Expression | Result | Reason |
|---|---|---|
| `5 > 2` | `True` | 5, 2-এর চেয়ে বড় |
| `5 < 2` | `False` | 5, 2-এর চেয়ে ছোট নয় |
| `10 == 10` | `True` | দুটি value সমান |
| `10 != 10` | `False` | দুটি value আলাদা নয় |
| `7 >= 7` | `True` | সমান হওয়াও গ্রহণযোগ্য |
| `4 <= 2` | `False` | 4, 2-এর চেয়ে ছোট বা সমান নয় |

## 5. Creating Conditions with Comparison Operators

Comparison operators ব্যবহার করে দুটি value-এর মধ্যে তুলনা করা যায়।

| Operator | Meaning | Example |
|---|---|---|
| `==` | Equal to | `a == b` |
| `!=` | Not equal to | `a != b` |
| `>` | Greater than | `a > b` |
| `<` | Less than | `a < b` |
| `>=` | Greater than or equal to | `a >= b` |
| `<=` | Less than or equal to | `a <= b` |

Example:

```python
marks = 75

print(marks >= 40)
print(marks < 40)
```

Output:

```text
True
False
```

এখানে `marks >= 40` সত্য, তাই result `True`।

### Using a Condition in an if Statement

```python
marks = 75

if marks >= 40:
    print("Pass")
```

Output:

```text
Pass
```

এখানে Boolean expression সরাসরি `if` statement-এর condition হিসেবে ব্যবহৃত হয়েছে।

## 6. Conditions Using Variables

বাস্তব program-এ condition তৈরির সময় প্রায়ই variable ব্যবহার করা হয়।

Example:

```python
age = 22
minimum_age = 18

print(age >= minimum_age)
```

Output:

```text
True
```

Python প্রথমে variable-গুলোর value নেয়, তারপর comparison করে।

আরেকটি উদাহরণ:

```python
balance = 5000
withdraw = 2000

if balance >= withdraw:
    print("Sufficient balance")
```

Output:

```text
Sufficient balance
```

এখানে balance withdrawal amount-এর সমান বা বেশি কি না যাচাই করা হয়েছে।

## 7. Conditions Using Arithmetic Expressions

Condition-এর মধ্যে arithmetic calculation-ও করা যায়।

Example:

```python
a = 10
b = 5

print(a + b > 12)
print(a * b == 50)
print(a - b < 3)
```

Output:

```text
True
True
False
```

ব্যাখ্যা:

- `a + b > 12` → `15 > 12` → `True`
- `a * b == 50` → `50 == 50` → `True`
- `a - b < 3` → `5 < 3` → `False`

Python expression evaluate করে তারপর comparison-এর result দেয়।

## 8. Logical Boolean Expressions

একাধিক condition একসঙ্গে যাচাই করতে logical operators ব্যবহার করা হয়।

প্রধান তিনটি logical operator হলো:

- `and`
- `or`
- `not`

### 8.1 The `and` Operator

`and`-এর result `True` হবে যখন দুটি condition-ই সত্য।

```python
age = 22
has_id = True

print(age >= 18 and has_id)
```

Output:

```text
True
```

এখানে দুটি condition-ই সত্য।

### 8.2 The `or` Operator

`or`-এর result `True` হবে যখন অন্তত একটি condition সত্য।

```python
has_ticket = False
has_pass = True

print(has_ticket or has_pass)
```

Output:

```text
True
```

দ্বিতীয় condition সত্য হওয়ায় result `True`।

### 8.3 The `not` Operator

`not` Boolean result উল্টে দেয়।

```python
is_raining = False

print(not is_raining)
```

Output:

```text
True
```

কারণ `not False` হলো `True`।

### Truth Table

| A | B | `A and B` | `A or B` |
|---|---|---|---|
| `True` | `True` | `True` | `True` |
| `True` | `False` | `False` | `True` |
| `False` | `True` | `False` | `True` |
| `False` | `False` | `False` | `False` |

`not` operator-এর ক্ষেত্রে:

| A | `not A` |
|---|---|
| `True` | `False` |
| `False` | `True` |

**Note:** Python-এর `and` ও `or` শুধু Boolean literal-এর সঙ্গেই কাজ করে না; এগুলো অন্য value-ও return করতে পারে। এই advanced behavior পরবর্তী logical operators ও truthiness topics-এ বিস্তারিত শেখা হবে।

## 9. Boolean Expressions with Strings

String-এর value তুলনা করেও condition তৈরি করা যায়।

Example:

```python
password = "python123"

print(password == "python123")
print(password == "Python123")
```

Output:

```text
True
False
```

Python-এর string comparison case-sensitive। তাই `"python123"` এবং `"Python123"` সমান নয়।

### Using Strings in Conditions

```python
role = "admin"

if role == "admin":
    print("Admin access")
```

Output:

```text
Admin access
```

এখানে condition যাচাই করছে `role`-এর value `"admin"` কি না।

## 10. Boolean Expressions with User Input

User input নিয়েও condition তৈরি করা যায়।

Example:

```python
number = int(input("Enter a number: "))

is_positive = number > 0

print(is_positive)
```

Sample Input:

```text
Enter a number: 12
```

Output:

```text
True
```

এখানে:

1. `input()` string নেয়।
2. `int()` input-কে integer-এ convert করে।
3. `number > 0` condition evaluate করে।
4. Result Boolean value হিসেবে `is_positive`-এ রাখা হয়।
5. `print()` result দেখায়।

**Important:** User যদি integer হিসেবে convert করা যায় না এমন text দেয়, তাহলে `ValueError` হতে পারে। Input validation-এর বিস্তারিত পরে শেখা হবে।

## 11. Storing Boolean Results in Variables

Boolean expression-এর result variable-এ রাখা যায়।

```python
temperature = 35

is_hot = temperature >= 30

print(is_hot)
```

Output:

```text
True
```

এখানে `is_hot` variable-এ Boolean value রাখা হয়েছে।

পরে এই variable condition হিসেবে ব্যবহার করা যায়:

```python
if is_hot:
    print("It is hot.")
```

Output:

```text
It is hot.
```

এই পদ্ধতি program-কে readable করতে সাহায্য করে, বিশেষ করে condition জটিল হলে।

## 12. Expression vs Statement

এই দুটি term-এর পার্থক্য বোঝা গুরুত্বপূর্ণ।

### Expression

Expression একটি value তৈরি করে।

```python
10 > 5
```

এটির result `True`।

### Statement

Statement হলো Python-এর একটি instruction, যা কোনো কাজ সম্পন্ন করে।

```python
if 10 > 5:
    print("True condition")
```

এখানে `if` statement condition পরীক্ষা করে এবং প্রয়োজন অনুযায়ী code execute করে।

সহজভাবে:

- **Expression:** একটি value হিসাব করে বা return করে।
- **Statement:** program-কে একটি কাজ করতে নির্দেশ দেয়।

## 13. Common Mistakes

### Mistake 1: Using `=` Instead of `==`

Incorrect:

```python
number = 10

if number = 10:
    print("Equal")
```

এখানে `SyntaxError` হবে।

Correct:

```python
number = 10

if number == 10:
    print("Equal")
```

### Mistake 2: Writing `true` Instead of `True`

Incorrect:

```python
is_active = true
```

`true` আগে define করা না থাকলে `NameError` হবে।

Correct:

```python
is_active = True
```

### Mistake 3: Confusing a Number with a String

```python
age = 18

print(age == "18")
```

Output:

```text
False
```

কারণ `18` হলো integer, কিন্তু `"18"` হলো string।

### Mistake 4: Incorrect Logical Condition

```python
age = 15

if age >= 18 and age <= 60:
    print("Eligible")
```

এখানে output হবে না। কারণ `age >= 18` মিথ্যা, তাই পুরো `and` expression মিথ্যা।

### Mistake 5: Forgetting to Store the Result

```python
number = 10

number > 5
print(number)
```

Output:

```text
10
```

`number > 5` expression-এর result কোথাও store করা হয়নি এবং print-ও করা হয়নি। তাই শুধু `number`-এর value দেখানো হয়েছে।

Correct:

```python
number = 10
result = number > 5

print(result)
```

Output:

```text
True
```

## 14. Practice Exercises

প্রথমে নিজে solve করার চেষ্টা করো।

### Exercise 1: Boolean Values

নিচের code-এর output predict করো:

```python
print(15 > 10)
print(5 == 8)
print(7 != 3)
print(4 >= 4)
```

### Exercise 2: Age Condition

একটি `age` variable তৈরি করো। বয়স 18 বা তার বেশি কি না, তা Boolean value হিসেবে print করো।

### Exercise 3: Even Number

একটি integer input নিয়ে সেটি even কি না, তা Boolean value হিসেবে print করো।

Hint: `number % 2 == 0`

### Exercise 4: Logical Expression

নিচের code-এর output predict করো:

```python
print(10 > 5 and 8 < 12)
print(10 < 5 or 8 < 12)
print(not (5 == 5))
```

### Exercise 5: Password Comparison

User-এর কাছ থেকে password input নিয়ে সেটি `"python123"`-এর সমান কি না, তা Boolean value হিসেবে print করো।

### Exercise 6: Store a Boolean Result

একটি `marks` variable-এ 75 রাখো। `marks >= 40` expression-এর result `is_pass` variable-এ store করে print করো।

## 15. Practice Answer Key

### Answer 1

```text
True
False
True
True
```

### Answer 2

```python
age = int(input("Enter age: "))

print(age >= 18)
```

### Answer 3

```python
number = int(input("Enter a number: "))

print(number % 2 == 0)
```

### Answer 4

```text
True
True
False
```

ব্যাখ্যা:

- `True and True` → `True`
- `False or True` → `True`
- `not True` → `False`

### Answer 5

```python
password = input("Enter password: ")

print(password == "python123")
```

### Answer 6

```python
marks = 75

is_pass = marks >= 40

print(is_pass)
```

Output:

```text
True
```

## 16. Chapter Summary

- Condition কোনো নির্দিষ্ট শর্ত যাচাই করে।
- Boolean data type-এর value হলো `True` ও `False`।
- Boolean expression evaluate হয়ে Boolean result দেয়।
- Comparison operators দিয়ে condition তৈরি করা যায়।
- Variable ও arithmetic expression ব্যবহার করেও condition তৈরি করা যায়।
- `and`, `or` ও `not` দিয়ে logical expressions তৈরি করা যায়।
- Boolean result variable-এ store করে পরে ব্যবহার করা যায়।
- Expression value তৈরি করে; statement program-কে কাজ করতে নির্দেশ দেয়।
- Python-এ `True` ও `False`-এর capitalization সঠিক রাখতে হয়।

## 17. Self-Assessment Checklist

- [ ] Condition কী, তা ব্যাখ্যা করতে পারি।
- [ ] Boolean data type ও Boolean expression-এর পার্থক্য বুঝি।
- [ ] `True` ও `False`-এর result predict করতে পারি।
- [ ] Comparison operators ব্যবহার করে condition তৈরি করতে পারি।
- [ ] `and`, `or` ও `not` দিয়ে logical expression লিখতে পারি।
- [ ] Boolean result variable-এ store করতে পারি।
- [ ] Expression ও statement-এর পার্থক্য বুঝি।
- [ ] Common Boolean expression errors শনাক্ত করতে পারি।

## 18. Next Topic

পরবর্তী file:

`04_Comparison_Operators_in_Conditions.md`

সেখানে `==`, `!=`, `>`, `<`, `>=` এবং `<=` operator-এর ব্যবহার, উদাহরণ, common mistakes ও practice exercises বিস্তারিতভাবে শেখানো হবে।