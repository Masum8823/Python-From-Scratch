# 31. Operator-Based Problem Solving in Python

## 1. Introduction

Python-এ operators ব্যবহার করে mathematical calculation, condition checking, number analysis এবং বিভিন্ন programming problem solve করা যায়।

Operator-based problem solving বলতে বোঝায়, কোনো সমস্যার সমাধানের জন্য উপযুক্ত operator নির্বাচন করে সঠিক expression তৈরি করা।

এই অধ্যায়ে আমরা শিখব:

- দুটি সংখ্যার calculation করা
- Even ও Odd নির্ণয় করা
- Positive, Negative ও Zero শনাক্ত করা
- দুটি বা তিনটি সংখ্যার maximum ও minimum বের করা
- Divisibility পরীক্ষা করা
- Digit-এর calculation করা
- Percentage ও average হিসাব করা
- Logical condition দিয়ে eligibility পরীক্ষা করা
- Bitwise operator দিয়ে কিছু problem solve করা

---

## 2. Problem-Solving Steps

কোনো programming problem solve করার আগে নিচের ধাপগুলো অনুসরণ করো।

1. **Understand the Problem:** কী বের করতে হবে, তা বোঝো।
2. **Identify the Inputs:** কোন data প্রয়োজন, তা নির্ধারণ করো।
3. **Choose the Operators:** প্রয়োজন অনুযায়ী operator নির্বাচন করো।
4. **Write the Logic:** ধাপে ধাপে সমাধানের নিয়ম তৈরি করো।
5. **Write the Code:** Python-এ logic implement করো।
6. **Test the Output:** বিভিন্ন input দিয়ে ফলাফল যাচাই করো।

### Example

Problem: একটি সংখ্যা জোড় নাকি বিজোড়, তা নির্ণয় করতে হবে।

**Logic:**

- একটি integer input নিতে হবে।
- সংখ্যাটিকে `2` দিয়ে ভাগ করে remainder বের করতে হবে।
- Remainder `0` হলে Even, অন্যথায় Odd।

এখানে `%` এবং `==` operator ব্যবহার করা হবে।

---

## 3. Problem 1: Arithmetic Calculator

### Problem

দুটি সংখ্যা নিয়ে তাদের যোগ, বিয়োগ, গুণ ও ভাগফল বের করতে হবে।

### Code

```python
a = 20
b = 5

print("Addition:", a + b)
print("Subtraction:", a - b)
print("Multiplication:", a * b)
print("Division:", a / b)
```

### Output

```text
Addition: 25
Subtraction: 15
Multiplication: 100
Division: 4.0
```

### Explanation

| Operation | Operator | Calculation |
|---|---|---|
| Addition | `+` | `20 + 5 = 25` |
| Subtraction | `-` | `20 - 5 = 15` |
| Multiplication | `*` | `20 * 5 = 100` |
| Division | `/` | `20 / 5 = 4.0` |

**যা শিখলাম:** Arithmetic operator দিয়ে মৌলিক mathematical calculation করা যায়।

---

## 4. Problem 2: Even or Odd Number

### Problem

একটি integer Even নাকি Odd, তা নির্ণয় করতে হবে।

### Logic

- `%` দিয়ে `2`-এর remainder বের করো।
- Remainder `0` হলে Even।
- অন্যথায় Odd।

### Code

```python
number = 17

result = "Even" if number % 2 == 0 else "Odd"

print(result)
```

### Output

```text
Odd
```

### Explanation

```python
17 % 2
```

Remainder হলো `1`। তাই সংখ্যাটি Odd।

আরেকটি উদাহরণ:

```python
number = 24

print("Even" if number % 2 == 0 else "Odd")
```

Output:

```text
Even
```

**Operators Used:** `%`, `==`, conditional expression।

---

## 5. Problem 3: Positive, Negative or Zero

### Problem

একটি সংখ্যা Positive, Negative নাকি Zero, তা নির্ণয় করতে হবে।

