# 04. Type Checking with `type()`

## 1. What Is Type Checking?

**Type Checking** হলো কোনো value বা object কোন data type-এর, তা যাচাই করার প্রক্রিয়া।

Python-এ type checking গুরুত্বপূর্ণ, কারণ বিভিন্ন data type-এর ওপর বিভিন্ন operation করা যায়।

Example:

```python
age = 22
name = "Masum"

print(type(age))
print(type(name))
```

Output:

```text
<class 'int'>
<class 'str'>
```

এখানে `age` হলো integer object এবং `name` হলো string object।

## 2. What Is the `type()` Function?

`type()` হলো Python-এর একটি built-in function, যা কোনো object-এর type সম্পর্কে তথ্য দেয়।

Syntax:

```python
type(object)
```

এখানে `object` হলো যে value বা object-এর type জানতে চাও।

Example:

```python
number = 100

result = type(number)

print(result)
```

Output:

```text
<class 'int'>
```

এখানে:

- `number` হলো variable।
- `100` হলো integer value।
- `type(number)` object-এর type নির্ধারণ করে।
- `result` variable-এ type object-টি রাখা হয়।

**মনে রাখবে:** `type()` শুধু type সম্পর্কে তথ্য দেয়। এটি value-কে অন্য data type-এ convert করে না।

## 3. Checking Different Data Types

### 3.1 Integer

```python
age = 22

print(type(age))
```

Output:

```text
<class 'int'>
```

### 3.2 Float

```python
cgpa = 3.95

print(type(cgpa))
```

Output:

```text
<class 'float'>
```

### 3.3 String

```python
name = "Masum"

print(type(name))
```

Output:

```text
<class 'str'>
```

### 3.4 Boolean

```python
is_student = True

print(type(is_student))
```

Output:

```text
<class 'bool'>
```

### 3.5 NoneType

```python
result = None

print(type(result))
```

Output:

```text
<class 'NoneType'>
```

### 3.6 List, Tuple, Set and Dictionary

```python
a = [10, 20, 30]
b = (10, 20, 30)
c = {10, 20, 30}
d = {"name": "Masum"}

print(type(a))
print(type(b))
print(type(c))
print(type(d))
```

Output:

```text
<class 'list'>
<class 'tuple'>
<class 'set'>
<class 'dict'>
```

এভাবে `type()` ব্যবহার করে প্রায় যেকোনো Python object-এর type পরীক্ষা করা যায়।

## 4. Understanding the Output of `type()`

`type()`-এর output সাধারণত এমন দেখায়:

```text
<class 'int'>
```

এখানে:

- `class` বোঝায় Python object-এর type একটি class দিয়ে প্রকাশিত হচ্ছে।
- `int` হলো integer type-এর নাম।

Python-এ built-in data types-গুলো class হিসেবে বাস্তবায়িত। তাই output-এ `<class 'int'>`, `<class 'str'>` ইত্যাদি দেখা যায়।

এই output-কে শুধু text হিসেবে মনে না রেখে বুঝবে যে `type()` একটি type object return করে।

Example:

```python
x = 10

result = type(x)

print(result)
print(result.__name__)
```

Output:

```text
<class 'int'>
int
```

`result.__name__` type-এর নাম string হিসেবে দেয়।

তবে সাধারণ type checking-এর জন্য শুধু `type(x)` ব্যবহার করাই যথেষ্ট।

## 5. Using `type()` Directly

`type()` ব্যবহার করার জন্য variable তৈরি করা বাধ্যতামূলক নয়। সরাসরি value-ও দেওয়া যায়।

```python
print(type(100))
print(type(3.14))
print(type("Python"))
print(type(True))
print(type(None))
```

Output:

```text
<class 'int'>
<class 'float'>
<class 'str'>
<class 'bool'>
<class 'NoneType'>
```

এটি ছোট example পরীক্ষা করার জন্য সুবিধাজনক।

## 6. Type Checking with User Input

Beginner-দের একটি গুরুত্বপূর্ণ বিষয় হলো, `input()` সাধারণত string return করে।

Example:

```python
age = input("Enter your age: ")

print(type(age))
```

User যদি `22` লেখে, output হবে:

```text
<class 'str'>
```

কারণ user-এর input text হিসেবে গ্রহণ করা হয়েছে।

