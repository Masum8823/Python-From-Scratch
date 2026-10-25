# 07. Statements and Expressions in Python

## 1. Introduction

Python-এ program লেখার সময় আমরা বিভিন্ন ধরনের code ব্যবহার করি। এর মধ্যে দুটি গুরুত্বপূর্ণ concept হলো:

1. **Statement**
2. **Expression**

দুটিই Python program-এর অংশ, কিন্তু এদের কাজ এক নয়।

- **Statement:** Python-কে কোনো কাজ সম্পন্ন করার নির্দেশ দেয়।
- **Expression:** এমন একটি code যা evaluate হয়ে একটি value তৈরি করে।

উদাহরণ:

```python
x = 10
```

এটি একটি assignment statement। এটি `10` value-টি `x` variable-এর সঙ্গে যুক্ত করে।

অন্যদিকে:

```python
5 + 3
```

এটি একটি expression, কারণ এটি evaluate হয়ে `8` value তৈরি করে।

## 2. What Is a Statement?

**Statement** হলো Python code-এর এমন একটি instruction, যা কোনো কাজ সম্পন্ন করে।

Statement-এর মাধ্যমে variable তৈরি বা update করা, condition পরীক্ষা করা, loop চালানো, function তৈরি করা এবং function call করা যায়।

উদাহরণ:

```python
name = "Masum"
age = 22

print(name)
```

এখানে:

- `name = "Masum"` একটি assignment statement।
- `age = 22` একটি assignment statement।
- `print(name)` একটি function call statement হিসেবে ব্যবহৃত হয়েছে।

Output:

```text
Masum
```

### Common Types of Statements

Python-এ বিভিন্ন ধরনের statement রয়েছে।

| Statement Type | Example | কাজ |
|---|---|---|
| Assignment | `x = 10` | Variable-এ value assign করা |
| Expression statement | `print("Hello")` | Expression evaluate করা |
| Conditional | `if x > 5:` | Condition অনুযায়ী কাজ করা |
| Loop | `for i in range(3):` | বারবার কাজ করা |
| Function definition | `def greet():` | Function তৈরি করা |
| Import | `import math` | Module ব্যবহার করা |
| Return | `return result` | Function থেকে value ফেরত দেওয়া |
| Exception handling | `try:` | সম্ভাব্য error সামলানো |

সব statement-এর কাজ এক নয়। কোনো statement সরাসরি value তৈরি বা return করতে পারে, আবার কোনোটি program-এর execution flow নিয়ন্ত্রণ করে।

## 3. What Is an Expression?

**Expression** হলো এমন একটি combination of values, variables, operators বা function calls, যা evaluate হয়ে একটি value দেয়।

উদাহরণ:

```python
5 + 3
```

Result: `8`

আরেকটি উদাহরণ:

```python
10 * 2
```

Result: `20`

আরও কয়েকটি expression:

```python
10
```

```python
"Hello"
```

```python
x + 5
```

```python
10 > 5
```

এগুলো যথাক্রমে `10`, `"Hello"`, `x`-এর value-এর সঙ্গে `5` যোগের ফল এবং `True` বা `False` তৈরি করতে পারে।

**মনে রাখবে:** Expression-এর result সবসময় number হতে হবে না। এটি string, Boolean, list বা অন্য কোনো Python object-ও হতে পারে।

## 4. Types of Expressions

### 4.1 Arithmetic Expression

Mathematical calculation করার জন্য ব্যবহৃত হয়।

```python
a = 10
b = 5

result = a + b
print(result)
```

Output:

```text
15
```

এখানে `a + b` হলো arithmetic expression।

### 4.2 Comparison Expression

দুটি value তুলনা করে এবং সাধারণত `True` অথবা `False` result দেয়।

```python
age = 22

print(age >= 18)
print(age == 20)
```

Output:

```text
True
False
```

এখানে `age >= 18` এবং `age == 20` হলো comparison expressions।

### 4.3 Logical Expression

এক বা একাধিক condition-এর ওপর logical operation করে।

```python
age = 22
has_id = True

result = age >= 18 and has_id
print(result)
```

