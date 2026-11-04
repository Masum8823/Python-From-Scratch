# 11. Type Conversion in User Input

## 1. Introduction

Python-এ `input()` function ব্যবহার করে user-এর কাছ থেকে data নেওয়া হয়। কিন্তু `input()` সবসময় user-এর দেওয়া value-কে `str` হিসেবে return করে।

যখন user-এর input দিয়ে mathematical calculation করতে হয়, তখন সেই string-কে উপযুক্ত numeric data type-এ convert করতে হয়।

এই প্রক্রিয়াকে **Type Conversion** বলা হয়।

### Example: Without Type Conversion

```python
a = input("Enter first number: ")
b = input("Enter second number: ")

print(a + b)
```

Sample Interaction:

```text
Enter first number: 10
Enter second number: 20
1020
```

এখানে `10` ও `20` যোগ হয়ে `30` হয়নি। কারণ দুটি input-ই string।

### Example: With Type Conversion

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print(a + b)
```

Sample Interaction:

```text
Enter first number: 10
Enter second number: 20
30
```

এখানে `int()` ব্যবহার করে input-গুলোকে integer-এ convert করা হয়েছে। তাই সঠিক যোগফল পাওয়া গেছে।

## 2. What Is Type Conversion?

**Type Conversion** হলো কোনো value-কে একটি data type থেকে অন্য data type-এ পরিবর্তন করার প্রক্রিয়া।

Python-এ প্রয়োজন অনুযায়ী একটি value-কে `int`, `float`, `str`, `bool` এবং অন্যান্য data type-এ convert করা যায়।

### Example

```python
number = "25"

print(number)
print(type(number))

converted_number = int(number)

print(converted_number)
print(type(converted_number))
```

Output:

```text
25
<class 'str'>
25
<class 'int'>
```

এখানে:

1. প্রথমে `number` একটি string ছিল।
2. `int(number)` string-টিকে integer-এ convert করেছে।
3. `converted_number` এখন integer value ধারণ করছে।

**মনে রাখবে:** শুধু variable-এর নাম পরিবর্তন করলে data type পরিবর্তন হয় না। প্রয়োজনীয় conversion operation ব্যবহার করতে হয়।

## 3. Why Is Type Conversion Necessary?

Type conversion-এর মাধ্যমে user input-কে প্রয়োজন অনুযায়ী ব্যবহার করা যায়।

### Reason 1: Mathematical Calculation

```python
age = input("Enter your age: ")
```

এখানে `age` একটি string।

বয়সের সঙ্গে ৫ যোগ করতে চাইলে:

```python
age = int(input("Enter your age: "))

print("Age after 5 years:", age + 5)
```

Input `20` হলে output:

```text
Age after 5 years: 25
```

### Reason 2: Decimal Calculation

```python
price = float(input("Enter product price: "))

print("Price:", price)
```

Input `99.50` হলে `price` একটি float value হবে।

### Reason 3: Comparing Numeric Values

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("Adult")
else:
    print("Minor")
```

এখানে input-কে integer-এ convert করা হয়েছে, যাতে numeric comparison করা যায়।

### Reason 4: Avoiding Type Errors

```python
number = input("Enter a number: ")

print(number + 5)
```

এখানে `number` string এবং `5` integer। তাই `TypeError` হবে।

সঠিক code:

```python
number = int(input("Enter a number: "))

print(number + 5)
```

## 4. General Syntax of Type Conversion

Type conversion করার সাধারণ syntax:

```python
data_type(value)
```

এখানে `data_type` হলো যে type-এ convert করতে চাই এবং `value` হলো যে value-টিকে convert করা হবে।

### Common Conversion Functions

| Function | কাজ | Example |
|---|---|---|
| `int()` | Integer-এ convert করে | `int("25")` → `25` |
| `float()` | Float-এ convert করে | `float("2.5")` → `2.5` |
| `str()` | String-এ convert করে | `str(25)` → `"25"` |
| `bool()` | Boolean-এ convert করে | `bool(1)` → `True` |
| `list()` | List তৈরি করে | `list("cat")` → `['c', 'a', 't']` |
| `tuple()` | Tuple তৈরি করে | `tuple([1, 2])` → `(1, 2)` |
| `set()` | Set তৈরি করে | `set([1, 1, 2])` → `{1, 2}` |

