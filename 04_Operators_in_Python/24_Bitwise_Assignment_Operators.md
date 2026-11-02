# 24. Bitwise Assignment Operators

## 1. Introduction

Python-এ Assignment Operator ব্যবহার করে variable-এর মধ্যে value রাখা বা update করা যায়।

Bitwise Assignment Operators হলো এমন operators, যেগুলো bitwise operation সম্পন্ন করে সেই ফলাফল আবার একই variable-এ assign করে।

উদাহরণ:

```python
x = 10
x &= 6
```

এটি নিচের code-এর সমতুল্য:

```python
x = 10
x = x & 6
```

দুটি ক্ষেত্রেই `x`-এর নতুন value হবে `2`।

## 2. Types of Bitwise Assignment Operators

Python-এ প্রধান Bitwise Assignment Operators:

| Operator | Equivalent Expression | কাজ |
|---|---|---|
| `&=` | `x = x & y` | Bitwise AND করে update |
| `|=` | `x = x \| y` | Bitwise OR করে update |
| `^=` | `x = x ^ y` | Bitwise XOR করে update |
| `<<=` | `x = x << y` | Left Shift করে update |
| `>>=` | `x = x >> y` | Right Shift করে update |

**মনে রাখবে:** `=` হলো assignment, আর তার আগে bitwise operator যুক্ত হলে operation-এর ফলাফল variable-এ assign হয়।

## 3. Bitwise AND Assignment (`&=`)

`&=` operator প্রথমে AND operation করে, তারপর ফলাফল variable-এ assign করে।

### Example

```python
x = 10
x &= 6

print(x)
```

**Output:**

```text
2
```

### Binary Calculation

```text
10 = 1010
 6 = 0110
-----------
AND 0010
```

Binary `0010`-এর Decimal value `2`।

তাই `x`-এর নতুন value `2`।

### Equivalent Code

```python
x = 10
x = x & 6

print(x)
```

Output:

```text
2
```

দুটি code-এর ফলাফল একই।

## 4. Bitwise OR Assignment (`|=`)

`|=` operator OR operation করে এবং ফলাফল variable-এ assign করে।

### Example

```python
x = 10
x |= 6

print(x)
```

**Output:**

```text
14
```

### Binary Calculation

```text
10 = 1010
 6 = 0110
-----------
 OR 1110
```

Binary `1110`-এর Decimal value `14`।

### Equivalent Code

```python
x = 10
x = x | 6

print(x)
```

Output:

```text
14
```

## 5. Bitwise XOR Assignment (`^=`)

`^=` operator XOR operation করে এবং ফলাফল variable-এ assign করে।

XOR-এর নিয়ম হলো: দুটি bit আলাদা হলে output `1`, আর একই হলে output `0`।

### Example

```python
x = 10
x ^= 6

print(x)
```

**Output:**

```text
12
```

### Binary Calculation

```text
10 = 1010
 6 = 0110
-----------
XOR 1100
```

Binary `1100`-এর Decimal value `12`।

### Equivalent Code

```python
x = 10
x = x ^ 6

print(x)
```

Output:

```text
12
```

## 6. Left Shift Assignment (`<<=`)

`<<=` operator bit-গুলোকে বাম দিকে shift করে এবং ফলাফল variable-এ assign করে।

### Example

```python
x = 5
x <<= 2

print(x)
```

**Output:**

```text
20
```

### Explanation

```text
5 = 101

101 << 2 = 10100
```

Binary `10100`-এর Decimal value `20`।

তাই `x`-এর নতুন value `20`।

### Equivalent Code

```python
x = 5
x = x << 2

print(x)
```

Output:

```text
20
```

Non-negative integer-এর ক্ষেত্রে দুই bit left shift করা মানে \(2^2\) দিয়ে গুণ করার সমতুল্য।

## 7. Right Shift Assignment (`>>=`)

`>>=` operator bit-গুলোকে ডান দিকে shift করে এবং ফলাফল variable-এ assign করে।

### Example

```python
x = 20
x >>= 2

print(x)
```

