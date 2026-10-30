# 27. Type Conversion Errors in Python

## 1. Introduction to Type Conversion Errors

Python-এ Type Conversion হলো একটি data type-এর value-কে অন্য data type-এ রূপান্তর করা।

Conversion করার সময় input ভুল হলে, অথবা কোনো value-কে নির্দিষ্ট type-এ convert করা সম্ভব না হলে error হতে পারে।

Example:

```python
number = int("hello")
```

Output:

```text
ValueError: invalid literal for int() with base 10: 'hello'
```

এখানে `"hello"` একটি String, কিন্তু এটি valid Integer representation নয়। তাই `int()` conversion ব্যর্থ হয়েছে।

Type Conversion-এর error বুঝতে পারলে program debugging এবং user input validation অনেক সহজ হয়।

## 2. Common Types of Conversion Errors

Type conversion-এর সময় সাধারণত যেসব error দেখা যায়:

| Error | কখন হয় |
|---|---|
| `ValueError` | Value-এর format বা content গ্রহণযোগ্য নয় |
| `TypeError` | Value-এর type বা object conversion-এর জন্য উপযুক্ত নয় |
| `OverflowError` | কোনো numeric operation বা conversion-এর result নির্দিষ্ট representation-এর সীমা ছাড়িয়ে যায় |
| `UnicodeDecodeError` | Bytes-কে নির্দিষ্ট encoding দিয়ে decode করা সম্ভব হয় না |

প্রতিটি error-এর কারণ ও সমাধান আলাদা হতে পারে।

## 3. ValueError

`ValueError` হয় যখন function সঠিক ধরনের object পায়, কিন্তু object-এর value গ্রহণযোগ্য নয়।

### 3.1 Invalid Integer Conversion

```python
number = int("hello")
```

এখানে `"hello"` String হলেও এটি Integer হিসেবে convert করা যায় না।

সঠিক উদাহরণ:

```python
number = int("123")

print(number)
print(type(number))
```

Output:

```text
123
<class 'int'>
```

### 3.2 Invalid Float Conversion

```python
number = float("abc")
```

এখানে `"abc"` valid numeric String নয়। তাই `ValueError` হবে।

সঠিক উদাহরণ:

```python
number = float("12.75")

print(number)
```

Output:

```text
12.75
```

### 3.3 Invalid Number Format

```python
number = int("12.5")
```

এখানে `ValueError` হবে, কারণ `int()` decimal point-যুক্ত String `"12.5"`-কে সরাসরি Integer হিসেবে parse করতে পারে না।

যদি decimal number গ্রহণ করতে চাও:

```python
number = float("12.5")

print(number)
```

Output:

```text
12.5
```

আর decimal String থেকে Float-এর মাধ্যমে Integer করতে চাইলে:

```python
number = int(float("12.5"))

print(number)
```

Output:

```text
12
```

এখানে Float থেকে Integer conversion decimal অংশ truncate করে।

**মনে রাখবে:** `int(float("12.5"))` এবং `int("12.5")` এক নয়।

## 4. TypeError

`TypeError` হয় যখন কোনো operation বা function-এর জন্য দেওয়া object-এর type উপযুক্ত নয়।

### 4.1 Converting None to Integer

```python
number = int(None)
```

এখানে `TypeError` হবে, কারণ `None` সরাসরি Integer-এ convert করা যায় না।

### 4.2 Converting Complex to Float

```python
number = float(3 + 2j)
```

এখানেও `TypeError` হবে।

যদি Complex number-এর real part প্রয়োজন হয়:

```python
number = float((3 + 2j).real)

print(number)
```

Output:

```text
3.0
```

তবে imaginary part বাদ দেওয়া তোমার কাজের জন্য সঠিক কি না, তা আগে নিশ্চিত হতে হবে।

### 4.3 Converting a Non-Iterable to List

```python
numbers = list(10)
```

এখানে `TypeError` হবে, কারণ Integer `10` iterable নয়।

যদি Integer-টিকে একটি List-এর element হিসেবে রাখতে চাও:

```python
numbers = [10]

print(numbers)
```

Output:

```text
[10]
```

## 5. OverflowError

