# 20. Understanding Errors and Debugging Basics

## 1. Introduction

Python program লেখার সময় অনেক ধরনের সমস্যা হতে পারে। যেমন, code-এর syntax ভুল হওয়া, ভুল data type ব্যবহার করা অথবা calculation-এর logic ভুল হওয়া।

এই সমস্যাগুলো বুঝতে প্রধানত তিনটি বিষয় জানতে হবে:

- **Error:** Program-এ কোনো সমস্যা, যার কারণে code সঠিকভাবে কাজ করতে পারে না।
- **Bug:** Program-এর এমন কোনো defect, যার কারণে ভুল result বা unexpected behavior হয়।
- **Debugging:** Program-এর bug বা সমস্যার কারণ খুঁজে বের করে ঠিক করার প্রক্রিয়া।

উদাহরণ:

```python
print("Hello Python"
```

এই code-এ closing parenthesis `)` নেই। তাই Python `SyntaxError` দেখাবে।

সঠিক code:

```python
print("Hello Python")
```

মনে রাখবে, error হওয়া মানেই তুমি programming পারো না—এমন নয়। Error message বুঝতে শেখা programming শেখার গুরুত্বপূর্ণ অংশ।

## 2. What Is an Error?

Error হলো program execute করার সময় বা code যাচাই করার সময় পাওয়া কোনো সমস্যা, যা program-এর স্বাভাবিক execution-কে বাধাগ্রস্ত করতে পারে।

উদাহরণ:

```python
number = 10
result = number / 0

print(result)
```

Output:

```text
ZeroDivisionError: division by zero
```

এখানে শূন্য দিয়ে ভাগ করা হয়েছে, যা Python-এর সাধারণ numeric division-এ অনুমোদিত নয়।

Python error message-এর মাধ্যমে সমস্যার ধরন এবং অনেক সময় সমস্যাটি কোথায় হয়েছে, তা জানায়।

## 3. What Is a Bug?

**Bug** হলো program-এর কোনো ভুল, যার কারণে program প্রত্যাশিত result দেয় না অথবা ভুলভাবে কাজ করে।

উদাহরণ:

```python
length = 10
width = 5

area = length + width

print(area)
```

Output:

```text
15
```

কিন্তু rectangle-এর area বের করার সঠিক formula হলো:

\[
\text{Area}=\text{Length}\times\text{Width}
\]

তাই সঠিক code হবে:

```python
length = 10
width = 5

area = length * width

print(area)
```

Output:

```text
50
```

প্রথম code-টি কোনো syntax error ছাড়াই চলেছে, কিন্তু calculation ভুল ছিল। এটি একটি **logical bug**।

## 4. What Is Debugging?

Debugging হলো program-এর সমস্যা শনাক্ত করা, তার কারণ বোঝা এবং প্রয়োজনীয় পরিবর্তনের মাধ্যমে সমস্যাটি সমাধান করা।

একটি সহজ debugging process:

1. Program চালাও এবং সমস্যা লক্ষ্য করো।
2. Error message থাকলে সেটি পড়ো।
3. Code-এর সংশ্লিষ্ট line খুঁজে বের করো।
4. Input, variable এবং calculation যাচাই করো।
5. প্রয়োজন অনুযায়ী code পরিবর্তন করো।
6. আবার program চালিয়ে result যাচাই করো।

উদাহরণ:

```python
a = 10
b = 20

result = a - b

print(result)
```

যদি উদ্দেশ্য হয় দুটি সংখ্যার যোগফল বের করা, তাহলে `-` operator-টি ভুল।

সংশোধিত code:

```python
a = 10
b = 20

result = a + b

print(result)
```

Output:

```text
30
```

এখানে debugging-এর মাধ্যমে logical mistake ঠিক করা হয়েছে।

## 5. Main Types of Errors in Python

Beginner level-এ Python-এর error-কে তিনটি প্রধান category-তে বুঝতে পারো।

1. Syntax Error
2. Runtime Error
3. Logical Error

| Error Type | কখন বা কীভাবে সমস্যা হয় | Example |
|---|---|---|
| Syntax Error | Python code-এর syntax সঠিক নয় | Closing bracket বাদ পড়া |
| Runtime Error | Code execute করার সময় exception ঘটে | শূন্য দিয়ে ভাগ |
| Logical Error | Code চলে, কিন্তু result ভুল হয় | ভুল formula ব্যবহার |

