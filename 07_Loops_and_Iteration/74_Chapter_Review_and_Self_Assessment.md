# 74. Chapter Review and Self-Assessment

## 1. Chapter Overview

এই chapter-এ Python-এর **Loops & Iteration** সম্পর্কে বিস্তারিত আলোচনা করা হয়েছে।

Loop ব্যবহার করে একই কাজ বারবার execute করা যায়। এর মাধ্যমে counting, accumulation, searching, pattern printing, input validation এবং বিভিন্ন mathematical problem সমাধান করা সম্ভব।

এই chapter-এর প্রধান topics:

- `for` ও `while` loops
- `range()` function
- Loop conditions ও control variables
- `break`, `continue` এবং `pass`
- Loop-এর `else` clause
- Nested loops
- Counter ও accumulator
- Number-based problems
- List processing ও searching
- Loop debugging ও performance
- Output prediction ও programming exercises

## 2. Basic Loop Concepts

### 2.1 What Is a Loop?

Loop হলো এমন একটি programming structure, যা নির্দিষ্ট condition বা iteration-এর নিয়ম অনুযায়ী এক বা একাধিক statement বারবার execute করে।

Example:

```python
for number in range(1, 4):
    print(number)
```

Output:

```text
1
2
3
```

এখানে `print(number)` তিনবার execute হয়েছে।

### 2.2 Types of Loops in Python

| Loop | Main purpose |
|---|---|
| `for` | Iterable-এর item বা নির্দিষ্ট sequence নিয়ে কাজ করা |
| `while` | Condition সত্য থাকা পর্যন্ত কাজ করা |

### 2.3 `for` Loop Syntax

```python
for variable in iterable:
    # Statements
```

Example:

```python
for number in range(1, 6):
    print(number)
```

### 2.4 `while` Loop Syntax

```python
while condition:
    # Statements
```

Example:

```python
number = 1

while number <= 5:
    print(number)
    number += 1
```

`while` loop-এ condition সত্য থাকলে loop চলতে থাকে। Condition মিথ্যা হলে loop শেষ হয়।

## 3. Choosing Between `for` and `while`

| Situation | Recommended loop |
|---|---|
| নির্দিষ্ট সংখ্যক iteration | `for` |
| List-এর প্রতিটি item process করা | `for` |
| String-এর প্রতিটি character process করা | `for` |
| User-এর input-এর ওপর নির্ভরশীল repetition | `while` |
| Sentinel value না আসা পর্যন্ত input নেওয়া | `while` |
| Menu বারবার দেখানো | `while` |
| Condition-নির্ভর repetition | `while` |

এগুলো সাধারণ guideline। কোনো কোনো problem দুই ধরনের loop দিয়েই সমাধান করা সম্ভব।

## 4. Understanding the `range()` Function

`range()` সাধারণত `for` loop-এর সঙ্গে নির্দিষ্ট sequence-এর integer তৈরি করতে ব্যবহৃত হয়।

### Syntax

```python
range(stop)
range(start, stop)
range(start, stop, step)
```

### Examples

| Code | Values |
|---|---|
| `range(5)` | `0, 1, 2, 3, 4` |
| `range(1, 5)` | `1, 2, 3, 4` |
| `range(2, 11, 2)` | `2, 4, 6, 8, 10` |
| `range(5, 0, -1)` | `5, 4, 3, 2, 1` |
| `range(5, 1)` | Empty sequence |

**Important rules:**

- `start` অন্তর্ভুক্ত হয়।
- `stop` অন্তর্ভুক্ত হয় না।
- Default `start` হলো `0`।
- Default `step` হলো `1`।
- `step=0` হলে `ValueError` হয়।
- Backward iteration-এর জন্য সাধারণত negative step প্রয়োজন।

## 5. Loop Control Variables

Loop control variable iteration-এর সঙ্গে পরিবর্তিত হতে পারে।

Example:

```python
number = 1

while number <= 3:
    print(number)
    number += 1
```

এখানে `number` হলো control variable।

একটি `while` loop সঠিকভাবে শেষ করতে অনেক ক্ষেত্রে তিনটি বিষয় গুরুত্বপূর্ণ:

1. Initial value নির্ধারণ।
2. Condition পরীক্ষা।
3. প্রয়োজনীয় update করা।

Update ভুলে গেলে infinite loop হতে পারে।

## 6. Counter vs Accumulator

| Feature | Counter | Accumulator |
|---|---|---|
| কাজ | কোনো ঘটনা কতবার ঘটেছে গণনা | মোট বা combined value হিসাব |
| Initial value | সাধারণত `0` | যোগের ক্ষেত্রে সাধারণত `0` |
| Update | `count += 1` | `total += value` |
| Example | Even number count | Sum of numbers |

Example:

```python
count = 0
total = 0

for number in range(1, 6):
    count += 1
    total += number

print("Count:", count)
print("Total:", total)
```

Output:

```text
Count: 5
Total: 15
```

## 7. Loop Control Statements

