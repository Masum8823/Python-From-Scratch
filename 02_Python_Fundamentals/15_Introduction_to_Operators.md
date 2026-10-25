# 15. Introduction to Operators in Python

## 1. Introduction

Python-এ **Operator** হলো special symbol বা keyword, যা value বা variable-এর ওপর নির্দিষ্ট operation সম্পন্ন করে।

উদাহরণ:

```python
a = 10
b = 5

print(a + b)
print(a > b)
```

Output:

```text
15
True
```

এখানে:

- `+` হলো arithmetic operator।
- `>` হলো comparison operator।
- `=` হলো assignment operator।

এই topic-এ আমরা শিখব:

- Operator ও operand
- Arithmetic operators
- Assignment operators
- Comparison operators
- Logical operators
- Bitwise operators
- Membership operators
- Identity operators
- Operator-এর practical use ও common mistakes

## 2. Operator and Operand

Operator কীভাবে কাজ করে, তা বোঝার জন্য operator ও operand-এর ধারণা জানতে হবে।

```python
a = 10 + 5
```

এখানে:

- `10` এবং `5` হলো operands।
- `+` হলো operator।
- `15` হলো operation-এর result।

### Types Based on Number of Operands

**Unary operator:** একটি operand-এর ওপর কাজ করে।

```python
x = 10

print(-x)
print(not True)
```

Output:

```text
-10
False
```

**Binary operator:** দুটি operand-এর ওপর কাজ করে।

```python
print(10 + 5)
print(10 > 5)
```

Output:

```text
15
True
```

Python-এ operator-এর আরও জটিল ব্যবহার রয়েছে, তবে শুরুতে unary ও binary operator বোঝা যথেষ্ট।

## 3. Types of Operators in Python

Python-এর গুরুত্বপূর্ণ operator category-গুলো হলো:

| Category | Main Operators | Purpose |
|---|---|---|
| Arithmetic | `+`, `-`, `*`, `/`, `//`, `%`, `**` | Mathematical calculations |
| Assignment | `=`, `+=`, `-=`, `*=`, `/=` | Value assign বা update করা |
| Comparison | `==`, `!=`, `>`, `<`, `>=`, `<=` | Value তুলনা করা |
| Logical | `and`, `or`, `not` | Logical conditions |
| Bitwise | `&`, `|`, `^`, `~`, `<<`, `>>` | Integer-এর binary bits নিয়ে কাজ |
| Membership | `in`, `not in` | Collection-এর মধ্যে item খোঁজা |
| Identity | `is`, `is not` | একই object কি না পরীক্ষা করা |

এখন প্রতিটি category উদাহরণসহ আলোচনা করা যাক।

## 4. Arithmetic Operators

Arithmetic operators ব্যবহার করে mathematical calculation করা হয়।

ধরি:

```python
a = 10
b = 3
```

### 4.1 Addition (`+`)

দুটি value যোগ করে।

```python
print(a + b)
```

Output:

```text
13
```

### 4.2 Subtraction (`-`)

একটি value থেকে অন্যটি বিয়োগ করে।

```python
print(a - b)
```

Output:

```text
7
```

### 4.3 Multiplication (`*`)

দুটি value গুণ করে।

```python
print(a * b)
```

Output:

```text
30
```

### 4.4 Division (`/`)

একটি value-কে অন্যটি দিয়ে ভাগ করে।

```python
print(a / b)
```

Output:

```text
3.3333333333333335
```

`/` ব্যবহার করলে সাধারণত floating-point result পাওয়া যায়।

### 4.5 Floor Division (`//`)

ভাগফলকে নিচের integer-এর দিকে floor করে।

```python
print(a // b)
print(-10 // 3)
```

Output:

```text
3
-4
```

মনে রাখবে, negative number-এর ক্ষেত্রে floor division শূন্যের দিকে truncate করে না।

### 4.6 Modulus (`%`)

ভাগশেষ বের করে।

```python
print(a % b)
```

Output:

```text
1
```

### 4.7 Exponentiation (`**`)

Power হিসাব করে।

```python
print(2 ** 3)
```

Output:

```text
8
```

### Arithmetic Operators Summary