এই তিনটি category-এর পার্থক্য ভালোভাবে বোঝা জরুরি।

## 6. Syntax Error

**Syntax Error** হয় যখন code Python-এর grammar বা syntax rules অনুসরণ করে না।

### Example 1: Missing Parenthesis

ভুল code:

```python
print("Hello Python"
```

Error:

```text
SyntaxError
```

সঠিক code:

```python
print("Hello Python")
```

### Example 2: Missing Colon

ভুল code:

```python
if age >= 18
    print("Adult")
```

সঠিক code:

```python
age = 20

if age >= 18:
    print("Adult")
```

এখানে `if` statement-এর শেষে colon `:` দিতে হয়।

### Example 3: Incorrect Assignment

ভুল code:

```python
if age = 18:
    print("Age is 18")
```

সঠিক code:

```python
if age == 18:
    print("Age is 18")
```

এখানে comparison করার জন্য `==` ব্যবহার করতে হয়, assignment operator `=` নয়।

### Common Causes of Syntax Errors

- Closing bracket বাদ দেওয়া।
- String-এর quotation mark বন্ধ না করা।
- প্রয়োজনীয় colon বাদ দেওয়া।
- ভুল indentation-এর কারণে invalid structure তৈরি করা।
- Keyword বা operator ভুলভাবে লেখা।

**মনে রাখবে:** Syntax Error হলে প্রথমে Python-এর grammar, brackets, quotation marks, colon এবং indentation পরীক্ষা করবে।

## 7. Runtime Errors and Exceptions

কিছু code syntax অনুযায়ী সঠিক হলেও execute করার সময় সমস্যা হতে পারে। এ ধরনের সমস্যায় Python exception তৈরি করতে পারে।

উদাহরণ:

```python
a = 10
b = 0

print(a / b)
```

Output:

```text
ZeroDivisionError: division by zero
```

এখানে code-এর syntax সঠিক, কিন্তু execution-এর সময় শূন্য দিয়ে ভাগ করার চেষ্টা করা হয়েছে।

### Common Runtime Exceptions

| Exception | সাধারণ কারণ |
|---|---|
| `ZeroDivisionError` | শূন্য দিয়ে ভাগ করা |
| `NameError` | কোনো নাম বা variable খুঁজে না পাওয়া |
| `TypeError` | Incompatible type-এর operation করা |
| `ValueError` | সঠিক type হলেও invalid value দেওয়া |
| `IndexError` | Sequence-এর invalid index ব্যবহার করা |
| `KeyError` | Dictionary-তে অনুপস্থিত key access করা |
| `FileNotFoundError` | যে file পাওয়া যাচ্ছে না, সেটি খোলার চেষ্টা করা |
| `AttributeError` | Object-এর নেই এমন attribute বা method ব্যবহার করা |
| `ModuleNotFoundError` | প্রয়োজনীয় module খুঁজে না পাওয়া |

### Example 1: `NameError`

ভুল code:

```python
print(total)
```

যদি `total` নামে কোনো variable আগে define করা না থাকে, তাহলে `NameError` হতে পারে।

সঠিক code:

```python
total = 100

print(total)
```

### Example 2: `TypeError`

ভুল code:

```python
age = 20

print("Age: " + age)
```

এখানে string-এর সঙ্গে integer সরাসরি concatenate করার চেষ্টা করা হয়েছে।

সঠিক code:

```python
age = 20

print("Age:", age)
```

অথবা:

```python
age = 20

print(f"Age: {age}")
```

### Example 3: `ValueError`

ভুল code:

```python
number = int("hello")
```

এখানে `"hello"`-কে integer-এ convert করা সম্ভব নয়।

সঠিক approach:

```python
try:
    number = int(input("Enter an integer: "))
    print(number)
except ValueError:
    print("Please enter a valid integer.")
```

এখানে invalid integer input দিলে program error message দেখাবে।

## 8. Logical Errors

**Logical Error** হলো এমন ভুল, যেখানে program execute হয়, কিন্তু result বা behavior প্রত্যাশা অনুযায়ী হয় না।

উদাহরণ:

```python
num1 = 10
num2 = 5

result = num1 - num2

print("Sum:", result)
```

Output:

```text
Sum: 5
```