Set-এর output-এর element order নির্দিষ্ট নয়। একই element একাধিকবার থাকলে set-এ সেটি একবারই থাকে।

এই chapter-এর পরবর্তী topic-গুলোতে conversion function-গুলো আরও বিস্তারিত শিখব।

## 5. Using `int()` with User Input

`int()` ব্যবহার করে উপযুক্ত input-কে integer-এ convert করা যায়।

### Example: Taking Age

```python
age = int(input("Enter your age: "))

print(age)
print(type(age))
```

Sample Interaction:

```text
Enter your age: 21
21
<class 'int'>
```

### Example: Adding Two Integers

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

total = a + b

print("Total:", total)
```

Sample Interaction:

```text
Enter first number: 15
Enter second number: 25
Total: 40
```

এখানে `int()` ব্যবহার করার কারণে input-গুলো integer হিসেবে কাজ করছে।

## 6. Using `float()` with User Input

Decimal number নিয়ে কাজ করার জন্য `float()` ব্যবহার করা হয়।

### Example: Taking Price

```python
price = float(input("Enter price: "))

print("Price:", price)
print(type(price))
```

Sample Interaction:

```text
Enter price: 125.75
Price: 125.75
<class 'float'>
```

### Example: Calculating Average

```python
mark1 = float(input("Enter first mark: "))
mark2 = float(input("Enter second mark: "))

average = (mark1 + mark2) / 2

print("Average:", average)
```

Sample Interaction:

```text
Enter first mark: 80
Enter second mark: 91
Average: 85.5
```

`float()` ব্যবহার করার ফলে পূর্ণসংখ্যার মতো input দিলেও সেটি float হিসেবে সংরক্ষিত হয়।

## 7. Using `str()` with User Input and Numbers

`str()` ব্যবহার করে value-কে string-এ convert করা যায়।

এটি তখন কাজে লাগে, যখন numeric value-কে text-এর সঙ্গে যুক্ত করতে চাই।

### Example

```python
age = 22

message = "My age is " + str(age)

print(message)
```

Output:

```text
My age is 22
```

এখানে `age` integer ছিল। `str(age)` এটিকে string-এ convert করেছে।

### Another Example

```python
price = 150

print("Product price: " + str(price))
```

Output:

```text
Product price: 150
```

তবে text ও numeric value একসঙ্গে print করার আরেকটি সহজ উপায় হলো comma ব্যবহার করা:

```python
price = 150

print("Product price:", price)
```

Output:

```text
Product price: 150
```

এক্ষেত্রে `str()` ব্যবহার করা বাধ্যতামূলক নয়।

## 8. Understanding `bool()` Conversion

`bool()` কোনো value-কে `True` অথবা `False`-এ convert করে।

সাধারণভাবে:

- `0`, `0.0`, `""`, `None` এবং empty collection-এর মতো value `False` হয়।
- Non-zero number, non-empty string এবং non-empty collection সাধারণত `True` হয়।

### Example

```python
print(bool(0))
print(bool(1))
print(bool(""))
print(bool("Hello"))
```

Output:

```text
False
True
False
True
```

### Important: Converting Input Directly to `bool()`

```python
answer = bool(input("Enter yes or no: "))

print(answer)
```

User `no` লিখলেও output হবে:

```text
Enter yes or no: no
True
```

কেন?

কারণ `"no"` একটি non-empty string। `bool()` এখানে শব্দটির অর্থ বুঝে না; শুধু string-টি খালি কি না, তা দেখে।

একইভাবে `"False"` string-টিও non-empty, তাই `bool("False")`-এর ফল `True`।

সুতরাং user-এর কাছ থেকে yes/no বা true/false ধরনের উত্তর নিতে চাইলে সরাসরি `bool(input())` ব্যবহার করা সাধারণত সঠিক পদ্ধতি নয়। আগে input-এর text পরীক্ষা করতে হয়।

## 9. Implicit and Explicit Type Conversion

Python-এ type conversion প্রধানত দুইভাবে আলোচনা করা হয়।

### 9.1 Implicit Type Conversion

যখন Python নিজে থেকে প্রয়োজন অনুযায়ী একটি numeric type-কে অন্য numeric type-এ রূপান্তর করে, তখন তাকে implicit type conversion বলে।

Example:

```python
a = 5
b = 2.5

