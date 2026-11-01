# 15. Augmented Assignment Operators in Python

## 1. Introduction to Augmented Assignment Operators

Python-এ **Augmented Assignment Operators** ব্যবহার করে কোনো Variable-এর বর্তমান Value-এর সঙ্গে একটি Operation সম্পন্ন করে Result আবার সেই Variable-এ Assign করা যায়।

Example:

```python
x = 10

x = x + 5

print(x)
```

Output:

```text
15
```

একই কাজ আরও সংক্ষেপে লেখা যায়:

```python
x = 10

x += 5

print(x)
```

Output:

```text
15
```

এখানে `+=` হলো Augmented Assignment Operator।

**মনে রাখবে:** Augmented Assignment ব্যবহার করলে অনেক ক্ষেত্রে Code ছোট ও সহজে পড়ার উপযোগী হয়। তবে Mutable Object-এর ক্ষেত্রে এর আচরণ সাধারণ Assignment-এর থেকে আলাদা হতে পারে।

---

## 2. Basic Syntax

Augmented Assignment-এর সাধারণ Syntax:

```python
variable operator= value
```

Example:

```python
x = 10
x += 5
```

এখানে:

- `x` হলো Variable।
- `+=` হলো Augmented Assignment Operator।
- `5` হলো যে Value দিয়ে Operation করা হচ্ছে।

সাধারণ Integer-এর ক্ষেত্রে:

```python
x += 5
```

এটি নিচের Expression-এর সমতুল্য:

```python
x = x + 5
```

একইভাবে:

```python
x -= 5
```

সাধারণ Integer-এর ক্ষেত্রে:

```python
x = x - 5
```

**গুরুত্বপূর্ণ:** সব Data Type-এর ক্ষেত্রে `x += y`-কে `x = x + y`-এর সম্পূর্ণ সমতুল্য ধরে নেওয়া যাবে না।

---

## 3. Overview of Augmented Assignment Operators

| Operator | কাজ | Example |
|---|---|---|
| `+=` | যোগ করে Assign | `x += 5` |
| `-=` | বিয়োগ করে Assign | `x -= 5` |
| `*=` | গুণ করে Assign | `x *= 5` |
| `/=` | ভাগ করে Assign | `x /= 5` |
| `//=` | Floor Division করে Assign | `x //= 5` |
| `%=` | Modulo করে Assign | `x %= 5` |
| `**=` | Power করে Assign | `x **= 5` |
| `&=` | Bitwise AND করে Assign | `x &= 5` |
| `\|=` | Bitwise OR করে Assign | `x \|= 5` |
| `^=` | Bitwise XOR করে Assign | `x ^= 5` |
| `>>=` | Right Shift করে Assign | `x >>= 1` |
| `<<=` | Left Shift করে Assign | `x <<= 1` |
| `@=` | Matrix Multiplication করে Assign | `x @= matrix` |

এই Chapter-এ প্রথমে Arithmetic Augmented Assignment Operators শিখব। Bitwise Operators পরে আলাদাভাবে আলোচনা করা হবে।

---

## 4. Addition Assignment (`+=`)

`+=` Operator দিয়ে Variable-এর বর্তমান Value-এর সঙ্গে নতুন Value যোগ করা হয়।

### Example 1: Integer

```python
x = 10

x += 5

print(x)
```

Output:

```text
15
```

ব্যাখ্যা:

- শুরুতে `x = 10`।
- `x += 5` করার পর `x`-এর Value `15`।

### Example 2: Multiple Updates

```python
score = 50

score += 10
score += 15

print(score)
```

Output:

```text
75
```

ধাপে ধাপে:

| Operation | Value |
|---|---:|
| শুরুতে | 50 |
| `score += 10` | 60 |
| `score += 15` | 75 |

### Example 3: String

```python
message = "Hello"

message += " Python"

print(message)
```

Output:

```text
Hello Python
```

String-এর ক্ষেত্রে `+=` ব্যবহার করে নতুন String যুক্ত করা যায়।

### Example 4: List

```python
numbers = [1, 2]

numbers += [3, 4]

print(numbers)
```

Output:

```text
[1, 2, 3, 4]
```

List-এর ক্ষেত্রে `+=` সাধারণত বিদ্যমান List-এ নতুন Elements যুক্ত করে।

---

## 5. Subtraction Assignment (`-=`)