`OverflowError` ঘটে যখন কোনো numeric operation-এর result নির্দিষ্ট numeric representation-এর সীমার বাইরে চলে যায়।

তবে Python-এর Integer-এর নির্দিষ্ট fixed-width limit নেই; memory-এর সীমা পর্যন্ত বড় Integer রাখা যায়। তাই বড় Integer তৈরি করলেই সাধারণত `OverflowError` হয় না।

### Example: Converting a Very Large Integer to Float

```python
number = 10 ** 10000
result = float(number)
```

সাধারণ CPython environment-এ এই conversion `OverflowError` তৈরি করতে পারে, কারণ সংখ্যাটি Float-এর finite range-এর বাইরে।

সব numeric operation-এ এই error হবে—এমন নয়। এটি operation ও conversion-এর ওপর নির্ভর করে।

## 6. UnicodeDecodeError

Bytes-কে String-এ decode করার সময় নির্দিষ্ট encoding-এর নিয়মের সঙ্গে data না মিললে `UnicodeDecodeError` হতে পারে।

Example:

```python
data = b"\xff"

text = data.decode("utf-8")
```

এখানে UTF-8 encoding অনুযায়ী `b"\xff"` valid standalone text sequence নয়। তাই decoding ব্যর্থ হবে।

সঠিক উদাহরণ:

```python
data = "Hello".encode("utf-8")
text = data.decode("utf-8")

print(text)
```

Output:

```text
Hello
```

**মনে রাখবে:** Encoding ও decoding-এর সময় সঠিক encoding জানা গুরুত্বপূর্ণ।

## 7. Handling Conversion Errors with try-except

Python-এ `try-except` ব্যবহার করে conversion error handle করা যায়।

### 7.1 Basic Example

```python
text = input("Enter an integer: ")

try:
    number = int(text)
    print("Number:", number)
except ValueError:
    print("Invalid integer input.")
```

Input:

```text
hello
```

Output:

```text
Invalid integer input.
```

এখানে conversion ব্যর্থ হলেও program error message দেখাতে পারে।

### 7.2 Handling Multiple Error Types

যখন বিভিন্ন ধরনের error হওয়ার সম্ভাবনা থাকে, তখন একাধিক `except` block ব্যবহার করা যায়।

```python
value = input("Enter a number: ")

try:
    number = int(value)
    print("Number:", number)
except ValueError:
    print("The value is not a valid integer.")
except TypeError:
    print("The value has an unsupported type.")
```

এখানে `input()` থেকে পাওয়া String-এর ক্ষেত্রে সাধারণত invalid content-এর জন্য `ValueError` হবে। `TypeError` handling দেখানো হয়েছে অন্য ধরনের input object-এর সম্ভাবনা বোঝাতে।

**Best practice:** যে error বাস্তবে ঘটতে পারে, শুধু সেটিই handle করো।

## 8. Validating User Input Before Conversion

Conversion-এর আগে user input যাচাই করলে invalid input-এর সমস্যা কমানো যায়।

তবে সব numeric format শুধু `isdigit()` দিয়ে যাচাই করা যায় না।

### 8.1 Why `isdigit()` Is Not Enough

```python
text = "-25"

print(text.isdigit())
```

Output:

```text
False
```

এখানে `"-25"` একটি valid Integer representation হলেও `isdigit()` `False` return করে, কারণ এতে minus sign রয়েছে।

একইভাবে `"12.5"`-এর জন্যও `isdigit()` `False` হবে।

তাই সাধারণ numeric conversion-এর জন্য `try-except` একটি ভালো পদ্ধতি।

### 8.2 Safe Integer Input

```python
text = input("Enter an integer: ")

try:
    number = int(text)
    print("Valid integer:", number)
except ValueError:
    print("Please enter a valid integer.")
```

এখানে valid Integer হলে result পাওয়া যাবে, অন্যথায় error message দেখাবে।

### 8.3 Safe Float Input

```python
text = input("Enter a decimal number: ")

try:
    number = float(text)
    print("Valid number:", number)
except ValueError:
    print("Please enter a valid number.")
```

এখানে Integer-looking এবং decimal numeric String—দুটিই গ্রহণযোগ্য।

