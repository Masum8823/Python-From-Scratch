# 25. Operator Precedence in Python

## 1. Introduction

Python-এ একটি expression-এর মধ্যে একাধিক operator থাকলে কোন operator আগে কাজ করবে, সেই নিয়মকে **Operator Precedence** বলে।

সহজভাবে:

> Operator Precedence determines which operator is evaluated first in an expression.

### Example

```python
result = 5 + 3 * 2
print(result)
```

**Output:**

```text
11
```

কেন `16` হলো না?

কারণ Python-এ multiplication (`*`) operator-এর precedence addition (`+`)-এর চেয়ে বেশি।

তাই আগে:

```text
3 * 2 = 6
```

তারপর:

```text
5 + 6 = 11
```

সুতরাং output `11`।

## 2. Why Is Operator Precedence Important?

Operator Precedence জানা গুরুত্বপূর্ণ, কারণ এটি:

- Expression-এর সঠিক output বুঝতে সাহায্য করে।
- Output prediction-এর প্রশ্ন সমাধানে কাজে লাগে।
- Mathematical calculation-এর ভুল কমায়।
- Complex expression পড়া ও debug করা সহজ করে।
- Code-এ parentheses সঠিকভাবে ব্যবহার করতে সাহায্য করে।

## 3. Basic Operator Precedence

নিচে Python-এর কয়েকটি গুরুত্বপূর্ণ operator group-এর precedence দেওয়া হলো। তালিকাটি উচ্চ precedence থেকে নিম্ন precedence অনুযায়ী সাজানো।

| Priority | Operator / Group | Example |
|---:|---|---|
| 1 — Highest | Parentheses | `(a + b)` |
| 2 | Exponentiation | `**` |
| 3 | Unary operators | `+x`, `-x`, `~x` |
| 4 | Multiplication, division, floor division, modulo | `*`, `/`, `//`, `%` |
| 5 | Addition and subtraction | `+`, `-` |
| 6 | Bitwise shifts | `<<`, `>>` |
| 7 | Bitwise AND | `&` |
| 8 | Bitwise XOR | `^` |
| 9 | Bitwise OR | `|` |
| 10 | Comparisons, membership and identity | `<`, `==`, `in`, `is` |
| 11 | Logical NOT | `not` |
| 12 | Logical AND | `and` |
| 13 | Logical OR | `or` |
| 14 — Lowest here | Conditional expression | `x if condition else y` |

**Note:** এটি গুরুত্বপূর্ণ operator group-গুলোর একটি simplified table। Python-এর পূর্ণ precedence rules-এ আরও কিছু group রয়েছে। বিশেষ করে `not`, comparisons এবং bitwise operators-এর অবস্থান ঠিকভাবে মনে রাখতে হবে।

## 4. Parentheses Have High Priority

Parentheses বা বন্ধনীর মধ্যে থাকা expression আগে evaluate করা হয়।

### Example 1

```python
print((5 + 3) * 2)
```

**Output:**

```text
16
```

Calculation:

```text
5 + 3 = 8
8 * 2 = 16
```

### Example 2

```python
print(5 + 3 * 2)
```

**Output:**

```text
11
```

এখানে parentheses নেই, তাই multiplication আগে হয়েছে।

### Comparison

| Expression | Output |
|---|---:|
| `5 + 3 * 2` | `11` |
| `(5 + 3) * 2` | `16` |
| `5 * (3 + 2)` | `25` |

**মনে রাখবে:** কোনো expression নিয়ে সন্দেহ হলে parentheses ব্যবহার করে intended order পরিষ্কার করা যায়।

## 5. Exponentiation (`**`) Has Higher Precedence Than Multiplication

Exponentiation operator (`**`) multiplication (`*`) এবং addition (`+`)-এর আগে evaluate হয়।

### Example

```python
print(2 + 3 ** 2)
```

**Output:**

```text
11
```

Calculation:

```text
3 ** 2 = 9
2 + 9 = 11
```

### Another Example

```python
print(2 * 3 ** 2)
```

**Output:**

```text
18
```

Calculation:

```text
3 ** 2 = 9
2 * 9 = 18
```

## 6. Unary Operators and Exponentiation

Python-এ unary `+` ও `-` এবং exponentiation-এর মধ্যে একটি গুরুত্বপূর্ণ নিয়ম আছে।

`-2 ** 2`-এর অর্থ `-(2 ** 2)`।

### Example 1

```python
print(-2 ** 2)
```

**Output:**

```text
-4
```

কারণ:

```text
-(2 ** 2)
= -4
```

### Example 2

```python
print((-2) ** 2)
```

**Output:**

```text
4
```

এখানে parentheses-এর কারণে `-2` পুরো base হিসেবে ব্যবহৃত হয়েছে।

তাই:

```text
(-2) * (-2) = 4
```