Program execute হয়েছে, কিন্তু sum বের করার পরিবর্তে subtraction করা হয়েছে।

সঠিক code:

```python
num1 = 10
num2 = 5

result = num1 + num2

print("Sum:", result)
```

Output:

```text
Sum: 15
```

### Common Causes of Logical Errors

- ভুল formula ব্যবহার করা।
- ভুল operator ব্যবহার করা।
- ভুল variable ব্যবহার করা।
- Condition ভুলভাবে লেখা।
- Loop-এর stopping condition ভুল হওয়া।
- Calculation-এর order ভুল হওয়া।
- Boundary case বিবেচনা না করা।

Logical error খুঁজে বের করতে expected result এবং actual result তুলনা করা গুরুত্বপূর্ণ।

## 9. Understanding Error Messages

Python-এর error message দেখে সমস্যা বুঝতে শেখা খুব গুরুত্বপূর্ণ।

উদাহরণ:

```python
number = 10
result = number / 0
```

সম্ভাব্য error message:

```text
Traceback (most recent call last):
  ...
ZeroDivisionError: division by zero
```

Error message-এর গুরুত্বপূর্ণ অংশগুলো:

- **Traceback:** কোন কোন execution step-এর মাধ্যমে error হয়েছে, তা দেখায়।
- **File name and line number:** কোন file এবং line-এ সমস্যা হয়েছে, তা শনাক্ত করতে সাহায্য করে।
- **Exception type:** সমস্যার ধরন জানায়, যেমন `ZeroDivisionError`।
- **Error message:** সমস্যার সংক্ষিপ্ত কারণ জানায়, যেমন `division by zero`।

Traceback-এর format সবসময় একই রকম নাও হতে পারে। IDE বা execution environment অনুযায়ী কিছু অংশ আলাদা হতে পারে।

### How to Read an Error Message

ধাপে ধাপে:

1. Error-এর শেষের line পড়ো।
2. Exception-এর নাম শনাক্ত করো।
3. Error message বুঝে নাও।
4. সংশ্লিষ্ট file ও line number দেখো।
5. সেই line-এর পাশাপাশি প্রয়োজন হলে আগের line-গুলোর code-ও পরীক্ষা করো।

শুধু error-এর line-টিই সবসময় মূল কারণ নয়। আগের কোনো operation ভুল value তৈরি করে থাকলেও পরের line-এ error দেখা দিতে পারে।

## 10. Using `print()` for Debugging

Beginner-দের জন্য debugging-এর সহজ পদ্ধতি হলো গুরুত্বপূর্ণ variable-এর value `print()` দিয়ে দেখা।

উদাহরণ:

```python
price = 100
quantity = 3

print("Price:", price)
print("Quantity:", quantity)

total = price + quantity

print("Total:", total)
```

Output:

```text
Price: 100
Quantity: 3
Total: 103
```

যদি উদ্দেশ্য হয় মোট মূল্য হিসাব করা, তাহলে `+` operator-টি ভুল। এখানে `*` ব্যবহার করতে হবে।

সঠিক code:

```python
price = 100
quantity = 3

total = price * quantity

print("Total:", total)
```

Output:

```text
Total: 300
```

Debugging-এর সময় variable-এর value দেখা ভুল calculation বা unexpected data শনাক্ত করতে সাহায্য করে।

তবে professional project-এ অনেক diagnostic output-এর পরিবর্তে `logging` বা debugger ব্যবহার করা সুবিধাজনক।

## 11. Debugging with VS Code

VS Code-এর debugger ব্যবহার করে program ধাপে ধাপে execute করা যায়।

### Important Debugging Terms

- **Breakpoint:** নির্দিষ্ট line-এ program execution থামানোর নির্দেশ।
- **Step Over:** বর্তমান line execute করে পরের line-এ যাওয়া।
- **Step Into:** কোনো function call-এর ভেতরে প্রবেশ করে execution দেখা।
- **Continue:** পরবর্তী breakpoint পর্যন্ত execution চালানো।
- **Variables Panel:** বর্তমানে থাকা variable-এর value দেখা।
- **Call Stack:** function call-এর execution history বোঝা।

### Basic Debugging Steps