| Operator | Meaning | Example | Result |
|---|---|---|---:|
| `+` | Addition | `10 + 3` | 13 |
| `-` | Subtraction | `10 - 3` | 7 |
| `*` | Multiplication | `10 * 3` | 30 |
| `/` | Division | `10 / 3` | Approximately 3.333 |
| `//` | Floor division | `10 // 3` | 3 |
| `%` | Modulus | `10 % 3` | 1 |
| `**` | Exponentiation | `2 ** 3` | 8 |

### Practical Example

```python
price = 250
quantity = 4

total = price * quantity
discount = 100
final_bill = total - discount

print("Total:", total)
print("Final Bill:", final_bill)
```

Output:

```text
Total: 1000
Final Bill: 900
```

## 5. Assignment Operators

Assignment operators variable-এর সঙ্গে value bind করতে অথবা variable-এর বর্তমান value update করতে ব্যবহৃত হয়।

### 5.1 Simple Assignment (`=`)

```python
x = 10

print(x)
```

Output:

```text
10
```

এখানে `x` নামটি `10`-কে refer করছে।

### 5.2 Addition Assignment (`+=`)

```python
x = 10
x += 5

print(x)
```

Output:

```text
15
```

সাধারণ numeric ক্ষেত্রে এটি `x = x + 5`-এর সমতুল্য।

### 5.3 Other Augmented Assignment Operators

```python
x = 20
x -= 5
print(x)
```

Output:

```text
15
```

```python
x = 5
x *= 3
print(x)
```

Output:

```text
15
```

```python
x = 20
x /= 4
print(x)
```

Output:

```text
5.0
```

```python
x = 17
x //= 5
print(x)
```

Output:

```text
3
```

```python
x = 17
x %= 5
print(x)
```

Output:

```text
2
```

```python
x = 2
x **= 3
print(x)
```

Output:

```text
8
```

### Assignment Operators Summary

| Operator | General Numeric Equivalent |
|---|---|
| `=` | `x = value` |
| `+=` | `x = x + value` |
| `-=` | `x = x - value` |
| `*=` | `x = x * value` |
| `/=` | `x = x / value` |
| `//=` | `x = x // value` |
| `%=` | `x = x % value` |
| `**=` | `x = x ** value` |

Python-এ bitwise augmented assignment-ও রয়েছে, যেমন `&=`, `|=`, `^=`, `<<=` এবং `>>=`।

**গুরুত্বপূর্ণ:** `=` এবং `==` এক নয়। `=` assignment করে, আর `==` equality পরীক্ষা করে।

## 6. Comparison Operators

Comparison operators দুটি value তুলনা করে এবং Boolean result দেয়।

ধরি:

```python
a = 10
b = 5
```

### Examples

```python
print(a == b)
print(a != b)
print(a > b)
print(a < b)
print(a >= b)
print(a <= b)
```

Output:

```text
False
True
True
False
True
False
```

### Comparison Operators Summary

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `==` | Equal to | `10 == 10` | `True` |
| `!=` | Not equal to | `10 != 5` | `True` |
| `>` | Greater than | `10 > 5` | `True` |
| `<` | Less than | `5 < 10` | `True` |
| `>=` | Greater than or equal to | `10 >= 10` | `True` |
| `<=` | Less than or equal to | `5 <= 3` | `False` |

### Chained Comparison

Python-এ একাধিক comparison একসঙ্গে লেখা যায়।

```python
age = 22

print(18 <= age <= 60)
```

Output:

```text
True
```

এটি বোঝায়, `age` একই সঙ্গে `18` বা তার বেশি এবং `60` বা তার কম কি না।

## 7. Logical Operators

Logical operators condition-এর ওপর কাজ করে।

Python-এ তিনটি প্রধান logical operator রয়েছে:

- `and`
- `or`
- `not`

### 7.1 `and`

দুটি condition-ই সত্য হলে result সত্য হয়।

```python
age = 22
has_id = True

print(age >= 18 and has_id)
```

Output:

```text
True
```

### 7.2 `or`

অন্তত একটি condition সত্য হলে result সত্য হয়।

```python
is_weekend = False
is_holiday = True

print(is_weekend or is_holiday)
```

Output:

```text
True
```

### 7.3 `not`

