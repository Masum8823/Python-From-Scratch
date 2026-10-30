# 03. Overview of Python Operators

## 1. Introduction

Python-এ Operators ব্যবহার করে Calculation, Comparison, Logical Decision, Assignment এবং বিভিন্ন ধরনের Data Operation করা হয়।

Operator-এর কাজ অনুযায়ী Python Operators-কে কয়েকটি প্রধান Category-তে ভাগ করা যায়।

এই Topic-এর উদ্দেশ্য হলো সব Category সম্পর্কে একটি পরিষ্কার ধারণা তৈরি করা। প্রতিটি Operator-এর বিস্তারিত আলোচনা পরবর্তী আলাদা ফাইলগুলোতে থাকবে।

## 2. Complete Overview of Python Operators

| Category | Operators | Main Purpose |
|---|---|---|
| Arithmetic | `+`, `-`, `*`, `/`, `//`, `%`, `**` | Mathematical Calculation |
| Comparison | `==`, `!=`, `>`, `<`, `>=`, `<=` | Value তুলনা করা |
| Logical | `and`, `or`, `not` | Conditions Combine বা Reverse করা |
| Assignment | `=`, `+=`, `-=`, `*=`, `/=`, `//=`, `%=`, `**=`, `&=`, `\|=`, `^=`, `>>=`, `<<=`, `@=`, `:=` | Value Assign বা Update করা |
| Identity | `is`, `is not` | একই Object কি না পরীক্ষা করা |
| Membership | `in`, `not in` | কোনো Element আছে কি না পরীক্ষা করা |
| Bitwise | `&`, `\|`, `^`, `~`, `<<`, `>>` | Integer-এর Bits নিয়ে কাজ করা |
| Conditional Expression | `value_if_true if condition else value_if_false` | Condition অনুযায়ী Value নির্বাচন করা |

**Note:** `:=` হলো Assignment Expression Operator, যা Walrus Operator নামেও পরিচিত। এটি Assignment Statement-এর `=` থেকে আলাদা।

## 3. Arithmetic Operators

Arithmetic Operators ব্যবহার করে Mathematical Calculation করা হয়।

| Operator | Name | Example | Result |
|---|---|---|---:|
| `+` | Addition | `10 + 3` | `13` |
| `-` | Subtraction | `10 - 3` | `7` |
| `*` | Multiplication | `10 * 3` | `30` |
| `/` | Division | `10 / 4` | `2.5` |
| `//` | Floor Division | `10 // 3` | `3` |
| `%` | Modulo | `10 % 3` | `1` |
| `**` | Exponentiation | `2 ** 3` | `8` |

Example:

```python id="27hmmj"
a = 10
b = 3

print(a + b)
print(a // b)
print(a % b)
print(a ** b)
```

Output:

```text id="p3fzbe"
13
3
1
1000
```

এখানে `//` Floor Division করে, `%` Remainder দেয় এবং `**` Power হিসাব করে।

## 4. Comparison Operators

Comparison Operators দুটি Value তুলনা করে।

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `==` | Equal To | `5 == 5` | `True` |
| `!=` | Not Equal To | `5 != 3` | `True` |
| `>` | Greater Than | `5 > 3` | `True` |
| `<` | Less Than | `3 < 5` | `True` |
| `>=` | Greater Than or Equal To | `5 >= 5` | `True` |
| `<=` | Less Than or Equal To | `3 <= 5` | `True` |

Example:

```python id="hkm5f4"
marks = 85

print(marks >= 40)
print(marks == 100)
print(marks < 50)
```

Output:

```text id="47j7fr"
True
False
False
```

Comparison Operators-এর Result সাধারণত `bool` Type-এর হয়।

## 5. Logical Operators

Logical Operators Condition-এর ওপর কাজ করে।

| Operator | Meaning |
|---|---|
| `and` | উভয় Operand Truthy হলে শেষ পর্যন্ত Result Truthy হয় |
| `or` | কোনো Operand Truthy হলে সেটি Result হিসেবে পাওয়া যেতে পারে |
| `not` | Truth Value উল্টে দেয় |

