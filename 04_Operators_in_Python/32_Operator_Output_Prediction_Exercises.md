# 32. Operator Output Prediction Exercises

## 1. Introduction

Python-এ Output Prediction বলতে বোঝায়, কোনো code execute করার আগে তার output কী হবে, তা নির্ণয় করা।

Operator-based output prediction practice করলে নিচের বিষয়গুলো পরিষ্কার হবে:

- Arithmetic operators
- Floor division ও modulo
- Comparison ও logical operators
- Assignment operators
- Identity ও membership operators
- Bitwise operators
- Operator precedence ও associativity
- Conditional expressions
- Short-circuit evaluation
- Common operator mistakes

## 2. Rules to Follow Before Predicting Output

Output নির্ণয় করার সময় নিচের নিয়মগুলো মনে রাখবে।

1. Parentheses `()` আগে evaluate করো।
2. Operator precedence অনুযায়ী expression evaluate করো।
3. একই precedence-এর operator হলে associativity বিবেচনা করো।
4. `and` ও `or`-এর short-circuit behavior মনে রাখো।
5. `/` এবং `//`-এর পার্থক্য বোঝো।
6. `==` ও `is`-কে এক মনে করো না।
7. `print()`-এর output-এর spacing ও data type খেয়াল করো।
8. একটি expression-এ একাধিক operator থাকলে ধাপে ধাপে হিসাব করো।

---

## 3. Level 1: Basic Arithmetic Operators

### Question 1

```python
a = 10
b = 3

print(a + b)
print(a - b)
print(a * b)
```

**Predict the output before checking the answer.**

Answer:

```text
13
7
30
```

Explanation:

- `10 + 3 = 13`
- `10 - 3 = 7`
- `10 * 3 = 30`

### Question 2

```python
print(20 / 4)
print(20 // 6)
print(20 % 6)
```

Answer:

```text
5.0
3
2
```

Explanation:

- `/` সাধারণ division করে এবং এখানে result `5.0`।
- `//` floor division করে: `20 // 6 = 3`।
- `%` remainder দেয়: `20 % 6 = 2`।

### Question 3

```python
print(2 ** 4)
print(3 ** 2)
print(16 // 5)
```

Answer:

```text
16
9
3
```

Explanation:

- `2 ** 4 = 16`
- `3 ** 2 = 9`
- `16 // 5 = 3`

### Question 4

```python
print(10 + 5 * 2)
print((10 + 5) * 2)
```

Answer:

```text
20
30
```

Explanation:

প্রথম expression-এ multiplication আগে হয়:

`10 + (5 * 2) = 20`

দ্বিতীয় expression-এ parentheses আগে evaluate হয়:

`(10 + 5) * 2 = 30`

---

## 4. Level 2: Floor Division and Modulo

### Question 5

```python
print(17 // 5)
print(17 % 5)
```

Answer:

```text
3
2
```

### Question 6

```python
print(-7 // 2)
print(-7 % 2)
```

Answer:

```text
-4
1
```

Explanation:

Python-এর `//` floor division করে, অর্থাৎ ফলকে নিচের integer-এর দিকে নামায়।

`-7 / 2 = -3.5`

তাই:

- `-7 // 2 = -4`
- `-7 % 2 = 1`

এই identity-টিও মনে রাখবে:

`a == (a // b) * b + (a % b)`

যেখানে `b` শূন্য নয়।

### Question 7

```python
print(7 // -3)
print(7 % -3)
```

Answer:

```text
-3
-2
```

Explanation:

Python-এ modulo result divisor-এর sign-এর সঙ্গে সামঞ্জস্যপূর্ণ হয়।

`7 = (-3 * -3) + (-2)`

তাই remainder `-2`।

### Question 8

```python
number = 5837

print(number % 10)
print(number // 10)
```

Answer:

```text
7
583
```

Explanation:

- `% 10` দিয়ে non-negative integer-এর শেষ digit পাওয়া যায়।
- `// 10` দিয়ে শেষ digit বাদ দেওয়া যায়।

---

## 5. Level 3: Comparison Operators

### Question 9

```python
a = 10
b = 20

print(a > b)
print(a < b)
print(a == b)
```

Answer:

```text
False
True
False
```

### Question 10

```python
print(5 >= 5)
print(8 != 8)
print(3 <= 7)
```

