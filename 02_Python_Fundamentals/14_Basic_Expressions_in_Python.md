# 14. Basic Expressions in Python

## 1. Introduction

Python-এ **Expression** হলো code-এর এমন একটি অংশ, যেটি evaluate করলে একটি value পাওয়া যায়।

উদাহরণ:

```python
10 + 5
```

এখানে `10 + 5` একটি expression। এটি evaluate করলে `15` পাওয়া যায়।

আরও কিছু উদাহরণ:

```python
100
x
10 * 5
"Hello" + " Python"
10 > 5
```

এগুলো প্রত্যেকটি expression, কারণ এগুলো থেকে একটি value পাওয়া যায়।

এই topic-এ আমরা শিখব:

- Expression কী
- Expression কীভাবে evaluate হয়
- Arithmetic expressions
- Comparison expressions
- Logical expressions
- String expressions
- Variable ও function ব্যবহার করে expression
- Operator precedence
- Common errors এবং practice exercises

## 2. What Is an Expression?

Expression হলো value, variable, operator, function call অথবা এদের সমন্বয়ে তৈরি code-এর এমন অংশ, যেটি evaluate করলে একটি result পাওয়া যায়।

উদাহরণ:

```python
x = 10
y = 20

result = x + y

print(result)
```

Output:

```text
30
```

এখানে `x + y` হলো expression। এটি evaluate হয়ে `30` result দেয়।

### More Examples

| Expression | Result |
|---|---|
| `10 + 5` | `15` |
| `20 - 8` | `12` |
| `4 * 3` | `12` |
| `10 > 5` | `True` |
| `"Py" + "thon"` | `"Python"` |
| `len("Python")` | `6` |

**মনে রাখবে:** Expression-এর result সবসময় সংখ্যা হতে হবে না। এটি string, Boolean, list অথবা অন্য কোনো object-ও হতে পারে।

## 3. Expression vs Statement

Expression এবং statement-এর পার্থক্য বোঝা গুরুত্বপূর্ণ।

### Expression

যে code evaluate করলে একটি value পাওয়া যায়।

```python
10 + 20
```

Result: `30`

### Statement

Statement হলো Python-এর এমন একটি instruction, যা কোনো কাজ সম্পন্ন করে।

```python
x = 10
```

এটি একটি assignment statement। এটি `x`-এর সঙ্গে `10` object-কে bind করে।

### Comparison Table

| Expression | Statement |
|---|---|
| Value তৈরি বা নির্ধারণ করে | কোনো instruction সম্পন্ন করে |
| `10 + 20` | `x = 10` |
| `x > 5` | `if x > 5:` |
| `len("Python")` | `print("Python")` |

কিছু statement-এর মধ্যে expression থাকে।

উদাহরণ:

```python
x = 10 + 20
```

এখানে:

- `10 + 20` হলো expression।
- `x = 10 + 20` হলো assignment statement।

## 4. How Python Evaluates an Expression

Python expression evaluate করে result নির্ধারণ করে। Expression-এর মধ্যে একাধিক operator থাকলে operator precedence ও associativity অনুযায়ী কাজ হয়।

উদাহরণ:

```python
result = 10 + 5 * 2

print(result)
```

Output:

```text
20
```

কেন?

1. `5 * 2` আগে calculate হয়।
2. এরপর `10 + 10` calculate হয়।
3. Final result হয় `20`।

অন্যদিকে parentheses ব্যবহার করলে calculation-এর order পরিবর্তন করা যায়।

```python
result = (10 + 5) * 2

print(result)
```

Output:

```text
30
```

এখানে parentheses-এর ভেতরের addition আগে হয়েছে।

## 5. Arithmetic Expressions

Arithmetic expression ব্যবহার করে mathematical calculation করা হয়।

### 5.1 Addition (`+`)

```python
result = 10 + 5

print(result)
```

Output:

```text
15
```

### 5.2 Subtraction (`-`)

```python
result = 10 - 5

print(result)
```

Output:

```text
5
```

### 5.3 Multiplication (`*`)

```python
result = 10 * 5

print(result)
```

Output:

```text
50
```

### 5.4 Division (`/`)

```python
result = 10 / 4

print(result)
```

Output:

```text
2.5
```

Python-এ `/` ব্যবহার করলে সাধারণত floating-point result পাওয়া যায়।

### 5.5 Floor Division (`//`)

```python
result = 10 // 4

print(result)
```

Output:

```text
2
```