এই পার্থক্যটি output prediction-এর জন্য খুব গুরুত্বপূর্ণ।

## 7. Multiplication, Division, Floor Division and Modulo

`*`, `/`, `//` এবং `%` একই precedence level-এ থাকে।

একই level-এর operator একসঙ্গে থাকলে সাধারণত বাম দিক থেকে ডান দিকে evaluate হয়।

### Example 1

```python
print(20 / 5 * 2)
```

**Output:**

```text
8.0
```

Calculation:

```text
20 / 5 = 4.0
4.0 * 2 = 8.0
```

### Example 2

```python
print(17 // 3 * 2)
```

**Output:**

```text
10
```

Calculation:

```text
17 // 3 = 5
5 * 2 = 10
```

### Example 3

```python
print(17 % 5 * 2)
```

**Output:**

```text
4
```

Calculation:

```text
17 % 5 = 2
2 * 2 = 4
```

## 8. Addition and Subtraction

Addition (`+`) এবং subtraction (`-`) একই precedence level-এ থাকে।

তাই একই level-এর operator সাধারণত বাম থেকে ডানে evaluate হয়।

### Example

```python
print(20 - 5 + 3)
```

**Output:**

```text
18
```

Calculation:

```text
20 - 5 = 15
15 + 3 = 18
```

এখানে `20 - (5 + 3)` হিসেবে evaluate করা হয় না।

## 9. Bitwise Operator Precedence

Bitwise operators-এর precedence আলাদা আলাদা।

উচ্চ থেকে নিম্ন:

1. `<<`, `>>`
2. `&`
3. `^`
4. `|`

### Example 1: Shift and Addition

```python
print(1 << 2 + 1)
```

**Output:**

```text
8
```

কারণ addition-এর precedence shift-এর চেয়ে বেশি।

Calculation:

```text
2 + 1 = 3
1 << 3 = 8
```

### Example 2: AND and OR

```python
print(5 | 2 & 3)
```

**Output:**

```text
7
```

কারণ `&`-এর precedence `|`-এর চেয়ে বেশি।

Calculation:

```text
2 & 3 = 2
5 | 2 = 7
```

### Example 3: XOR and AND

```python
print(5 ^ 3 & 1)
```

**Output:**

```text
6
```

কারণ `&`-এর precedence `^`-এর চেয়ে বেশি।

Calculation:

```text
3 & 1 = 1
5 ^ 1 = 4
```

উপরের expression-এর সঠিক output হলো `4`।

**মনে রাখবে:** Bitwise expression-এ আগে precedence অনুযায়ী operation চিহ্নিত করবে, তারপর binary calculation করবে।

## 10. Comparison Operators

Comparison operators-এর মধ্যে রয়েছে:

```text
<   >   <=   >=   ==   !=
```

এগুলো value compare করে Boolean result দেয়।

### Example

```python
print(5 + 2 > 6)
```

**Output:**

```text
True
```

Calculation:

```text
5 + 2 = 7
7 > 6 → True
```

কারণ addition-এর precedence comparison-এর চেয়ে বেশি।

### Another Example

```python
print(10 == 5 + 5)
```

**Output:**

```text
True
```

কারণ আগে `5 + 5` evaluate হয়, তারপর equality comparison হয়।

## 11. Logical Operator Precedence

Logical operators-এর precedence:

```text
not > and > or
```

অর্থাৎ `not`-এর precedence সবচেয়ে বেশি, তারপর `and`, তারপর `or`।

### Example 1

```python
print(True or False and False)
```

**Output:**

```text
True
```

Calculation:

```text
False and False = False
True or False = True
```

### Example 2

```python
print(not True or True)
```

**Output:**

```text
True
```

Calculation:

```text
not True = False
False or True = True
```

### Example 3

```python
print(True and not False)
```

**Output:**

```text
True
```

Calculation:

```text
not False = True
True and True = True
```

## 12. Comparisons and Logical Operators

Comparison operators-এর precedence logical `not`, `and` এবং `or`-এর চেয়ে বেশি।

### Example

```python
x = 5

print(x > 3 and x < 10)
```

**Output:**

```text
True
```

Calculation:

```text
x > 3   → True
x < 10  → True
True and True → True
```

এখানে দুইটি comparison আগে evaluate হয়েছে, তারপর logical AND কাজ করেছে।

## 13. Conditional Expression Precedence

Python-এ conditional expression লেখা যায় এভাবে:

```python
value_if_true if condition else value_if_false
```

### Example

```python
x = 10

result = "Pass" if x >= 5 else "Fail"

print(result)
```

**Output:**

```text
Pass
```

এখানে `x >= 5` সত্য হওয়ায় `"Pass"` নির্বাচিত হয়েছে।

Conditional expression ব্যবহার করার সময় complex condition থাকলে parentheses দিয়ে expression পরিষ্কার রাখা ভালো।