**Output:**

```text
5
```

### Explanation

```text
20 = 10100

10100 >> 2 = 00101
```

Binary `00101`-এর Decimal value `5`।

তাই `x`-এর নতুন value `5`।

### Equivalent Code

```python
x = 20
x = x >> 2

print(x)
```

Output:

```text
5
```

## 8. Comparing All Bitwise Assignment Operators

একই initial value ব্যবহার করে পাঁচটি operator-এর ফলাফল দেখি।

### Example

```python
a = 10
a &= 6
print(a)

b = 10
b |= 6
print(b)

c = 10
c ^= 6
print(c)

d = 5
d <<= 2
print(d)

e = 20
e >>= 2
print(e)
```

**Output:**

```text
2
14
12
20
5
```

### Quick Reference

| Expression | Calculation | Result |
|---|---|---:|
| `10 &= 6` | `10 & 6` | `2` |
| `10 |= 6` | `10 \| 6` | `14` |
| `10 ^= 6` | `10 ^ 6` | `12` |
| `5 <<= 2` | `5 << 2` | `20` |
| `20 >>= 2` | `20 >> 2` | `5` |

উপরের টেবিলে প্রথম column-এ ধারণাগতভাবে initial value দেখানো হয়েছে। বাস্তব Python code-এ assignment হবে `x = 10` এবং এরপর `x &= 6`-এর মতো।

## 9. Updating a Variable Multiple Times

Bitwise Assignment Operators একাধিকবার ব্যবহার করে variable-এর value ধাপে ধাপে update করা যায়।

### Example

```python
x = 12

x &= 10
print(x)

x |= 1
print(x)

x ^= 3
print(x)
```

**Output:**

```text
8
9
10
```

### Step-by-Step Explanation

**Step 1:**

```text
12 = 1100
10 = 1010
-----------
AND 1000 = 8
```

তাই `x = 8`।

**Step 2:**

```text
8 = 1000
1 = 0001
----------
OR  1001 = 9
```

তাই `x = 9`।

**Step 3:**

```text
9 = 1001
3 = 0011
----------
XOR 1010 = 10
```

তাই শেষ পর্যন্ত `x = 10`।

## 10. Practical Example: Setting and Clearing Bits

Bitwise Assignment Operators ব্যবহার করে নির্দিষ্ট bit set বা clear করা যায়।

ধরি, একটি bit position-কে `1` করতে চাই।

### Setting a Bit Using `|=`

```python
x = 8       # Binary: 1000
mask = 2    # Binary: 0010

x |= mask

print(x)
```

**Output:**

```text
10
```

কারণ:

```text
1000
0010
----
1010 = 10
```

এখানে mask-এর যে position-এ `1` আছে, সেই position-এ bit set হয়েছে।

### Clearing a Bit Using `&=`

```python
x = 10      # Binary: 1010
mask = ~2

x &= mask

print(x)
```

**Output:**

```text
8
```

এখানে `~2` হলো `-3`। Python-এর bitwise integer semantics অনুযায়ী, `x &= ~2` দ্বিতীয় bit position-এর bit clear করে।

সহজভাবে, `x = 10`-এর binary pattern `1010`; দ্বিতীয় bit clear করলে `1000`, যার Decimal value `8`।

**Note:** বাস্তবে bit flags নিয়ে কাজ করার সময় mask-এর width ও bit position ঠিকভাবে বুঝে ব্যবহার করা জরুরি।

## 11. Bitwise Assignment vs Regular Assignment

Bitwise Assignment Operators-কে সাধারণ Assignment Operators-এর সঙ্গে গুলিয়ে ফেলবে না।

| Operator | কাজ |
|---|---|
| `=` | Value assign করে |
| `+=` | Addition করে assign |
| `-=` | Subtraction করে assign |
| `*=` | Multiplication করে assign |
| `&=` | Bitwise AND করে assign |
| `|=` | Bitwise OR করে assign |
| `^=` | Bitwise XOR করে assign |
| `<<=` | Left Shift করে assign |
| `>>=` | Right Shift করে assign |

