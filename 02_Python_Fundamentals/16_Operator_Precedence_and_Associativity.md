# 16. Operator Precedence and Associativity in Python

## 1. Introduction

Python-এ একটি expression-এর মধ্যে একাধিক operator থাকলে কোন operator আগে execute হবে এবং কোনটি পরে হবে, তা নির্ধারণ করার নিয়মকে **Operator Precedence** বলে।

আর একই precedence-এর একাধিক operator থাকলে কোন দিক থেকে evaluation হবে, সেই নিয়মকে **Operator Associativity** বলে।

উদাহরণ:

```python
result = 10 + 5 * 2

print(result)
```

Output:

```text
20
```

এখানে `*` operator, `+` operator-এর আগে কাজ করেছে।

প্রথমে:

```text
5 * 2 = 10
```

তারপর:

```text
10 + 10 = 20
```

তাই result `30` নয়, `20`।

## 2. What Is Operator Precedence?

**Operator Precedence** নির্ধারণ করে একটি expression-এ কোন operator আগে কাজ করবে।

সাধারণভাবে, higher-precedence operator আগে evaluate হয়।

উদাহরণ:

```python
print(2 + 3 * 4)
```

Output:

```text
14
```

কারণ multiplication, addition-এর আগে হয়।

ধাপে ধাপে:

```text
3 * 4 = 12
2 + 12 = 14
```

### Another Example

```python
print(20 - 8 / 2)
```

Output:

```text
16.0
```

কারণ division, subtraction-এর আগে হয়।

```text
8 / 2 = 4.0
20 - 4.0 = 16.0
```

## 3. What Is Operator Associativity?

একই precedence-এর একাধিক operator থাকলে কোন দিক থেকে evaluation হবে, তা associativity নির্ধারণ করে।

Python-এ অধিকাংশ arithmetic operator left-to-right associate করে। তবে exponentiation (`**`) এবং কিছু অন্য operator-এর ক্ষেত্রে নিয়ম আলাদা।

### 3.1 Left-to-Right Associativity

উদাহরণ:

```python
print(20 - 5 - 3)
```

Output:

```text
12
```

Evaluation:

```text
(20 - 5) - 3
= 15 - 3
= 12
```

এখানে প্রথম subtraction আগে হয়েছে।

আরেকটি উদাহরণ:

```python
print(24 / 4 * 2)
```

Output:

```text
12.0
```

Evaluation:

```text
(24 / 4) * 2
= 6.0 * 2
= 12.0
```

`/` এবং `*` একই precedence-এর হওয়ায় এখানে বাম দিক থেকে evaluation হয়েছে।

### 3.2 Right-to-Left Associativity

Exponentiation (`**`) ডান দিক থেকে associate করে।

```python
print(2 ** 3 ** 2)
```

Output:

```text
512
```

Evaluation:

```text
2 ** (3 ** 2)
= 2 ** 9
= 512
```

এখানে `2 ** 3` আগে করা হয়নি।

**মনে রাখবে:** Associativity হলো expression কীভাবে group হবে তার নিয়ম। এটি সব ক্ষেত্রে function বা operand-এর বাস্তব execution order সম্পর্কে সম্পূর্ণ ধারণা দেয় না।

## 4. Parentheses and Operator Precedence

Parentheses বা `()` ব্যবহার করে evaluation-এর order স্পষ্ট করা যায়।

উদাহরণ:

```python
print(2 + 3 * 4)
print((2 + 3) * 4)
```

Output:

```text
14
20
```

প্রথম expression-এ multiplication আগে হয়েছে।

দ্বিতীয় expression-এ parentheses-এর ভেতরের addition আগে হয়েছে।

### Nested Parentheses

```python
result = (10 + (6 - 2)) * 3

print(result)
```

Output:

```text
42
```

ধাপে ধাপে:

```text
6 - 2 = 4
10 + 4 = 14
14 * 3 = 42
```

Complex expression-এ parentheses ব্যবহার করলে code পড়া এবং ভুল এড়ানো সহজ হয়।

## 5. Python Operator Precedence Table