## 14. Associativity vs Precedence

Operator Precedence এবং Associativity এক জিনিস নয়।

- **Precedence:** ভিন্ন precedence-এর operator থাকলে কোনটি আগে evaluate হবে।
- **Associativity:** একই precedence-এর operator একসঙ্গে থাকলে expression কীভাবে group হবে।

### Example

```python
print(20 - 5 - 3)
```

**Output:**

```text
12
```

Subtraction left-to-right associate করে:

```text
(20 - 5) - 3
= 15 - 3
= 12
```

অন্যদিকে exponentiation right-to-left associate করে:

```python
print(2 ** 3 ** 2)
```

**Output:**

```text
512
```

কারণ:

```text
2 ** (3 ** 2)
= 2 ** 9
= 512
```

Associativity নিয়ে বিস্তারিত পরের টপিকে আলোচনা করা হবে।

## 15. Short-Circuit Evaluation Is Different from Precedence

Precedence নির্ধারণ করে operator-এর grouping বা কোন operation আগে হবে। Short-circuit evaluation নির্ধারণ করে logical expression-এর ক্ষেত্রে Python বাকি অংশ evaluate করবে কি না।

### Example

```python
x = 0

print(False and (10 / x > 1))
```

**Output:**

```text
False
```

এখানে `False and ...` expression-এর ফলাফল আগেই `False` নিশ্চিত হওয়ায় Python ডান পাশের expression evaluate করে না। তাই division-by-zero error হয় না।

## 16. Common Mistakes

### Mistake 1: সব operator-কে বাম থেকে ডানে evaluate করা

```python
print(5 + 3 * 2)
```

সঠিক output `11`, `16` নয়। কারণ multiplication-এর precedence বেশি।

### Mistake 2: Exponentiation-এর আগে negative sign-কে evaluate করা

```python
print(-2 ** 2)
```

Output `-4`, কারণ এটি `-(2 ** 2)` হিসেবে evaluate হয়।

### Mistake 3: Logical এবং bitwise precedence গুলিয়ে ফেলা

`and` এবং `&` একই operator নয়। তাদের precedence-ও আলাদা।

### Mistake 4: Parentheses ব্যবহার না করা

Complex expression-এ parentheses না থাকলে code পড়া কঠিন হতে পারে।

```python
result = (a + b) * (c - d)
```

এভাবে লিখলে intended calculation স্পষ্ট হয়।

## 17. Practice Exercises

### Exercise 1: Predict the Output

```python
print(4 + 2 * 3)
```

**Answer:**

```text
10
```

### Exercise 2: Predict the Output

```python
print((4 + 2) * 3)
```

**Answer:**

```text
18
```

### Exercise 3: Predict the Output

```python
print(2 ** 3 * 2)
```

**Answer:**

```text
16
```

### Exercise 4: Predict the Output

```python
print(-3 ** 2)
```

**Answer:**

```text
-9
```

### Exercise 5: Predict the Output

```python
print(10 - 4 + 2)
```

**Answer:**

```text
8
```

### Exercise 6: Predict the Output

```python
print(5 | 2 & 3)
```

**Answer:**

```text
7
```

### Exercise 7: Predict the Output

```python
print(True or False and False)
```

**Answer:**

```text
True
```

### Exercise 8: Predict the Output

```python
print(2 ** 2 ** 3)
```

**Answer:**

```text
256
```

কারণ:

```text
2 ** (2 ** 3)
= 2 ** 8
= 256
```

## 18. Summary

- Operator Precedence নির্ধারণ করে কোন operator আগে evaluate হবে।
- Parentheses ব্যবহার করে calculation-এর order স্পষ্ট করা যায়।
- Exponentiation multiplication-এর আগে evaluate হয়।
- Multiplication, division, floor division ও modulo একই precedence level-এ থাকে।
- Addition ও subtraction একই precedence level-এ থাকে।
- Bitwise shift-এর precedence bitwise AND, XOR ও OR-এর চেয়ে বেশি।
- Logical operator-এর precedence হলো `not > and > or`।
- Associativity নির্ধারণ করে একই precedence-এর operator কীভাবে group হবে।
- Short-circuit evaluation হলো logical expression-এর একটি আলাদা আচরণ।

## 19. Self-Assessment Checklist

- [ ] Operator Precedence-এর অর্থ বুঝি।
- [ ] Parentheses-এর প্রভাব ব্যাখ্যা করতে পারি।
- [ ] Arithmetic expression-এর output বের করতে পারি।
- [ ] Unary minus ও exponentiation-এর precedence বুঝি।
- [ ] Bitwise operators-এর precedence মনে রাখতে পারি।
- [ ] Logical operators-এর precedence জানি।
- [ ] Precedence এবং associativity-এর পার্থক্য বুঝি।
- [ ] Output prediction-এর সময় ধাপে ধাপে calculation করতে পারি।