Example:

```python id="c7n9za"
age = 22
has_id = True

print(age >= 18 and has_id)
print(age < 18 or has_id)
print(not has_id)
```

Output:

```text id="81l7ax"
True
True
False
```

**Important:** Python-এর `and` এবং `or` সবসময় `True` বা `False` Return করে না। এগুলো Operand-এর Value-ও Return করতে পারে।

Example:

```python id="v00jsw"
print(0 or 10)
print("Python" and "Programming")
```

Output:

```text id="m0vpv9"
10
Programming
```

Logical Operators-এর Truthiness এবং Short-Circuit Evaluation পরবর্তী Topics-এ বিস্তারিত শেখা হবে।

## 6. Assignment Operators

Assignment Operators Variable-এ Value Assign বা Update করতে ব্যবহার করা হয়।

| Operator | Example | Equivalent Form |
|---|---|---|
| `=` | `x = 10` | Value Assign |
| `+=` | `x += 5` | `x = x + 5` |
| `-=` | `x -= 5` | `x = x - 5` |
| `*=` | `x *= 2` | `x = x * 2` |
| `/=` | `x /= 2` | `x = x / 2` |
| `//=` | `x //= 2` | `x = x // 2` |
| `%=` | `x %= 3` | `x = x % 3` |
| `**=` | `x **= 2` | `x = x ** 2` |

Example:

```python id="n3rt4z"
number = 10

number += 5
number *= 2

print(number)
```

Output:

```text id="r1fhmq"
30
```

প্রথমে `10 + 5 = 15`, তারপর `15 * 2 = 30`।

Bitwise Augmented Assignment Operators-এর মধ্যে `&=`, `|=`, `^=`, `<<=` এবং `>>=` রয়েছে। এগুলো সংশ্লিষ্ট Bitwise Operation করে Variable Update করে।

## 7. Identity Operators

Identity Operators পরীক্ষা করে দুটি Reference একই Object-কে নির্দেশ করছে কি না।

| Operator | Meaning |
|---|---|
| `is` | একই Object কি না |
| `is not` | আলাদা Object কি না |

Example:

```python id="9s1qpe"
a = [1, 2, 3]
b = a
c = [1, 2, 3]

print(a is b)
print(a is c)
print(a == c)
```

Output:

```text id="6mq8pq"
True
False
True
```

`a` এবং `b` একই Object-কে Reference করছে। `c` আলাদা List, যদিও তার Content একই।

`None` পরীক্ষা করার জন্য সাধারণত `is None` ব্যবহার করা হয়।

```python id="vtd8xe"
value = None

print(value is None)
```

Output:

```text id="zgr9ee"
True
```

## 8. Membership Operators

Membership Operators পরীক্ষা করে কোনো Value নির্দিষ্ট Collection বা Sequence-এর মধ্যে আছে কি না।

| Operator | Meaning |
|---|---|
| `in` | আছে কি না |
| `not in` | নেই কি না |

Example:

```python id="hn6czj"
languages = ["Python", "Java", "C++"]

print("Python" in languages)
print("PHP" not in languages)
```

Output:

```text id="n5egah"
True
True
```

Dictionary-এর ক্ষেত্রে Membership Operator সাধারণত Key পরীক্ষা করে, Value নয়।

```python id="jshp5c"
student = {
    "name": "Masum",
    "age": 22
}

print("name" in student)
print("Masum" in student)
```

Output:

```text id="8ag8cs"
True
False
```

Value পরীক্ষা করতে `student.values()` ব্যবহার করা যায়।

## 9. Bitwise Operators

Bitwise Operators Integer-এর Binary Representation-এর ওপর কাজ করে।

| Operator | Name | Main Purpose |
|---|---|---|
| `&` | Bitwise AND | উভয় Bit `1` হলে `1` |
| `\|` | Bitwise OR | যেকোনো Bit `1` হলে `1` |
| `^` | Bitwise XOR | Bit দুটি আলাদা হলে `1` |
| `~` | Bitwise NOT | Bit Complement |
| `<<` | Left Shift | Bit বাম দিকে Shift |
| `>>` | Right Shift | Bit ডান দিকে Shift |

