# 23. Bitwise NOT and Shift Operators

## 1. Introduction

Python-এ Bitwise NOT এবং Shift Operators integer-এর binary bits নিয়ে কাজ করে।

এই টপিকে আমরা তিনটি operator শিখব:

| Operator | Name | কাজ |
|---|---|---|
| `~` | Bitwise NOT | প্রতিটি bit উল্টে দেয় |
| `<<` | Left Shift | Bit-গুলোকে বাম দিকে সরায় |
| `>>` | Right Shift | Bit-গুলোকে ডান দিকে সরায় |

Bitwise AND, OR ও XOR-এর মতো এই operator-গুলোও bitwise operation-এর অংশ।

## 2. Bitwise NOT (`~`)

Bitwise NOT প্রতিটি bit উল্টে দেয়:

- `0` পরিবর্তিত হয়ে `1` হয়।
- `1` পরিবর্তিত হয়ে `0` হয়।

একে bit inversion-ও বলা হয়।

### Example

ধরি, একটি ৪-bit pattern:

```text
Original:  0101
NOT:       1010
```

এখানে প্রতিটি bit উল্টে গেছে।

**কিন্তু গুরুত্বপূর্ণ বিষয়:** Python-এর integer সাধারণ fixed ৪-bit বা ৮-bit representation-এ সীমাবদ্ধ নয়। তাই উপরের উদাহরণটি শুধু bit উল্টানোর ধারণা বোঝানোর জন্য।

## 3. Why Does `~5` Return `-6` in Python?

Python-এ Bitwise NOT-এর একটি গুরুত্বপূর্ণ নিয়ম হলো:

\[
\sim x = -(x+1)
\]

অর্থাৎ, কোনো integer `x`-এর Bitwise NOT করলে ফলাফল হয় `-(x + 1)`।

### Example 1

```python
print(~5)
```

**Output:**

```text
-6
```

কারণ:

\[
\sim 5 = -(5+1)=-6
\]

### Example 2

```python
print(~10)
```

**Output:**

```text
-11
```

কারণ:

\[
\sim 10 = -(10+1)=-11
\]

### Example 3

```python
print(~0)
```

**Output:**

```text
-1
```

কারণ:

\[
\sim 0 = -(0+1)=-1
\]

### Quick Table

| Expression | Output |
|---|---:|
| `~0` | `-1` |
| `~1` | `-2` |
| `~2` | `-3` |
| `~5` | `-6` |
| `~10` | `-11` |

**মনে রাখার কৌশল:** `~x` বের করতে সংখ্যাটির সঙ্গে `1` যোগ করে negative করে দাও।

## 4. Bitwise NOT in Binary

Python-এর Bitwise NOT বুঝতে signed integer-এর binary representation সম্পর্কে ধারণা কাজে লাগে।

কম্পিউটারের hardware সাধারণত নির্দিষ্ট-width representation ব্যবহার করে; signed integer-এর ক্ষেত্রে two's complement একটি প্রচলিত পদ্ধতি। Python-এর integer অবশ্য fixed-width নয়, এবং তার bitwise operation-গুলো এমনভাবে সংজ্ঞায়িত যে এগুলোকে ধারণাগতভাবে two's complement-এর অসীম sign extension-সহ হিসাব করা যায়।

ধারণাটি বোঝার জন্য ৮-bit উদাহরণ দেখি।

```text
 5  = 00000101
~5  = 11111010
```

এই ৮-bit two's complement pattern-টি signed integer হিসেবে `-6` বোঝায়।

তাই Python-এ:

```python
print(~5)
```

Output:

```text
-6
```

এখানে ৮-bit pattern শুধু বোঝানোর জন্য ব্যবহার করা হয়েছে; Python নিজে integer-কে ৮-bit-এ সীমাবদ্ধ করে না।

## 5. Left Shift Operator (`<<`)

Left Shift operator bit-গুলোকে নির্দিষ্ট সংখ্যক position বাম দিকে সরায়।

ডান পাশ থেকে শূন্য bit যোগ হয়।

### Syntax

```python
number << shift_amount
```

এখানে:

- `number` হলো integer।
- `shift_amount` হলো কতটি bit বাম দিকে সরাতে হবে।

### Example 1

```python
print(5 << 1)
```

প্রথমে `5`-এর binary representation:

```text
5 = 0101
```

এক bit বাম দিকে সরালে:

```text
0101 << 1 = 1010
```

`1010`-এর Decimal value `10`।

**Output:**

```text
10
```

### Example 2

```python
print(5 << 2)
```

Binary calculation:

```text
0101 << 2 = 10100
```

`10100`-এর Decimal value `20`।

**Output:**

```text
20
```

### Example 3

```python
print(3 << 3)
```

Binary calculation:

```text
3 = 11

11 << 3 = 11000
```

Binary `11000`-এর Decimal value `24`।

**Output:**

```text
24
```

