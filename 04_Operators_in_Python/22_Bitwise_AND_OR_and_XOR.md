# 22. Bitwise AND, OR and XOR

## 1. Introduction to Bitwise Operators

Bitwise Operators হলো এমন operators, যেগুলো integer-এর binary representation-এর প্রতিটি bit-এর ওপর কাজ করে।

Python-এ গুরুত্বপূর্ণ তিনটি Bitwise Operator হলো:

| Operator | Name | কাজ |
|---|---|---|
| `&` | Bitwise AND | দুটি bit-ই `1` হলে ফলাফল `1` |
| `|` | Bitwise OR | অন্তত একটি bit `1` হলে ফলাফল `1` |
| `^` | Bitwise XOR | দুটি bit আলাদা হলে ফলাফল `1` |

**মনে রাখার সহজ নিয়ম:**

- AND (`&`) → দুটোই `1` হতে হবে।
- OR (`|`) → যেকোনো একটি `1` হলেই হবে।
- XOR (`^`) → দুটো bit আলাদা হতে হবে।

## 2. Understanding Bitwise AND (`&`)

Bitwise AND প্রতিটি bit position-এ দুটি bit পরীক্ষা করে।

দুটি bit-ই `1` হলে output `1` হয়। অন্য সব ক্ষেত্রে output `0` হয়।

### AND Truth Table

| A | B | A & B |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

### Example 1: Simple Calculation

ধরি:

```text
A = 5  →  101
B = 3  →  011
```

এখন bitwise AND করি:

```text
  101
& 011
-----
  001
```

ফলাফল Binary `001`, যার Decimal value `1`।

### Python Code

```python
a = 5
b = 3

print(a & b)
```

**Output:**

```text
1
```

### Example 2

```python
a = 12
b = 10

print(a & b)
```

Binary representation:

```text
12 = 1100
10 = 1010
-----------
AND 1000
```

**Output:**

```text
8
```

কারণ Binary `1000`-এর Decimal value `8`।

## 3. Understanding Bitwise OR (`|`)

Bitwise OR প্রতিটি bit position-এ দুটি bit পরীক্ষা করে।

কমপক্ষে একটি bit `1` হলে output `1` হয়। শুধু দুটি bit-ই `0` হলে output `0` হয়।

### OR Truth Table

| A | B | A \| B |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

### Example 1: Simple Calculation

ধরি:

```text
A = 5  →  101
B = 3  →  011
```

এখন bitwise OR করি:

```text
  101
| 011
-----
  111
```

Binary `111`-এর Decimal value `7`।

### Python Code

```python
a = 5
b = 3

print(a | b)
```

**Output:**

```text
7
```

### Example 2

```python
a = 12
b = 10

print(a | b)
```

Calculation:

```text
12 = 1100
10 = 1010
-----------
 OR 1110
```

Binary `1110`-এর Decimal value `14`।

**Output:**

```text
14
```

## 4. Understanding Bitwise XOR (`^`)

XOR-এর পূর্ণরূপ হলো **Exclusive OR**।

Bitwise XOR-এর নিয়ম হলো:

- দুটি bit একই হলে output `0`।
- দুটি bit আলাদা হলে output `1`।

### XOR Truth Table

| A | B | A ^ B |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

### Example 1: Simple Calculation

ধরি:

```text
A = 5  →  101
B = 3  →  011
```

এখন XOR করি:

```text
  101
^ 011
-----
  110
```

Binary `110`-এর Decimal value `6`।

### Python Code

```python
a = 5
b = 3

print(a ^ b)
```

**Output:**

```text
6
```

### Example 2

```python
a = 12
b = 10

print(a ^ b)
```

Calculation:

```text
12 = 1100
10 = 1010
-----------
XOR 0110
```

Binary `0110`-এর Decimal value `6`।

**Output:**

```text
6
```

## 5. Comparing AND, OR and XOR

একই দুটি number দিয়ে তিনটি operator ব্যবহার করলে ফলাফল আলাদা হতে পারে।

### Example

```python
a = 5
b = 3

print("AND:", a & b)
print("OR:", a | b)
print("XOR:", a ^ b)
```

**Output:**

```text
AND: 1
OR: 7
XOR: 6
```

### Binary Calculation

```text
a = 5 = 101
b = 3 = 011
```

AND:

```text
  101
& 011
-----
  001  = 1
```

OR:

```text
  101
| 011
-----
  111  = 7
```