Output:

```text
True
```

এখানে `age >= 18 and has_id` হলো logical expression।

### 4.4 String Expression

String concatenate বা combine করতে ব্যবহার করা যায়।

```python
first_name = "Abdulla"
last_name = "Masum"

full_name = first_name + " " + last_name
print(full_name)
```

Output:

```text
Abdulla Masum
```

এখানে `first_name + " " + last_name` হলো string expression।

### 4.5 Function Call Expression

অনেক function call একটি value return করে, যা অন্য expression-এর অংশ হিসেবে ব্যবহার করা যায়।

```python
numbers = [10, 20, 30]

result = len(numbers) + 5
print(result)
```

Output:

```text
8
```

এখানে `len(numbers)` value `3` return করে এবং `len(numbers) + 5` পুরো expression-এর result হয় `8`।

তবে সব function call value return করে না। `print()` সাধারণত `None` return করে।

## 5. Difference Between Statements and Expressions

এটি exam এবং programming-এর জন্য খুব গুরুত্বপূর্ণ।

| Statement | Expression |
|---|---|
| কোনো instruction বা কাজ সম্পন্ন করে | Evaluate হয়ে একটি value তৈরি করে |
| Program-এর execution নিয়ন্ত্রণ করতে পারে | Value calculation বা determination-এ ব্যবহৃত হয় |
| সব statement নিজে value produce করে না | Expression-এর একটি resulting value থাকে |
| Example: `x = 10` | Example: `5 + 3` |
| Example: `if x > 5:` | Example: `x > 5` |
| Example: `def greet():` | Example: `len("Python")` |

### Example to Understand the Difference

```python
x = 10
y = 20

total = x + y

print(total)
```

এখানে:

- `x = 10` — assignment statement।
- `y = 20` — assignment statement।
- `x + y` — expression, যার result `30`।
- `total = x + y` — assignment statement, যার ডান পাশের অংশটি expression।
- `print(total)` — function call statement হিসেবে ব্যবহৃত হয়েছে।

অর্থাৎ, একটি statement-এর ভেতরেও expression থাকতে পারে।

## 6. Expressions Inside Statements

Python code-এ expression প্রায়ই statement-এর অংশ হিসেবে ব্যবহৃত হয়।

### Example 1: Assignment Statement

```python
result = 10 + 20
```

এখানে:

- `10 + 20` হলো expression।
- `result = 10 + 20` হলো assignment statement।

Python প্রথমে ডান পাশের expression evaluate করে, তারপর result-টি `result` variable-এর সঙ্গে assign করে।

### Example 2: If Statement

```python
age = 20

if age >= 18:
    print("Adult")
```

এখানে:

- `age >= 18` হলো expression।
- `if age >= 18:` হলো conditional statement-এর header।
- `print("Adult")` হলো conditional block-এর ভেতরের statement।

Condition `True` হলে `print()` execute হয়।

### Example 3: While Statement

```python
count = 1

while count <= 3:
    print(count)
    count += 1
```

Output:

```text
1
2
3
```

এখানে `count <= 3` হলো expression, যা প্রতিবার evaluate হয়ে loop চলবে কি না তা নির্ধারণ করে।

## 7. Expression Evaluation

**Expression evaluation** হলো expression-এর value নির্ণয় করার প্রক্রিয়া।

উদাহরণ:

```python
result = 5 + 3 * 2
print(result)
```

Output:

```text
11
```

এখানে multiplication-এর precedence addition-এর চেয়ে বেশি। তাই আগে `3 * 2 = 6`, তারপর `5 + 6 = 11` হিসাব করা হয়।

আরেকটি উদাহরণ:

```python
x = 10
result = x > 5
print(result)
```

Output:

```text
True
```

এখানে `x > 5` evaluate হয়ে `True` তৈরি করে।

### Evaluation-এর সাধারণ ধাপ

1. Expression-এর values ও variables শনাক্ত করা হয়।
2. Operators-এর precedence ও associativity অনুযায়ী expression evaluate করা হয়।
3. প্রয়োজন হলে function call execute হয়।
4. Expression-এর final value পাওয়া যায়।
5. Statement-এর নিয়ম অনুযায়ী সেই value ব্যবহার করা হয়।

