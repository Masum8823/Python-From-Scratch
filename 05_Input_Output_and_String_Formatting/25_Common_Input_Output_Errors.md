# 25. Common Input/Output Errors in Python

## 1. Introduction

Python-এ user input নেওয়া এবং output দেখানো সহজ। তবে data type, conversion, formatting কিংবা input-এর সঠিক format নিয়ে ভুল হলে program error দিতে পারে অথবা ভুল result দেখাতে পারে।

এই chapter-এ আমরা শিখব:

- `input()`-এর সাধারণ ভুল
- `print()` ও string concatenation-এর ভুল
- Type conversion errors
- Multiple input-এর ভুল
- String formatting errors
- Division by zero ও invalid input
- Error handling-এর basic পদ্ধতি

## 2. Forgetting That `input()` Returns a String

Python-এর `input()` function user-এর input-কে string হিসেবে return করে।

### Incorrect Example

```python
age = input("Enter your age: ")

print(age + 5)
```

User input:

```text
20
```

এখানে `age` হলো `"20"`—একটি string। String-এর সঙ্গে integer যোগ করায় `TypeError` হবে।

### Correct Example

```python
age = int(input("Enter your age: "))

print(age + 5)
```

User input:

```text
20
```

Output:

```text
25
```

**মনে রাখবে:** Numeric calculation করার আগে প্রয়োজন অনুযায়ী `int()` বা `float()` ব্যবহার করো।

## 3. Forgetting Type Conversion

শুধু input নেওয়া যথেষ্ট নয়; input-এর data type-ও বিবেচনা করতে হবে।

### Incorrect Example

```python
first = input("Enter first number: ")
second = input("Enter second number: ")

print(first + second)
```

User input:

```text
10
20
```

Output:

```text
1020
```

কারণ `+` এখানে দুইটি string concatenate করেছে।

### Correct Example

```python
first = int(input("Enter first number: "))
second = int(input("Enter second number: "))

print(first + second)
```

User input:

```text
10
20
```

Output:

```text
30
```

যদি decimal number প্রয়োজন হয়, তাহলে `float()` ব্যবহার করতে পারো।

## 4. Mixing Strings and Numbers

Python-এ সাধারণ string concatenation-এর সময় string ও integer সরাসরি `+` দিয়ে যুক্ত করা যায় না।

### Incorrect Example

```python
age = 22

print("My age is " + age)
```

এটি `TypeError` তৈরি করবে।

### Correct Method 1: Using Commas

```python
age = 22

print("My age is", age)
```

Output:

```text
My age is 22
```

### Correct Method 2: Using `str()`

```python
age = 22

print("My age is " + str(age))
```

Output:

```text
My age is 22
```

### Correct Method 3: Using an f-String

```python
age = 22

print(f"My age is {age}")
```

Output:

```text
My age is 22
```

**Recommendation:** সাধারণত f-string সবচেয়ে পরিষ্কার পদ্ধতি।

## 5. `ValueError` During Type Conversion

যখন string-কে number-এ convert করার চেষ্টা করা হয় কিন্তু string-টি উপযুক্ত numeric representation নয়, তখন `ValueError` হতে পারে।

### Incorrect Example

```python
age = int("twenty")
```

এখানে `"twenty"`-কে integer-এ convert করা যায় না।

### Another Example

```python
price = float("ten taka")
```

এখানেও `ValueError` হবে।

### Correct Method: Validate or Handle the Error

```python
try:
    age = int(input("Enter your age: "))
    print(f"Age: {age}")
except ValueError:
    print("Please enter a valid whole number.")
```

যদি user `abc` লেখে, program error দিয়ে বন্ধ না হয়ে message দেখাবে।

**মনে রাখবে:** `ValueError` সাধারণত বোঝায় value-এর format বা content প্রত্যাশিত ধরনের নয়।

## 6. Using `int()` for Decimal Text

`int()` দিয়ে `"12.5"`-এর মতো decimal text সরাসরি convert করা যায় না।

### Incorrect Example

```python
number = int("12.5")
```

এটি `ValueError` দেবে।

### Correct Method

```python
number = float("12.5")

print(number)
```

Output:

```text
12.5
```

যদি integer দরকার হয়, তাহলে conversion-এর নিয়ম বুঝে কাজ করো:

```python
number = int(float("12.5"))

print(number)
```

Output:

```text
12
```

এখানে `int()` দশমিক অংশ বাদ দিয়েছে; এটি rounding করেনি।

## 7. Taking Multiple Inputs Incorrectly

একই লাইনে একাধিক input নিতে চাইলে `split()` ও unpacking ব্যবহার করা যায়।

### Incorrect Example

```python
first, second = input("Enter two numbers: ")
```

User input:

```text
10 20
```

এখানে `input()` পুরো `"10 20"` string return করে। সেটিকে সরাসরি unpack করলে character অনুযায়ী unpacking করার চেষ্টা হবে, ফলে এখানে `ValueError` হবে।

### Correct Example

```python
first, second = input("Enter two numbers: ").split()

first = int(first)
second = int(second)

print(first + second)
```

User input:

```text
10 20
```

Output:

```text
30
```

### Shorter Version

```python
first, second = map(int, input().split())

print(first + second)
```

এখানে `split()` input-কে আলাদা string-এ ভাগ করে এবং `map(int, ...)` প্রতিটি value-কে integer-এ convert করে।

## 8. Wrong Number of Inputs

Unpacking করার সময় variable-এর সংখ্যা এবং input value-এর সংখ্যা মিলতে হবে।

### Incorrect Example

```python
a, b, c = input().split()
```

User input:

```text
10 20
```

এখানে তিনটি variable থাকলেও input-এ দুটি value আছে। তাই `ValueError` হবে।

### Correct Example

```python
a, b = input().split()

print(a, b)
```

User input:

```text
10 20
```

Output:

```text
10 20
```

**মনে রাখবে:** Unpacking করার সময় value-এর সংখ্যা ঠিক রাখো।

## 9. Forgetting to Use `split()`

`input().split()` ছাড়া এক লাইনে দেওয়া multiple values সাধারণত আলাদা হবে না।

### Example

```python
data = input("Enter two numbers: ")

print(data)
print(type(data))
```

User input:

```text
10 20
```

Output:

```text
10 20
<class 'str'>
```

`data` একটি string; এর মধ্যে space থাকলেও এটি automatically দুটি number হয়ে যায় না।

### Correct Example

```python
data = input("Enter two numbers: ").split()

print(data)
```

User input:

```text
10 20
```

Output:

```text
['10', '20']
```

এখন প্রতিটি value আলাদাভাবে access ও convert করা যায়।

## 10. Using `split()` with the Wrong Separator

`split()`-এ ভুল separator দিলে input প্রত্যাশিতভাবে ভাগ নাও হতে পারে।

### Example

```python
data = "10,20,30"

print(data.split())
```

Output:

```text
['10,20,30']
```

Default `split()` whitespace দিয়ে ভাগ করে। এখানে comma আছে, তাই string-টি একটিই element হিসেবে রয়েছে।

### Correct Example

```python
data = "10,20,30"

print(data.split(","))
```

Output:

```text
['10', '20', '30']
```

Comma-separated numeric values convert করতে:

```python
numbers = list(map(int, input().split(",")))

print(numbers)
```

Input:

```text
10,20,30
```

Output:

```text
[10, 20, 30]
```

## 11. Forgetting the `sep` and `end` Difference

`sep` ও `end`-এর কাজ আলাদা।

- `sep` একই `print()` call-এর একাধিক value-এর মাঝখানে বসে।
- `end` প্রতিটি `print()` call-এর শেষে বসে।

### Example

```python
print("A", "B", "C", sep="-", end="!")
print("Python")
```

Output:

```text
A-B-C!Python
```

এখানে `sep="-"` value-গুলোর মাঝে hyphen বসিয়েছে। `end="!"` প্রথম `print()`-এর শেষে newline-এর বদলে `!` বসিয়েছে।

### Common Mistake

```python
print("A", "B", end="-")
print("C")
```

Output:

```text
A B-C
```

`end="-"` শুধু প্রথম `print()`-এর শেষে কাজ করেছে; `"A"` ও `"B"`-এর মাঝে নয়।

## 12. Forgetting Quotes Around Strings

Python-এ string লিখতে quotes প্রয়োজন।

### Incorrect Example