নিচের table-এ Python-এর operator-গুলোকে উচ্চ precedence থেকে নিম্ন precedence অনুযায়ী সাজানো হয়েছে। একই row-তে থাকা operator-গুলোর precedence সাধারণত একই।

| Priority | Operators | Description |
|---:|---|---|
| 1 — Highest | `()` | Grouping expressions |
| 2 | `x[index]`, `x[key]`, `x(...)`, `x.attribute` | Indexing, function call, attribute access |
| 3 | `await x` | Await expression |
| 4 | `**` | Exponentiation |
| 5 | `+x`, `-x`, `~x` | Unary plus, minus, bitwise NOT |
| 6 | `*`, `@`, `/`, `//`, `%` | Multiplication, matrix multiplication, division |
| 7 | `+`, `-` | Addition, subtraction |
| 8 | `<<`, `>>` | Bitwise shifts |
| 9 | `&` | Bitwise AND |
| 10 | `^` | Bitwise XOR |
| 11 | `\|` | Bitwise OR |
| 12 | `<`, `<=`, `>`, `>=`, `!=`, `==`, `in`, `not in`, `is`, `is not` | Comparisons |
| 13 | `not` | Logical NOT |
| 14 | `and` | Logical AND |
| 15 | `or` | Logical OR |
| 16 | `x if condition else y` | Conditional expression |
| 17 | `lambda` | Lambda expression |
| 18 — Lowest | `:=` | Assignment expression |

**Important notes:**

- `()` দিয়ে expression group করলে parentheses-এর ভেতরের expression আগে evaluate হয়।
- `**` operator-এর সঙ্গে unary operator-এর interaction কিছুটা বিশেষ। যেমন, `-2 ** 2` হলো `-(2 ** 2)`, তাই result `-4`।
- Comparison operators chaining support করে, যেমন `10 < x < 20`।
- `lambda` ও `:=`-এর ক্ষেত্রে expression-এর আরও কিছু syntax restriction রয়েছে।
- এই table মূলত expression precedence বোঝার জন্য। Python-এর সম্পূর্ণ grammar-এর বিকল্প নয়।

## 6. Arithmetic Operator Precedence

Arithmetic expression-এ সাধারণত নিচের order মনে রাখবে:

1. Parentheses `()`
2. Exponentiation `**`
3. Unary `+x`, `-x`
4. Multiplication, division, floor division ও modulus
5. Addition ও subtraction

উদাহরণ:

```python
result = 2 + 3 * 4 ** 2

print(result)
```

Output:

```text
50
```

Evaluation:

```text
4 ** 2 = 16
3 * 16 = 48
2 + 48 = 50
```

### Example with Parentheses

```python
result = (2 + 3) * 4 ** 2

print(result)
```

Output:

```text
80
```

Evaluation:

```text
2 + 3 = 5
4 ** 2 = 16
5 * 16 = 80
```

## 7. Unary Operators and Exponentiation

Unary minus (`-`) এবং exponentiation (`**`)-এর precedence নিয়ে beginner-দের প্রায়ই confusion হয়।

উদাহরণ:

```python
print(-2 ** 2)
print((-2) ** 2)
```

Output:

```text
-4
4
```

ব্যাখ্যা:

প্রথম expression:

```text
-2 ** 2
= -(2 ** 2)
= -4
```

দ্বিতীয় expression:

```text
(-2) ** 2
= (-2) * (-2)
= 4
```

তাই negative number-এর power হিসাব করার সময় parentheses প্রয়োজন কি না, তা খেয়াল করবে।

## 8. Comparison and Logical Operator Precedence

Comparison operators, `not`, `and` এবং `or`-এর precedence আলাদা।

সাধারণ order:

```text
Comparison → not → and → or
```

উদাহরণ:

```python
result = 10 > 5 and 3 < 2 or True

print(result)
```

Output:

```text
True
```

ধাপে ধাপে:

```text
10 > 5       → True
3 < 2        → False

True and False → False
False or True  → True
```

আরেকটি উদাহরণ:

```python
age = 20
has_id = True

result = age >= 18 and has_id

print(result)
```

Output:

```text
True
```