Floor division result-কে নিচের পূর্ণসংখ্যার দিকে নামায়। Negative number-এর ক্ষেত্রে এটি শূন্যের দিকে নয়, বরং negative infinity-এর দিকে floor করে।

উদাহরণ:

```python
print(-10 // 4)
```

Output:

```text
-3
```

### 5.6 Modulus (`%`)

Modulus operator ভাগশেষ বের করে।

```python
result = 10 % 3

print(result)
```

Output:

```text
1
```

### 5.7 Exponentiation (`**`)

Exponentiation operator power হিসাব করে।

```python
result = 2 ** 3

print(result)
```

Output:

```text
8
```

### Arithmetic Operators Summary

| Operator | Meaning | Example | Result |
|---|---|---|---:|
| `+` | Addition | `10 + 5` | 15 |
| `-` | Subtraction | `10 - 5` | 5 |
| `*` | Multiplication | `10 * 5` | 50 |
| `/` | Division | `10 / 4` | 2.5 |
| `//` | Floor division | `10 // 4` | 2 |
| `%` | Modulus | `10 % 3` | 1 |
| `**` | Exponentiation | `2 ** 3` | 8 |

## 6. Expressions Using Variables

Expression-এ সরাসরি value-এর পরিবর্তে variable ব্যবহার করা যায়।

উদাহরণ:

```python
price = 100
quantity = 3

total = price * quantity

print(total)
```

Output:

```text
300
```

এখানে `price * quantity` একটি expression।

Python variable-এর বর্তমান value ব্যবহার করে expression evaluate করেছে।

### Multiple Variables in an Expression

```python
a = 10
b = 20
c = 5

result = a + b - c

print(result)
```

Output:

```text
25
```

এখানে `a + b - c` evaluate হয়ে `25` result দিয়েছে।

## 7. Comparison Expressions

Comparison expression দুটি value-এর মধ্যে তুলনা করে এবং Boolean result দেয়—`True` অথবা `False`।

### Comparison Operators

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `==` | Equal to | `10 == 10` | `True` |
| `!=` | Not equal to | `10 != 5` | `True` |
| `>` | Greater than | `10 > 5` | `True` |
| `<` | Less than | `5 < 10` | `True` |
| `>=` | Greater than or equal to | `10 >= 10` | `True` |
| `<=` | Less than or equal to | `5 <= 3` | `False` |

উদাহরণ:

```python
age = 22

print(age >= 18)
print(age < 18)
```

Output:

```text
True
False
```

### Chained Comparisons

Python-এ একাধিক comparison একসঙ্গে লেখা যায়।

```python
age = 22

print(18 <= age <= 60)
```

Output:

```text
True
```

এটি নিচের logical expression-এর সমতুল্য:

```python
18 <= age and age <= 60
```

এভাবে range check করা সহজ হয়।

## 8. Logical Expressions

Logical expression-এ `and`, `or` ও `not` ব্যবহার করে এক বা একাধিক condition নিয়ে কাজ করা হয়।

### 8.1 `and`

দুটি condition-ই সত্য হলে result সত্য হয়।

```python
age = 22
has_id = True

result = age >= 18 and has_id

print(result)
```

Output:

```text
True
```

### 8.2 `or`

অন্তত একটি condition সত্য হলে result সত্য হয়।

```python
is_weekend = False
is_holiday = True

result = is_weekend or is_holiday

print(result)
```

Output:

```text
True
```

### 8.3 `not`

Boolean result উল্টে দেয়।

```python
is_active = True

print(not is_active)
```

Output:

```text
False
```

### Truth Table

| A | B | `A and B` | `A or B` |
|---|---|---|---|
| `True` | `True` | `True` | `True` |
| `True` | `False` | `False` | `True` |
| `False` | `True` | `False` | `True` |
| `False` | `False` | `False` | `False` |

`not True` হলো `False`, আর `not False` হলো `True`।

### Important: Logical Operators Can Return Non-Boolean Values

Python-এ `and` ও `or` সবসময় `True` বা `False` return করে না। এগুলো operand-এর কোনো একটি value return করতে পারে।

উদাহরণ:

```python
print(0 or 10)
print(5 and 20)
```

Output:

```text
10
20
```

এখানে `0` false-like এবং `10` true-like, তাই `0 or 10` result হিসেবে `10` দিয়েছে।

`5 and 20`-এ প্রথম value true-like হওয়ায় শেষ operand `20` result হিসেবে পাওয়া গেছে।