## 6. Left Shift and Multiplication

Non-negative integer-এর ক্ষেত্রে left shift-এর ফলাফলকে এভাবে প্রকাশ করা যায়:

\[
x \ll n = x \times 2^n
\]

অর্থাৎ, `n` bit বাম দিকে সরালে সংখ্যাটিকে \(2^n\) দিয়ে গুণ করার সমতুল্য ফল পাওয়া যায়।

### Examples

| Expression | Calculation | Output |
|---|---|---:|
| `5 << 1` | \(5 \times 2\) | `10` |
| `5 << 2` | \(5 \times 4\) | `20` |
| `5 << 3` | \(5 \times 8\) | `40` |
| `7 << 2` | \(7 \times 4\) | `28` |

### Python Code

```python
x = 7

print(x << 1)
print(x << 2)
print(x << 3)
```

**Output:**

```text
14
28
56
```

এই নিয়মটি Python integer-এর ক্ষেত্রে mathematicalভাবে প্রযোজ্য। তবে বাস্তব hardware বা fixed-width data type-এ overflow-এর মতো বিষয় থাকতে পারে।

## 7. Right Shift Operator (`>>`)

Right Shift operator bit-গুলোকে নির্দিষ্ট সংখ্যক position ডান দিকে সরায়।

Python signed integer-এর ক্ষেত্রে right shift arithmetic right shift-এর মতো আচরণ করে। অর্থাৎ, ডান দিকে সরানোর সময় sign বজায় রাখতে বাম পাশে sign bit-এর মান দিয়ে জায়গা পূরণ করা হয়।

### Syntax

```python
number >> shift_amount
```

### Example 1

```python
print(10 >> 1)
```

Binary representation:

```text
10 = 1010

1010 >> 1 = 0101
```

Binary `0101`-এর Decimal value `5`।

**Output:**

```text
5
```

### Example 2

```python
print(20 >> 2)
```

Binary representation:

```text
20 = 10100

10100 >> 2 = 00101
```

Binary `00101`-এর Decimal value `5`।

**Output:**

```text
5
```

### Example 3

```python
print(40 >> 3)
```

**Output:**

```text
5
```

কারণ:

\[
40 \gg 3 = 40 \div 2^3 = 5
\]

## 8. Right Shift and Division

Non-negative integer-এর ক্ষেত্রে right shift সাধারণত \(2^n\) দিয়ে integer division করার সমতুল্য।

\[
x \gg n = \left\lfloor \frac{x}{2^n} \right\rfloor
\]

এখানে \(\lfloor \ \rfloor\) বোঝায় নিচের পূর্ণসংখ্যায় নামিয়ে আনা।

### Example

```python
print(13 >> 1)
print(13 >> 2)
print(13 >> 3)
```

**Output:**

```text
6
3
1
```

ব্যাখ্যা:

- `13 >> 1` → \(13 // 2 = 6\)
- `13 >> 2` → \(13 // 4 = 3\)
- `13 >> 3` → \(13 // 8 = 1\)

খেয়াল রাখবে, `>>`-এর সঙ্গে negative number থাকলে ফলাফল বোঝার জন্য শুধু সাধারণ division নয়, arithmetic right shift-এর নিয়ম অনুসরণ করতে হবে।

## 9. Understanding Negative Numbers with Right Shift

Python-এ negative integer-এর right shift-ও arithmetic right shift-এর নিয়ম মেনে চলে।

### Example

```python
print(-5 >> 1)
print(-5 >> 2)
```

**Output:**

```text
-3
-2
```

কারণ Python-এর right shift negative number-এর ক্ষেত্রে ফলাফলকে নিচের পূর্ণসংখ্যার দিকে নেয়:

- `-5 >> 1` → \(\lfloor -5/2 \rfloor = -3\)
- `-5 >> 2` → \(\lfloor -5/4 \rfloor = -2\)

এজন্য negative number-এর right shift-কে সবসময় সাধারণ truncating division-এর সমান মনে করা যাবে না।

## 10. Shift by Zero

কোনো integer-কে zero bit shift করলে সংখ্যাটি অপরিবর্তিত থাকে।

### Example

```python
x = 12

print(x << 0)
print(x >> 0)
```

**Output:**

```text
12
12
```

কারণ কোনো bit সরানো হয়নি।

## 11. Shifting by a Negative Number

Python-এ shift amount negative হতে পারে না।

### Example

```python
print(5 << -1)
```

এতে `ValueError` হবে।

একইভাবে:

```python
print(10 >> -2)
```

এতেও `ValueError` হবে।

**মনে রাখবে:** Shift amount অবশ্যই non-negative integer হতে হবে।

## 12. Shifting by a Large Number

Python integer fixed-width নয়। তাই positive integer-কে অনেক bit বাম দিকে shift করলে Python বড় integer তৈরি করতে পারে।

### Example

```python
print(1 << 10)
```

**Output:**

```text
1024
```

কারণ:

\[
1 \times 2^{10}=1024
\]

আরেকটি উদাহরণ:

```python
print(1 << 20)
```

**Output:**

```text
1048576
```

বড় shift-এর ফলে খুব বড় integer তৈরি হতে পারে, যা বেশি memory ও processing time নিতে পারে।

## 13. Comparing NOT, Left Shift and Right Shift

| Operator | Example | Output | কাজ |
|---|---|---:|---|
| `~` | `~5` | `-6` | Bitwise NOT |
| `<<` | `5 << 1` | `10` | এক bit বামে সরায় |
| `<<` | `5 << 2` | `20` | দুই bit বামে সরায় |
| `>>` | `10 >> 1` | `5` | এক bit ডানে সরায় |
| `>>` | `20 >> 2` | `5` | দুই bit ডানে সরায় |

## 14. Common Mistakes

### Mistake 1: `~5`-এর ফলাফল `-5` মনে করা

ভুল ধারণা:

```text
~5 = -5
```

সঠিক ফলাফল:

```text
~5 = -6
```

কারণ:

\[
\sim x = -(x+1)
\]

### Mistake 2: Left Shift-কে শুধু bit সরানো মনে করা

Bit সরানোর পাশাপাশি ফলাফলের numeric value-ও পরিবর্তিত হয়।

```python
print(4 << 2)
```

Output:

```text
16
```

কারণ \(4 \times 2^2 = 16\)।

### Mistake 3: Right Shift-কে সাধারণ division-এর সঙ্গে গুলিয়ে ফেলা

Positive integer-এর ক্ষেত্রে right shift-কে floor division দিয়ে বোঝানো যায়। Negative integer-এর ক্ষেত্রে Python arithmetic right shift ব্যবহার করে, তাই ফলাফল বুঝতে floor-এর নিয়ম গুরুত্বপূর্ণ।

### Mistake 4: Negative shift amount ব্যবহার করা

```python
print(8 << -1)
```

এটি `ValueError` তৈরি করবে। Shift amount negative হতে পারে না।

## 15. Practice Exercises

### Exercise 1: Predict the Output

```python
print(~3)
print(~7)
print(~0)
```

**Answers:**

```text
-4
-8
-1
```

### Exercise 2: Left Shift

```python
print(3 << 1)
print(3 << 2)
print(6 << 3)
```

**Answers:**

```text
6
12
48
```

### Exercise 3: Right Shift

```python
print(16 >> 1)
print(16 >> 2)
print(15 >> 2)
```

**Answers:**

```text
8
4
3
```

### Exercise 4: Mixed Operations

```python
x = 8

print(x << 1)
print(x >> 1)
print(~x)
```

**Answers:**

```text
16
4
-9
```

### Exercise 5: Negative Right Shift

```python
print(-7 >> 1)
print(-7 >> 2)
```

**Answers:**

```text
-4
-2
```

### Exercise 6: Fill in the Blanks

1. Bitwise NOT operator হলো `_____`।
2. Left Shift operator হলো `_____`।
3. Right Shift operator হলো `_____`।
4. `~5`-এর output হলো `_____`।
5. `4 << 2`-এর output হলো `_____`।
6. `20 >> 2`-এর output হলো `_____`।

**Answers:** `~`, `<<`, `>>`, `-6`, `16`, `5`

## 16. Summary

- `~` প্রতিটি bit উল্টে দেয়।
- Python-এ `~x`-এর ফলাফল `-(x + 1)`।
- `<<` bit-গুলোকে বাম দিকে সরায়।
- `>>` bit-গুলোকে ডান দিকে সরায় এবং Python-এ signed integer-এর sign বজায় রাখে।
- Non-negative integer-এর ক্ষেত্রে `x << n` হলো `x * (2 ** n)`-এর সমতুল্য।
- Non-negative integer-এর ক্ষেত্রে `x >> n` হলো `x // (2 ** n)`-এর সমতুল্য।
- Negative integer-এর right shift arithmetic shift-এর নিয়ম মেনে চলে।
- Negative shift amount ব্যবহার করলে `ValueError` হয়।
- Python integer fixed-width নয়; তাই hardware-এর fixed-width integer-এর সঙ্গে কিছু পার্থক্য থাকতে পারে।

## 17. Self-Assessment Checklist

- [ ] Bitwise NOT-এর কাজ বুঝি।
- [ ] কেন `~5`-এর ফলাফল `-6` হয়, তা ব্যাখ্যা করতে পারি।
- [ ] Left Shift ও Right Shift-এর পার্থক্য জানি।
- [ ] Shift operation-এর binary calculation করতে পারি।
- [ ] Positive integer-এর shift result বের করতে পারি।
- [ ] Negative integer-এর right shift-এর আচরণ বুঝি।
- [ ] Negative shift amount কেন error তৈরি করে, তা জানি।