বাস্তবে operator-এর precedence, evaluation order এবং short-circuiting-এর মতো নিয়মও গুরুত্বপূর্ণ।

## 8. Simple and Complex Expressions

### 8.1 Simple Expression

যে expression সহজে বোঝা যায় এবং সাধারণত কম operation থাকে।

```python
5 + 3
```

Result: `8`

```python
age >= 18
```

এটি age-এর value অনুযায়ী `True` বা `False` তৈরি করে।

### 8.2 Complex Expression

যে expression-এ একাধিক operator বা subexpression থাকে।

```python
result = (10 + 5) * 2 - 4
print(result)
```

Output:

```text
26
```

হিসাব:

1. `10 + 5 = 15`
2. `15 * 2 = 30`
3. `30 - 4 = 26`

Complex expression বোঝা কঠিন হলে parentheses ব্যবহার করে calculation স্পষ্ট করা যায়।

## 9. Expression Statements

কিছু expression-কে সরাসরি statement হিসেবে লেখা যায়। এগুলোকে **expression statements** বলা হয়।

উদাহরণ:

```python
print("Hello")
```

এখানে `print("Hello")` একটি function call expression, যা expression statement হিসেবে ব্যবহৃত হয়েছে।

Output:

```text
Hello
```

আরেকটি উদাহরণ:

```python
2 + 3
```

এই expression-টি interactive Python REPL-এ `5` দেখাতে পারে। কিন্তু সাধারণ `.py` file-এ এভাবে লিখলে result সাধারণত নিজে থেকে screen-এ দেখা যায় না।

ফাইলে result দেখতে লিখতে হবে:

```python
print(2 + 3)
```

Output:

```text
5
```

এটি REPL এবং script-এর মধ্যে একটি গুরুত্বপূর্ণ পার্থক্য।

## 10. Statements That Control Program Flow

কিছু statement program-এর execution flow নিয়ন্ত্রণ করে।

### 10.1 Conditional Statement

```python
marks = 85

if marks >= 80:
    print("A+")
else:
    print("Other grade")
```

Output:

```text
A+
```

`if` statement condition অনুযায়ী কোন block execute হবে তা নির্ধারণ করে।

### 10.2 Loop Statement

```python
for i in range(3):
    print(i)
```

Output:

```text
0
1
2
```

`for` statement নির্দিষ্ট sequence-এর ওপর iteration করে।

### 10.3 Function Definition Statement

```python
def greet():
    print("Hello")

greet()
```

Output:

```text
Hello
```

`def` statement একটি function তৈরি করে। পরে function call করলে তার body execute হয়।

## 11. Common Beginner Mistakes

### Mistake 1: Assuming Every Expression Prints Its Result

ভুল ধারণা:

```python
10 + 20
```

একটি `.py` file-এ লিখলেই result `30` screen-এ দেখা যাবে।

সঠিক:

```python
print(10 + 20)
```

Output:

```text
30
```

### Mistake 2: Confusing an Expression with an Assignment Statement

```python
x = 10 + 5
```

এখানে `10 + 5` হলো expression এবং পুরো `x = 10 + 5` হলো assignment statement।

### Mistake 3: Assuming Every Statement Returns a Value

```python
x = 10
```

Assignment statement-এর result expression-এর মতো সরাসরি ব্যবহার করা যায় না। যেমন, নিচের code invalid:

```python
# Invalid Python syntax
# result = (x = 10)
```

Python-এ সাধারণ assignment statement-কে এভাবে অন্য expression-এর ভেতরে বসানো যায় না।

### Mistake 4: Ignoring Operator Precedence

```python
result = 5 + 3 * 2
print(result)
```

Output:

```text
11
```

এটি `16` নয়, কারণ multiplication আগে হয়।

যদি আগে addition করতে চাও:

```python
result = (5 + 3) * 2
print(result)
```

Output:

```text
16
```

## 12. Practical Examples

### Example 1: Calculate Total Marks

