# 33. Chapter Review and Self-Assessment

## 1. Chapter Overview

এই Chapter-এ আমরা Python-এর বিভিন্ন operator, তাদের ব্যবহার, precedence, associativity এবং problem-solving techniques শিখেছি।

Operators ব্যবহার করে আমরা mathematical calculation, value comparison, logical decision, bit manipulation এবং variable assignment করতে পারি।

এই chapter-এর প্রধান বিষয়গুলো:

- Arithmetic Operators
- Comparison Operators
- Logical Operators
- Assignment Operators
- Walrus Operator
- Identity Operators
- Membership Operators
- Bitwise Operators
- Operator Precedence and Associativity
- Conditional Expressions
- Operator Overloading
- Common Errors and Output Prediction

---

## 2. Complete Operator Summary

| Operator Category | Operators | Main Purpose |
|---|---|---|
| Arithmetic | `+`, `-`, `*`, `/` | Basic calculation |
| Floor Division and Modulo | `//`, `%` | Quotient ও remainder |
| Exponentiation | `**` | Power calculation |
| Comparison | `==`, `!=`, `>`, `<`, `>=`, `<=` | Values compare করা |
| Logical | `and`, `or`, `not` | Conditions combine বা reverse করা |
| Assignment | `=` | Variable-এ value assign করা |
| Augmented Assignment | `+=`, `-=`, `*=`, `/=`, `//=`, `%=` | Operation করে assignment করা |
| Walrus | `:=` | Expression-এর মধ্যে assignment করা |
| Identity | `is`, `is not` | একই object কি না পরীক্ষা |
| Membership | `in`, `not in` | Collection-এ membership পরীক্ষা |
| Bitwise | `&`, `|`, `^`, `~`, `<<`, `>>` | Integer-এর bits নিয়ে কাজ করা |
| Conditional Expression | `value_if_true if condition else value_if_false` | Condition অনুযায়ী value নির্বাচন |

---

## 3. Arithmetic Operators: Quick Revision

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `+` | Addition | `8 + 3` | `11` |
| `-` | Subtraction | `8 - 3` | `5` |
| `*` | Multiplication | `8 * 3` | `24` |
| `/` | Division | `8 / 2` | `4.0` |
| `//` | Floor division | `8 // 3` | `2` |
| `%` | Modulo | `8 % 3` | `2` |
| `**` | Exponentiation | `2 ** 3` | `8` |

### Important Rules

- Python 3-এ `/` সাধারণত `float` result দেয়।
- `//` floor division করে; negative number-এর ক্ষেত্রে ফল নিচের integer-এর দিকে যায়।
- `%` remainder দেয়।
- `**` exponentiation করে।
- Division বা modulo-তে divisor `0` হলে `ZeroDivisionError` হয়।

### Negative Number Examples

```python
print(-7 // 2)
print(-7 % 2)
```

Output:

```text
-4
1
```

---

## 4. Comparison Operators: Quick Revision

Comparison operators-এর result সাধারণত `True` অথবা `False` হয়।

```python
print(10 == 10)
print(10 != 5)
print(10 > 5)
print(10 < 5)
print(10 >= 10)
print(5 <= 10)
```

Output:

```text
True
True
True
False
True
True
```

### Chained Comparison

```python
x = 15

print(10 < x < 20)
```

Output:

```text
True
```

এটি সাধারণভাবে নিচের expression-এর সমতুল্য:

```python
10 < x and x < 20
```

### Important Difference

```python
print(5 == 5.0)
print(5 == "5")
```

Output:

```text
True
False
```

`5` ও `5.0` numeric value হিসেবে সমান। কিন্তু integer `5` এবং string `"5"` সমান নয়।

---

## 5. Logical Operators: Quick Revision

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `and` | উভয় operand truthy হলে শেষ operand return করে | `5 and 8` | `8` |
| `or` | প্রথম truthy operand return করে | `0 or 8` | `8` |
| `not` | Truth value উল্টে দেয় | `not True` | `False` |

### Important Truth Table

| A | B | `A and B` | `A or B` |
|---|---|---|---|
| True | True | True | True |
| True | False | False | True |
| False | True | False | True |
| False | False | False | False |

এখানে truth table-টি Boolean operands-এর জন্য।