Example:

```python id="yt3fr7"
a = 5
b = 3

print(a & b)
print(a | b)
print(a ^ b)
print(a << 1)
print(a >> 1)
```

Output:

```text id="92ctpi"
1
7
6
10
2
```

Python Integer-এর Bitwise Operations-এ Negative Number এবং Shift-এর আচরণ বুঝতে Two's Complement-ভিত্তিক ধারণা ও Python-এর Integer Model সম্পর্কে জানতে হবে। সেগুলো Bitwise Topics-এ বিস্তারিত আলোচনা করা হবে।

## 10. Conditional Expression

Conditional Expression Condition অনুযায়ী দুটি Expression-এর একটি নির্বাচন করে।

Syntax:

```python id="jqm2t0"
value_if_true if condition else value_if_false
```

Example:

```python id="c0d1d5"
marks = 75

result = "Pass" if marks >= 40 else "Fail"

print(result)
```

Output:

```text id="mvr2nt"
Pass
```

এখানে `marks >= 40` True হওয়ায় `"Pass"` নির্বাচন করা হয়েছে।

## 11. Walrus Operator (`:=`)

Walrus Operator একই Expression-এর মধ্যে একটি Variable-এ Value Assign করে এবং সেই Value-টি Expression হিসেবে দেয়।

Example:

```python id="m54n1y"
if (length := len("Python")) > 5:
    print(length)
```

Output:

```text id="6xry1c"
6
```

এখানে `len("Python")`-এর Result `length` Variable-এ Assign হয়েছে এবং Condition-এ ব্যবহার হয়েছে।

**মনে রাখবে:** Walrus Operator সব ক্ষেত্রে প্রয়োজন হয় না। Code পরিষ্কার রাখতে সাধারণ Assignment ব্যবহার করাই অনেক সময় ভালো।

## 12. Operator Categories: Important Differences

### 12.1 `=` vs `==` vs `is`

| Operator | Purpose | Example |
|---|---|---|
| `=` | Assignment | `x = 10` |
| `==` | Value Equality | `x == 10` |
| `is` | Object Identity | `x is None` |

### 12.2 `and` vs `&`

- `and` হলো Logical Operator, যা Truthiness এবং Short-Circuit Evaluation ব্যবহার করে।
- `&` হলো Bitwise AND Operator; Integer-এর ক্ষেত্রে Bit-Level Operation করে।
- কিছু Data Type, যেমন Boolean বা কিছু Library Object-এর ক্ষেত্রে `&`-এর আচরণ আলাদা হতে পারে।

Example:

```python id="36o7vt"
print(True and False)
print(5 & 3)
```

Output:

```text id="0c08wk"
False
1
```

### 12.3 `in` vs `is`

- `in` Collection-এর মধ্যে কোনো Value আছে কি না পরীক্ষা করে।
- `is` দুটি Reference একই Object-কে নির্দেশ করছে কি না পরীক্ষা করে।

## 13. Operator Precedence: Introduction

একটি Expression-এ একাধিক Operator থাকলে Python নির্দিষ্ট Precedence অনুযায়ী কাজ করে।

Example:

```python id="zxxc47"
print(10 + 5 * 2)
```

Output:

```text id="7kdd12"
20
```

Multiplication আগে হয়, তারপর Addition।

Parentheses ব্যবহার করে Evaluation Order স্পষ্ট করা যায়।

```python id="5r32fy"
print((10 + 5) * 2)
```

Output:

```text id="dx6u1d"
30
```

Operator Precedence ও Associativity-এর বিস্তারিত পরবর্তী Topics-এ আলোচনা করা হবে।

## 14. Common Mistakes

### Mistake 1: Assignment and Comparison Confusion

```python id="5tb77n"
x = 10
print(x == 10)
```

Output:

```text id="ud2g1y"
True
```

### Mistake 2: Using `is` for Value Equality

দুটি আলাদা List-এর Value তুলনা করতে `==` ব্যবহার করো, `is` নয়।