```python
print(Hello)
```

যদি `Hello` নামে কোনো variable define করা না থাকে, তাহলে `NameError` হবে।

### Correct Example

```python
print("Hello")
```

Output:

```text
Hello
```

যদি variable ব্যবহার করতে চাও, তাহলে আগে সেটি define করো:

```python
message = "Hello"

print(message)
```

Output:

```text
Hello
```

## 13. Incorrect String Formatting

f-string-এর braces-এর মধ্যে variable বা valid expression লিখতে হয়।

### Incorrect Example

```python
name = "Masum"

print("Hello, {name}")
```

Output:

```text
Hello, {name}
```

এখানে string-টি f-string নয়, তাই `{name}` literal text হিসেবেই দেখানো হয়েছে।

### Correct Example

```python
name = "Masum"

print(f"Hello, {name}")
```

Output:

```text
Hello, Masum
```

**মনে রাখবে:** Variable interpolate করতে string-এর আগে `f` লিখতে হবে।

## 14. Using Wrong Braces or Format Specifiers

String formatting-এ ভুল placeholder বা format specification ব্যবহার করলে error হতে পারে।

### Example: Invalid Format Type

```python
number = 12.5

# print(f"{number:d}")
```

এখানে `d` integer format, কিন্তু `number` float। এটি `ValueError` দিতে পারে।

Correct version:

```python
number = 12.5

print(f"{number:.1f}")
```

Output:

```text
12.5
```

### Example: Literal Curly Braces

f-string-এ literal curly braces দেখাতে double braces ব্যবহার করতে হয়।

```python
name = "Masum"

print(f"{{Name: {name}}}")
```

Output:

```text
{Name: Masum}
```

## 15. Division by Zero

দুইটি number দিয়ে division করার সময় divisor শূন্য হলে `ZeroDivisionError` হয়।

### Incorrect Example

```python
a = 10
b = 0

print(a / b)
```

### Correct Example

```python
a = 10
b = 0

if b != 0:
    print(a / b)
else:
    print("Cannot divide by zero.")
```

Output:

```text
Cannot divide by zero.
```

Input নিয়ে calculation করার সময়ও divisor শূন্য কি না, তা check করা গুরুত্বপূর্ণ।

## 16. Empty Input and Whitespace

User শুধু Enter চাপলে `input()` একটি empty string (`""`) return করে। Space দেওয়া হলে string-টি empty না হলেও `.strip()` করার পরে empty হতে পারে।

### Example

```python
name = input("Enter your name: ")

if not name.strip():
    print("Name cannot be empty.")
else:
    print(f"Hello, {name.strip()}!")
```

Input:

```text
   [শুধু spaces দিয়ে Enter]
```

Output:

```text
Name cannot be empty.
```

`.strip()` string-এর শুরু ও শেষের whitespace সরায়। এটি original string পরিবর্তন করে না; নতুন string return করে।

## 17. Confusing `print()` with `return`

`print()` কোনো value screen-এ দেখায়, কিন্তু `return` function থেকে value ফেরত দেয়।

### Example

```python
def add(a, b):
    print(a + b)

result = add(10, 20)

print(result)
```

Output:

```text
30
None
```

কারণ `add()` function কোনো explicit `return` statement ব্যবহার করেনি। তাই function call-এর result হলো `None`।

### Correct Example

```python
def add(a, b):
    return a + b

result = add(10, 20)

print(result)
```

Output:

```text
30
```

**মনে রাখবে:**

- `print()` → output দেখায়।
- `return` → function-এর result ফেরত দেয়।

## 18. Confusing `input()` Prompt with the Output

`input()`-এর prompt user-কে কী লিখতে হবে তা জানায়। এটি user-এর input-এর সঙ্গে automatically যোগ হয়ে variable-এর value হয় না।

### Example

```python
name = input("Enter your name: ")

print(name)
```

User input:

```text
Masum
```

Console-এ দেখা যাবে:

```text
Enter your name: Masum
Masum
```

প্রথম লাইনে prompt ও user-এর input দেখা যাচ্ছে। দ্বিতীয় লাইনে `print(name)` stored value দেখাচ্ছে।

## 19. Handling Invalid Input Safely