Integer হিসেবে ব্যবহার করতে চাইলে conversion করতে হবে:

```python
age = int(input("Enter your age: "))

print(type(age))
```

User যদি `22` লেখে, output হবে:

```text
<class 'int'>
```

**Important:** `input()`-এর মাধ্যমে নেওয়া numeric-looking text স্বয়ংক্রিয়ভাবে number হয়ে যায় না।

## 7. `type()` Does Not Convert Data

`type()` এবং type conversion আলাদা বিষয়।

Example:

```python
number = "100"

print(type(number))
```

Output:

```text
<class 'str'>
```

এবার:

```python
number = int(number)

print(type(number))
```

Output:

```text
<class 'int'>
```

এখানে `int()` string-কে integer-এ convert করেছে। `type()` শুধু conversion-এর পর type যাচাই করেছে।

পার্থক্য:

| Function | Purpose |
|---|---|
| `type(value)` | Object-এর type সম্পর্কে তথ্য দেয় |
| `int(value)` | উপযুক্ত value-কে integer-এ convert করার চেষ্টা করে |
| `float(value)` | উপযুক্ত value-কে float-এ convert করার চেষ্টা করে |
| `str(value)` | Value-এর string representation তৈরি করে |
| `bool(value)` | Value-এর truth value নির্ধারণ করে |

Conversion সব value-এর ক্ষেত্রে সফল হবে না। Invalid conversion হলে error হতে পারে।

## 8. Using `type()` in Conditional Statements

`type()`-এর result comparison করে condition তৈরি করা যায়।

```python
value = 100

if type(value) == int:
    print("The value is an integer.")
else:
    print("The value is not an integer.")
```

Output:

```text
The value is an integer.
```

এখানে `type(value) == int` পরীক্ষা করে object-এর exact type `int` কি না।

আরেকটি example:

```python
value = "Python"

if type(value) == str:
    print("The value is a string.")
```

Output:

```text
The value is a string.
```

এই পদ্ধতি কাজ করে, তবে অনেক সাধারণ type-checking পরিস্থিতিতে `isinstance()` আরও উপযোগী।

## 9. `type()` vs `isinstance()`

এই পার্থক্যটি গুরুত্বপূর্ণ।

### Using `type()`

```python
class Animal:
    pass


class Dog(Animal):
    pass


dog = Dog()

print(type(dog) == Dog)
print(type(dog) == Animal)
```

Output:

```text
True
False
```

`type(dog) == Animal` হলো `False`, কারণ `dog`-এর exact type `Dog`।

### Using `isinstance()`

```python
print(isinstance(dog, Dog))
print(isinstance(dog, Animal))
```

Output:

```text
True
True
```

কারণ `Dog` হলো `Animal`-এর subclass। তাই `Dog` object একই সঙ্গে `Animal` class-এর instance হিসেবেও গণ্য হয়।

### Comparison Table

| `type()` | `isinstance()` |
|---|---|
| Object-এর exact type জানতে সাহায্য করে | Object নির্দিষ্ট type বা class-এর instance কি না যাচাই করে |
| সাধারণত exact type comparison-এর জন্য উপযোগী | Inheritance থাকলে বেশি flexible |
| Example: `type(x) == int` | Example: `isinstance(x, int)` |
| Subclass relationship নিজে যাচাই করে না | Subclass relationship বিবেচনা করে |

**Best Practice:** সাধারণ type validation-এর ক্ষেত্রে `isinstance()` ব্যবহার করো। Exact type জানা প্রয়োজন হলে `type()` ব্যবহার করতে পারো।

## 10. Checking Whether a Value Is a Number

একটি value integer অথবা float কি না যাচাই করতে চাইলে `isinstance()` ব্যবহার করা যায়।

```python
value = 10.5

if isinstance(value, (int, float)):
    print("The value is numeric.")
else:
    print("The value is not numeric.")
```

Output:

```text
The value is numeric.
```

এখানে `(int, float)` tuple-এর মাধ্যমে একাধিক type পরীক্ষা করা হয়েছে।

তবে মনে রাখবে, Python-এ `bool` হলো `int`-এর subclass। তাই:

```python
print(isinstance(True, int))
```

Output:

```text
True
```