## 9. Creating a Reusable Conversion Function

একই conversion logic বারবার লিখতে না চাইলে function তৈরি করা যায়।

### Example: Safe Integer Conversion

```python
def safe_int(value):
    try:
        return int(value)
    except (ValueError, TypeError):
        return None


print(safe_int("123"))
print(safe_int("hello"))
print(safe_int(None))
```

Output:

```text
123
None
None
```

এখানে:

- Valid input হলে Integer return করে।
- Invalid String বা unsupported type হলে `None` return করে।

**Important:** এই function-এ `None` মানে conversion ব্যর্থ হয়েছে। তাই valid result-এর সঙ্গে failure-এর পার্থক্য বুঝে ব্যবহার করতে হবে।

যদি `None`-ও একটি valid application value হতে পারে, তাহলে failure আলাদাভাবে প্রকাশ করার পদ্ধতি বেছে নেওয়া ভালো।

## 10. The Difference Between int() and float() Conversion Errors

নিচের উদাহরণগুলো লক্ষ করো:

```python
print(int("25"))
print(float("25"))
print(float("25.5"))
```

Output:

```text
25
25.0
25.5
```

কিন্তু:

```python
int("25.5")
```

এটি `ValueError` তৈরি করবে।

অন্যদিকে:

```python
int(float("25.5"))
```

Output:

```text
25
```

কারণ প্রথমে String-টি Float হয়, তারপর Integer conversion-এর সময় fractional part বাদ পড়ে।

**মনে রাখবে:** Conversion-এর আগে input-এর format এবং প্রয়োজনীয় output type বুঝে নিতে হবে।

## 11. Common Mistakes

### 11.1 Using `except` Without a Specific Error

```python
try:
    number = int("abc")
except:
    print("Something went wrong.")
```

এটি কাজ করলেও bare `except` অনেক অপ্রত্যাশিত error-ও ধরে ফেলতে পারে।

আরও ভালো:

```python
try:
    number = int("abc")
except ValueError:
    print("Invalid integer.")
```

প্রয়োজন অনুযায়ী নির্দিষ্ট error handle করো।

### 11.2 Ignoring the Failed Conversion

```python
try:
    number = int(input("Enter an integer: "))
except ValueError:
    print("Invalid input.")

print(number)
```

যদি conversion ব্যর্থ হয়, তাহলে `number` assign নাও হতে পারে। ফলে পরের `print(number)`-এ `NameError` হতে পারে।

সঠিক পদ্ধতি:

```python
try:
    number = int(input("Enter an integer: "))
except ValueError:
    print("Invalid input.")
else:
    print("Number:", number)
```

এখানে `else` block শুধু `try` block সফল হলে execute হবে।

### 11.3 Converting Without Checking Data Loss

```python
number = int(9.99)

print(number)
```

Output:

```text
9
```

এখানে fractional part বাদ গেছে। যদি decimal অংশ গুরুত্বপূর্ণ হয়, তাহলে Integer conversion ব্যবহার করার আগে সতর্ক হতে হবে।

### 11.4 Assuming Every Invalid Input Causes the Same Error

সব conversion failure একই ধরনের error তৈরি করে না।

- Invalid numeric String → সাধারণত `ValueError`
- Unsupported object type → সাধারণত `TypeError`
- Numeric range অতিক্রম করা → কিছু ক্ষেত্রে `OverflowError`
- Invalid text decoding → `UnicodeDecodeError`

Error type বুঝে handle করা উচিত।

## 12. Practical Examples

### Example 1: Calculate Average Safely

```python
try:
    mark1 = float(input("Enter first mark: "))
    mark2 = float(input("Enter second mark: "))
    mark3 = float(input("Enter third mark: "))

    average = (mark1 + mark2 + mark3) / 3

except ValueError:
    print("Please enter valid numeric marks.")

else:
    print(f"Average: {average:.2f}")
```

এখানে যেকোনো একটি input invalid হলে `ValueError` handle হবে। সব input valid হলে average দেখানো হবে।

### Example 2: Positive Integer Validation