User সবসময় সঠিক input দেবে—এমন নিশ্চয়তা নেই। তাই input conversion-এর সময় `try-except` ব্যবহার করা যায়।

### Example: Integer Validation

```python
try:
    age = int(input("Enter your age: "))

    if age < 0:
        print("Age cannot be negative.")
    else:
        print(f"Your age is {age}.")

except ValueError:
    print("Please enter a valid integer.")
```

User `abc` লিখলে output হবে:

```text
Please enter a valid integer.
```

এখানে `try` block-এ conversion করা হয়েছে এবং conversion ব্যর্থ হলে `except ValueError` কাজ করেছে।

**Best practice:** প্রয়োজনীয় নির্দিষ্ট exception handle করো। অকারণে bare `except:` ব্যবহার করা উচিত নয়।

## 20. Practical Program: Safe Calculator

নিচের program দুটি number input নিয়ে তাদের যোগফল বের করে। Invalid input এলে error message দেখায়।

```python
try:
    first = float(input("Enter first number: "))
    second = float(input("Enter second number: "))

    total = first + second

    print(f"Sum: {total:.2f}")

except ValueError:
    print("Please enter valid numbers.")
```

Example input:

```text
Enter first number: 10.5
Enter second number: 20.5
```

Output:

```text
Sum: 31.00
```

এখানে `float()` decimal input নিতে পারে এবং `try-except` invalid numeric input handle করে।

## 21. Practical Program: Average Calculator with Validation

```python
try:
    marks_text = input("Enter three marks separated by spaces: ")
    parts = marks_text.split()

    if len(parts) != 3:
        print("Please enter exactly three marks.")
    else:
        marks = list(map(float, parts))

        if any(mark < 0 or mark > 100 for mark in marks):
            print("Each mark must be between 0 and 100.")
        else:
            average = sum(marks) / len(marks)
            print(f"Average: {average:.2f}")

except ValueError:
    print("Please enter numeric marks.")
```

Example input:

```text
80 90 85
```

Output:

```text
Average: 85.00
```

এই program-এ:

- `split()` input-কে আলাদা value-তে ভাগ করেছে।
- `len(parts)` দিয়ে তিনটি value আছে কি না check করা হয়েছে।
- `map(float, parts)` প্রতিটি value-কে float-এ convert করেছে।
- `any()` দিয়ে marks-এর range যাচাই করা হয়েছে।
- `try-except` invalid numeric input handle করেছে।

## 22. Common Errors Quick Reference

| Error | সাধারণ কারণ | সমাধান |
|---|---|---|
| `ValueError` | Invalid value conversion | Input validate করো বা `try-except` ব্যবহার করো |
| `TypeError` | Incompatible data types | প্রয়োজনমতো conversion করো |
| `IndexError` | Invalid sequence index বা positional format argument | সঠিক index ও argument count ব্যবহার করো |
| `KeyError` | Dictionary key বা named format field নেই | সঠিক key/name ব্যবহার করো |
| `NameError` | Undefined variable | Variable define করো বা spelling ঠিক করো |
| `ZeroDivisionError` | শূন্য দিয়ে division | Division-এর আগে divisor check করো |

Error-এর সঠিক কারণ বুঝতে traceback-এর শেষের অংশ এবং সংশ্লিষ্ট code line দেখো।

## 23. Practice Exercises

### Exercise 1: Input Conversion

User-এর কাছ থেকে দুটি integer নিয়ে যোগফল দেখাও।

### Exercise 2: String and Integer

নিচের code-এ error কেন হবে? সঠিকভাবে লিখো।

```python
age = 20
print("Age: " + age)
```

### Exercise 3: Multiple Inputs

একই লাইনে তিনটি number নিয়ে তাদের sum দেখাও।

### Exercise 4: Invalid Numeric Input

`try-except` ব্যবহার করে invalid integer input handle করো।

### Exercise 5: Division by Zero

দুটি number input নিয়ে ভাগফল বের করো। দ্বিতীয় number শূন্য হলে error message দেখাও।

### Exercise 6: Empty Name

User-এর name input নাও এবং `.strip()` দিয়ে empty বা whitespace-only input reject করো।

### Exercise 7: String Formatting

নিচের code-এ variable-এর নাম কেন print হচ্ছে? সঠিক করো।