Answer:

```text
True
False
True
```

### Question 11: Chained Comparison

```python
x = 15

print(10 < x < 20)
print(10 < x > 20)
```

Answer:

```text
True
False
```

Explanation:

প্রথম expression-এর অর্থ:

`10 < x and x < 20`

দ্বিতীয় expression-এর অর্থ:

`10 < x and x > 20`

দ্বিতীয় ক্ষেত্রে `15 > 20` মিথ্যা।

### Question 12: Comparing Different Types

```python
print(5 == 5.0)
print(True == 1)
print(False == 0)
```

Answer:

```text
True
True
True
```

Explanation:

Python-এ numeric equality comparison-এ `int`, `float` এবং `bool`-এর কিছু value সমান হিসেবে গণ্য হয়।

তবে `5 == "5"` হলে ফল `False`, কারণ string `"5"` ও number `5` সমান নয়।

---

## 6. Level 4: Logical Operators

### Question 13

```python
print(True and False)
print(True or False)
print(not True)
```

Answer:

```text
False
True
False
```

### Question 14

```python
x = 8

print(x > 5 and x < 10)
print(x < 5 or x == 8)
```

Answer:

```text
True
True
```

Explanation:

- `8 > 5` এবং `8 < 10` উভয়ই সত্য।
- `8 < 5` মিথ্যা, কিন্তু `8 == 8` সত্য। তাই `or` expression সত্য।

### Question 15: Truthiness

```python
print(bool(0))
print(bool(10))
print(bool(""))
print(bool("False"))
```

Answer:

```text
False
True
False
True
```

Explanation:

- `0` falsy।
- Non-zero number truthy।
- Empty string `""` falsy।
- `"False"` একটি non-empty string, তাই truthy।

মনে রাখবে, string-এর ভেতরে `"False"` লেখা থাকলেই সেটি Boolean `False` হয়ে যায় না।

### Question 16: Logical Operators Return Values

```python
print(5 and 8)
print(0 and 8)
print(0 or 8)
print(5 or 8)
```

Answer:

```text
8
0
8
5
```

Explanation:

Python-এর `and` ও `or` সবসময় `True` বা `False` return করে না। তারা operand-এর value return করতে পারে।

- `and` প্রথম falsy operand পেলে সেটি return করে; সব truthy হলে শেষ operand return করে।
- `or` প্রথম truthy operand পেলে সেটি return করে; সব falsy হলে শেষ operand return করে।

---

## 7. Level 5: Assignment Operators

### Question 17

```python
x = 10
x += 5

print(x)
```

Answer:

```text
15
```

Explanation:

`x += 5` সাধারণভাবে `x = x + 5`-এর সমতুল্য।

### Question 18

```python
x = 20

x -= 4
x *= 2
x //= 3

print(x)
```

Answer:

```text
10
```

Explanation:

ধাপে ধাপে:

1. `20 - 4 = 16`
2. `16 * 2 = 32`
3. `32 // 3 = 10`

### Question 19: Chained Assignment

```python
a = b = c = 100

a = 20

print(a)
print(b)
print(c)
```

Answer:

```text
20
100
100
```

Explanation:

প্রথমে তিনটি variable-এ `100` assign হয়েছে। পরে শুধু `a`-কে `20` দেওয়া হয়েছে। তাই `b` ও `c`-এর value বদলায়নি।

### Question 20: Multiple Assignment

```python
a = 5
b = 10

a, b = b, a

print(a, b)
```

Answer:

```text
10 5
```

Explanation:

Python-এ multiple assignment ব্যবহার করে দুই variable-এর value সহজে swap করা যায়।

---

## 8. Level 6: Identity and Membership Operators

### Question 21: Equality vs Identity

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)
print(a is b)
```

Answer:

```text
True
False
```

Explanation:

- `==` value সমান কি না পরীক্ষা করে।
- `is` দুটি reference একই object-কে নির্দেশ করছে কি না পরীক্ষা করে।

এখানে list দুটি দেখতে একই রকম, কিন্তু আলাদা object।

### Question 22: Identity with the Same Object

```python
a = [1, 2, 3]
b = a

print(a == b)
print(a is b)
```

Answer:

```text
True
True
```

Explanation:

`b = a` করার ফলে `a` ও `b` একই list object-কে reference করে।

### Question 23: Membership

```python
numbers = [10, 20, 30]