Python-এর `and` ও `or` non-Boolean operand-এর ক্ষেত্রেও ব্যবহার করা যায় এবং সে ক্ষেত্রে operand-এর value return করতে পারে।

### Short-Circuit Example

```python
x = 0

print(x != 0 and 10 / x > 2)
```

Output:

```text
False
```

প্রথম condition মিথ্যা হওয়ায় `10 / x` evaluate হয় না।

---

## 6. Assignment Operators: Quick Revision

### Basic Assignment

```python
x = 10
```

`x`-এ `10` assign করা হয়েছে।

### Augmented Assignment

```python
x = 10
x += 5
print(x)
```

Output:

```text
15
```

সাধারণভাবে `x += 5`-কে `x = x + 5`-এর মতো বোঝা যায়। তবে mutable object ও custom operator-এর ক্ষেত্রে augmented assignment-এর behavior আলাদা হতে পারে।

### Common Augmented Assignment Operators

| Operator | General Meaning |
|---|---|
| `+=` | যোগ করে assign |
| `-=` | বিয়োগ করে assign |
| `*=` | গুণ করে assign |
| `/=` | ভাগ করে assign |
| `//=` | Floor division করে assign |
| `%=` | Remainder করে assign |
| `**=` | Power করে assign |

### Multiple Assignment

```python
a, b = 10, 20
a, b = b, a

print(a, b)
```

Output:

```text
20 10
```

---

## 7. Identity vs Equality

এই পার্থক্যটি খুব গুরুত্বপূর্ণ।

| Operator | Purpose |
|---|---|
| `==` | দুটি value সমান কি না |
| `is` | দুটি reference একই object-কে নির্দেশ করছে কি না |
| `!=` | দুটি value অসমান কি না |
| `is not` | দুটি reference একই object নয় কি না |

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

দুটি list-এর value সমান, কিন্তু তারা আলাদা object।

**Best Practice:** Value comparison-এর জন্য সাধারণত `==` ব্যবহার করো। `None` পরীক্ষা করার সময় `is None` বা `is not None` ব্যবহার করো।

---

## 8. Membership Operators

`in` এবং `not in` collection বা sequence-এর মধ্যে কোনো value আছে কি না পরীক্ষা করে।

```python
numbers = [10, 20, 30]

print(20 in numbers)
print(40 not in numbers)
```

Output:

```text
True
True
```

String-এর ক্ষেত্রেও ব্যবহার করা যায়:

```python
print("Py" in "Python")
```

Output:

```text
True
```

---

## 9. Bitwise Operators

Bitwise operators integer-এর binary representation-এর bits নিয়ে কাজ করে।

| Operator | Name | Purpose |
|---|---|---|
| `&` | AND | দুই bit-ই `1` হলে `1` |
| `\|` | OR | যেকোনো একটি bit `1` হলে `1` |
| `^` | XOR | দুই bit আলাদা হলে `1` |
| `~` | NOT | Integer-এর bitwise inversion |
| `<<` | Left shift | Bits বামে সরানো |
| `>>` | Right shift | Bits ডানে সরানো |

Example:

```python
print(5 & 3)
print(5 | 3)
print(5 ^ 3)
```

Output:

```text
1
7
6
```

### Important Difference

```python
print(5 & 3)
print(5 and 3)
```

Output:

```text
1
3
```

`&` bitwise operation করে, কিন্তু `and` logical short-circuit evaluation করে।

---

## 10. Operator Precedence

একটি expression-এ একাধিক operator থাকলে precedence নির্ধারণ করে কোন operation আগে হবে।

### Common Precedence: High to Low

| Priority | Operator / Category |
|---|---|
| 1 | Parentheses দিয়ে grouping |
| 2 | `**` |
| 3 | Unary `+`, `-`, `~` |
| 4 | `*`, `@`, `/`, `//`, `%` |
| 5 | `+`, `-` |
| 6 | `<<`, `>>` |
| 7 | `&` |
| 8 | `^` |
| 9 | `\|` |
| 10 | Comparisons, `in`, `not in`, `is`, `is not` |
| 11 | `not` |
| 12 | `and` |
| 13 | `or` |
| 14 | Conditional expression |
| 15 | `lambda` |
| 16 | `:=` |

এটি একটি সংক্ষিপ্ত revision list। Full precedence table-এর জন্য `25_Operator_Precedence.md` দেখবে।