```python
try:
    age = int(input("Enter your age: "))

    if age <= 0:
        print("Age must be positive.")
    else:
        print("Age:", age)

except ValueError:
    print("Please enter a valid integer.")
```

এখানে দুটি বিষয় পরীক্ষা করা হচ্ছে:

1. Input Integer-এ convert করা যায় কি না।
2. Converted value positive কি না।

### Example 3: Retry Until Valid Input

```python
while True:
    text = input("Enter an integer: ")

    try:
        number = int(text)
        break
    except ValueError:
        print("Invalid input. Try again.")

print("Accepted number:", number)
```

এখানে user valid Integer না দেওয়া পর্যন্ত program input চাইবে।

### Example 4: Safe Float Conversion Function

```python
def get_float(prompt):
    while True:
        text = input(prompt)

        try:
            return float(text)
        except ValueError:
            print("Invalid number. Please try again.")


price = get_float("Enter product price: ")

print(f"Price: {price:.2f}")
```

এই function invalid input পেলে আবার input নেয় এবং valid Float পেলে result return করে।

## 13. Practice Exercises

### Exercise 1: Identify the Error

নিচের expression-গুলোতে কী error হতে পারে, তা নির্ণয় করো:

```python
int("hello")
float(None)
list(10)
float(2 + 3j)
int("12.5")
```

### Exercise 2: Safe Integer Conversion

একটি program তৈরি করো, যা user-এর কাছ থেকে Integer নেবে। Invalid input হলে error message দেখাবে।

### Exercise 3: Safe Float Conversion

User-এর কাছ থেকে decimal number নাও। Conversion ব্যর্থ হলে `ValueError` handle করো।

### Exercise 4: Find the Bug

নিচের code-এ কী সমস্যা হতে পারে?

```python
try:
    number = int(input("Enter a number: "))
except ValueError:
    print("Invalid input.")

print(number)
```

Code-টি সংশোধন করো।

### Exercise 5: Reusable Function

`safe_float(value)` নামে একটি function তৈরি করো। Valid input হলে Float return করবে; `ValueError` বা `TypeError` হলে `None` return করবে।

### Exercise 6: Positive Number Validation

একটি program তৈরি করো, যা user-এর কাছ থেকে একটি number নেবে। Input valid হতে হবে এবং number positive হতে হবে।

### Exercise 7: Retry Until Valid

একটি `while` loop ব্যবহার করে user-এর কাছ থেকে valid Integer না পাওয়া পর্যন্ত input নিতে থাকো।

### Exercise 8: Mini Project — Simple Marks Calculator

একটি program তৈরি করো, যা তিনটি subject-এর marks input নেবে।

শর্ত:

1. প্রতিটি mark Float-এ convert করতে হবে।
2. Invalid input হলে error message দেখাতে হবে।
3. সব input valid হলে average হিসাব করতে হবে।
4. Average দুই decimal places-এ দেখাতে হবে।

## 14. Key Takeaways

- `ValueError` হয় যখন value-এর content বা format গ্রহণযোগ্য নয়।
- `TypeError` হয় যখন object-এর type কোনো operation-এর জন্য উপযুক্ত নয়।
- `OverflowError` কিছু numeric operation বা conversion-এর ক্ষেত্রে range অতিক্রম করলে হতে পারে।
- Bytes decoding ব্যর্থ হলে `UnicodeDecodeError` হতে পারে।
- `try-except` ব্যবহার করে conversion error handle করা যায়।
- `else` block conversion সফল হলে পরবর্তী কাজ করতে সাহায্য করে।
- `isdigit()` সব valid numeric String শনাক্ত করতে পারে না।
- `int()` Float-এর fractional part truncate করে; এটি rounding নয়।
- নির্দিষ্ট error handle করা bare `except` ব্যবহারের চেয়ে ভালো।
- User input গ্রহণ করার সময় validation এবং error handling গুরুত্বপূর্ণ।

## 15. Next Topic

পরবর্তী ফাইল:

**`28_Mutable_and_Immutable_Objects.md`**

সেখানে Mutable ও Immutable objects, object পরিবর্তন, variable references, identity এবং Python-এ assignment-এর আচরণ বিস্তারিতভাবে শেখা হবে।