```python
# Store marks
math_marks = 85
english_marks = 80
science_marks = 90

# Calculate total marks
total = math_marks + english_marks + science_marks

# Display the result
print("Total marks:", total)
```

Output:

```text
Total marks: 255
```

এখানে তিনটি marks-এর যোগফল হলো expression এবং পুরো assignment-টি একটি statement।

### Example 2: Check Eligibility

```python
age = 20

eligible = age >= 18

print(eligible)
```

Output:

```text
True
```

এখানে `age >= 18` expression-টি `True` তৈরি করে, যা `eligible` variable-এ assign হয়।

### Example 3: Calculate Average

```python
mark1 = 80
mark2 = 90
mark3 = 85

average = (mark1 + mark2 + mark3) / 3

print("Average:", average)
```

Output:

```text
Average: 85.0
```

এখানে `(mark1 + mark2 + mark3) / 3` হলো একটি complex arithmetic expression।

## 13. Practice Exercises

### Exercise 1: Identify Statements and Expressions

নিচের code-এ statements ও expressions চিহ্নিত করো।

```python
x = 10
y = 20
total = x + y
print(total)
```

### Exercise 2: Evaluate the Expressions

প্রতিটি expression-এর result বের করো।

```python
10 + 5
20 - 8
4 * 3
20 / 4
5 + 2 * 3
(5 + 2) * 3
10 > 5
```

### Exercise 3: Predict the Output

```python
x = 5
y = 10

result = x + y * 2

print(result)
```

Output কী হবে এবং কেন?

### Exercise 4: Create a Conditional Statement

একটি `age` variable তৈরি করো। Expression ব্যবহার করে যাচাই করো বয়স ১৮ বা তার বেশি কি না। উপযুক্ত message print করো।

### Exercise 5: Calculate Average Marks

তিনটি subject-এর marks নিয়ে average হিসাব করো। Expression ও statement আলাদাভাবে শনাক্ত করো।

### Exercise 6: Explain the Difference

নিজের ভাষায় উত্তর দাও:

1. Statement কী?
2. Expression কী?
3. Expression কীভাবে value তৈরি করে?
4. একটি statement-এর মধ্যে expression থাকতে পারে কি?
5. সাধারণ Python script-এ `10 + 20` লিখলে কেন result screen-এ দেখা যায় না?
6. `x = 10 + 20`-এ কোন অংশটি expression?

## 14. Quick Revision

| Concept | Example | Explanation |
|---|---|---|
| Statement | `x = 10` | Value assign করে |
| Arithmetic expression | `5 + 3` | `8` তৈরি করে |
| Comparison expression | `10 > 5` | `True` তৈরি করে |
| Logical expression | `True and False` | `False` তৈরি করে |
| Function call | `print("Hello")` | Output দেখায় |
| Conditional statement | `if x > 5:` | Condition অনুযায়ী কাজ করে |
| Loop statement | `for i in range(3):` | Iteration করে |
| Expression evaluation | `5 + 3 * 2` | `11` তৈরি করে |

## 15. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Statement হলো Python-এর instruction, যা কোনো কাজ সম্পন্ন করে।
- Expression evaluate হয়ে একটি value তৈরি করে।
- Assignment statement-এর ডান পাশে expression থাকতে পারে।
- Arithmetic, comparison, logical এবং string expression Python-এ বহুল ব্যবহৃত হয়।
- Conditional ও loop statement program-এর execution flow নিয়ন্ত্রণ করে।
- Expression-এর result সাধারণ script-এ দেখাতে প্রায়ই `print()` ব্যবহার করতে হয়।
- Operator precedence expression evaluation-কে প্রভাবিত করে।

## 16. Next Topic

পরবর্তী ফাইল: [`08_Python_Keywords_and_Reserved_Words.md`](08_Python_Keywords_and_Reserved_Words.md)

এখানে আমরা Python keywords, reserved words, `if`, `else`, `for`, `while`, `def`, `class` এবং keyword-গুলোকে identifier হিসেবে ব্যবহার করা যায় না কেন, তা শিখব।