### Code

```python
number = -8

if number > 0:
    print("Positive")
elif number < 0:
    print("Negative")
else:
    print("Zero")
```

### Output

```text
Negative
```

### Explanation

- `number > 0` হলে সংখ্যাটি Positive।
- `number < 0` হলে সংখ্যাটি Negative।
- উপরের কোনো condition সত্য না হলে সংখ্যাটি Zero।

এখানে `>`, `<` এবং `elif-else` ব্যবহার করা হয়েছে।

---

## 6. Problem 4: Find the Maximum of Two Numbers

### Problem

দুটি সংখ্যার মধ্যে বড় সংখ্যাটি বের করতে হবে।

### Code

```python
a = 25
b = 40

maximum = a if a > b else b

print("Maximum:", maximum)
```

### Output

```text
Maximum: 40
```

### Explanation

Condition:

```python
a > b
```

এখানে `25 > 40` মিথ্যা। তাই `b`-এর value নির্বাচন করা হয়েছে।

**Operators Used:** `>`, conditional expression।

### Alternative Using if-else

```python
a = 25
b = 40

if a > b:
    print(a)
else:
    print(b)
```

Output:

```text
40
```

---

## 7. Problem 5: Find the Maximum of Three Numbers

### Problem

তিনটি সংখ্যার মধ্যে সবচেয়ে বড় সংখ্যাটি বের করতে হবে।

### Code

```python
a = 15
b = 45
c = 30

maximum = a if a > b and a > c else (b if b > c else c)

print("Maximum:", maximum)
```

### Output

```text
Maximum: 45
```

### Explanation

প্রথমে পরীক্ষা করা হয়:

```python
a > b and a > c
```

`a` যদি `b` ও `c`—দুটির চেয়ে বড় হয়, তাহলে `a` maximum।

অন্যথায় পরীক্ষা করা হয়:

```python
b > c
```

- সত্য হলে `b` maximum।
- মিথ্যা হলে `c` maximum।

### Beginner-Friendly Alternative

```python
a = 15
b = 45
c = 30

maximum = a

if b > maximum:
    maximum = b

if c > maximum:
    maximum = c

print("Maximum:", maximum)
```

Output:

```text
Maximum: 45
```

দ্বিতীয় পদ্ধতিতে logic ধাপে ধাপে বোঝা সহজ।

---

## 8. Problem 6: Find the Minimum of Three Numbers

### Problem

তিনটি সংখ্যার মধ্যে সবচেয়ে ছোট সংখ্যাটি বের করতে হবে।

### Code

```python
a = 15
b = 45
c = 10

minimum = a

if b < minimum:
    minimum = b

if c < minimum:
    minimum = c

print("Minimum:", minimum)
```

### Output

```text
Minimum: 10
```

### Explanation

1. শুরুতে `a`-কে minimum ধরা হয়েছে।
2. `b` ছোট হলে minimum update করা হয়।
3. `c` ছোট হলে আবার minimum update করা হয়।

এখানে `<` operator দিয়ে প্রতিটি সংখ্যা তুলনা করা হয়েছে।

---

## 9. Problem 7: Check Divisibility

### Problem

একটি সংখ্যা অন্য একটি সংখ্যা দিয়ে নিঃশেষে বিভাজ্য কি না, তা পরীক্ষা করতে হবে।

### Code

```python
number = 24
divisor = 6

if divisor != 0 and number % divisor == 0:
    print("Divisible")
else:
    print("Not Divisible")
```

### Output

```text
Divisible
```

### Explanation

- `divisor != 0` নিশ্চিত করে divisor শূন্য নয়।
- `number % divisor == 0` পরীক্ষা করে remainder শূন্য কি না।
- উভয় condition সত্য হলে সংখ্যাটি বিভাজ্য।

এখানে `and` short-circuit করে। তাই divisor `0` হলে দ্বিতীয় condition evaluate হয় না।