এখানে `age >= 18` আগে evaluate হয়। এরপর `and` দুইটি condition-এর result ব্যবহার করে।

### Why Use Parentheses?

```python
result = (age >= 18) and has_id
```

এভাবে লিখলে expression-এর উদ্দেশ্য আরও পরিষ্কার হয়।

## 9. Bitwise Operator Precedence

Bitwise operators-এর precedence-ও আলাদা।

সাধারণ order:

```text
Shift → & → ^ → |
```

উদাহরণ:

```python
result = 2 | 3 & 1

print(result)
```

Output:

```text
3
```

কারণ `&`-এর precedence `|`-এর চেয়ে বেশি।

ধাপে ধাপে:

```text
3 & 1 = 1
2 | 1 = 3
```

Parentheses দিয়ে order স্পষ্ট করা যায়:

```python
print((2 | 3) & 1)
```

Output:

```text
1
```

এখানে প্রথমে `2 | 3`, তারপর `& 1` হয়েছে।

## 10. Assignment Operators and Expressions

Assignment statement এবং expression-এর মধ্যে পার্থক্য মনে রাখা জরুরি।

### Simple Assignment

```python
x = 10
```

এটি assignment statement। সাধারণ assignment-কে arithmetic expression-এর মতো precedence table-এ বসানো যায় না।

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

Augmented assignment statement-এর নিজস্ব semantics আছে। এটি সাধারণ expression-এর precedence table-এর মতো করে evaluate হয় না।

### Assignment Expression (`:=`)

Python-এ `:=`-কে **assignment expression** বা walrus operator বলা হয়।

```python
if (length := len("Python")) > 5:
    print(length)
```

Output:

```text
6
```

এখানে `len("Python")`-এর result `length`-এ assign হয়েছে এবং একই expression-এ result ব্যবহার করা হয়েছে।

সাধারণ assignment এবং assignment expression এক নয়।

## 11. Short-Circuit Evaluation

Python-এর `and` এবং `or` operator short-circuit evaluation ব্যবহার করে।

অর্থাৎ, result নির্ধারণ করা সম্ভব হলে পরের operand evaluate না-ও হতে পারে।

### `and` Example

```python
print(False and (10 / 0))
```

Output:

```text
False
```

এখানে প্রথম operand `False` হওয়ায় `and`-এর result ইতিমধ্যে নির্ধারিত। তাই `10 / 0` evaluate হয় না।

### `or` Example

```python
print(True or (10 / 0))
```

Output:

```text
True
```

প্রথম operand `True` হওয়ায় `or`-এর result নির্ধারিত। তাই পরের operand evaluate হয় না।

**মনে রাখবে:** Short-circuiting হলো evaluation behavior; এটি শুধু precedence-এর বিষয় নয়।

## 12. Common Mistakes

### Mistake 1: Assuming All Operators Have Equal Priority

ভুল ধারণা:

```python
print(2 + 3 * 4)
```

এখানে বাম দিক থেকে সব operator চালালে result `20` মনে হতে পারে।

সঠিক output:

```text
14
```

কারণ multiplication আগে হয়।

### Mistake 2: Misunderstanding Exponentiation

```python
print(2 ** 3 ** 2)
```

সঠিক output:

```text
512
```

কারণ expression-টি `2 ** (3 ** 2)` হিসেবে associate করে।

### Mistake 3: Forgetting Parentheses with Negative Powers

```python
print(-3 ** 2)
print((-3) ** 2)
```

Output:

```text
-9
9
```

### Mistake 4: Confusing `and` and `or` Priority

```python
print(True or False and False)
```

Output:

```text
True
```

কারণ `and`-এর precedence `or`-এর চেয়ে বেশি।

Evaluation:

```text
False and False = False
True or False = True
```

### Mistake 5: Writing Hard-to-Read Expressions

যদিও Python precedence অনুসরণ করে expression evaluate করতে পারে, অনেক operator একসঙ্গে থাকলে code বোঝা কঠিন হতে পারে।

কম পরিষ্কার:

```python
result = a > 10 and b < 20 or c == 5
```

আরও পরিষ্কার:

```python
result = (a > 10 and b < 20) or (c == 5)
```

Parentheses ব্যবহার করে intended logic স্পষ্ট করা যায়।

## 13. Practical Examples

### Example 1: Calculate Final Bill

```python
price = 500
quantity = 3
discount = 200

total = price * quantity - discount

print(total)
```

Output:

```text
1300
```

Evaluation:

```text
500 * 3 = 1500
1500 - 200 = 1300
```

### Example 2: Check Age and Marks

```python
age = 21
marks = 85

eligible = age >= 18 and marks >= 40

print(eligible)
```

Output:

```text
True
```

### Example 3: Mixed Operators

```python
result = (10 + 5) * 2 ** 2 - 8 / 4

print(result)
```

Output:

```text
58.0
```

Evaluation:

```text
10 + 5 = 15
2 ** 2 = 4
15 * 4 = 60
8 / 4 = 2.0
60 - 2.0 = 58.0
```

## 14. Practice Exercises

### Exercise 1: Predict the Output

```python
print(5 + 3 * 2)
print((5 + 3) * 2)
print(20 / 5 * 2)
print(2 ** 3 ** 2)
```

প্রতিটি expression-এর evaluation order ব্যাখ্যা করো।

### Exercise 2: Unary Operator

```python
print(-4 ** 2)
print((-4) ** 2)
print(2 ** -2)
```

Output নির্ণয় করো।

### Exercise 3: Comparison and Logical Operators

```python
a = 10
b = 20
c = 5

print(a < b and b > c)
print(a > b or c < b)
print(not a == b)
```

প্রতিটি result ধাপে ধাপে বের করো।

### Exercise 4: Bitwise Precedence

```python
print(2 | 3 & 1)
print((2 | 3) & 1)
```

দুটি expression-এর result কেন আলাদা, তা ব্যাখ্যা করো।

### Exercise 5: Short-Circuit

```python
print(False and (1 / 0))
print(True or (1 / 0))
```

দুটি expression-ই কেন `ZeroDivisionError` তৈরি করে না, তা ব্যাখ্যা করো।

### Exercise 6: Mixed Expression

```python
a = 8
b = 3

result = a + b * 2 ** 2 - 4 // 2

print(result)
```

প্রথমে নিজে result বের করো, তারপর Python-এ run করে যাচাই করো।

## 15. Quick Revision

| Concept | Meaning |
|---|---|
| Operator Precedence | কোন operator আগে কাজ করবে |
| Operator Associativity | একই precedence-এর operator কীভাবে group হবে |
| Parentheses | Evaluation order স্পষ্ট বা পরিবর্তন করতে ব্যবহার হয় |
| Left-to-right | উদাহরণ: `20 - 5 - 3` |
| Right-to-left | উদাহরণ: `2 ** 3 ** 2` |
| Short-circuit | Result নির্ধারিত হলে `and` বা `or` পরের operand evaluate না-ও করতে পারে |
| `=` | Assignment statement |
| `:=` | Assignment expression |

## 16. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Operator precedence expression-এর evaluation order নির্ধারণে সাহায্য করে।
- Associativity একই precedence-এর operator কীভাবে group হবে তা নির্ধারণ করে।
- Python-এ arithmetic operator-এর precedence আলাদা।
- Exponentiation (`**`) ডান দিক থেকে associate করে।
- Unary minus ও exponentiation একসঙ্গে ব্যবহার করলে parentheses গুরুত্বপূর্ণ।
- Comparison operators-এর পরে logical `not`, `and` এবং `or`-এর precedence আলাদা।
- Parentheses code-কে সহজে পড়তে এবং ভুল এড়াতে সাহায্য করে।
- `and` ও `or` short-circuit evaluation ব্যবহার করে।

## 17. Next Topic

পরবর্তী ফাইল: [`17_Indentation_and_Code_Blocks.md`](17_Indentation_and_Code_Blocks.md)

সেখানে Python-এ indentation, code block, `if`, `for`, `while` এবং function-এর body কীভাবে সঠিকভাবে লিখতে হয়, তা বিস্তারিতভাবে শেখা হবে।