`-=` Operator দিয়ে Variable-এর বর্তমান Value থেকে অন্য একটি Value বিয়োগ করা হয়।

### Example 1

```python
x = 20

x -= 5

print(x)
```

Output:

```text
15
```

### Example 2: Shopping Balance

```python
balance = 1000

balance -= 250
balance -= 100

print(balance)
```

Output:

```text
650
```

ব্যাখ্যা:

- শুরুতে Balance `1000`।
- প্রথমে `250` বিয়োগ করলে `750`।
- এরপর `100` বিয়োগ করলে `650`।

### Example 3: Countdown

```python
count = 5

count -= 1
count -= 1

print(count)
```

Output:

```text
3
```

Countdown বা কোনো Counter কমানোর কাজে `-=` ব্যবহার করা যায়।

---

## 6. Multiplication Assignment (`*=`)

`*=` Operator দিয়ে Variable-এর বর্তমান Value-কে অন্য একটি Value দিয়ে গুণ করা হয়।

### Example 1

```python
x = 5

x *= 3

print(x)
```

Output:

```text
15
```

### Example 2: Price Calculation

```python
price = 100

price *= 2

print(price)
```

Output:

```text
200
```

### Example 3: Repeated Multiplication

```python
number = 2

number *= 3
number *= 4

print(number)
```

Output:

```text
24
```

ধাপে ধাপে:

- প্রথমে `2 × 3 = 6`।
- এরপর `6 × 4 = 24`।

---

## 7. Division Assignment (`/=`)

`/=` Operator দিয়ে Variable-এর বর্তমান Value-কে অন্য একটি Value দিয়ে ভাগ করা হয়।

### Example 1

```python
x = 20

x /= 4

print(x)
```

Output:

```text
5.0
```

Python-এ `/` ব্যবহার করলে সাধারণত Float Result পাওয়া যায়।

### Example 2

```python
total = 100

total /= 3

print(total)
```

Output:

```text
33.333333333333336
```

এখানে Floating-Point Precision-এর কারণে দশমিকের মান পুরোপুরি নিখুঁতভাবে প্রকাশ নাও পেতে পারে।

### Example 3: Dividing a Value Repeatedly

```python
number = 100

number /= 2
number /= 5

print(number)
```

Output:

```text
10.0
```

**সতর্কতা:** `x /= 0` করলে `ZeroDivisionError` হবে।

---

## 8. Floor Division Assignment (`//=`)

`//=` Operator দিয়ে Floor Division করে Result Variable-এ Assign করা হয়।

### Example 1

```python
x = 17

x //= 5

print(x)
```

Output:

```text
3
```

ব্যাখ্যা:

`17 // 5`-এর Result `3`।

### Example 2: Negative Number

```python
x = -17

x //= 5

print(x)
```

Output:

```text
-4
```

Python-এর Floor Division Result-কে নিচের পূর্ণসংখ্যার দিকে নিয়ে যায়। তাই `-17 // 5`-এর Result `-4`।

### Example 3: Integer and Float

```python
x = 17.0

x //= 5

print(x)
```

Output:

```text
3.0
```

এখানে একটি Float Operand থাকায় Result Float হয়েছে।

---

## 9. Modulo Assignment (`%=`)

`%=` Operator দিয়ে Division-এর Remainder বা ভাগশেষ Variable-এ Assign করা হয়।

### Example 1

```python
x = 17

x %= 5

print(x)
```

Output:

```text
2
```

কারণ `17 % 5 = 2`।

### Example 2: Checking Even or Odd

```python
number = 14

number %= 2

print(number)
```

Output:

```text
0
```

কারণ 14-কে 2 দিয়ে ভাগ করলে ভাগশেষ 0।

### Example 3: Odd Number

```python
number = 15

number %= 2

print(number)
```

Output:

```text
1
```

এখানে ভাগশেষ 1।

**মনে রাখবে:** `x %= y` করার পর `x`-এ মূল Number থাকে না; Remainder Assign হয়।

---

## 10. Exponentiation Assignment (`**=`)

`**=` Operator দিয়ে Power বা ঘাত নির্ণয় করে Result Variable-এ Assign করা হয়।

### Example 1

```python
x = 2

x **= 3

print(x)
```

Output:

```text
8
```

কারণ:

\[
2^3 = 2 \times 2 \times 2 = 8
\]

### Example 2

```python
number = 3

number **= 2

print(number)
```

Output:

```text
9
```