```python
name = "Masum"
print("Hello, {name}")
```

### Exercise 8: `print()` vs `return`

নিচের code-এর output কী হবে এবং কেন?

```python
def multiply(a, b):
    print(a * b)

result = multiply(4, 5)
print(result)
```

### Exercise 9: Output Prediction

```python
first = input()
second = input()

print(first + second)
print(int(first) + int(second))
```

Input:

```text
12
8
```

### Exercise 10: Mini Challenge

একটি program লেখো, যা user-এর কাছ থেকে তিনটি marks নেবে, valid range `0` থেকে `100` check করবে এবং average দুই decimal places-এ দেখাবে।

## 24. Practice Answer Key

### Answer 1

```python
a = int(input("Enter first integer: "))
b = int(input("Enter second integer: "))

print(a + b)
```

### Answer 2

```python
age = 20

print("Age: " + str(age))
```

অথবা:

```python
print(f"Age: {age}")
```

### Answer 3

```python
a, b, c = map(int, input("Enter three numbers: ").split())

print(a + b + c)
```

### Answer 4

```python
try:
    number = int(input("Enter an integer: "))
    print(number)
except ValueError:
    print("Invalid integer.")
```

### Answer 5

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

if b == 0:
    print("Cannot divide by zero.")
else:
    print(f"Result: {a / b}")
```

### Answer 6

```python
name = input("Enter your name: ").strip()

if name:
    print(f"Hello, {name}!")
else:
    print("Name cannot be empty.")
```

### Answer 7

```python
name = "Masum"

print(f"Hello, {name}")
```

### Answer 8

Output:

```text
20
None
```

কারণ function-টি product print করেছে, কিন্তু value `return` করেনি।

### Answer 9

Output:

```text
128
20
```

প্রথম লাইনে string concatenation হয়েছে। দ্বিতীয় লাইনে integer addition হয়েছে।

### Answer 10

```python
try:
    parts = input("Enter three marks: ").split()

    if len(parts) != 3:
        print("Enter exactly three marks.")
    else:
        marks = list(map(float, parts))

        if any(mark < 0 or mark > 100 for mark in marks):
            print("Marks must be between 0 and 100.")
        else:
            average = sum(marks) / 3
            print(f"Average: {average:.2f}")

except ValueError:
    print("Please enter valid numeric marks.")
```

## 25. Chapter Summary

- `input()` সবসময় string return করে।
- Numeric calculation-এর আগে প্রয়োজন অনুযায়ী `int()` বা `float()` ব্যবহার করতে হয়।
- String ও number সরাসরি concatenate করলে `TypeError` হতে পারে।
- Invalid conversion-এর কারণে `ValueError` হতে পারে।
- Multiple input-এর জন্য `split()` এবং প্রয়োজন অনুযায়ী `map()` ব্যবহার করা যায়।
- Unpacking-এর সময় variable ও value-এর সংখ্যা মিলতে হবে।
- `sep` value-গুলোর মাঝখানে এবং `end` `print()` call-এর শেষে কাজ করে।
- f-string-এর জন্য string-এর আগে `f` দিতে হয়।
- Division-এর আগে zero divisor check করা উচিত।
- `print()` output দেখায়, আর `return` function থেকে value ফেরত দেয়।
- `try-except` ব্যবহার করে প্রত্যাশিত input error handle করা যায়।

## 26. Self-Assessment Checklist

- [ ] `input()`-এর return type বুঝি।
- [ ] String থেকে integer ও float conversion করতে পারি।
- [ ] `ValueError` ও `TypeError`-এর পার্থক্য বুঝি।
- [ ] Multiple input নিয়ে calculation করতে পারি।
- [ ] Invalid input handle করতে পারি।
- [ ] Empty input ও whitespace check করতে পারি।
- [ ] `print()` এবং `return`-এর পার্থক্য বুঝি।
- [ ] Percentage ও number formatting-এ common mistakes এড়াতে পারি।
- [ ] ছোট calculator বা average calculator তৈরি করতে পারি।

**Next Topic:** `26_Practical_Input_Output_Programs.md` — এখানে input, output, validation ও formatting ব্যবহার করে কয়েকটি পূর্ণাঙ্গ beginner-friendly program তৈরি করব।