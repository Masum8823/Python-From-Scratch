# 19. Basic Input and Output in Python

## 1. Introduction

Programming-এ **Input** হলো program-এ data দেওয়া, আর **Output** হলো program-এর result বা information দেখানো।

Python-এ basic input ও output-এর জন্য প্রধানত দুটি built-in function ব্যবহার করা হয়:

- `input()` — user-এর কাছ থেকে input নেওয়ার জন্য।
- `print()` — screen-এ output দেখানোর জন্য।

উদাহরণ:

```python
name = input("Enter your name: ")

print("Hello", name)
```

ধরি, user input দিয়েছে:

```text
Enter your name: Masum
```

Output:

```text
Hello Masum
```

এখানে `input()` নাম নিয়েছে এবং `print()` greeting দেখিয়েছে।

## 2. What Is Input?

Input হলো program-এর বাইরে থেকে data গ্রহণ করা।

এই data user keyboard দিয়ে দিতে পারে অথবা file, database, API কিংবা অন্য কোনো source থেকে আসতে পারে।

Beginner level-এ আমরা keyboard input নিয়ে কাজ করব।

উদাহরণ:

```python
name = input("Enter your name: ")

print(name)
```

এখানে:

1. `input()` user-কে prompt দেখায়।
2. User keyboard দিয়ে নাম লেখে।
3. Enter চাপলে input গ্রহণ করা হয়।
4. Input-এর result `name` variable-এ রাখা হয়।
5. `print()` নামটি output হিসেবে দেখায়।

## 3. Using the `input()` Function

Python-এর `input()` function keyboard থেকে একটি line of text গ্রহণ করে।

Syntax:

```python
input(prompt)
```

এখানে `prompt` হলো optional message, যা user-কে কী লিখতে হবে তা জানায়।

### Example 1: Without a Prompt

```python
name = input()

print(name)
```

User input:

```text
Masum
```

Output:

```text
Masum
```

### Example 2: With a Prompt

```python
name = input("Enter your name: ")

print(name)
```

User input:

```text
Enter your name: Masum
```

Output:

```text
Masum
```

Prompt-এর message input-এর অংশ নয়। এটি শুধু user-কে নির্দেশনা দেয়।

### Example 3: Multiple Inputs

```python
name = input("Enter your name: ")
department = input("Enter your department: ")

print("Name:", name)
print("Department:", department)
```

User input:

```text
Enter your name: Masum
Enter your department: CSE
```

Output:

```text
Name: Masum
Department: CSE
```

## 4. Important Rule: `input()` Returns a String

Python-এ `input()` function-এর result সবসময় `str` type-এর হয়।

User যদি number লেখে, তবুও input প্রথমে string হিসেবে পাওয়া যায়।

উদাহরণ:

```python
age = input("Enter your age: ")

print(age)
print(type(age))
```

User input:

```text
Enter your age: 22
```

Output:

```text
22
<class 'str'>
```

এখানে `22` দেখতে number-এর মতো হলেও এটি string `"22"`।

এ কারণে arithmetic operation করার আগে প্রয়োজন অনুযায়ী type conversion করতে হয়।

## 5. Taking Integer Input

Integer input নেওয়ার জন্য `input()`-এর result-কে `int()` দিয়ে convert করা যায়।

উদাহরণ:

```python
age = int(input("Enter your age: "))

print(age)
print(type(age))
```

User input:

```text
Enter your age: 22
```

Output:

```text
22
<class 'int'>
```

এখানে:

1. `input()` text গ্রহণ করেছে।
2. `int()` text-কে integer-এ convert করেছে।
3. Converted value `age`-এ assign হয়েছে।

### Practical Example: Add Two Numbers

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

result = a + b

print("Sum:", result)
```

User input:

```text
Enter first number: 10
Enter second number: 20
```

Output:

```text
Sum: 30
```

এখানে `a` ও `b` integer হওয়ায় `+` arithmetic addition করেছে।

## 6. Taking Floating-Point Input

Decimal number গ্রহণ করতে `float()` ব্যবহার করা যায়।

উদাহরণ:

```python
price = float(input("Enter product price: "))

print("Price:", price)
print(type(price))
```

User input:

```text
Enter product price: 250.50
```

Output:

```text
Price: 250.5
<class 'float'>
```

Python floating-point value display করার সময় প্রয়োজন অনুযায়ী trailing zero বাদ দিতে পারে।

### Example: Calculate Average

```python
mark1 = float(input("Enter first mark: "))
mark2 = float(input("Enter second mark: "))
mark3 = float(input("Enter third mark: "))

average = (mark1 + mark2 + mark3) / 3