1. VS Code-এ Python file খোলো।
2. যে line পরীক্ষা করতে চাও, তার পাশে click করে breakpoint বসাও।
3. Run and Debug option থেকে debugging শুরু করো।
4. Program breakpoint-এ থামলে Variables Panel পরীক্ষা করো।
5. Step Over বা Step Into ব্যবহার করে execution অনুসরণ করো।
6. ভুলের কারণ বুঝে code সংশোধন করো।
7. আবার program চালিয়ে যাচাই করো।

Breakpoint সাধারণত line-এর পাশে লাল চিহ্ন হিসেবে দেখা যায়।

Debugging-এর জন্য VS Code-এ Python extension এবং উপযুক্ত Python interpreter নির্বাচন করা থাকা প্রয়োজন।

## 12. Using `try` and `except` to Handle Exceptions

কিছু expected error handle করে program-কে আরও user-friendly করা যায়।

উদাহরণ:

```python
try:
    number = int(input("Enter a number: "))
    result = 100 / number
    print("Result:", result)

except ValueError:
    print("Please enter an integer.")

except ZeroDivisionError:
    print("Number cannot be zero.")
```

এখানে দুটি exception আলাদাভাবে handle করা হয়েছে।

- User integer না দিলে `ValueError` handle হবে।
- User `0` দিলে `ZeroDivisionError` handle হবে।

### Why Use Exception Handling?

- User-friendly error message দেখাতে।
- Expected exceptional situations সামলাতে।
- Program-এর অপ্রয়োজনীয় crash এড়াতে।
- সম্ভাব্য failure-এর ক্ষেত্রে সঠিক response দিতে।

তবে `try-except` ব্যবহার করে সব error লুকিয়ে ফেলা উচিত নয়। Error-এর কারণ বুঝে প্রয়োজনীয় exception-ই handle করতে হবে।

## 13. Basic Debugging Techniques

### Technique 1: Read the Error Message

Error message-এর শেষের line থেকে শুরু করে exception type ও কারণ বোঝার চেষ্টা করো।

### Technique 2: Check Variable Values

`print()` ব্যবহার করে গুরুত্বপূর্ণ variable-এর value যাচাই করো।

### Technique 3: Check Data Types

```python
value = input("Enter a number: ")

print(type(value))
```

এতে input-এর type বোঝা যাবে। Numeric calculation-এর জন্য প্রয়োজন হলে type conversion করো।

### Technique 4: Test Small Parts

বড় program একসঙ্গে পরীক্ষা না করে ছোট অংশ আলাদাভাবে পরীক্ষা করো।

### Technique 5: Check the Logic

Expected result, formula, operator এবং condition সঠিক কি না যাচাই করো।

### Technique 6: Reproduce the Problem

একই input ও পরিস্থিতিতে সমস্যাটি আবার ঘটানো যায় কি না দেখো। এতে কারণ শনাক্ত করা সহজ হয়।

### Technique 7: Change One Thing at a Time

একবারে একটি পরিবর্তন করে program আবার চালাও। এতে কোন পরিবর্তনে সমস্যা সমাধান হয়েছে, তা বোঝা সহজ হয়।

## 14. Common Beginner Mistakes

### Mistake 1: Ignoring the Error Message

Error message না পড়ে অনুমান করে code পরিবর্তন করলে মূল সমস্যা থেকে যেতে পারে।

**Solution:** Exception type, message এবং line number পড়ো।

### Mistake 2: Confusing `=` and `==`

```python
age = 20
```

এখানে `=` assignment-এর জন্য।

```python
age == 20
```

এখানে `==` comparison-এর জন্য।

### Mistake 3: Forgetting Type Conversion

```python
a = input("Enter first number: ")
b = input("Enter second number: ")

print(a + b)
```

এখানে দুটি input string হওয়ায় `10` ও `20` দিলে result `1020` হবে।

**Solution:**

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print(a + b)
```

### Mistake 4: Fixing the Symptom Instead of the Cause

কোনো একটি error এড়িয়ে গেলেই মূল bug সমাধান হয়েছে—এমন নয়।

**Solution:** সমস্যাটি কেন হয়েছে, তা বুঝে code সংশোধন করো।

### Mistake 5: Catching Every Exception Without a Reason

```python
try:
    result = 10 / 0
except:
    print("Something went wrong.")