যদি Boolean-কে integer হিসেবে গ্রহণ করতে না চাও, তাহলে আলাদাভাবে exact type check করতে হবে অথবা Boolean বাদ দেওয়ার condition লিখতে হবে।

## 11. Common Beginner Mistakes

### Mistake 1: `type()`-কে String Return করে মনে করা

```python
value = 10

print(type(value) == "int")
```

Output:

```text
False
```

কারণ `type(value)` একটি type object return করে, `"int"` string নয়।

Exact type comparison:

```python
print(type(value) == int)
```

Output:

```text
True
```

### Mistake 2: `type()`-এর Result-কে সরাসরি Value মনে করা

```python
value = "100"

print(type(value))
print(value)
```

Output:

```text
<class 'str'>
100
```

প্রথম output type দেখায়, দ্বিতীয়টি original value দেখায়।

### Mistake 3: `input()`-কে Automatically Numeric মনে করা

```python
age = input("Enter age: ")

print(type(age))
```

User `22` দিলেও type হবে `str`।

### Mistake 4: সব ক্ষেত্রে Exact Type Check করা

```python
if type(value) == int:
    print("Integer")
```

এটি exact `int` type-এর জন্য কাজ করে। কিন্তু subclass গ্রহণ করতে চাইলে `isinstance(value, int)` বেশি উপযোগী হতে পারে।

## 12. Practice Exercises

### Exercise 1: Identify the Types

নিচের code-এর output অনুমান করো:

```python
a = 25
b = 3.14
c = "Python"
d = False
e = None

print(type(a))
print(type(b))
print(type(c))
print(type(d))
print(type(e))
```

### Exercise 2: Collection Types

```python
numbers = [1, 2, 3]
coordinates = (10, 20)
unique = {1, 2, 3}
student = {"name": "Masum"}

print(type(numbers))
print(type(coordinates))
print(type(unique))
print(type(student))
```

Output লিখে প্রতিটি type-এর নাম ব্যাখ্যা করো।

### Exercise 3: Input Type

একটি program লেখো, যা user-এর কাছ থেকে age নেবে এবং নিচের বিষয়গুলো print করবে:

1. Original value।
2. Original value-এর type।
3. Integer conversion-এর পর value।
4. Converted value-এর type।

### Exercise 4: Fix the Error

```python
value = 50

if type(value) == "int":
    print("Integer")
```

Condition-টি এমনভাবে সংশোধন করো, যাতে expected result পাওয়া যায়।

### Exercise 5: Exact Type vs Instance

নিচের code-এর output অনুমান করো:

```python
class Vehicle:
    pass


class Car(Vehicle):
    pass


my_car = Car()

print(type(my_car) == Car)
print(type(my_car) == Vehicle)

print(isinstance(my_car, Car))
print(isinstance(my_car, Vehicle))
```

প্রতিটি result-এর কারণ ব্যাখ্যা করো।

### Exercise 6: Build a Type Checker

একটি program লেখো, যা নিচের values-এর type print করবে:

```python
values = [10, 2.5, "Python", True, None, [1, 2]]
```

`for` loop ব্যবহার করে প্রতিটি value এবং তার type দেখাও। Loop এখনো ভালোভাবে শেখা না থাকলে আপাতত প্রতিটি value-এর জন্য আলাদা `print(type(...))` লিখতে পারো।

## 13. Key Takeaways

- `type()` হলো Python-এর built-in function।
- এটি object-এর type object return করে।
- `type()` দিয়ে `int`, `float`, `str`, `bool`, `list`, `tuple`, `set`, `dict` এবং অন্যান্য object-এর type দেখা যায়।
- `type()` value-কে convert করে না।
- `input()` থেকে পাওয়া value সাধারণত `str` হয়।
- `type(value) == int` exact type checking-এর জন্য ব্যবহার করা যায়।
- `isinstance()` subclass relationship-ও বিবেচনা করে।
- সাধারণ type validation-এর জন্য `isinstance()` অনেক ক্ষেত্রে ভালো পছন্দ।

## 14. Next Topic

পরবর্তী ফাইল:

**`05_Type_Checking_with_isinstance.md`**

সেখানে `isinstance()` function বিস্তারিতভাবে শেখা হবে—একাধিক type check, inheritance, practical validation এবং `type()`-এর সঙ্গে এর পার্থক্যসহ।