print("Average:", average)
```

User input:

```text
Enter first mark: 80
Enter second mark: 85
Enter third mark: 90
```

Output:

```text
Average: 85.0
```

## 7. Taking String Input

Text input-এর জন্য `input()` সরাসরি ব্যবহার করা যায়।

```python
student_name = input("Enter student name: ")
department = input("Enter department: ")

print("Student:", student_name)
print("Department:", department)
```

এখানে `student_name` এবং `department`—দুটি variable-ই string store করবে।

### Removing Extra Spaces

User input-এর শুরু ও শেষে অতিরিক্ত whitespace থাকলে `strip()` ব্যবহার করা যায়।

```python
name = input("Enter your name: ").strip()

print("Name:", name)
```

যদি user input দেয়:

```text
  Masum
```

তাহলে `strip()`-এর পরে string হবে:

```text
Masum
```

`strip()` মাঝখানের spaces সরায় না।

## 8. Taking Boolean Input

Python-এর `input()` সরাসরি Boolean value দেয় না। User যদি `True` লেখে, result হবে string `"True"`।

```python
answer = input("Are you a student? ")

print(answer)
print(type(answer))
```

User input:

```text
Are you a student? True
```

Output:

```text
True
<class 'str'>
```

### A Common Mistake

নিচের code-টি সঠিক Boolean conversion নয়:

```python
answer = bool(input("Enter True or False: "))
```

কারণ `bool()` non-empty string-কে `True` হিসেবে বিবেচনা করে।

উদাহরণ:

```python
print(bool("False"))
print(bool(""))
```

Output:

```text
True
False
```

প্রথম result `True`, কারণ `"False"` একটি non-empty string।

### A Better Method

যদি user-এর কাছ থেকে `yes` বা `no` নেওয়া হয়:

```python
answer = input("Are you a student? ").strip().lower()

if answer == "yes":
    is_student = True
elif answer == "no":
    is_student = False
else:
    is_student = None

print(is_student)
```

User input:

```text
Are you a student? YES
```

Output:

```text
True
```

এখানে `.strip().lower()` input-এর পাশের whitespace সরিয়ে lowercase করেছে। Invalid input-এর ক্ষেত্রে `None` রাখা হয়েছে।

## 9. What Is Type Conversion?

একটি data type-কে অন্য data type-এ পরিবর্তন করাকে **Type Conversion** বা **Type Casting** বলা হয়।

Input নেওয়ার সময় এটি খুব গুরুত্বপূর্ণ।

উদাহরণ:

```python
number = input("Enter a number: ")

print(type(number))

number = int(number)

print(type(number))
```

User input:

```text
Enter a number: 25
```

Output:

```text
<class 'str'>
<class 'int'>
```

### Common Conversion Functions

| Function | Purpose | Example |
|---|---|---|
| `int()` | Integer-এ convert করে | `int("25")` → `25` |
| `float()` | Float-এ convert করে | `float("3.5")` → `3.5` |
| `str()` | String-এ convert করে | `str(100)` → `"100"` |
| `bool()` | Truth value নির্ধারণ করে | `bool(1)` → `True` |

### Important Examples

```python
print(int("25"))
print(float("3.5"))
print(str(100))
print(bool(0))
print(bool(1))
```

Output:

```text
25
3.5
100
False
True
```

`int("25")` কাজ করে, কিন্তু `int("hello")` করলে `ValueError` হবে।

Type conversion-এর আরও বিস্তারিত আলোচনা পরবর্তী Data Types ও Type Conversion chapter-এ করা হবে।

## 10. What Is Output?

Output হলো program-এর result বা information user-এর কাছে প্রদর্শন করা।

Python-এ basic output-এর জন্য `print()` function ব্যবহার করা হয়।

উদাহরণ:

```python
print("Hello Python")
print(100)
print(10 + 20)
```

Output:

```text
Hello Python
100
30
```

`print()` string, number, variable এবং expression-এর result দেখাতে পারে।

## 11. Using `print()` with Variables

Variable-এর value দেখানোর জন্য `print()` ব্যবহার করা হয়।

```python
name = "Masum"
age = 22
cgpa = 3.95

print(name)
print(age)
print(cgpa)
```

Output:

```text
Masum
22
3.95
```

### Printing Multiple Values

```python
name = "Masum"
department = "CSE"
age = 22

print(name, department, age)
```

Output:

```text
Masum CSE 22
```

একাধিক value comma দিয়ে দিলে `print()` defaultভাবে তাদের মধ্যে একটি space রাখে।

### Using `sep`

`sep` parameter দিয়ে value-গুলোর মাঝের separator পরিবর্তন করা যায়।

```python
print("2026", "10", "15", sep="-")
```

Output:

```text
2026-10-15
```

### Using `end`

`end` parameter দিয়ে `print()`-এর শেষে কী থাকবে তা নির্ধারণ করা যায়। Default value হলো newline (`\n`)।

```python
print("Hello", end=" ")
print("Python")
```

Output:

```text
Hello Python
```

এখানে প্রথম `print()`-এর পরে নতুন line না দিয়ে space দেওয়া হয়েছে।

## 12. Formatted Output with f-Strings

একটি string-এর মধ্যে variable বা expression-এর value সুন্দরভাবে দেখানোর জন্য f-string ব্যবহার করা যায়।

উদাহরণ:

```python
name = "Masum"
age = 22