result = a + b

print(result)
print(type(result))
```

Output:

```text
7.5
<class 'float'>
```

এখানে integer `5` এবং float `2.5` যোগ করার সময় Python ফলাফল float হিসেবে তৈরি করেছে।

### 9.2 Explicit Type Conversion

যখন programmer নিজে `int()`, `float()` বা `str()`-এর মতো function ব্যবহার করে conversion করে, তখন তাকে explicit type conversion বলে।

Example:

```python
number = "100"

converted_number = int(number)

print(converted_number)
print(type(converted_number))
```

Output:

```text
100
<class 'int'>
```

এখানে programmer নিজেই conversion করেছে।

### Difference Between Implicit and Explicit Conversion

| বিষয় | Implicit Conversion | Explicit Conversion |
|---|---|---|
| কে করে? | Python নিজে | Programmer |
| কীভাবে? | স্বয়ংক্রিয়ভাবে | Conversion function ব্যবহার করে |
| Example | `5 + 2.5` | `int("100")` |
| প্রয়োজন | Type compatibility অনুযায়ী | Programmer-এর প্রয়োজন অনুযায়ী |

**মনে রাখবে:** User input-কে `int()` বা `float()` দিয়ে convert করা হলো explicit type conversion।

## 10. Type Conversion Errors

সব value-কে সব data type-এ convert করা যায় না। কিছু ক্ষেত্রে error হতে পারে।

### Example 1: Invalid Integer

```python
number = int("hello")
```

এতে `ValueError` হবে, কারণ `"hello"` একটি valid integer representation নয়।

### Example 2: Invalid Float

```python
number = float("abc")
```

এতেও `ValueError` হবে।

### Example 3: Decimal String to Integer

```python
number = int("12.5")
```

এখানেও `ValueError` হবে।

তবে numeric float-কে integer-এ convert করা যায়:

```python
number = int(12.5)

print(number)
```

Output:

```text
12
```

এখানে দশমিক অংশ বাদ পড়ে; এটি সাধারণ rounding নয়।

### Example 4: Empty String to Integer

```python
number = int("")
```

এখানেও `ValueError` হবে।

কারণ empty string কোনো valid integer representation নয়।

### Important Rule

`int()` বা `float()` ব্যবহার করার আগে input-টি সংশ্লিষ্ট conversion-এর জন্য valid কি না, তা বিবেচনা করতে হবে।

## 11. Practical Program: Simple Calculator

নিচের program-এ user-এর কাছ থেকে দুটি সংখ্যা নিয়ে চারটি arithmetic operation করা হয়েছে।

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

print("Addition:", a + b)
print("Subtraction:", a - b)
print("Multiplication:", a * b)

if b != 0:
    print("Division:", a / b)
else:
    print("Division is not possible by zero.")
```

Sample Interaction:

```text
Enter first number: 10
Enter second number: 4
Addition: 14.0
Subtraction: 6.0
Multiplication: 40.0
Division: 2.5
```

এখানে `float()` ব্যবহার করা হয়েছে, তাই পূর্ণসংখ্যা এবং decimal input—দুই ধরনের numeric input-ই নেওয়া যায়।

Division করার আগে দ্বিতীয় সংখ্যাটি zero কি না, সেটিও পরীক্ষা করা হয়েছে।

## 12. Best Practices

1. Calculation-এর জন্য user input নিলে প্রয়োজন অনুযায়ী `int()` বা `float()` ব্যবহার করো।
2. Name, phone number, student ID-এর মতো তথ্য সাধারণত string হিসেবে রাখো।
3. `input()` নিজে numeric conversion করে না—এটি মনে রাখো।
4. `bool(input())` ব্যবহার করে সরাসরি yes/no যাচাই কোরো না।
5. Invalid input দিলে conversion error হতে পারে—এটি মাথায় রাখো।
6. Text ও number একসঙ্গে print করার সময় comma অথবা f-string ব্যবহার করতে পারো।
7. যে data type প্রয়োজন, সেটিই নির্বাচন করো; অকারণে conversion কোরো না।