**Operators Used:** `!=`, `%`, `==`, `and`।

---

## 10. Problem 8: Check Whether a Number Is a Multiple of 5 and 3

### Problem

একটি সংখ্যা একই সঙ্গে `3` ও `5` দিয়ে বিভাজ্য কি না, তা পরীক্ষা করতে হবে।

### Code

```python
number = 30

if number % 3 == 0 and number % 5 == 0:
    print("Divisible by both 3 and 5")
else:
    print("Not divisible by both")
```

### Output

```text
Divisible by both 3 and 5
```

### Explanation

`30 % 3 == 0` সত্য এবং `30 % 5 == 0`-ও সত্য।

তাই `and` expression-এর ফল `True`।

### Alternative: Either 3 or 5

যদি যেকোনো একটি দিয়ে বিভাজ্য হলেই গ্রহণযোগ্য হয়, তাহলে `and`-এর পরিবর্তে `or` ব্যবহার করতে হবে।

```python
number = 10

if number % 3 == 0 or number % 5 == 0:
    print("Divisible by 3 or 5")
else:
    print("Not divisible")
```

Output:

```text
Divisible by 3 or 5
```

**মনে রাখবে:** `and` মানে সব condition সত্য; `or` মানে অন্তত একটি condition সত্য।

---

## 11. Problem 9: Swap Two Variables

### Problem

দুটি variable-এর value অদলবদল করতে হবে।

### Method 1: Using a Temporary Variable

```python
a = 10
b = 20

temp = a
a = b
b = temp

print("a =", a)
print("b =", b)
```

### Output

```text
a = 20
b = 10
```

### Method 2: Using Multiple Assignment

Python-এ সহজভাবে:

```python
a = 10
b = 20

a, b = b, a

print("a =", a)
print("b =", b)
```

### Output

```text
a = 20
b = 10
```

এখানে Python-এর multiple assignment ও unpacking ব্যবহার করা হয়েছে।

**যা শিখলাম:** Variable swap করার জন্য temporary variable প্রয়োজন হতে পারে, তবে Python-এ multiple assignment ব্যবহার করে সহজে করা যায়।

---

## 12. Problem 10: Calculate the Last Digit

### Problem

একটি non-negative integer-এর শেষ digit বের করতে হবে।

### Code

```python
number = 5837

last_digit = number % 10

print("Last digit:", last_digit)
```

### Output

```text
Last digit: 7
```

### Explanation

কোনো non-negative integer-কে `10` দিয়ে ভাগ করলে remainder তার শেষ digit দেয়।

```python
5837 % 10
```

Result হলো `7`।

### Negative Number সম্পর্কে

Python-এ negative number-এর `%` result divisor-এর sign-এর সঙ্গে সম্পর্কিত। তাই negative integer-এর শেষ digit-এর magnitude পেতে:

```python
number = -5837

last_digit = abs(number) % 10

print(last_digit)
```

Output:

```text
7
```

এখানে `abs()` absolute value বের করে।

---

## 13. Problem 11: Remove the Last Digit

### Problem

একটি non-negative integer-এর শেষ digit বাদ দিতে হবে।

### Code

```python
number = 5837

result = number // 10

print(result)
```

### Output

```text
583
```

### Explanation

Integer-কে `10` দিয়ে floor division করলে non-negative integer-এর শেষ digit বাদ পড়ে।

```python
5837 // 10
```

Result হলো `583`।

**Operators Used:** `//`।

---

## 14. Problem 12: Sum of the Last Two Digits

### Problem

একটি non-negative integer-এর শেষ দুটি digit-এর যোগফল বের করতে হবে।

### Code

```python
number = 5837

last_digit = number % 10
second_last_digit = (number // 10) % 10

total = last_digit + second_last_digit

print("Sum:", total)
```

### Output

```text
Sum: 10
```

### Explanation

প্রথমে:

```python
5837 % 10
```

শেষ digit পাওয়া যায় `7`।

এরপর:

```python
5837 // 10
```

ফল `583`।

তারপর:

```python
583 % 10
```

দ্বিতীয় শেষ digit পাওয়া যায় `3`।

অতএব:

```text
7 + 3 = 10
```

**Operators Used:** `%`, `//`, `+`।

---

## 15. Problem 13: Calculate Average

### Problem

তিনটি সংখ্যার average বের করতে হবে।

### Formula

\[
\text{Average} = \frac{a+b+c}{3}
\]

### Code

```python
a = 70
b = 80
c = 90

average = (a + b + c) / 3

print("Average:", average)
```

### Output

```text
Average: 80.0
```

### Explanation

প্রথমে তিনটি সংখ্যা যোগ করা হয়:

```text
70 + 80 + 90 = 240
```

এরপর:

```text
240 / 3 = 80.0
```

এখানে `/` operator ব্যবহারের কারণে result `float` হয়েছে।

---

## 16. Problem 14: Calculate Percentage

### Problem

কোনো শিক্ষার্থী প্রাপ্ত নম্বর ও পূর্ণ নম্বর থেকে percentage বের করতে হবে।

### Formula

\[
\text{Percentage} = \frac{\text{Obtained Marks}}{\text{Total Marks}} \times 100
\]

### Code

```python
obtained_marks = 420
total_marks = 500

if total_marks > 0:
    percentage = (obtained_marks / total_marks) * 100
    print("Percentage:", percentage, "%")
else:
    print("Total marks must be positive")
```

### Output

```text
Percentage: 84.0 %
```

### Explanation

```text
(420 / 500) * 100 = 84.0
```

এখানে division করার আগে `total_marks > 0` পরীক্ষা করা হয়েছে, যাতে শূন্য দিয়ে ভাগ না হয়।

---

## 17. Problem 15: Check Eligibility Using Logical Operators

### Problem

কোনো আবেদনকারীর বয়স কমপক্ষে `18` এবং পরীক্ষার নম্বর কমপক্ষে `50` হলে তাকে eligible বলতে হবে।

### Code

```python
age = 20
marks = 65

if age >= 18 and marks >= 50:
    print("Eligible")
else:
    print("Not Eligible")
```

### Output

```text
Eligible
```

### Explanation

দুটি condition পরীক্ষা করা হয়:

- `age >= 18`
- `marks >= 50`

`and` ব্যবহারের কারণে দুটি condition-ই সত্য হতে হবে।

### Example with a Failed Condition

```python
age = 17
marks = 80

if age >= 18 and marks >= 50:
    print("Eligible")
else:
    print("Not Eligible")
```

Output:

```text
Not Eligible
```

নম্বর যথেষ্ট হলেও বয়সের condition পূরণ হয়নি।

---

## 18. Problem 16: Check Whether a Number Is Within a Range

### Problem

একটি সংখ্যা `10` থেকে `50`-এর মধ্যে আছে কি না, তা পরীক্ষা করতে হবে। এখানে দুই প্রান্তই অন্তর্ভুক্ত।

### Code

```python
number = 35

if 10 <= number <= 50:
    print("Within Range")
else:
    print("Outside Range")
```

### Output

```text
Within Range
```

### Explanation

`10 <= number <= 50` একটি chained comparison।

এটি পরীক্ষা করে:

```python
10 <= number and number <= 50
```

দুটি condition-ই সত্য হলে সংখ্যাটি range-এর মধ্যে থাকবে।

---

## 19. Problem 17: Calculate Simple Interest

### Problem

Principal, Rate এবং Time ব্যবহার করে simple interest বের করতে হবে।

### Formula

\[
\text{Simple Interest} = \frac{P \times R \times T}{100}
\]

যেখানে:

- `P` = Principal
- `R` = Annual interest rate in percent
- `T` = Time in years

### Code

```python
principal = 10000
rate = 5
time = 2

simple_interest = (principal * rate * time) / 100

print("Simple Interest:", simple_interest)
```

