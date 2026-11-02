# 21. Binary Number Basics

## 1. Introduction to Binary Numbers

কম্পিউটার মূলত data সংরক্ষণ ও প্রক্রিয়াকরণের জন্য দুটি অবস্থা ব্যবহার করে:

- `0` — Low বা Off
- `1` — High বা On

এই দুটি digit ব্যবহার করে যে number system তৈরি হয়, তাকে **Binary Number System** বলে।

আমরা দৈনন্দিন জীবনে সাধারণত Decimal Number System ব্যবহার করি, যেখানে `0` থেকে `9` পর্যন্ত মোট ১০টি digit রয়েছে।

কিন্তু Binary Number System-এ শুধু দুটি digit থাকে: `0` এবং `1`।

### Example

| Number System | ব্যবহৃত Digit | Base |
|---|---|---:|
| Binary | `0`, `1` | 2 |
| Decimal | `0`–`9` | 10 |
| Octal | `0`–`7` | 8 |
| Hexadecimal | `0`–`9`, `A`–`F` | 16 |

এখানে **Base** বা Radix হলো একটি number system-এ ব্যবহৃত মোট digit-এর সংখ্যা।

## 2. Why Does a Computer Use Binary?

কম্পিউটারের electronic circuits সহজে দুটি আলাদা অবস্থা শনাক্ত করতে পারে, যেমন voltage-এর Low এবং High অবস্থা।

এই দুই অবস্থাকে সহজভাবে `0` ও `1` দিয়ে প্রকাশ করা হয়।

Binary ব্যবহার করে কম্পিউটার বিভিন্ন ধরনের data represent করতে পারে:

- Numbers
- Text
- Images
- Audio
- Videos
- Program Instructions

অর্থাৎ, কম্পিউটারের ভেতরে বিভিন্ন ধরনের data শেষ পর্যন্ত binary representation-এ সংরক্ষিত ও প্রক্রিয়াজাত হয়।

## 3. What Is a Bit?

**Bit**-এর পূর্ণরূপ হলো *Binary Digit*।

একটি bit-এর value হয় `0` অথবা `1`।

এটি কম্পিউটারের digital data-এর সবচেয়ে ছোট সাধারণ একক।

### Example

```text
0
1
```

প্রতিটি উদাহরণে একটি করে bit রয়েছে।

```text
1010
```

এখানে মোট ৪টি bit রয়েছে।

## 4. What Is a Byte?

একটি **Byte** সাধারণত ৮টি bit নিয়ে গঠিত।

```text
1 Byte = 8 Bits
```

### Example

```text
10110010
```

এই binary sequence-এ ৮টি bit রয়েছে, তাই এটি ১ byte data।

| Unit | Size |
|---|---:|
| 1 Bit | 1 binary digit |
| 1 Byte | 8 bits |
| 1 Kilobyte (KB) | সাধারণ হিসাবে 1,000 bytes |
| 1 Megabyte (MB) | সাধারণ হিসাবে 1,000 KB |
| 1 Gigabyte (GB) | সাধারণ হিসাবে 1,000 MB |

**Note:** Memory ও storage-এর ক্ষেত্রে decimal এবং binary—দুই ধরনের unit convention ব্যবহৃত হয়। Binary convention-এ 1 KiB = 1,024 bytes এবং 1 MiB = 1,024 KiB।

## 5. Understanding Binary Place Values

Decimal number system-এ প্রতিটি position-এর value 10-এর power অনুযায়ী বাড়ে।

যেমন:

```text
345 = 3 × 100 + 4 × 10 + 5 × 1
```

Binary number system-এ প্রতিটি position-এর value 2-এর power অনুযায়ী বাড়ে।

ডান দিক থেকে position শুরু হয় \(2^0\) দিয়ে।

### Binary Place Values

| Position (ডান থেকে) | Power | Value |
|---:|---:|---:|
| 1st | \(2^0\) | 1 |
| 2nd | \(2^1\) | 2 |
| 3rd | \(2^2\) | 4 |
| 4th | \(2^3\) | 8 |
| 5th | \(2^4\) | 16 |
| 6th | \(2^5\) | 32 |
| 7th | \(2^6\) | 64 |
| 8th | \(2^7\) | 128 |

মনে রাখবে, Binary number-এর ডান দিকের digit-এর place value হলো 1, তার বামে 2, তারপর 4, 8, 16—এভাবে বাড়তে থাকে।