### 7.1 `break`

`break` বর্তমান সবচেয়ে ভেতরের loop-টি সঙ্গে সঙ্গে শেষ করে।

```python
for number in range(1, 6):
    if number == 3:
        break
    print(number)
```

Output:

```text
1
2
```

### 7.2 `continue`

`continue` বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে পরবর্তী iteration শুরু করে।

```python
for number in range(1, 6):
    if number == 3:
        continue
    print(number)
```

Output:

```text
1
2
4
5
```

### 7.3 `pass`

`pass` কোনো কাজ করে না। এটি syntax-এর জন্য placeholder হিসেবে ব্যবহৃত হয়।

```python
for number in range(3):
    pass

print("Done")
```

Output:

```text
Done
```

### Comparison

| Statement | Effect |
|---|---|
| `break` | বর্তমান loop শেষ করে |
| `continue` | বর্তমান iteration-এর বাকি অংশ বাদ দেয় |
| `pass` | কোনো কাজ না করে পরের statement-এ যায় |

## 8. The `else` Clause in Loops

Python-এর `for` ও `while` loop-এ `else` ব্যবহার করা যায়।

```python
for number in range(3):
    print(number)
else:
    print("Completed")
```

Output:

```text
0
1
2
Completed
```

Loop স্বাভাবিকভাবে শেষ হলে `else` execute হয়। `break` দিয়ে loop বন্ধ হলে loop-এর `else` execute হয় না।

**Important:** `continue` ব্যবহার করলে loop-এর `else` বন্ধ হয় না। Loop শেষ পর্যন্ত স্বাভাবিকভাবে শেষ হলে `else` execute হবে।

## 9. Nested Loops

একটি loop-এর ভেতরে আরেকটি loop থাকলে তাকে nested loop বলে।

```python
for row in range(1, 4):
    for column in range(1, 3):
        print(row, column)
```

Outer loop-এর প্রতিটি iteration-এর জন্য inner loop সম্পূর্ণ execute হয়।

যদি outer loop \(m\) বার এবং inner loop প্রতিবার \(n\) বার চলে, তাহলে মোট inner-loop iteration:

\[
m \times n
\]

Nested loop ব্যবহার করা হয়:

- Star ও number patterns
- Multiplication tables
- Grid processing
- Matrix operations
- Pair generation

সব nested loop-এর complexity \(O(n^2)\) নয়; iteration-এর পরিমাণ কীভাবে বাড়ে, তা বিবেচনা করতে হবে।

## 10. Common Loop-Based Problems

এই chapter-এ যেসব problem শেখা হয়েছে, সেগুলোর গুরুত্বপূর্ণ ধারণা নিচে দেওয়া হলো।

| Problem | Main technique |
|---|---|
| Sum of numbers | Accumulator |
| Average | Sum / Count |
| Maximum and minimum | Comparison |
| Even/odd counting | Modulo `%` |
| Factorial | Repeated multiplication |
| Fibonacci | Previous two values |
| Prime checking | Divisor testing |
| Reverse a number | `% 10` and `// 10` |
| Sum of digits | Digit extraction |
| Count digits | Repeated division |
| Palindrome | Reverse and compare |
| Linear search | Sequential comparison |
| Menu program | `while` + conditions |
| Pattern printing | Nested loops |

### Important formulas

**Average:**

\[
\text{Average}=\frac{\text{Sum}}{\text{Count}}
\]

Count শূন্য হলে division করা যাবে না।

**Factorial:**

\[
n! = 1 \times 2 \times \cdots \times n
\]

এবং \(0! = 1\)।

**Digit extraction:**

```python
digit = number % 10
number //= 10
```

Positive integer-এর ক্ষেত্রে এই পদ্ধতিতে শেষ digit বের করা যায় এবং সেটি বাদ দেওয়া যায়। Negative number handle করতে আগে `abs()` ব্যবহার করা যেতে পারে।

## 11. Loop Debugging Checklist

Loop সঠিক output না দিলে নিচের বিষয়গুলো পরীক্ষা করো:

- [ ] Initial variable value সঠিক কি না।
- [ ] Loop condition সঠিক কি না।
- [ ] `range()`-এর stop value ঠিক আছে কি না।
- [ ] প্রয়োজনীয় variable update হচ্ছে কি না।
- [ ] Update-এর অবস্থান সঠিক কি না।
- [ ] Indentation ঠিক আছে কি না।
- [ ] Counter ও accumulator সঠিকভাবে initialize হয়েছে কি না।
- [ ] `break` বা `continue` অপ্রত্যাশিতভাবে কাজ করছে কি না।
- [ ] Nested loop-এ সঠিক variable ব্যবহার করা হয়েছে কি না।
- [ ] Empty list ও boundary cases handle করা হয়েছে কি না।
- [ ] Sentinel value-কে ভুল করে data হিসেবে গণনা করা হচ্ছে কি না।

## 12. Important Performance Concepts