## 13. Practice Exercises

### Exercise 1: Integer Conversion

User-এর কাছ থেকে একটি পূর্ণসংখ্যা নাও এবং তার type print করো।

### Exercise 2: Float Conversion

User-এর কাছ থেকে একটি decimal number নাও এবং তার সঙ্গে `10` যোগ করে ফল দেখাও।

### Exercise 3: Fix the Program

নিচের code-এ `10` এবং `20` input দিলে যোগফল `1020` আসে। এটিকে ঠিক করো।

```python
a = input("Enter first number: ")
b = input("Enter second number: ")

print(a + b)
```

### Exercise 4: String Conversion

`age = 21` দেওয়া আছে। `str()` ব্যবহার করে নিচের output তৈরি করো:

```text
My age is 21
```

### Exercise 5: Predict the Output

```python
print(bool(""))
print(bool("False"))
print(bool(0))
print(bool(10))
```

### Exercise 6: Find the Error

```python
number = int(input("Enter number: "))
```

User `15.5` লিখলে কী error হবে? কেন?

### Exercise 7: Calculate Total and Average

User-এর কাছ থেকে তিনটি marks নাও। Total ও average হিসাব করে দেখাও।

### Exercise 8: Challenge

User-এর কাছ থেকে product-এর নাম, quantity এবং unit price নাও। Product-এর নাম string হিসেবে এবং quantity ও price উপযুক্ত numeric type-এ রেখে total price হিসাব করো।

## 14. Practice Answer Key

### Answer 1

```python
number = int(input("Enter an integer: "))

print(number)
print(type(number))
```

### Answer 2

```python
number = float(input("Enter a decimal number: "))

print(number + 10)
```

### Answer 3

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print(a + b)
```

### Answer 4

```python
age = 21

message = "My age is " + str(age)

print(message)
```

### Answer 5

```text
False
True
False
True
```

### Answer 6

`ValueError` হবে, কারণ `"15.5"` সরাসরি `int()` দিয়ে convert করা যায় না।

### Answer 7

```python
mark1 = float(input("Enter first mark: "))
mark2 = float(input("Enter second mark: "))
mark3 = float(input("Enter third mark: "))

total = mark1 + mark2 + mark3
average = total / 3

print("Total:", total)
print("Average:", average)
```

### Answer 8

```python
product_name = input("Enter product name: ")
quantity = int(input("Enter quantity: "))
unit_price = float(input("Enter unit price: "))

total_price = quantity * unit_price

print("Product:", product_name)
print("Quantity:", quantity)
print("Unit Price:", unit_price)
print("Total Price:", total_price)
```

## 15. Chapter Summary

- Type Conversion হলো একটি data type থেকে অন্য data type-এ value পরিবর্তন করা।
- `input()` সবসময় string return করে।
- `int()` integer এবং `float()` decimal number-এর জন্য ব্যবহৃত হয়।
- `str()` value-কে string-এ convert করে।
- `bool()` value-এর truth value নির্ধারণ করে।
- Implicit conversion Python নিজে করে; explicit conversion programmer করে।
- Invalid conversion-এর কারণে `ValueError` হতে পারে।
- সঠিক data type নির্বাচন করলে calculation ও program-এর logic ঠিক রাখা সহজ হয়।

## 16. Self-Assessment Checklist

- [ ] Type Conversion কী, তা ব্যাখ্যা করতে পারি।
- [ ] `input()` থেকে পাওয়া value convert করতে পারি।
- [ ] `int()`, `float()`, `str()` এবং `bool()`-এর ব্যবহার বুঝি।
- [ ] Implicit ও explicit conversion-এর পার্থক্য বুঝি।
- [ ] String concatenation এবং numeric addition আলাদা করতে পারি।
- [ ] সাধারণ conversion error-এর কারণ শনাক্ত করতে পারি।
- [ ] User input ব্যবহার করে calculation program লিখতে পারি।

**Next Topic:** `12_Taking_Integer_and_Float_Input.md` — এখানে integer ও float input নেওয়ার নিয়ম, তাদের পার্থক্য এবং বাস্তব উদাহরণ আরও বিস্তারিতভাবে শিখব।