## 6. Converting Binary to Decimal

Binary থেকে Decimal-এ রূপান্তর করতে প্রতিটি bit-কে তার position অনুযায়ী \(2\)-এর power দিয়ে গুণ করে সব value যোগ করতে হয়।

### Example 1: Convert `1011` to Decimal

প্রথমে place value বসাই:

| Binary Digit | Place Value | Calculation |
|---:|---:|---:|
| 1 | 8 | \(1 \times 8 = 8\) |
| 0 | 4 | \(0 \times 4 = 0\) |
| 1 | 2 | \(1 \times 2 = 2\) |
| 1 | 1 | \(1 \times 1 = 1\) |

এখন যোগ করি:

\[
8 + 0 + 2 + 1 = 11
\]

সুতরাং:

\[
(1011)_2 = (11)_{10}
\]

### Example 2: Convert `11010` to Decimal

\[
\begin{aligned}
(11010)_2 &= 1(16)+1(8)+0(4)+1(2)+0(1)\\
&=16+8+0+2+0\\
&=26
\end{aligned}
\]

সুতরাং Decimal value হলো `26`।

## 7. Converting Decimal to Binary

Decimal number-কে Binary-তে রূপান্তর করার একটি সাধারণ পদ্ধতি হলো বারবার `2` দিয়ে ভাগ করা এবং প্রতিবার remainder বা ভাগশেষ বের করা।

### Steps

1. Decimal number-কে `2` দিয়ে ভাগ করো।
2. Remainder লিখে রাখো।
3. Quotient-কে আবার `2` দিয়ে ভাগ করো।
4. Quotient `0` না হওয়া পর্যন্ত চালিয়ে যাও।
5. Remainder-গুলো **নিচ থেকে উপরে** পড়ো।

### Example 1: Convert Decimal `13` to Binary

| Division | Quotient | Remainder |
|---|---:|---:|
| 13 ÷ 2 | 6 | 1 |
| 6 ÷ 2 | 3 | 0 |
| 3 ÷ 2 | 1 | 1 |
| 1 ÷ 2 | 0 | 1 |

Remainder নিচ থেকে উপরে পড়লে পাই:

```text
1101
```

সুতরাং:

\[
(13)_{10} = (1101)_2
\]

### Example 2: Convert Decimal `10` to Binary

| Division | Quotient | Remainder |
|---|---:|---:|
| 10 ÷ 2 | 5 | 0 |
| 5 ÷ 2 | 2 | 1 |
| 2 ÷ 2 | 1 | 0 |
| 1 ÷ 2 | 0 | 1 |

নিচ থেকে উপরে পড়লে:

```text
1010
```

সুতরাং:

\[
(10)_{10} = (1010)_2
\]

## 8. Binary Numbers in Python

Python-এ integer-কে binary string-এ রূপান্তর করার জন্য `bin()` function ব্যবহার করা যায়।

### Example

```python
number = 10

print(bin(number))
```

**Output:**

```text
0b1010
```

এখানে:

- `bin()` integer-এর binary representation দেয়।
- `0b` হলো Python-এর binary prefix।
- `1010` হলো সংখ্যাটির binary digits।

`0b` prefix-সহ binary literal লিখেও Python-এ integer তৈরি করা যায়।

```python
number = 0b1010

print(number)
```

**Output:**

```text
10
```

Python `0b1010`-কে binary হিসেবে বুঝে এবং তার integer value `10` হিসেবে প্রকাশ করে।

### আরও কিছু Example

```python
print(bin(5))
print(bin(8))
print(bin(15))
print(bin(20))
```

**Output:**

```text
0b101
0b1000
0b1111
0b10100
```

## 9. Converting Binary Strings to Decimal in Python

Binary string-কে integer-এ রূপান্তর করতে `int()` function-এর দ্বিতীয় argument হিসেবে base `2` দেওয়া যায়।

### Example

```python
binary_number = "1011"

decimal_number = int(binary_number, 2)

print(decimal_number)
```

**Output:**

```text
11
```

এখানে `int(binary_number, 2)` Python-কে জানায় যে string-টি Base 2 বা Binary number।

**মনে রাখবে:**

```python
bin(10)        # Integer থেকে binary string
int("1010", 2) # Binary string থেকে integer
```

## 10. Binary Number and Bitwise Operators