print(f"My name is {name} and I am {age} years old.")
```

Output:

```text
My name is Masum and I am 22 years old.
```

### Using Expressions

```python
a = 10
b = 20

print(f"Sum = {a + b}")
```

Output:

```text
Sum = 30
```

### Formatting Decimal Places

```python
cgpa = 3.9567

print(f"CGPA: {cgpa:.2f}")
```

Output:

```text
CGPA: 3.96
```

এখানে `.2f` floating-point value-কে দশমিকের পরে দুই ঘর পর্যন্ত দেখায়।

f-string-এর বিস্তারিত আলোচনা `05_Print_Function_and_Output.md` ফাইলে রয়েছে।

## 13. Complete Input-Process-Output Example

অনেক beginner program-কে তিনটি ধাপে বোঝা যায়:

1. **Input:** Data গ্রহণ করা।
2. **Process:** Data নিয়ে calculation বা operation করা।
3. **Output:** Result দেখানো।

এই pattern-কে IPO model বলা হয়।

### Example: Calculate Rectangle Area

```python
length = float(input("Enter length: "))
width = float(input("Enter width: "))

area = length * width

print(f"Rectangle area: {area}")
```

User input:

```text
Enter length: 10
Enter width: 5
```

Output:

```text
Rectangle area: 50.0
```

এখানে:

| Step | Operation |
|---|---|
| Input | `length` এবং `width` নেওয়া |
| Process | `length * width` |
| Output | Rectangle-এর area দেখানো |

## 14. Handling Invalid Input

User সবসময় সঠিক input দেবে, এমন নিশ্চয়তা নেই।

উদাহরণ:

```python
age = int(input("Enter your age: "))
```

User যদি `twenty` লেখে, তাহলে `int()` সেটিকে integer-এ convert করতে পারবে না। ফলে `ValueError` হবে।

### Using `try` and `except`

```python
try:
    age = int(input("Enter your age: "))
    print("Your age:", age)
except ValueError:
    print("Please enter a valid integer.")
```

User input:

```text
Enter your age: twenty
```

Output:

```text
Please enter a valid integer.
```

এখানে `try` block-এ conversion করা হয়েছে এবং conversion ব্যর্থ হলে `except` block execute হয়েছে।

Exception handling-এর বিস্তারিত আলোচনা `14_Exception_Handling.md` নামে নির্ধারিত chapter file-এ থাকবে।

## 15. Practical Example: Simple Calculator

```python
num1 = float(input("Enter first number: "))
operator = input("Enter operator (+, -, *, /): ")
num2 = float(input("Enter second number: "))

if operator == "+":
    result = num1 + num2
elif operator == "-":
    result = num1 - num2
elif operator == "*":
    result = num1 * num2
elif operator == "/":
    if num2 != 0:
        result = num1 / num2
    else:
        result = None
        print("Cannot divide by zero.")
else:
    result = None
    print("Invalid operator.")

if result is not None:
    print(f"Result: {result}")
```

User input:

```text
Enter first number: 10
Enter operator (+, -, *, /): *
Enter second number: 5
```

Output:

```text
Result: 50.0
```

এই program-এ আমরা ব্যবহার করেছি:

- `input()` — user input নেওয়ার জন্য।
- `float()` — number conversion-এর জন্য।
- `if`, `elif`, `else` — condition অনুযায়ী operation বেছে নিতে।
- Arithmetic operators — calculation-এর জন্য।
- `print()` — output দেখানোর জন্য।

## 16. Common Mistakes

### Mistake 1: Adding Two Numeric Strings

```python
a = input("Enter first number: ")
b = input("Enter second number: ")

print(a + b)
```

User input:

```text
Enter first number: 10
Enter second number: 20
```

Output:

```text
1020
```

কারণ `a` ও `b` string। তাই `+` concatenation করেছে।

সঠিক:

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print(a + b)
```

Output:

```text
30
```

### Mistake 2: Invalid Integer Conversion

```python
# age = int("twenty")
```

এটি uncomment করলে `ValueError` হবে। কারণ `"twenty"` একটি valid integer representation নয়।

### Mistake 3: Forgetting Quotes Around Text

```python
# name = input("Enter your name: ")
# print(name)
```