এটি Python-এর short-circuit evaluation-এর অংশ। Beginner হিসেবে প্রথমে Boolean condition-এর ব্যবহার ভালোভাবে বোঝো; পরে এটি আরও কাজে লাগবে।

## 9. String Expressions

String expression ব্যবহার করে text একত্র করা, পুনরাবৃত্তি করা বা তুলনা করা যায়।

### 9.1 String Concatenation

`+` operator দিয়ে দুটি string একত্র করা যায়।

```python
first_name = "Abdulla"
last_name = "Masum"

full_name = first_name + " " + last_name

print(full_name)
```

Output:

```text
Abdulla Masum
```

### 9.2 String Repetition

`*` operator দিয়ে string পুনরাবৃত্তি করা যায়।

```python
message = "Python "

print(message * 3)
```

Output:

```text
Python Python Python 
```

### 9.3 String Comparison

```python
print("Python" == "Python")
print("Python" == "python")
```

Output:

```text
True
False
```

String comparison case-sensitive। তাই `"Python"` এবং `"python"` সমান নয়।

### 9.4 Mixing Strings and Numbers

নিচের code-টি error তৈরি করবে:

```python
age = 22

# print("Age: " + age)
```

কারণ string-এর সঙ্গে integer সরাসরি `+` দিয়ে concatenate করা যায় না।

সঠিক উপায়:

```python
age = 22

print("Age:", age)
print("Age: " + str(age))
print(f"Age: {age}")
```

Output:

```text
Age: 22
Age: 22
Age: 22
```

F-string সাধারণত text-এর সঙ্গে variable-এর value প্রকাশ করার একটি পরিষ্কার উপায়।

## 10. Membership Expressions

`in` এবং `not in` ব্যবহার করে কোনো item একটি collection বা sequence-এর মধ্যে আছে কি না পরীক্ষা করা যায়।

### Using `in`

```python
languages = ["Python", "Java", "C++"]

print("Python" in languages)
print("PHP" in languages)
```

Output:

```text
True
False
```

### Using `not in`

```python
text = "Python Programming"

print("Java" not in text)
```

Output:

```text
True
```

Membership operator list, tuple, set, dictionary এবং string-এর মতো data type-এর সঙ্গে ব্যবহার করা যায়। Dictionary-তে `in` সাধারণত key পরীক্ষা করে।

## 11. Identity Expressions

`is` এবং `is not` operator দুটি object একই object কি না পরীক্ষা করে।

উদাহরণ:

```python
result = None

print(result is None)
print(result is not None)
```

Output:

```text
True
False
```

এখানে `is None` ব্যবহার করা সঠিক ও প্রচলিত practice।

### Equality vs Identity

- `==` দুটি value সমান কি না পরীক্ষা করে।
- `is` দুটি reference একই object-কে নির্দেশ করছে কি না পরীক্ষা করে।

উদাহরণ:

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

দুটি list-এর value সমান, কিন্তু তারা আলাদা list object।

সাধারণ value comparison-এর জন্য `==` ব্যবহার করো। Object identity পরীক্ষা করার প্রয়োজন হলেই `is` ব্যবহার করো।

## 12. Function Calls as Expressions

Function call-এর result-ও expression-এর মধ্যে ব্যবহার করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 30]

result = len(numbers) + 5

print(result)
```

Output:

```text
8
```

এখানে:

1. `len(numbers)` evaluate হয়ে `3` দেয়।
2. `3 + 5` evaluate হয়ে `8` হয়।
3. `result`-এ `8` assign হয়।

আরেকটি উদাহরণ:

```python
name = "masum"

print(name.upper())
```

Output:

```text
MASUM
```

এখানে `name.upper()` একটি function বা method call expression।

## 13. Conditional Expressions

Python-এ condition অনুযায়ী expression-এর result নির্বাচন করতে conditional expression ব্যবহার করা যায়।

Syntax:

```python
value_if_true if condition else value_if_false
```

উদাহরণ:

```python
age = 22

status = "Adult" if age >= 18 else "Minor"

print(status)
```

Output:

```text
Adult
```

এখানে:

- `age >= 18` সত্য হলে `"Adult"` result হবে।
- অন্যথায় `"Minor"` result হবে।

এটি ছোট expression-এর জন্য উপযোগী। জটিল condition হলে সাধারণ `if-else` statement বেশি readable হতে পারে।

## 14. Operator Precedence in Expressions

একটি expression-এ একাধিক operator থাকলে কোন operator আগে কাজ করবে, সেটিকে operator precedence বলা হয়।

উদাহরণ:

```python
result = 10 + 5 * 2