```

এভাবে সব ধরনের exception ধরলে আসল সমস্যা আড়াল হয়ে যেতে পারে।

**Better approach:**

```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero.")
```

সম্ভব হলে নির্দিষ্ট exception handle করো।

## 15. Practice Exercises

### Exercise 1: Fix a Syntax Error

নিচের code-এ কী সমস্যা আছে? ঠিক করে চালাও।

```python
print("Welcome to Python"
```

### Exercise 2: Fix a `NameError`

```python
name = "Masum"

print(nam)
```

Variable-এর নামের ভুলটি খুঁজে বের করো।

### Exercise 3: Fix a Type Error

```python
age = 22

print("My age is " + age)
```

`print()` অথবা type conversion ব্যবহার করে code-টি ঠিক করো।

### Exercise 4: Fix a Logical Error

```python
length = 8
width = 4

area = length + width

print("Area:", area)
```

Rectangle-এর সঠিক area বের করো।

### Exercise 5: Handle Invalid Input

User-এর কাছ থেকে integer input নাও। Invalid input দিলে যেন `ValueError` handle করা যায়।

### Exercise 6: Handle Division by Zero

দুটি সংখ্যা input নিয়ে ভাগ করো। দ্বিতীয় সংখ্যা `0` হলে উপযুক্ত message দেখাও।

### Exercise 7: Debug Using `print()`

```python
price = 50
quantity = 4

total = price + quantity

print(total)
```

Expected total price কত? `print()` ব্যবহার করে bug খুঁজে বের করো এবং সঠিক code লেখো।

### Exercise 8: Identify Error Types

প্রতিটি উদাহরণে কোন ধরনের সমস্যা হয়েছে তা শনাক্ত করো।

**A.**

```python
print("Hello"
```

**B.**

```python
print(10 / 0)
```

**C.**

```python
print(10 - 5)
```

যদি উদ্দেশ্য হয় 10 ও 5-এর যোগফল বের করা।

### Exercise 9: Debug a Condition

```python
marks = 85

if marks >= 90:
    print("A+")
else:
    print("Below A+")
```

যদি তোমার grading rule অনুযায়ী 85-এর জন্য `A+` পাওয়ার কথা হয়, তাহলে condition-এ কী পরিবর্তন প্রয়োজন? এখানে নিজস্ব grading rule ব্যবহার করে code সংশোধন করো।

## 16. Quick Revision

| Concept | Meaning |
|---|---|
| Error | Code যাচাই বা execution-এর সময় পাওয়া সমস্যা |
| Bug | Program-এর defect, যা ভুল result বা behavior ঘটায় |
| Debugging | সমস্যা খুঁজে বের করে ঠিক করার প্রক্রিয়া |
| Syntax Error | Python syntax rules ভাঙার কারণে হওয়া error |
| Runtime Error | Execution-এর সময় ঘটে যাওয়া exception |
| Logical Error | Program চললেও ভুল result দেওয়ার সমস্যা |
| Traceback | Exception ঘটার execution path-এর তথ্য |
| Breakpoint | নির্দিষ্ট line-এ execution থামানোর নির্দেশ |
| `print()` debugging | Variable-এর value দেখিয়ে সমস্যা শনাক্ত করা |
| `try-except` | নির্দিষ্ট exception handle করার পদ্ধতি |

## 17. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Error, bug এবং debugging-এর পার্থক্য।
- Syntax Error, Runtime Error এবং Logical Error।
- `NameError`, `TypeError`, `ValueError` ও `ZeroDivisionError`-এর মতো common exception।
- Traceback ও error message কীভাবে পড়তে হয়।
- `print()` দিয়ে variable ও calculation যাচাই করা।
- VS Code debugger-এর breakpoint, step over ও step into।
- `try-except` ব্যবহার করে expected exception handle করা।
- ছোট অংশ পরীক্ষা করে ধাপে ধাপে bug সমাধান করা।

সবচেয়ে গুরুত্বপূর্ণ বিষয় হলো, **error message পড়বে, সমস্যার কারণ বুঝবে, ছোট পরিবর্তন করবে এবং আবার পরীক্ষা করবে।**

## 18. Next Topic

পরবর্তী ফাইল: [`21_Writing_Clean_and_Readable_Code.md`](21_Writing_Clean_and_Readable_Code.md)

সেখানে meaningful variable names, proper indentation, code formatting, readability এবং clean code লেখার গুরুত্বপূর্ণ নিয়মগুলো শেখা হবে।