### Example 1

```python
print(5 + 3 * 2)
```

Output:

```text
11
```

Multiplication আগে হয়।

### Example 2

```python
print(2 ** 3 ** 2)
```

Output:

```text
512
```

Exponentiation right-to-left group করে:

`2 ** (3 ** 2) = 512`

### Example 3

```python
print(-2 ** 2)
print((-2) ** 2)
```

Output:

```text
-4
4
```

Parentheses result পরিবর্তন করতে পারে।

---

## 11. Associativity

Associativity নির্ধারণ করে একই precedence-এর operator কীভাবে group হবে।

### Left-to-Right Example

```python
print(20 - 5 - 3)
```

Output:

```text
12
```

Calculation:

`(20 - 5) - 3 = 12`

### Right-to-Left Example

```python
print(2 ** 3 ** 2)
```

Output:

```text
512
```

Calculation:

`2 ** (3 ** 2) = 512`

মনে রাখবে, chained comparisons-কে সাধারণ left-to-right বা right-to-left grouping-এর মতো সরলভাবে বোঝা উচিত নয়।

---

## 12. Conditional Expression

Conditional expression একটি condition অনুযায়ী দুটি value-এর মধ্যে একটি নির্বাচন করে।

### Syntax

```python
value_if_true if condition else value_if_false
```

Example:

```python
number = 8

result = "Even" if number % 2 == 0 else "Odd"

print(result)
```

Output:

```text
Even
```

Condition সত্য হলে `"Even"` এবং মিথ্যা হলে `"Odd"` নির্বাচন করা হয়।

---

## 13. Operator Overloading

Python-এর built-in type এবং custom class-এর object-এর জন্য operator-এর behavior নির্ধারিত থাকতে পারে।

Example:

```python
print(5 + 3)
print("Hello " + "Python")
print([1, 2] + [3, 4])
```

Output:

```text
8
Hello Python
[1, 2, 3, 4]
```

একই `+` operator integer-এর ক্ষেত্রে যোগ, string-এর ক্ষেত্রে concatenation এবং list-এর ক্ষেত্রে combination করে।

Custom class-এ `__add__()`-এর মতো special method ব্যবহার করে operator overloading করা যায়।

---

## 14. Common Mistakes to Avoid

### Mistake 1: Assignment ও Equality গুলিয়ে ফেলা

```python
x = 5
print(x == 5)
```

Output:

```text
True
```

`=` assignment করে, `==` equality পরীক্ষা করে।

### Mistake 2: `/` ও `//` গুলিয়ে ফেলা

```python
print(7 / 2)
print(7 // 2)
```

Output:

```text
3.5
3
```

### Mistake 3: Negative Floor Division ভুল করা

```python
print(-7 // 2)
```

Output:

```text
-4
```

### Mistake 4: `and` ও `&` এক মনে করা

```python
print(5 and 3)
print(5 & 3)
```

Output:

```text
3
1
```

### Mistake 5: `is` দিয়ে সাধারণ value comparison করা

সাধারণ value comparison-এর জন্য `==` ব্যবহার করো।

### Mistake 6: Precedence উপেক্ষা করা

```python
print(2 + 3 * 4)
```

Output:

```text
14
```

### Mistake 7: Division-এর আগে zero check না করা

```python
divisor = 0

if divisor != 0:
    print(10 / divisor)
else:
    print("Cannot divide by zero")
```

Output:

```text
Cannot divide by zero
```

---

## 15. Self-Assessment Quiz

নিজে উত্তর দেওয়ার চেষ্টা করো। তারপর Answer Key দিয়ে যাচাই করো।

### Question 1

```python
print(15 // 4)
print(15 % 4)
```

### Question 2

```python
print(3 + 4 * 2)
```

### Question 3

```python
print(2 ** 3 ** 2)
```

### Question 4

```python
print(-8 // 3)
print(-8 % 3)
```

### Question 5

```python
x = 10
x += 5
x *= 2

print(x)
```

### Question 6

```python
print(10 > 5 and 3 > 8)
```

### Question 7

```python
print(0 or 12)
```

### Question 8

```python
print(6 & 3)
```

### Question 9

```python
a = [1, 2]
b = [1, 2]

print(a == b)
print(a is b)
```

### Question 10