XOR:

```text
  101
^ 011
-----
  110  = 6
```

## 6. Bitwise Operators Work Position by Position

Bitwise operations করার সময় একই position-এর bit-গুলো তুলনা করা হয়।

যেমন:

```text
A = 1101
B = 0101
```

AND:

```text
  1101
& 0101
------
  0101
```

OR:

```text
  1101
| 0101
------
  1101
```

XOR:

```text
  1101
^ 0101
------
  1000
```

সুতরাং:

- AND-এর ফলাফল `0101` = Decimal `5`
- OR-এর ফলাফল `1101` = Decimal `13`
- XOR-এর ফলাফল `1000` = Decimal `8`

## 7. Important Properties of Bitwise Operators

### 7.1 AND with Zero

যেকোনো integer `x`-এর জন্য:

```python
print(x & 0)
```

ফলাফল সবসময় `0`।

কারণ AND-এর ক্ষেত্রে দুটি bit-ই `1` না হলে ফলাফল `1` হয় না।

### 7.2 OR with Zero

```python
x = 10
print(x | 0)
```

**Output:**

```text
10
```

কারণ OR-এর ক্ষেত্রে `0` অন্য bit-এর value পরিবর্তন করে না।

### 7.3 XOR with Zero

```python
x = 10
print(x ^ 0)
```

**Output:**

```text
10
```

কারণ কোনো bit-এর সঙ্গে `0` XOR করলে সেই bit-ই পাওয়া যায়।

### 7.4 XOR with the Same Number

```python
x = 10
print(x ^ x)
```

**Output:**

```text
0
```

কারণ প্রতিটি bit নিজের সঙ্গে XOR করলে `0` হয়।

### 7.5 AND with the Same Number

```python
x = 10
print(x & x)
```

**Output:**

```text
10
```

### 7.6 OR with the Same Number

```python
x = 10
print(x | x)
```

**Output:**

```text
10
```

## 8. Practical Example: Checking Whether a Number Is Odd or Even

Bitwise AND ব্যবহার করে কোনো integer odd নাকি even, তা পরীক্ষা করা যায়।

Integer-এর binary representation-এর শেষ bit:

- `0` হলে সংখ্যাটি even।
- `1` হলে সংখ্যাটি odd।

তাই `number & 1` ব্যবহার করা যায়।

### Example

```python
number = 7

if number & 1:
    print("Odd")
else:
    print("Even")
```

**Output:**

```text
Odd
```

কারণ:

```text
7 = 111
1 = 001
---------
AND 001 = 1
```

ফলাফল `1`, তাই সংখ্যাটি odd।

আরেকটি উদাহরণ:

```python
number = 8

print(number & 1)
```

**Output:**

```text
0
```

তাই `8` একটি even number।

## 9. Practical Example: Working with Flags

কোনো application-এ একাধিক Boolean option-কে bit দিয়ে represent করা যায়। একে সাধারণভাবে **bit flags** বলা হয়।

ধরি:

```python
READ = 1     # Binary 001
WRITE = 2    # Binary 010
EXECUTE = 4  # Binary 100
```

একাধিক permission একসঙ্গে রাখি:

```python
permissions = READ | WRITE

print(permissions)
```

**Output:**

```text
3
```

কারণ:

```text
READ  = 001
WRITE = 010
------------
OR      011 = 3
```

কোনো permission আছে কি না পরীক্ষা করতে AND ব্যবহার করা যায়:

```python
if permissions & READ:
    print("Read permission is enabled")
```

**Output:**

```text
Read permission is enabled
```

এখানে `permissions & READ` শূন্য নয়, কারণ `READ` bit সেট করা আছে।

## 10. Difference Between Logical and Bitwise Operators

Logical operators এবং bitwise operators দেখতে কিছুটা মিল থাকলেও তাদের কাজ আলাদা।

| বিষয় | Logical Operator | Bitwise Operator |
|---|---|---|
| AND | `and` | `&` |
| OR | `or` | `|` |
| XOR | সরাসরি কোনো logical keyword নেই | `^` |
| প্রধান কাজ | Truth value বা condition নিয়ে কাজ | Integer-এর binary bits নিয়ে কাজ |

### Example

```python
a = True
b = False

print(a and b)
print(a & b)
```

**Output:**

```text
False
False
```