### Example 3: Repeated Exponentiation

```python
x = 2

x **= 3
x **= 2

print(x)
```

Output:

```text
64
```

ধাপে ধাপে:

- প্রথমে \(2^3 = 8\)।
- এরপর \(8^2 = 64\)।

---

## 11. Bitwise Augmented Assignment Operators

Bitwise Operator Binary Bit-এর ওপর কাজ করে। তাদের Augmented Assignment Version-ও রয়েছে।

প্রধান Operators:

- `&=`
- `|=`
- `^=`
- `<<=`
- `>>=`

### Example 1: Bitwise AND Assignment

```python
x = 6

x &= 3

print(x)
```

Output:

```text
2
```

Binary:

```text
6 = 110
3 = 011
---------
    010 = 2
```

### Example 2: Bitwise OR Assignment

```python
x = 6

x |= 3

print(x)
```

Output:

```text
7
```

Binary:

```text
6 = 110
3 = 011
---------
    111 = 7
```

### Example 3: Bitwise XOR Assignment

```python
x = 6

x ^= 3

print(x)
```

Output:

```text
5
```

Binary:

```text
6 = 110
3 = 011
---------
    101 = 5
```

### Example 4: Left Shift Assignment

```python
x = 5

x <<= 1

print(x)
```

Output:

```text
10
```

Positive Integer-এর ক্ষেত্রে এখানে Binary Bits এক ধাপ বামে Shift করা হয়েছে।

### Example 5: Right Shift Assignment

```python
x = 20

x >>= 2

print(x)
```

Output:

```text
5
```

এখানে Binary Bits দুই ধাপ ডানে Shift করা হয়েছে।

Bitwise Operators-এর বিস্তারিত নিয়ম সংশ্লিষ্ট Bitwise Topic-এ আলোচনা করা হবে।

---

## 12. Augmented Assignment with Different Data Types

Augmented Assignment-এর আচরণ Data Type অনুযায়ী আলাদা হতে পারে।

### Example 1: Integer

```python
x = 10

x += 5

print(x)
```

Output:

```text
15
```

### Example 2: Float

```python
x = 10.5

x += 2

print(x)
```

Output:

```text
12.5
```

### Example 3: String

```python
text = "Hello"

text += " World"

print(text)
```

Output:

```text
Hello World
```

### Example 4: List

```python
items = [1, 2]

items += [3]

print(items)
```

Output:

```text
[1, 2, 3]
```

### Example 5: Unsupported Operation

```python
x = "10"

# x -= 2  # TypeError
```

String থেকে Integer সরাসরি বিয়োগ করা যায় না।

প্রয়োজনে Numeric Conversion করতে হবে:

```python
x = "10"

x = int(x)
x -= 2

print(x)
```

Output:

```text
8
```

---

## 13. Augmented Assignment vs Normal Assignment

দুটি পদ্ধতির তুলনা:

| Normal Assignment | Augmented Assignment |
|---|---|
| `x = x + 5` | `x += 5` |
| `x = x - 5` | `x -= 5` |
| `x = x * 5` | `x *= 5` |
| `x = x / 5` | `x /= 5` |
| `x = x // 5` | `x //= 5` |
| `x = x % 5` | `x %= 5` |
| `x = x ** 5` | `x **= 5` |

সাধারণ Integer-এর ক্ষেত্রে প্রতিটি জোড়ার ফল একই।

### Important Difference with Mutable Objects

List-এর ক্ষেত্রে একটি পার্থক্য দেখা যায়।

```python
a = [1, 2]
b = a

a += [3]

print(a)
print(b)
```

Output:

```text
[1, 2, 3]
[1, 2, 3]
```

এখানে List-এর `+=` সাধারণত বিদ্যমান List-কে Update করে।

অন্যদিকে:

```python
a = [1, 2]
b = a

a = a + [3]

print(a)
print(b)
```

Output:

```text
[1, 2, 3]
[1, 2]
```

এখানে `a + [3]` একটি নতুন List তৈরি করে এবং `a`-কে সেই নতুন List-এর সঙ্গে Reassign করে। `b` পুরোনো List-কে Reference করায় তার Value অপরিবর্তিত থাকে।

**মনে রাখবে:** Mutable Object-এর ক্ষেত্রে Augmented Assignment এবং Normal Assignment-এর মধ্যে গুরুত্বপূর্ণ পার্থক্য থাকতে পারে।