Result-এর truth value উল্টে দেয়।

```python
is_active = True

print(not is_active)
```

Output:

```text
False
```

### Logical Operators Truth Table

| A | B | `A and B` | `A or B` |
|---|---|---|---|
| `True` | `True` | `True` | `True` |
| `True` | `False` | `False` | `True` |
| `False` | `True` | `False` | `True` |
| `False` | `False` | `False` | `False` |

`not True` হলো `False` এবং `not False` হলো `True`।

### Practical Example

```python
marks = 85
attendance = 90

eligible = marks >= 40 and attendance >= 75

print(eligible)
```

Output:

```text
True
```

এখানে দুইটি condition সত্য হলেই `eligible`-এর result `True` হবে।

**মনে রাখবে:** Python-এর `and` ও `or` সবসময় Boolean object return করে না; operand-এর value-ও return করতে পারে। এদের short-circuit behavior রয়েছে।

## 8. Bitwise Operators

Bitwise operators integer-এর binary representation-এর bit নিয়ে কাজ করে।

এগুলো binary number এবং low-level programming বুঝতে গুরুত্বপূর্ণ।

ধরি:

```python
a = 5
b = 3
```

Binary representation:

```text
5 = 0101
3 = 0011
```

বোঝার সুবিধার জন্য এখানে চারটি bit দেখানো হয়েছে।

### 8.1 Bitwise AND (`&`)

দুটি bit-ই `1` হলে result bit `1` হয়।

```python
print(5 & 3)
```

Output:

```text
1
```

Binary operation:

```text
  0101
& 0011
------
  0001
```

### 8.2 Bitwise OR (`|`)

যেকোনো একটি bit `1` হলে result bit `1` হয়।

```python
print(5 | 3)
```

Output:

```text
7
```

Binary operation:

```text
  0101
| 0011
------
  0111
```

### 8.3 Bitwise XOR (`^`)

দুটি bit আলাদা হলে result bit `1` হয়।

```python
print(5 ^ 3)
```

Output:

```text
6
```

Binary operation:

```text
  0101
^ 0011
------
  0110
```

### 8.4 Bitwise NOT (`~`)

প্রতিটি bit-এর complement প্রকাশ করে। Python integer-এর ক্ষেত্রে negative value-সহ result পাওয়া যায়।

```python
print(~5)
```

Output:

```text
-6
```

Python integer-এর জন্য `~x`-এর result `-(x + 1)`।

### 8.5 Left Shift (`<<`)

Bit-গুলোকে বাম দিকে সরায়।

```python
print(5 << 1)
```

Output:

```text
10
```

এখানে `5`-এর binary bit এক ঘর বামে shift হয়েছে।

### 8.6 Right Shift (`>>`)

Bit-গুলোকে ডান দিকে সরায়।

```python
print(5 >> 1)
```

Output:

```text
2
```

### Bitwise Operators Summary

| Operator | Meaning | Example | Result |
|---|---|---|---:|
| `&` | Bitwise AND | `5 & 3` | 1 |
| `|` | Bitwise OR | `5 | 3` | 7 |
| `^` | Bitwise XOR | `5 ^ 3` | 6 |
| `~` | Bitwise NOT | `~5` | -6 |
| `<<` | Left shift | `5 << 1` | 10 |
| `>>` | Right shift | `5 >> 1` | 2 |

**সতর্কতা:** Bitwise operator এবং logical operator এক নয়। `&` ও `|` bit নিয়ে কাজ করে; `and` ও `or` truth value এবং operand-এর ওপর কাজ করে।

## 9. Membership Operators

কোনো item একটি collection বা sequence-এর মধ্যে আছে কি না পরীক্ষা করতে membership operators ব্যবহার করা হয়।

দুটি membership operator:

- `in`
- `not in`

### 9.1 `in`

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

### 9.2 `not in`

```python
languages = ["Python", "Java", "C++"]

print("PHP" not in languages)
```

Output:

```text
True
```

### Membership in a String

```python
text = "Python Programming"

print("Python" in text)
print("Java" in text)
```

Output:

```text
True
False
```

### Membership in a Dictionary

Dictionary-তে membership operator সাধারণত key পরীক্ষা করে।