```python id="d4q6qg"
a = [1, 2]
b = [1, 2]

print(a == b)
print(a is b)
```

Output:

```text id="wqkq8u"
True
False
```

### Mistake 3: Confusing Logical and Bitwise Operators

```python id="4a8bhf"
print(True and False)
print(5 & 3)
```

Output:

```text id="k7jbg3"
False
1
```

### Mistake 4: Assuming `in` Checks Dictionary Values

```python id="9s6lqp"
student = {"name": "Masum"}

print("Masum" in student)
```

Output:

```text id="crwd1q"
False
```

কারণ Dictionary Membership Operator Key পরীক্ষা করে।

## 15. Practice Exercises

### Basic Questions

1. Python-এর প্রধান Operator Categories-এর নাম লেখো।
2. Arithmetic এবং Comparison Operators-এর পার্থক্য কী?
3. Logical Operators কী কাজ করে?
4. Assignment Operator এবং Comparison Operator-এর পার্থক্য কী?
5. Identity এবং Membership Operators-এর কাজ কী?
6. Bitwise Operators কী ধরনের Operation করে?
7. Walrus Operator কী?
8. Operator Precedence কেন গুরুত্বপূর্ণ?

### Output Prediction

**Question 1**

```python id="jrs9ni"
print(8 + 2 * 3)
```

**Question 2**

```python id="o4uyad"
print(10 > 5 and 3 < 1)
```

**Question 3**

```python id="4ukq6d"
numbers = [1, 2, 3]

print(2 in numbers)
print(4 not in numbers)
```

**Question 4**

```python id="t13pkf"
a = [1, 2]
b = a

print(a is b)
```

**Question 5**

```python id="jq6u18"
x = 10
x += 5

print(x)
```

### Practical Exercises

1. Arithmetic Operators ব্যবহার করে একটি Basic Calculator তৈরি করো।
2. Comparison Operators ব্যবহার করে Pass/Fail নির্ধারণ করো।
3. Logical Operators দিয়ে Age এবং ID যাচাই করো।
4. Membership Operator দিয়ে List-এ একটি Course আছে কি না পরীক্ষা করো।
5. Identity Operator দিয়ে দুটি Variable একই Object Reference করছে কি না পরীক্ষা করো।
6. Bitwise AND ব্যবহার করে দুটি Integer-এর Result বের করো।
7. Parentheses ব্যবহার করে একটি Expression-এর Result পরিবর্তন করো।

## 16. Chapter Summary

এই Topic-এ Python-এর প্রধান Operator Categories-এর একটি Overview শেখা হয়েছে।

- Arithmetic Operators Calculation করে।
- Comparison Operators Value তুলনা করে।
- Logical Operators Truthiness-ভিত্তিক Logic পরিচালনা করে।
- Assignment Operators Value Assign বা Update করে।
- Identity Operators Object Identity পরীক্ষা করে।
- Membership Operators Collection Membership পরীক্ষা করে।
- Bitwise Operators Binary Bits নিয়ে কাজ করে।
- Conditional Expression Condition অনুযায়ী Value নির্বাচন করে।
- Walrus Operator Expression-এর মধ্যে Assignment করতে সাহায্য করে।
- Operator Precedence Expression Evaluation-এর Order নির্ধারণে গুরুত্বপূর্ণ।

## 17. Self-Assessment Checklist

- [ ] প্রধান Operator Categories চিনতে পারি।
- [ ] Arithmetic Operators-এর কাজ বুঝি।
- [ ] Comparison Operators-এর Result নির্ণয় করতে পারি।
- [ ] Logical Operators-এর Basic Behaviour বুঝি।
- [ ] Assignment ও Augmented Assignment চিনতে পারি।
- [ ] Identity ও Membership Operators আলাদা করতে পারি।
- [ ] Bitwise Operators-এর Basic ধারণা আছে।
- [ ] Conditional Expression বুঝি।
- [ ] Walrus Operator-এর Basic Usage বুঝি।
- [ ] Operator Precedence-এর প্রয়োজনীয়তা বুঝি।

**Next Topic:** `04_Arithmetic_Operators.md`