### Output

```text
Simple Interest: 1000.0
```

### Explanation

```text
(10000 * 5 * 2) / 100 = 1000.0
```

এখানে `*` এবং `/` operator ব্যবহার করা হয়েছে।

---

## 20. Problem 18: Convert Seconds into Minutes and Seconds

### Problem

মোট seconds-কে minutes ও remaining seconds-এ রূপান্তর করতে হবে।

### Code

```python
total_seconds = 150

minutes = total_seconds // 60
seconds = total_seconds % 60

print("Minutes:", minutes)
print("Seconds:", seconds)
```

### Output

```text
Minutes: 2
Seconds: 30
```

### Explanation

- `150 // 60 = 2` পূর্ণ মিনিট।
- `150 % 60 = 30` অবশিষ্ট seconds।

সুতরাং `150` seconds হলো `2` minutes `30` seconds।

**Operators Used:** `//`, `%`।

---

## 21. Problem 19: Check the Least Significant Bit

### Problem

একটি non-negative integer-এর শেষ binary bit `1` কি না, তা পরীক্ষা করতে হবে। এটি সংখ্যাটি odd কি না, তা নির্ণয় করতেও ব্যবহার করা যায়।

### Code

```python
number = 7

if number & 1:
    print("Odd")
else:
    print("Even")
```

### Output

```text
Odd
```

### Explanation

Binary representation:

```text
7 = 111
1 = 001
```

Bitwise AND:

```text
111
001
---
001
```

Result `1`, যা truthy। তাই সংখ্যাটি Odd।

### Even Example

```python
number = 8

print(number & 1)
```

Output:

```text
0
```

`8`-এর binary representation-এর শেষ bit `0`। তাই `8` Even।

**Note:** সাধারণ beginner code-এ `% 2` ব্যবহার করাই বেশি সহজবোধ্য। Bitwise পদ্ধতিটি binary operator শেখার জন্য উপকারী।

---

## 22. Problem 20: Calculate a Discounted Price

### Problem

কোনো পণ্যের price `1000` বা তার বেশি হলে `10%` discount দিতে হবে। অন্যথায় discount থাকবে না।

### Code

```python
price = 1500

discount = price * 0.10 if price >= 1000 else 0
final_price = price - discount

print("Discount:", discount)
print("Final Price:", final_price)
```

### Output

```text
Discount: 150.0
Final Price: 1350.0
```

### Explanation

Condition:

```python
price >= 1000
```

সত্য হওয়ায় discount:

```text
1500 * 0.10 = 150.0
```

Final price:

```text
1500 - 150.0 = 1350.0
```

এখানে `>=`, `*`, conditional expression এবং `-` operator ব্যবহৃত হয়েছে।

---

## 23. Important Operators Used in Problem Solving

| Operator | ব্যবহার | Example |
|---|---|---|
| `+` | যোগ | `10 + 5` |
| `-` | বিয়োগ | `10 - 5` |
| `*` | গুণ | `10 * 5` |
| `/` | সাধারণ ভাগ | `10 / 5` |
| `//` | Floor division | `11 // 5` |
| `%` | Remainder | `11 % 5` |
| `**` | Power | `2 ** 3` |
| `==` | সমান কি না | `5 == 5` |
| `!=` | অসমান কি না | `5 != 3` |
| `>` | বড় কি না | `10 > 5` |
| `<` | ছোট কি না | `3 < 5` |
| `>=` | বড় বা সমান | `5 >= 5` |
| `<=` | ছোট বা সমান | `4 <= 5` |
| `and` | সব condition সত্য | `True and True` |
| `or` | অন্তত একটি সত্য | `True or False` |
| `not` | Logical result উল্টানো | `not False` |
| `&` | Bitwise AND | `5 & 3` |
| `^` | Bitwise XOR | `5 ^ 3` |

---

## 24. Practice Exercises