Binary number বোঝা জরুরি, কারণ Python-এর bitwise operators integer-এর binary representation-এর bit-গুলোর ওপর কাজ করে।

যেমন:

- `&` — Bitwise AND
- `|` — Bitwise OR
- `^` — Bitwise XOR
- `~` — Bitwise NOT
- `<<` — Left Shift
- `>>` — Right Shift

এগুলোর বিস্তারিত পরের টপিকগুলোতে আলোচনা করা হবে।

### Simple Preview

```python
a = 5
b = 3

print(bin(a))
print(bin(b))
print(a & b)
```

**Output:**

```text
0b101
0b11
1
```

এখানে `5`-এর binary representation `101` এবং `3`-এর binary representation `11`।

Bitwise AND প্রতিটি bit position-এ দুটি bit-ই `1` হলে ফলাফল `1` দেয়।

```text
  101
& 011
-----
  001
```

ফলাফল `001`, যার Decimal value `1`।

## 11. Common Mistakes

### Mistake 1: Remainder ওপর থেকে নিচে পড়া

Decimal থেকে Binary conversion-এ remainder **নিচ থেকে উপরে** পড়তে হয়।

### Mistake 2: Binary number-এ `2` ব্যবহার করা

Binary system-এ শুধু `0` ও `1` বৈধ digit। তাই `1021` একটি valid binary number নয়।

### Mistake 3: `bin()`-এর output-কে সাধারণ string-এর মতো ভুল বোঝা

```python
print(bin(10))
```

Output `0b1010`। এখানে `0b` prefix-টি binary representation বোঝায়; এটি binary digit-এর অংশ নয়।

### Mistake 4: Bit এবং Byte-কে একই মনে করা

- Bit হলো একটি binary digit।
- Byte হলো ৮টি bit-এর সমষ্টি।

## 12. Practice Exercises

### Exercise 1: Binary to Decimal

নিচের Binary number-গুলোকে Decimal-এ রূপান্তর করো:

1. `101`
2. `1111`
3. `10000`

**Answers:**

1. `5`
2. `15`
3. `16`

### Exercise 2: Decimal to Binary

নিচের Decimal number-গুলোকে Binary-তে রূপান্তর করো:

1. `6`
2. `12`
3. `20`

**Answers:**

1. `110`
2. `1100`
3. `10100`

### Exercise 3: Python Practice

```python
a = 12

print(bin(a))
print(int("1100", 2))
```

**Output:**

```text
0b1100
12
```

### Exercise 4: Fill in the Blanks

1. Binary Number System-এর base হলো `_____`।
2. একটি byte-এ `_____` bits থাকে।
3. Binary থেকে Decimal conversion-এ position value নির্ধারিত হয় `_____`-এর power দিয়ে।
4. Python-এ integer-এর binary representation পেতে `_____()` ব্যবহার করা হয়।

**Answers:** `2`, `8`, `2`, `bin`

## 13. Summary

- Binary Number System-এ শুধু `0` এবং `1` থাকে।
- Binary number system-এর base হলো `2`।
- Bit হলো একটি binary digit।
- একটি byte সাধারণত ৮টি bit নিয়ে গঠিত।
- Binary থেকে Decimal conversion-এ প্রতিটি bit-কে তার \(2\)-এর power অনুযায়ী গুণ করে যোগ করতে হয়।
- Decimal থেকে Binary conversion-এ বারবার `2` দিয়ে ভাগ করে remainder নিচ থেকে উপরে পড়তে হয়।
- Python-এর `bin()` integer-কে binary representation-এ প্রকাশ করে।
- `int(binary_string, 2)` binary string-কে integer-এ রূপান্তর করে।
- Bitwise operators বোঝার জন্য binary number-এর ধারণা গুরুত্বপূর্ণ।

## 14. Self-Assessment Checklist

- [ ] Binary ও Decimal number system-এর পার্থক্য বুঝি।
- [ ] Bit ও Byte-এর পার্থক্য জানি।
- [ ] Binary থেকে Decimal-এ রূপান্তর করতে পারি।
- [ ] Decimal থেকে Binary-তে রূপান্তর করতে পারি।
- [ ] Python-এর `bin()` ব্যবহার করতে পারি।
- [ ] `int()` দিয়ে binary string-কে integer-এ রূপান্তর করতে পারি।
- [ ] Bitwise operators কীভাবে binary bits-এর ওপর কাজ করে, তার প্রাথমিক ধারণা আছে।