সঠিকভাবে লিখলে এটি কাজ করবে।

কিন্তু `print(Hello)` লিখলে Python `Hello`-কে variable বা identifier হিসেবে খুঁজবে। এটি string হিসেবে print করতে হলে `print("Hello")` লিখতে হবে।

### Mistake 4: Incorrect Boolean Conversion

```python
answer = bool("False")
print(answer)
```

Output:

```text
True
```

কারণ `"False"` non-empty string। Text হিসেবে `"True"` বা `"False"` গ্রহণ করলে সেটিকে সরাসরি `bool()`-এ পাঠানো ঠিক নয়।

### Mistake 5: Dividing by Zero

```python
# a = 10
# b = 0
# print(a / b)
```

এটি uncomment করলে `ZeroDivisionError` হবে। Division করার আগে denominator শূন্য কি না যাচাই করতে হবে।

## 17. Practice Exercises

### Exercise 1: Personal Information

User-এর কাছ থেকে নাম, বয়স এবং department নিয়ে সুন্দরভাবে output দেখাও।

Expected output-এর উদাহরণ:

```text
Name: Masum
Age: 22
Department: CSE
```

### Exercise 2: Add Two Numbers

দুটি integer input নিয়ে তাদের sum, difference এবং product দেখাও।

### Exercise 3: Calculate Average

তিনটি subject-এর marks input নিয়ে average হিসাব করো।

### Exercise 4: Temperature Converter

Celsius temperature input নিয়ে Fahrenheit-এ convert করো।

Formula:

```text
Fahrenheit = (Celsius × 9/5) + 32
```

### Exercise 5: Rectangle Area

Length ও width input নিয়ে rectangle-এর area বের করো।

Formula:

```text
Area = Length × Width
```

### Exercise 6: Age in Days

User-এর বয়স বছর হিসেবে input নিয়ে আনুমানিক দিন হিসাব করো। এই exercise-এ প্রতি বছর 365 দিন ধরে নাও।

### Exercise 7: Formatted Output

নাম, department এবং CGPA input নিয়ে একটি f-string ব্যবহার করে এক লাইনে সুন্দরভাবে দেখাও।

### Exercise 8: Simple Calculator

দুটি number এবং একটি operator input নিয়ে যোগ, বিয়োগ, গুণ বা ভাগ করো। Invalid operator এবং division by zero handle করো।

### Exercise 9: Input Type Investigation

```python
value = input("Enter something: ")

print(value)
print(type(value))
```

প্রথমে একটি integer-এর মতো input দাও, তারপর decimal-এর মতো input দাও। দুই ক্ষেত্রেই type কেন `str`, তা ব্যাখ্যা করো।

## 18. Quick Revision

| Function / Concept | Purpose |
|---|---|
| `input()` | User-এর কাছ থেকে text গ্রহণ করে |
| `print()` | Output দেখায় |
| `int()` | Integer conversion |
| `float()` | Floating-point conversion |
| `str()` | String conversion |
| `bool()` | Truth value নির্ধারণ করে |
| `type()` | Value-এর type দেখায় |
| `strip()` | String-এর দুই পাশের whitespace সরায় |
| `sep` | `print()`-এর value-গুলোর মধ্যকার separator |
| `end` | `print()`-এর শেষে কী থাকবে তা নির্ধারণ করে |
| f-string | String-এর মধ্যে value ও expression দেখায় |
| `try` / `except` | সম্ভাব্য error handle করতে সাহায্য করে |

## 19. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Input হলো program-এ data গ্রহণ করা এবং output হলো result দেখানো।
- `input()` keyboard থেকে text গ্রহণ করে।
- `input()`-এর result সবসময় `str` হয়।
- Numeric calculation-এর জন্য প্রয়োজন অনুযায়ী `int()` বা `float()` ব্যবহার করতে হয়।
- `print()` দিয়ে text, variable, একাধিক value এবং expression দেখানো যায়।
- `sep` ও `end` output formatting নিয়ন্ত্রণ করে।
- f-string দিয়ে formatted output তৈরি করা যায়।
- `strip()` user input-এর শুরু ও শেষের whitespace সরাতে সাহায্য করে।
- Invalid input-এর কারণে `ValueError` হতে পারে।
- `try` ও `except` দিয়ে conversion error handle করা যায়।
- IPO model হলো Input, Process এবং Output—এই তিনটি ধাপের একটি সহজ programming pattern।

## 20. Next Topic

পরবর্তী ফাইল: [`20_Understanding_Errors_and_Debugging_Basics.md`](20_Understanding_Errors_and_Debugging_Basics.md)

সেখানে Python-এর error types, error message পড়া, syntax error, runtime error, logical error এবং debugging-এর প্রাথমিক পদ্ধতি শেখা হবে।