### Example

```python
x = 5
x += 2
print(x)
```

Output:

```text
7
```

এটি arithmetic assignment।

অন্যদিকে:

```python
x = 5
x |= 2
print(x)
```

Output:

```text
7
```

এটি bitwise assignment।

এই উদাহরণে output একই হলেও operation দুটি আলাদা।

## 12. Common Mistakes

### Mistake 1: `&=`-কে `=`-এর মতো মনে করা

```python
x = 10
x &= 6
```

এখানে `x` সরাসরি `6` হয়ে যায় না। প্রথমে `10 & 6` হিসাব হয়, তারপর ফলাফল assign হয়।

Output:

```text
2
```

### Mistake 2: `^=`-কে Power Operator মনে করা

Python-এ `^` হলো Bitwise XOR, exponentiation নয়।

```python
x = 5
x ^= 2

print(x)
```

Output:

```text
7
```

Power বা exponentiation-এর জন্য `**` ব্যবহার করতে হয়:

```python
print(5 ** 2)
```

Output:

```text
25
```

### Mistake 3: Shift Amount ভুল দেওয়া

```python
x = 8
x <<= -1
```

এটি `ValueError` তৈরি করবে, কারণ shift amount negative হতে পারে না।

### Mistake 4: Variable-এর আগের Value ভুলে যাওয়া

```python
x = 10
x &= 6
x |= 1

print(x)
```

Output:

```text
3
```

কারণ প্রথম operation-এর পর `x = 2`, এরপর `2 | 1 = 3`।

## 13. Practice Exercises

### Exercise 1: Predict the Output

```python
x = 15
x &= 7

print(x)
```

**Answer:**

```text
7
```

### Exercise 2: Predict the Output

```python
x = 8
x |= 3

print(x)
```

**Answer:**

```text
11
```

### Exercise 3: Predict the Output

```python
x = 12
x ^= 5

print(x)
```

**Answer:**

```text
9
```

### Exercise 4: Predict the Output

```python
x = 3
x <<= 3

print(x)
```

**Answer:**

```text
24
```

### Exercise 5: Predict the Output

```python
x = 32
x >>= 3

print(x)
```

**Answer:**

```text
4
```

### Exercise 6: Multiple Operations

```python
x = 10

x &= 7
x |= 8
x ^= 3

print(x)
```

**Answer:**

```text
12
```

### Exercise 7: Fill in the Blanks

1. Bitwise AND Assignment Operator হলো `_____`।
2. Bitwise OR Assignment Operator হলো `_____`।
3. Bitwise XOR Assignment Operator হলো `_____`।
4. Left Shift Assignment Operator হলো `_____`।
5. Right Shift Assignment Operator হলো `_____`।

**Answers:** `&=`, `|=`, `^=`, `<<=`, `>>=`

## 14. Summary

- Bitwise Assignment Operators operation করে ফলাফল variable-এ assign করে।
- `&=` Bitwise AND করে।
- `|=` Bitwise OR করে।
- `^=` Bitwise XOR করে।
- `<<=` Left Shift করে।
- `>>=` Right Shift করে।
- `x &= y` হলো `x = x & y`-এর সমতুল্য।
- Bitwise Assignment Operators bit flags ও binary data manipulation-এ কাজে লাগে।
- `^` exponentiation নয়; Python-এ exponentiation-এর জন্য `**` ব্যবহার করতে হয়।

## 15. Self-Assessment Checklist

- [ ] পাঁচটি Bitwise Assignment Operator চিনতে পারি।
- [ ] প্রতিটি operator-এর ফলাফল binary calculation দিয়ে বের করতে পারি।
- [ ] `x &= y`-এর অর্থ ব্যাখ্যা করতে পারি।
- [ ] একাধিক bitwise assignment operation-এর output বের করতে পারি।
- [ ] Bitwise assignment ও arithmetic assignment-এর পার্থক্য বুঝি।
- [ ] Bit set এবং clear করার basic ধারণা বুঝি।