এই উদাহরণে ফলাফল একই হলেও operator দুটির semantics আলাদা। বিশেষ করে `and` ও `or` short-circuit করতে পারে, কিন্তু `&` ও `|` তা করে না এবং সাধারণত integer-এর bitwise operation হিসেবে ব্যবহৃত হয়।

সাধারণ condition লেখার সময় `and` ও `or` ব্যবহার করবে। Integer-এর bitwise manipulation-এর জন্য `&`, `|`, `^` ব্যবহার করবে।

## 11. Common Mistakes

### Mistake 1: `&` এবং `and`-কে একই মনে করা

```python
print(5 & 3)
```

Output `1`, কারণ এটি bitwise AND।

```python
print(5 and 3)
```

Output `3`, কারণ `and` truthiness অনুযায়ী operand return করে; এখানে দুটি সংখ্যাই truthy।

### Mistake 2: XOR-কে OR মনে করা

OR-এ অন্তত একটি bit `1` হলে output `1` হয়।

XOR-এ দুটি bit আলাদা হলে output `1` হয়।

বিশেষ করে:

```text
1 OR 1  = 1
1 XOR 1 = 0
```

### Mistake 3: Binary digits-এর position ভুল করা

দুটি number-এর bit পাশাপাশি align করে তুলনা করতে হবে। প্রয়োজন হলে বাম পাশে leading zero বসিয়ে নিতে পারো।

### Mistake 4: Binary result-কে Decimal result মনে করা

Bitwise calculation-এর পরে পাওয়া binary pattern-কে Decimal-এ রূপান্তর করলে Python-এর integer output পাওয়া যায়।

উদাহরণ:

```text
101 & 011 = 001
```

এখানে `001` হলো Binary representation, আর তার Decimal value `1`।

## 12. Practice Exercises

### Exercise 1: Predict the Output

```python
a = 6
b = 3

print(a & b)
print(a | b)
print(a ^ b)
```

**Answers:**

```text
2
7
5
```

### Exercise 2: Binary Calculation

নিচের operation-গুলোর binary ও Decimal result বের করো:

1. `1100 & 1010`
2. `1100 | 1010`
3. `1100 ^ 1010`

**Answers:**

1. `1000` = Decimal `8`
2. `1110` = Decimal `14`
3. `0110` = Decimal `6`

### Exercise 3: Find the Output

```python
print(9 & 1)
print(9 | 1)
print(9 ^ 1)
```

**Answers:**

```text
1
9
8
```

### Exercise 4: Find the Output

```python
x = 12

print(x & 0)
print(x | 0)
print(x ^ 0)
print(x ^ x)
```

**Answers:**

```text
0
12
12
0
```

### Exercise 5: Odd or Even

```python
number = 14

if number & 1:
    print("Odd")
else:
    print("Even")
```

**Answer:**

```text
Even
```

### Exercise 6: Complete the Table

| A | B | AND | OR | XOR |
|---:|---:|---:|---:|---:|
| 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 1 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 0 |

নিজে table-টি লিখে পূরণ করার চেষ্টা করো, তারপর answer-এর সঙ্গে মিলিয়ে দেখো।

## 13. Summary

- Bitwise operators integer-এর binary bits-এর ওপর কাজ করে।
- `&` হলো Bitwise AND; দুটি bit-ই `1` হলে output `1`।
- `|` হলো Bitwise OR; অন্তত একটি bit `1` হলে output `1`।
- `^` হলো Bitwise XOR; দুটি bit আলাদা হলে output `1`।
- `x & 0` এর ফলাফল `0`।
- `x | 0` এবং `x ^ 0` এর ফলাফল `x`।
- `x ^ x` এর ফলাফল `0`।
- `number & 1` দিয়ে non-negative integer odd নাকি even পরীক্ষা করা যায়।
- `and`, `or` এবং `&`, `|` এক জিনিস নয়।

## 14. Self-Assessment Checklist

- [ ] Bitwise AND-এর truth table জানি।
- [ ] Bitwise OR-এর truth table জানি।
- [ ] Bitwise XOR-এর truth table জানি।
- [ ] Binary representation ব্যবহার করে calculation করতে পারি।
- [ ] Python code-এর bitwise output অনুমান করতে পারি।
- [ ] Logical ও bitwise operators-এর পার্থক্য বুঝি।
- [ ] `&` দিয়ে odd/even পরীক্ষা করতে পারি।
- [ ] Bit flags-এর basic ধারণা বুঝি।