```python
student = {
    "name": "Masum",
    "department": "CSE"
}

print("name" in student)
print("Masum" in student)
```

Output:

```text
True
False
```

এখানে `"Masum"` value, key নয়। Dictionary-এর value পরীক্ষা করতে `student.values()` ব্যবহার করা যায়।

## 10. Identity Operators

Identity operators দুটি reference একই object-কে নির্দেশ করছে কি না পরীক্ষা করে।

দুটি identity operator:

- `is`
- `is not`

### 10.1 `is`

```python
a = None

print(a is None)
```

Output:

```text
True
```

### 10.2 `is not`

```python
a = 10

print(a is not None)
```

Output:

```text
True
```

### Equality vs Identity

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

ব্যাখ্যা:

- `a == b` — দুটি list-এর value সমান কি না পরীক্ষা করে।
- `a is b` — দুটি variable একই list object-কে refer করছে কি না পরীক্ষা করে।

সাধারণ value comparison-এর জন্য `==` ব্যবহার করবে। `is` ব্যবহার করবে object identity পরীক্ষা করতে, বিশেষ করে `None`-এর সঙ্গে comparison-এর ক্ষেত্রে।

## 11. Special Note: `+` and `*` Can Behave Differently by Type

একই operator ভিন্ন data type-এর ক্ষেত্রে ভিন্ন কাজ করতে পারে।

### Addition with Numbers

```python
print(10 + 5)
```

Output:

```text
15
```

### Addition with Strings

```python
print("Hello " + "Python")
```

Output:

```text
Hello Python
```

এখানে `+` string concatenate করেছে।

### Multiplication with a String

```python
print("Hi " * 3)
```

Output:

```text
Hi Hi Hi 
```

এখানে string তিনবার repeat হয়েছে।

অর্থাৎ, operator-এর behavior operand-এর data type-এর ওপর নির্ভর করতে পারে।

## 12. Operator Precedence: A Basic Introduction

একটি expression-এ একাধিক operator থাকলে কোন operator আগে কাজ করবে, সেটি operator precedence দিয়ে নির্ধারিত হয়।

উদাহরণ:

```python
result = 10 + 5 * 2

print(result)
```

Output:

```text
20
```

এখানে multiplication আগে হয়েছে, তারপর addition।

Parentheses ব্যবহার করলে order স্পষ্ট করা যায়:

```python
result = (10 + 5) * 2

print(result)
```

Output:

```text
30
```

Operator precedence ও associativity পরবর্তী ফাইলে আরও বিস্তারিতভাবে আলোচনা করা হবে।

## 13. Common Mistakes

### Mistake 1: Confusing `=` and `==`

ভুল:

```python
# if age = 18:
#     print("Eligible")
```

সঠিক:

```python
age = 18

if age == 18:
    print("Eligible")
```

Output:

```text
Eligible
```

### Mistake 2: Confusing `and` with `&`

```python
a = True
b = False

print(a and b)
print(a & b)
```

এই Boolean example-এ দুটিই `False` দেবে, কিন্তু তাদের semantics আলাদা। `and` logical short-circuit operator, আর `&` bitwise operator; `&` Boolean value-এর সঙ্গেও কাজ করতে পারে।

### Mistake 3: Using `is` for Ordinary Value Comparison

ভুল practice:

```python
a = 1000
b = 1000

# Value equality check-এর জন্য:
print(a == b)
```

Value তুলনা করতে `==` ব্যবহার করাই সঠিক। `is` দিয়ে identity পরীক্ষা করতে হবে; ছোট integer বা string-এর identity আচরণের ওপর নির্ভর করা উচিত নয়।

### Mistake 4: Dividing by Zero

```python
# print(10 / 0)
```

এটি `ZeroDivisionError` তৈরি করবে।

### Mistake 5: Incorrect Dictionary Membership Check

```python
student = {"name": "Masum"}

print("Masum" in student)
```

Output:

```text
False
```

কারণ dictionary membership সাধারণত key পরীক্ষা করে, value নয়।

সঠিক:

```python
print("Masum" in student.values())
```

Output:

```text
True
```

## 14. Practical Example: Student Eligibility Checker

এই example-এ arithmetic, comparison এবং logical operators একসঙ্গে ব্যবহার করা হয়েছে।