print(result)
```

Output:

```text
20
```

Multiplication আগে হয়েছে, তারপর addition।

### Common Precedence Order

নিচের তালিকাটি সাধারণ operators-এর উচ্চ থেকে নিম্ন precedence দেখায়। এটি সম্পূর্ণ তালিকা নয়।

| Priority | Operators | Example |
|---|---|---|
| Higher | Parentheses `()` | `(2 + 3)` |
| High | Exponentiation `**` | `2 ** 3` |
| High | Unary `+`, `-`, `~` | `-5` |
| Medium | `*`, `/`, `//`, `%` | `10 * 2` |
| Medium | `+`, `-` | `10 + 5` |
| Lower | Comparisons, `in`, `is` | `x >= 10` |
| Lower | `not` | `not x` |
| Lower | `and` | `a and b` |
| Lower | `or` | `a or b` |

### Using Parentheses

Expression পরিষ্কার রাখতে parentheses ব্যবহার করা যায়।

```python
result = (10 + 5) * 2

print(result)
```

Output:

```text
30
```

Parentheses শুধু precedence পরিবর্তন করে না, code পড়াও সহজ করে।

### Exponentiation and Unary Minus

Python-এ exponentiation এবং unary minus-এর precedence কিছুটা বিশেষ।

```python
print(-2 ** 2)
print((-2) ** 2)
```

Output:

```text
-4
4
```

প্রথম expression-টি `-(2 ** 2)` হিসেবে evaluate হয়। দ্বিতীয়টিতে `-2`-এর square করা হয়েছে।

## 15. Expressions Inside Assignment Statements

Expression-এর result variable-এ assign করা যায়।

```python
a = 10
b = 20

sum_result = a + b
difference = b - a
product = a * b

print(sum_result)
print(difference)
print(product)
```

Output:

```text
30
10
200
```

এখানে প্রতিটি assignment statement-এর ডান পাশে একটি expression রয়েছে।

### Assignment Does Not Mean Mathematical Equality

```python
x = 10
x = x + 5

print(x)
```

Output:

```text
15
```

Mathematics-এ `x = x + 5` সাধারণ সমীকরণ হিসেবে সমাধানযোগ্য নয়। কিন্তু programming-এ এর অর্থ হলো:

1. বর্তমান `x`-এর value নেওয়া।
2. তার সঙ্গে `5` যোগ করা।
3. result আবার `x`-এর সঙ্গে assign করা।

## 16. Common Expression Errors

### Error 1: Division by Zero

```python
# result = 10 / 0
```

এটি execute করলে `ZeroDivisionError` হবে।

সঠিকভাবে কাজ করার জন্য divisor শূন্য কি না পরীক্ষা করা যায়।

```python
divisor = 2

if divisor != 0:
    result = 10 / divisor
    print(result)
```

Output:

```text
5.0
```

### Error 2: Mixing Incompatible Data Types

```python
# result = "10" + 5
```

এখানে string ও integer সরাসরি যোগ করা যায় না। এতে `TypeError` হবে।

সঠিক:

```python
result = int("10") + 5

print(result)
```

Output:

```text
15
```

### Error 3: Using `=` Instead of `==`

ভুল:

```python
# if x = 10:
#     print("Ten")
```

সঠিক:

```python
x = 10

if x == 10:
    print("Ten")
```

Output:

```text
Ten
```

### Error 4: Forgetting Operator Precedence

```python
result = 2 + 3 * 4

print(result)
```

Output:

```text
14
```

যদি আগে addition করতে চাও:

```python
result = (2 + 3) * 4

print(result)
```

Output:

```text
20
```

### Error 5: Comparing Values with the Wrong Operator

```python
age = 22

print(age = 22)
```

এটি invalid syntax, কারণ function call-এর argument হিসেবে `age = 22` সাধারণ assignment statement নয়।

সঠিক:

```python
print(age == 22)
```

Output:

```text
True
```

## 17. Practical Example: Student Result Calculator

এই example-এ arithmetic, comparison, logical এবং conditional expressions একসঙ্গে ব্যবহার করা হয়েছে।