প্রথমে নিজে code লেখার চেষ্টা করো। এরপর output মিলিয়ে দেখো।

### Exercise 1: Even or Odd

একটি integer `number = 42` দেওয়া আছে। `%` operator ব্যবহার করে Even বা Odd print করো।

### Exercise 2: Maximum of Two Numbers

`a = 17` এবং `b = 29` দেওয়া আছে। বড় সংখ্যাটি বের করো।

### Exercise 3: Divisibility

`number = 45` দেওয়া আছে। সংখ্যাটি `5` ও `9`—উভয় দিয়ে বিভাজ্য কি না পরীক্ষা করো।

### Exercise 4: Last Digit

`number = 7642` দেওয়া আছে। `%` ব্যবহার করে শেষ digit বের করো।

### Exercise 5: Remove the Last Digit

`number = 7642` দেওয়া আছে। `//` ব্যবহার করে শেষ digit বাদ দাও।

### Exercise 6: Average

তিনটি সংখ্যার average বের করো: `75`, `85`, `95`।

### Exercise 7: Range Check

`number = 50` দেওয়া আছে। সংখ্যাটি `10` থেকে `50`-এর মধ্যে আছে কি না পরীক্ষা করো, দুই প্রান্তসহ।

### Exercise 8: Simple Interest

`principal = 5000`, `rate = 4`, `time = 3` দেওয়া আছে। Simple interest বের করো।

### Exercise 9: Swap

`a = 100`, `b = 200` দেওয়া আছে। Multiple assignment ব্যবহার করে তাদের value swap করো।

### Exercise 10: Seconds Conversion

`total_seconds = 245` দেওয়া আছে। পূর্ণ minutes ও remaining seconds বের করো।

### Exercise Answer Key

| Exercise | Expected Result |
|---|---|
| 1 | `Even` |
| 2 | `29` |
| 3 | `Divisible by both 5 and 9` |
| 4 | `2` |
| 5 | `764` |
| 6 | `85.0` |
| 7 | `Within Range` |
| 8 | `600.0` |
| 9 | `a = 200`, `b = 100` |
| 10 | `4 minutes`, `5 seconds` |

---

## 25. Quick Revision

- Problem-solving শুরু করার আগে input, expected output এবং logic বুঝে নাও।
- `%` দিয়ে remainder, Even/Odd এবং divisibility পরীক্ষা করা যায়।
- `//` দিয়ে non-negative integer-এর শেষ digit বাদ দেওয়া যায়।
- `>` ও `<` দিয়ে সংখ্যা তুলনা করা যায়।
- `and` ও `or` একাধিক condition একত্র করতে সাহায্য করে।
- Conditional expression দিয়ে সহজ value selection করা যায়।
- `**` power calculation করে।
- Bitwise operator binary-level problem-এ কাজে লাগে।
- Complex expression-এর grouping স্পষ্ট করতে parentheses ব্যবহার করো।
- বিভিন্ন input দিয়ে code test করো, বিশেষ করে `0`, negative number এবং boundary value।

## 26. Self-Assessment Checklist

- [ ] Arithmetic operator ব্যবহার করে calculation করতে পারি।
- [ ] Even/Odd ও Positive/Negative নির্ণয় করতে পারি।
- [ ] Maximum ও minimum বের করতে পারি।
- [ ] Divisibility পরীক্ষা করতে পারি।
- [ ] `%` এবং `//` দিয়ে digit-related problem solve করতে পারি।
- [ ] Average, percentage ও simple interest হিসাব করতে পারি।
- [ ] Logical operator দিয়ে eligibility ও range পরীক্ষা করতে পারি।
- [ ] Multiple assignment দিয়ে variable swap করতে পারি।
- [ ] Bitwise AND-এর সাহায্যে শেষ binary bit পরীক্ষা করতে পারি।
- [ ] নিজের code বিভিন্ন input দিয়ে যাচাই করতে পারি।

পরবর্তী Topic: **32. Operator Output Prediction Exercises**