```python
student_name = "Masum"

marks = 85
attendance = 90
minimum_marks = 40
minimum_attendance = 75

percentage = marks / 100 * 100

eligible = (
    marks >= minimum_marks
    and attendance >= minimum_attendance
)

print("Student:", student_name)
print("Percentage:", percentage)
print("Eligible:", eligible)
```

Output:

```text
Student: Masum
Percentage: 85.0
Eligible: True
```

এখানে:

- `/` এবং `*` arithmetic operation করেছে।
- `>=` comparison করেছে।
- `and` দুইটি condition একত্র করেছে।
- `=` variable-এর সঙ্গে result bind করেছে।

## 15. Practice Exercises

### Exercise 1: Arithmetic Operators

নিচের expression-গুলোর result বের করো:

```python
print(15 + 5)
print(15 - 5)
print(15 * 5)
print(15 / 5)
print(17 // 5)
print(17 % 5)
print(2 ** 5)
```

### Exercise 2: Assignment Operators

```python
x = 10
x += 5
x *= 2
x -= 4

print(x)
```

Final output কী হবে?

### Exercise 3: Comparison Operators

```python
a = 20
b = 10

print(a == b)
print(a != b)
print(a > b)
print(a <= b)
```

প্রতিটি result ব্যাখ্যা করো।

### Exercise 4: Logical Operators

```python
age = 22
has_id = True

print(age >= 18 and has_id)
print(age < 18 or has_id)
print(not has_id)
```

Output অনুমান করো।

### Exercise 5: Bitwise Operators

```python
print(5 & 3)
print(5 | 3)
print(5 ^ 3)
print(5 << 1)
print(5 >> 1)
```

প্রতিটি result binary representation ব্যবহার করে ব্যাখ্যা করার চেষ্টা করো।

### Exercise 6: Membership Operators

```python
languages = ["Python", "Java", "C++"]

print("Python" in languages)
print("PHP" not in languages)
```

Output নির্ণয় করো।

### Exercise 7: Identity Operators

```python
a = [1, 2]
b = [1, 2]

print(a == b)
print(a is b)
```

দুটি result-এর পার্থক্য ব্যাখ্যা করো।

### Exercise 8: Mini Calculator

দুটি number নিয়ে arithmetic operators ব্যবহার করে যোগ, বিয়োগ, গুণ, ভাগ, floor division এবং modulus বের করো।

## 16. Quick Revision

| Operator Category | Operators | Main Purpose |
|---|---|---|
| Arithmetic | `+`, `-`, `*`, `/`, `//`, `%`, `**` | Calculation |
| Assignment | `=`, `+=`, `-=`, `*=`, `/=` | Assign/update |
| Comparison | `==`, `!=`, `>`, `<`, `>=`, `<=` | Value comparison |
| Logical | `and`, `or`, `not` | Conditions |
| Bitwise | `&`, `|`, `^`, `~`, `<<`, `>>` | Binary bit operations |
| Membership | `in`, `not in` | Item membership |
| Identity | `is`, `is not` | Object identity |

## 17. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Operator হলো symbol বা keyword, যা operand-এর ওপর operation করে।
- Arithmetic operators mathematical calculation করে।
- Assignment operators value assign বা update করে।
- Comparison operators তুলনা করে Boolean result দেয়।
- Logical operators condition combine বা invert করে।
- Bitwise operators integer-এর binary bit নিয়ে কাজ করে।
- Membership operators collection-এর মধ্যে item আছে কি না পরীক্ষা করে।
- Identity operators দুটি reference একই object নির্দেশ করে কি না পরীক্ষা করে।
- একই operator ভিন্ন data type-এর ক্ষেত্রে ভিন্ন কাজ করতে পারে।
- Operator precedence expression-এর evaluation order নির্ধারণ করে।

## 18. Next Topic

পরবর্তী ফাইল: [`16_Operator_Precedence_and_Associativity.md`](16_Operator_Precedence_and_Associativity.md)

সেখানে operator precedence, associativity, parentheses, left-to-right ও right-to-left evaluation এবং complex expression ধাপে ধাপে solve করার নিয়ম আলোচনা করা হবে।