print(20 in numbers)
print(40 in numbers)
print(10 not in numbers)
```

Answer:

```text
True
False
False
```

Explanation:

`in` collection-এর মধ্যে value আছে কি না পরীক্ষা করে। `not in` তার বিপরীত।

### Question 24: String Membership

```python
text = "Python Programming"

print("Python" in text)
print("Java" in text)
print("Pro" in text)
```

Answer:

```text
True
False
True
```

Explanation:

String-এর মধ্যে substring খোঁজার সময় `in` ব্যবহার করা যায়।

---

## 9. Level 7: Bitwise Operators

### Question 25: Bitwise AND

```python
print(5 & 3)
```

Answer:

```text
1
```

Explanation:

```text
5 = 101
3 = 011
    ---
    001
```

শুধু দুই bit-ই `1` হলে AND result `1` হয়।

### Question 26: Bitwise OR

```python
print(5 | 3)
```

Answer:

```text
7
```

Explanation:

```text
5 = 101
3 = 011
    ---
    111
```

যেকোনো একটি bit `1` হলে OR result `1` হয়।

### Question 27: Bitwise XOR

```python
print(5 ^ 3)
```

Answer:

```text
6
```

Explanation:

```text
5 = 101
3 = 011
    ---
    110
```

দুই bit আলাদা হলে XOR result `1` হয়।

### Question 28: Left and Right Shift

```python
print(5 << 1)
print(20 >> 2)
```

Answer:

```text
10
5
```

Explanation:

- `5 << 1` হলো `5 * 2 = 10`।
- `20 >> 2` হলো `20 // 4 = 5`।

এখানে positive integer-এর ক্ষেত্রে এই উদাহরণগুলো সহজে বোঝা যায়। সব signed বা negative-number case-এ bit shifting-কে সরলভাবে multiplication বা division হিসেবে ধরে নেওয়া উচিত নয়।

### Question 29: Bitwise vs Logical Operator

```python
print(5 & 3)
print(5 and 3)
```

Answer:

```text
1
3
```

Explanation:

- `&` bitwise AND করে।
- `and` logical short-circuit evaluation করে এবং এখানে শেষ truthy operand `3` return করে।

দুটি operator দেখতে কাছাকাছি হলেও কাজ আলাদা।

---

## 10. Level 8: Operator Precedence

### Question 30

```python
print(5 + 3 * 2)
```

Answer:

```text
11
```

Explanation:

Multiplication আগে:

`5 + (3 * 2) = 11`

### Question 31

```python
print(2 ** 3 ** 2)
```

Answer:

```text
512
```

Explanation:

Exponentiation right-to-left group করে:

`2 ** (3 ** 2)`

`2 ** 9 = 512`

### Question 32

```python
print(-2 ** 2)
print((-2) ** 2)
```

Answer:

```text
-4
4
```

Explanation:

প্রথম expression:

`-(2 ** 2) = -4`

দ্বিতীয় expression:

`(-2) ** 2 = 4`

### Question 33

```python
print(10 - 4 - 2)
```

Answer:

```text
4
```

Explanation:

Subtraction left-to-right group করে:

`(10 - 4) - 2 = 4`

### Question 34

```python
print(5 ^ 3 & 1)
```

Answer:

```text
4
```

Explanation:

Bitwise AND-এর precedence XOR-এর চেয়ে বেশি।

তাই:

1. `3 & 1 = 1`
2. `5 ^ 1 = 4`

### Question 35

```python
print(not True or True)
```

Answer:

```text
True
```

Explanation:

`not`-এর precedence `or`-এর চেয়ে বেশি।

প্রথমে `not True` হয় `False`। এরপর:

`False or True = True`

### Question 36

```python
print(2 + 3 > 4 and 8 < 10)
```

Answer:

```text
True
```

Explanation:

1. `2 + 3 = 5`
2. `5 > 4` হলো `True`
3. `8 < 10` হলো `True`
4. `True and True` হলো `True`

---

## 11. Level 9: Conditional Expressions

### Question 37

```python
x = 12

result = "Even" if x % 2 == 0 else "Odd"

print(result)
```

Answer:

```text
Even
```

Explanation:

`12 % 2 == 0` সত্য, তাই `"Even"` নির্বাচন করা হয়েছে।

### Question 38

```python
a = 15
b = 9

print(a if a > b else b)
```

Answer:

```text
15
```

Explanation:

Condition `a > b` সত্য হওয়ায় `a`-এর value return হয়।

### Question 39: Nested Conditional Expression

```python
x = 0

result = "Positive" if x > 0 else ("Negative" if x < 0 else "Zero")

print(result)
```

Answer:

```text
Zero
```

Explanation:

- `x > 0` মিথ্যা।
- এরপর `x < 0` মিথ্যা।
- তাই শেষের `"Zero"` নির্বাচন করা হয়েছে।

Beginner code-এ জটিল nested conditional expression-এর বদলে `if-elif-else` ব্যবহার করলে অনেক সময় পড়া সহজ হয়।

---

## 12. Level 10: Short-Circuit Evaluation

### Question 40

```python
print(False and (10 / 0))
```

Answer:

```text
False
```

Explanation:

`and`-এর বাম পাশ `False`। তাই ডান পাশ evaluate হয় না এবং division error হয় না।

### Question 41

```python
print(True or (10 / 0))
```

Answer:

```text
True
```

Explanation:

`or`-এর বাম পাশ `True`। তাই ডান পাশ evaluate হয় না।

### Question 42

```python
x = 0

print(x != 0 and 10 / x > 2)
```

Answer:

```text
False
```

Explanation:

প্রথম condition `x != 0` মিথ্যা। তাই `10 / x` evaluate হয় না।

এটি short-circuit evaluation-এর একটি গুরুত্বপূর্ণ ব্যবহার।

### Question 43: Side Effect

```python
def show_message():
    print("Function called")
    return True

print(False and show_message())
```

Answer:

```text
False
```

Explanation:

`show_message()` call-ই হয় না, কারণ `and`-এর বাম পাশ `False`। তাই `"Function called"` print হয় না।

---

## 13. Level 11: Walrus Operator

### Question 44

```python
if (n := 5) > 3:
    print(n)
```

Answer:

```text
5
```

Explanation:

`:=` assignment expression। এটি `n`-এ `5` assign করে এবং expression-এর value হিসেবে `5` দেয়।

যেহেতু `5 > 3` সত্য, তাই `n` print হয়।

### Question 45

```python
print((x := 10) + 5)
print(x)
```

Answer:

```text
15
10
```

Explanation:

প্রথম লাইনে `x`-এ `10` assign হয়। এরপর `10 + 5` print হয়। পরের লাইনে `x`-এর value `10`।

---

## 14. Level 12: Mixed Operator Challenges

### Question 46

```python
a = 8
b = 3

print(a + b * 2 - 4)
```

Answer:

```text
10
```

Explanation:

1. `3 * 2 = 6`
2. `8 + 6 - 4 = 10`

### Question 47

```python
x = 7

print(x % 2 == 1 and x > 5)
```

Answer:

```text
True
```

Explanation:

- `7 % 2 == 1` সত্য।
- `7 > 5` সত্য।
- দুটি condition-ই সত্য হওয়ায় `and` result `True`।

### Question 48

```python
a = 4
b = 2

print(a ** b + b ** a)
```

Answer:

```text
24
```

Explanation:

- `4 ** 2 = 16`
- `2 ** 4 = 16`

সুতরাং `16 + 16 = 32`।

**Correct output:**

```text
32
```

### Question 49

```python
print(20 // 3 * 3 + 20 % 3)
```

Answer:

```text
20
```

Explanation:

1. `20 // 3 = 6`
2. `6 * 3 = 18`
3. `20 % 3 = 2`
4. `18 + 2 = 20`

### Question 50

```python
x = 10

x += 5 * 2

print(x)
```

Answer:

```text
20
```

Explanation:

প্রথমে `5 * 2 = 10`। এরপর `x += 10`, তাই `x = 20`।

---

## 15. Common Mistakes in Output Prediction

### Mistake 1: `/` ও `//` এক মনে করা

```python
print(7 / 2)
print(7 // 2)
```

Output:

```text
3.5
3
```

### Mistake 2: `=` ও `==` এক মনে করা

- `=` assignment করে।
- `==` equality পরীক্ষা করে।