Loop performance বুঝতে কয়েকটি basic ধারণা মনে রাখবে।

| Complexity | General meaning |
|---|---|
| \(O(1)\) | Constant growth |
| \(O(n)\) | Linear growth |
| \(O(n^2)\) | Quadratic growth |

একটি list-এর প্রতিটি element একবার process করলে সাধারণত \(O(n)\) time লাগে।

দুটি loop যদি প্রত্যেকটি \(n\) বার চলে, তাহলে সাধারণত \(O(n^2)\) time লাগতে পারে।

অপ্রয়োজনীয় iteration কমানো, উপযুক্ত built-in function ব্যবহার করা এবং প্রয়োজনের তুলনায় বেশি data store না করা performance উন্নত করতে সাহায্য করে।

তবে code optimize করার আগে correctness ও readability বজায় রাখা জরুরি।

## 13. Output Prediction Self-Test

উত্তর দেখার আগে নিজে predict করার চেষ্টা করো।

### Question 1

```python
for number in range(1, 5):
    print(number * 2)
```

### Question 2

```python
number = 1

while number < 5:
    print(number)
    number += 2
```

### Question 3

```python
total = 0

for number in range(1, 5):
    if number % 2 == 0:
        total += number

print(total)
```

### Question 4

```python
for number in range(1, 5):
    if number == 3:
        break
    print(number)
else:
    print("Done")
```

### Question 5

```python
for row in range(1, 4):
    for column in range(row):
        print("*", end="")
    print()
```

### Answer Key

**1.**

```text
2
4
6
8
```

**2.**

```text
1
3
```

**3.**

```text
6
```

**4.**

```text
1
2
```

`break` loop-কে স্বাভাবিকভাবে শেষ হতে দেয়নি, তাই `else` execute হয়নি।

**5.**

```text
*
**
***
```

## 14. Final Programming Self-Assessment

নিচের problem-গুলো কোনো solution না দেখে solve করার চেষ্টা করো।

### Basic Level

- [ ] 1 থেকে 100 পর্যন্ত সংখ্যা print করা।
- [ ] Even ও odd number print করা।
- [ ] 1 থেকে `n` পর্যন্ত sum বের করা।
- [ ] Multiplication table তৈরি করা।
- [ ] Countdown তৈরি করা।

### Intermediate Level

- [ ] Factorial বের করা।
- [ ] Fibonacci series তৈরি করা।
- [ ] Prime number check করা।
- [ ] Digit-এর sum বের করা।
- [ ] Number reverse করা।
- [ ] List থেকে maximum ও minimum বের করা।
- [ ] Linear search implement করা।

### Advanced Practice for This Chapter

- [ ] Nested loop দিয়ে বিভিন্ন pattern তৈরি করা।
- [ ] Menu-driven calculator তৈরি করা।
- [ ] Input validation implement করা।
- [ ] Loop ব্যবহার করে perfect number check করা।
- [ ] একটি problem-এর জন্য `for` ও `while`—দুই ধরনের solution লেখা।
- [ ] Dry run করে নিজের code debug করা।

## 15. Chapter Completion Checklist

Chapter 07 শেষ করার আগে নিশ্চিত হও যে তুমি:

- [ ] `for` ও `while` loop-এর syntax লিখতে পারো।
- [ ] Loop condition এবং control variable বুঝতে পারো।
- [ ] `range()`-এর তিনটি syntax form ব্যবহার করতে পারো।
- [ ] Counter ও accumulator-এর পার্থক্য বুঝতে পারো।
- [ ] `break`, `continue` ও `pass` ব্যবহার করতে পারো।
- [ ] Loop-এর `else` clause ব্যাখ্যা করতে পারো।
- [ ] Nested loops দিয়ে pattern ও table তৈরি করতে পারো।
- [ ] Number-based ও list-based problem solve করতে পারো।
- [ ] Output prediction ও dry run করতে পারো।
- [ ] Infinite loop ও off-by-one error শনাক্ত করতে পারো।
- [ ] Basic time complexity বুঝতে পারো।
- [ ] নিজে loop-based program লিখে test করতে পারো।

## 16. Chapter Conclusion

এই chapter-এর মূল শিক্ষা হলো, loop ব্যবহার করে repetitive কাজকে সহজ, পরিষ্কার এবং কার্যকরভাবে সমাধান করা যায়।

শুধু syntax মুখস্থ না করে প্রতিটি loop-এর execution flow, variable update, termination condition এবং output বোঝার চেষ্টা করবে।

Programming-এ দক্ষ হতে নিয়মিত problem solve করা, dry run করা এবং নিজের ভুল থেকে শেখা সবচেয়ে গুরুত্বপূর্ণ।

## 17. Next Chapter

Chapter 07: **Loops & Iteration** সম্পন্ন।

পরবর্তী chapter:

`08_Strings/README.md`

এখানে Python string-এর indexing, slicing, methods, searching, formatting এবং string-based problem solving বিস্তারিতভাবে শেখা হবে।