```python
number = 9
print("Even" if number % 2 == 0 else "Odd")
```

### Question 11

```python
print(not False and True)
```

### Question 12

```python
print(10 < 20 > 15)
```

### Answer Key

| Question | Expected Output |
|---|---|
| 1 | `3` এবং `3` |
| 2 | `11` |
| 3 | `512` |
| 4 | `-3` এবং `1` |
| 5 | `30` |
| 6 | `False` |
| 7 | `12` |
| 8 | `2` |
| 9 | `True` এবং `False` |
| 10 | `Odd` |
| 11 | `True` |
| 12 | `True` |

---

## 16. Practical Programming Exercises

নিচের problem-গুলো নিজে solve করো।

1. দুটি সংখ্যার যোগ, বিয়োগ, গুণ ও ভাগ বের করো।
2. একটি integer Even নাকি Odd নির্ণয় করো।
3. তিনটি সংখ্যার maximum বের করো।
4. একটি সংখ্যা `3` ও `5` উভয় দিয়ে বিভাজ্য কি না পরীক্ষা করো।
5. একটি non-negative integer-এর শেষ digit বের করো।
6. একটি non-negative integer-এর শেষ digit বাদ দাও।
7. তিনটি সংখ্যার average বের করো।
8. প্রাপ্ত নম্বর ও পূর্ণ নম্বর থেকে percentage বের করো।
9. দুটি variable-এর value swap করো।
10. একটি সংখ্যার range `10` থেকে `100`-এর মধ্যে কি না পরীক্ষা করো।
11. Seconds-কে minutes ও remaining seconds-এ রূপান্তর করো।
12. Price `1000` বা তার বেশি হলে `10%` discount প্রয়োগ করো।

Practice problem-এর বিস্তারিত উদাহরণ ও সমাধানের জন্য `31_Operator_Based_Problem_Solving.md` দেখবে।

---

## 17. Chapter Completion Checklist

### Basic Understanding

- [ ] Operator ও operand-এর পার্থক্য বুঝি।
- [ ] Arithmetic operators ব্যবহার করতে পারি।
- [ ] Comparison operators দিয়ে condition তৈরি করতে পারি।
- [ ] Logical operators দিয়ে একাধিক condition combine করতে পারি।
- [ ] Assignment ও augmented assignment বুঝি।

### Intermediate Understanding

- [ ] Floor division ও modulo-এর behavior বুঝি।
- [ ] Identity ও membership operator-এর পার্থক্য বুঝি।
- [ ] Bitwise AND, OR, XOR ও shift-এর basic calculation করতে পারি।
- [ ] Operator precedence ও associativity প্রয়োগ করতে পারি।
- [ ] Conditional expression লিখতে পারি।
- [ ] Short-circuit evaluation বুঝি।

### Practical Skills

- [ ] Output prediction problem solve করতে পারি।
- [ ] Operator ব্যবহার করে ছোট programming problem solve করতে পারি।
- [ ] Common operator errors শনাক্ত করতে পারি।
- [ ] নিজের code-এর output পরীক্ষা করতে পারি।

---

## 18. Final Summary

Python operators হলো programming-এর অন্যতম গুরুত্বপূর্ণ ভিত্তি। এগুলো দিয়ে calculation, comparison, decision-making, assignment এবং bit-level operation করা যায়।

এই chapter-এর সবচেয়ে গুরুত্বপূর্ণ বিষয়গুলো:

1. Arithmetic operators mathematical calculation করে।
2. Comparison operators `True` বা `False` result দেয়।
3. Logical operators condition combine করে এবং short-circuit evaluation করতে পারে।
4. Assignment operators variable-এ value assign বা update করে।
5. Identity operator object identity পরীক্ষা করে।
6. Membership operator collection-এ value আছে কি না পরীক্ষা করে।
7. Bitwise operators integer-এর binary bits নিয়ে কাজ করে।
8. Precedence ও associativity expression-এর evaluation order নির্ধারণ করে।
9. Conditional expression condition অনুযায়ী value নির্বাচন করে।
10. নিয়মিত output prediction practice করলে operator-এর ব্যবহার আরও পরিষ্কার হয়।

**Chapter 04 Complete:** Operators in Python.

পরবর্তী Chapter: **Chapter 05 — Input, Output & String Formatting**