```python
x = 5
print(x == 5)
```

Output:

```text
True
```

### Mistake 3: `is` ও `==` এক মনে করা

- `==` value comparison করে।
- `is` object identity পরীক্ষা করে।

### Mistake 4: `and` সবসময় Boolean দেয় মনে করা

```python
print(4 and 9)
```

Output:

```text
9
```

### Mistake 5: Negative floor division ভুল করা

```python
print(-7 // 2)
```

Output:

```text
-4
```

`//` শূন্যের দিকে truncate করে না; floor-এর দিকে যায়।

### Mistake 6: Precedence উপেক্ষা করা

```python
print(2 + 3 * 4)
```

Output:

```text
14
```

`2 + 3` আগে হয় না। Multiplication আগে হয়।

---

## 16. Independent Practice: Predict Without Running

নিচের প্রশ্নগুলোর উত্তর নিজে খাতায় লেখো। এরপর answer key দিয়ে মিলিয়ে দেখো।

### Question A

```python
print(12 + 8 // 3)
```

### Question B

```python
print(2 ** 3 ** 2)
```

### Question C

```python
print(-9 // 4)
print(-9 % 4)
```

### Question D

```python
x = 6
print(x > 5 and x < 10)
```

### Question E

```python
print(0 or 15)
print(0 and 15)
```

### Question F

```python
print(9 & 5)
print(9 | 5)
```

### Question G

```python
a = 10
b = 20
a, b = b, a
print(a - b)
```

### Question H

```python
print(3 + 4 * 2 ** 2)
```

### Question I

```python
x = 11
print("Yes" if x % 2 != 0 else "No")
```

### Question J

```python
print(10 < 20 > 15)
```

### Answer Key

| Question | Expected Output |
|---|---|
| A | `14` |
| B | `512` |
| C | `-3` তারপর `3` |
| D | `True` |
| E | `15` তারপর `0` |
| F | `1` তারপর `13` |
| G | `10` |
| H | `19` |
| I | `Yes` |
| J | `True` |

---

## 17. How to Improve Output Prediction Skills

1. প্রতিটি expression নিজে হাতে step-by-step evaluate করো।
2. Parentheses যোগ করে বোঝার চেষ্টা করো কোন operator আগে কাজ করছে।
3. Negative number, zero এবং boundary value দিয়ে practice করো।
4. `and` ও `or`-এর short-circuit behavior আলাদাভাবে পরীক্ষা করো।
5. `is`-এর বদলে value comparison-এর জন্য সাধারণত `==` ব্যবহার করো।
6. আগে output predict করো, তারপর VS Code বা Python interpreter-এ run করো।
7. ভুল হলে শুধু correct answer মুখস্থ না করে কেন ভুল হয়েছিল, তা বুঝে নাও।

## 18. Chapter Review Checklist

- [ ] Arithmetic operator-এর output predict করতে পারি।
- [ ] Floor division ও modulo সঠিকভাবে হিসাব করতে পারি।
- [ ] Negative number-এর `//` ও `%` বুঝি।
- [ ] Comparison ও chained comparison evaluate করতে পারি।
- [ ] Logical operator-এর truthiness ও return value বুঝি।
- [ ] Assignment ও augmented assignment-এর ফল বের করতে পারি।
- [ ] Identity ও membership operator-এর পার্থক্য বুঝি।
- [ ] Bitwise operator-এর basic calculation করতে পারি।
- [ ] Operator precedence ও associativity প্রয়োগ করতে পারি।
- [ ] Conditional expression-এর output predict করতে পারি।
- [ ] Short-circuit evaluation-এর কারণে কোন expression execute হবে তা বুঝতে পারি।

## 19. Final Revision

Output prediction ভালোভাবে শেখার সবচেয়ে কার্যকর উপায় হলো নিয়মিত practice করা।

প্রতিটি code-এর ক্ষেত্রে:

1. Input ও initial variable values শনাক্ত করো।
2. Precedence অনুযায়ী expression evaluate করো।
3. Assignment থাকলে variable-এর নতুন value update করো।
4. Condition থাকলে কোন branch execute হবে নির্ধারণ করো।
5. `print()` কী output দেবে, তা লিখে তারপর code run করো।

পরবর্তী Topic: **33. Chapter Review and Self-Assessment**