---

## 14. Common Mistakes

### Mistake 1: Using `+=` Without Defining the Variable

```python
# x += 5
```

যদি `x` আগে Define করা না থাকে, তাহলে `NameError` হবে।

সঠিক:

```python
x = 10
x += 5

print(x)
```

Output:

```text
15
```

### Mistake 2: Division by Zero

```python
x = 10

# x /= 0  # ZeroDivisionError
```

Zero দিয়ে ভাগ করা যায় না।

### Mistake 3: Confusing `%=` with `/=`

```python
x = 17
x %= 5

print(x)
```

Output:

```text
2
```

`%=` ভাগশেষ Assign করে; `/=` ভাগফল Assign করে।

### Mistake 4: Forgetting the Original Value Changes

```python
x = 10

x += 5
x *= 2

print(x)
```

Output:

```text
30
```

ধাপে ধাপে:

1. শুরুতে `x = 10`।
2. `x += 5` → `x = 15`।
3. `x *= 2` → `x = 30`।

### Mistake 5: Assuming Every Operator Works with Every Data Type

```python
text = "Python"

# text -= 1  # TypeError
```

প্রতিটি Operator সব Data Type-এর জন্য বৈধ নয়।

---

## 15. Practice Exercises

### Basic Level

1. `x = 10` হলে `x += 5`-এর পর `x` কত?
2. `x = 20` হলে `x -= 8`-এর পর `x` কত?
3. `x = 4` হলে `x *= 3`-এর পর `x` কত?
4. `x = 15` হলে `x //= 4`-এর পর `x` কত?
5. `x = 17` হলে `x %= 5`-এর পর `x` কত?

### Intermediate Level

6. `x = 2` দিয়ে `**=` ব্যবহার করে 8 তৈরি করো।
7. `balance = 1000` থেকে 250 বিয়োগ করো।
8. String `"Hello"`-এর সঙ্গে `" Python"` যোগ করতে `+=` ব্যবহার করো।
9. List `[1, 2]`-এর সঙ্গে `[3, 4]` যোগ করো।
10. `&=` এবং `|=`-এর কাজের পার্থক্য ব্যাখ্যা করো।

### Output Prediction

```python
x = 10
x += 5
x *= 2
x -= 4

print(x)

y = 17
y //= 5
print(y)

z = 17
z %= 5
print(z)

message = "Hi"
message += " Python"
print(message)
```

### Answers

```text
26
3
2
Hi Python
```

ব্যাখ্যা:

- `x`: \(10 + 5 = 15\), \(15 \times 2 = 30\), \(30 - 4 = 26\)।
- `y`: \(17 // 5 = 3\)।
- `z`: \(17 \% 5 = 2\)।
- `message`: `"Hi"`-এর সঙ্গে `" Python"` যুক্ত হয়েছে।

---

## 16. Chapter Summary

- Augmented Assignment Operator দিয়ে Variable-এর বর্তমান Value Update করা যায়।
- `+=` যোগ করে Assign করে।
- `-=` বিয়োগ করে Assign করে।
- `*=` গুণ করে Assign করে।
- `/=` ভাগ করে Assign করে।
- `//=` Floor Division করে Assign করে।
- `%=` ভাগশেষ Assign করে।
- `**=` Power নির্ণয় করে Assign করে।
- Bitwise Augmented Assignment Operators Binary Bits-এর ওপর কাজ করে।
- Augmented Assignment-এর আচরণ Data Type অনুযায়ী ভিন্ন হতে পারে।
- Mutable Object-এর ক্ষেত্রে `+=` এবং Normal Assignment-এর মধ্যে পার্থক্য থাকতে পারে।

## 17. Self-Assessment Checklist

- [ ] Augmented Assignment-এর Syntax বুঝি।
- [ ] `+=`, `-=`, `*=` এবং `/=` ব্যবহার করতে পারি।
- [ ] `//=`, `%=` এবং `**=` ব্যবহার করতে পারি।
- [ ] Bitwise Augmented Assignment-এর Basic ধারণা বুঝি।
- [ ] String ও List-এর সঙ্গে `+=` ব্যবহার করতে পারি।
- [ ] Mutable Object-এর ক্ষেত্রে `+=`-এর আচরণ বুঝি।
- [ ] Output Prediction Exercise সমাধান করতে পারি।

**Next Topic:** `16_Chained_Assignment_and_Multiple_Assignment.md`