```python
student_name = "Masum"

marks1 = 80
marks2 = 90
marks3 = 85

total = marks1 + marks2 + marks3
average = total / 3

is_passed = marks1 >= 40 and marks2 >= 40 and marks3 >= 40

status = "Passed" if is_passed else "Failed"

print("Student:", student_name)
print("Total Marks:", total)
print("Average Marks:", average)
print("Status:", status)
```

Output:

```text
Student: Masum
Total Marks: 255
Average Marks: 85.0
Status: Passed
```

এখানে:

- `marks1 + marks2 + marks3` হলো arithmetic expression।
- `total / 3` হলো division expression।
- `marks1 >= 40` হলো comparison expression।
- `and` দিয়ে একাধিক condition যুক্ত হয়েছে।
- Conditional expression দিয়ে status নির্বাচন করা হয়েছে।

## 18. Practice Exercises

### Exercise 1: Arithmetic Expressions

নিচের expression-গুলোর result বের করো।

```python
print(15 + 5)
print(20 - 8)
print(6 * 7)
print(20 / 4)
print(17 // 5)
print(17 % 5)
print(2 ** 4)
```

### Exercise 2: Operator Precedence

Output অনুমান করো।

```python
print(2 + 3 * 4)
print((2 + 3) * 4)
print(20 - 6 / 2)
print(2 ** 3 ** 2)
```

### Exercise 3: Comparison Expressions

```python
age = 22

print(age >= 18)
print(age < 18)
print(age == 22)
print(age != 22)
```

প্রতিটি result কেন `True` অথবা `False` হচ্ছে, ব্যাখ্যা করো।

### Exercise 4: Logical Expressions

```python
age = 22
has_id = True

print(age >= 18 and has_id)
print(age < 18 or has_id)
print(not has_id)
```

Output বের করো।

### Exercise 5: String Expressions

দুটি variable-এ first name এবং last name রাখো। `+` অথবা f-string ব্যবহার করে full name তৈরি করো।

### Exercise 6: Membership and Identity

```python
languages = ["Python", "Java", "C++"]

print("Python" in languages)
print("PHP" not in languages)

result = None
print(result is None)
```

প্রতিটি expression-এর অর্থ লেখো।

### Exercise 7: Conditional Expression

একটি `marks` variable তৈরি করো। Marks `40` বা তার বেশি হলে `"Passed"`, অন্যথায় `"Failed"` result দেবে—এমন conditional expression লেখো।

### Exercise 8: Mini Calculator

দুটি number নিয়ে নিচের result-গুলো বের করো:

- Addition
- Subtraction
- Multiplication
- Division
- Floor division
- Modulus

## 19. Quick Revision

| Concept | Example | Result or Purpose |
|---|---|---|
| Expression | `10 + 5` | `15` |
| Arithmetic | `10 * 2` | `20` |
| Comparison | `10 > 5` | `True` |
| Logical | `True and False` | `False` |
| String | `"Py" + "thon"` | `"Python"` |
| Membership | `"Py" in "Python"` | `True` |
| Identity | `x is None` | Object identity পরীক্ষা |
| Function call | `len("Python")` | `6` |
| Conditional | `"Pass" if marks >= 40 else "Fail"` | Condition অনুযায়ী result |
| Precedence | `2 + 3 * 4` | `14` |

## 20. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Expression evaluate করলে একটি value পাওয়া যায়।
- Expression ও statement আলাদা concept।
- Arithmetic expression দিয়ে calculation করা হয়।
- Comparison expression `True` বা `False` result দেয়।
- Logical expression-এ `and`, `or` ও `not` ব্যবহার করা হয়।
- String expression দিয়ে text concatenate, repeat ও compare করা যায়।
- Membership operator `in` এবং `not in` দিয়ে কোনো item আছে কি না পরীক্ষা করা হয়।
- Identity operator `is` ও `is not` object identity পরীক্ষা করে।
- Function call এবং conditional expression-ও expression-এর অংশ হতে পারে।
- Operator precedence expression evaluate হওয়ার order নির্ধারণ করে।
- Parentheses ব্যবহার করলে expression-এর order ও readability নিয়ন্ত্রণ করা যায়।

## 21. Next Topic

পরবর্তী ফাইল: [`15_Introduction_to_Operators.md`](15_Introduction_to_Operators.md)

সেখানে Python-এর operator-গুলোকে category অনুযায়ী সাজিয়ে arithmetic, assignment, comparison, logical, bitwise, membership ও identity operators নিয়ে বিস্তারিত আলোচনা করা হবে।