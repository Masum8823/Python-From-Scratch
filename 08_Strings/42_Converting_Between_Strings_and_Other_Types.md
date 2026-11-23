
# 42. Converting Between Strings and Other Types

## 1. Introduction

Python-এ এক data type থেকে অন্য data type-এ পরিবর্তন করাকে **Type Conversion** বলে।

অনেক সময় আমাদের কাছে কোনো data String হিসেবে থাকে, কিন্তু সেটিকে Integer বা Float হিসেবে ব্যবহার করতে হয়।

আবার কখনো Integer বা Float-কে String-এ convert করার প্রয়োজন হয়।

উদাহরণ:

```python
number = "100"

print(type(number))
```

**Output:**

```text
<class 'str'>
```

এখানে `100` দেখতে number-এর মতো হলেও এটি একটি String।

এটিকে Integer-এ convert করতে হবে।

```python
number = "100"

number = int(number)

print(number)
print(type(number))
```

**Output:**

```text
100
<class 'int'>
```

Python-এ Type Conversion করার জন্য বিভিন্ন built-in function রয়েছে।

যেমন:

- `str()` - String-এ convert করে।
- `int()` - Integer-এ convert করে।
- `float()` - Float-এ convert করে।
- `bool()` - Boolean-এ convert করে।
- `list()` - List-এ convert করে।
- `tuple()` - Tuple-এ convert করে।
- `set()` - Set-এ convert করে।

---

## 2. Converting Integer into String

Integer-কে String-এ convert করার জন্য `str()` function ব্যবহার করা হয়।

**Syntax:**

```python
str(value)
```

উদাহরণ:

```python
number = 100

result = str(number)

print(result)
print(type(result))
```

**Output:**

```text
100
<class 'str'>
```

এখানে:

- `number` একটি Integer।
- `str()` Integer-কে String-এ convert করেছে।
- `result` এখন একটি String।

আরেকটি উদাহরণ:

```python
age = 22

message = "My age is " + str(age)

print(message)
```

**Output:**

```text
My age is 22
```

এখানে `str(age)` ব্যবহার করা হয়েছে, কারণ String-এর সঙ্গে সরাসরি Integer যোগ করা যায় না।

**মনে রাখবে:** `str()` যেকোনো উপযুক্ত value-এর String representation তৈরি করে।

---

## 3. Converting Float into String

Float-কে String-এ convert করার জন্যও `str()` function ব্যবহার করা হয়।

উদাহরণ:

```python
price = 99.50

result = str(price)

print(result)
print(type(result))
```

**Output:**

```text
99.5
<class 'str'>
```

এখানে Python `99.50`-কে `99.5` হিসেবে দেখিয়েছে।

আরেকটি উদাহরণ:

```python
pi = 3.1416

result = str(pi)

print(result)
print(type(result))
```

**Output:**

```text
3.1416
<class 'str'>
```

**মনে রাখবে:** Integer এবং Float উভয়কেই String-এ convert করতে `str()` ব্যবহার করা হয়।

---

## 4. Converting String into Integer

একটি numeric String-কে Integer-এ convert করার জন্য `int()` function ব্যবহার করা হয়।

**Syntax:**

```python
int(value)
```

উদাহরণ:

```python
number = "500"

result = int(number)

print(result)
print(type(result))
```

**Output:**

```text
500
<class 'int'>
```

এখানে `"500"` একটি String ছিল। `int()` ব্যবহার করার ফলে এটি Integer হয়েছে।

আরেকটি উদাহরণ:

```python
a = "100"
b = "200"

result = int(a) + int(b)

print(result)
```

**Output:**

```text
300
```

এখানে String দুটিকে Integer-এ convert করে যোগ করা হয়েছে।

**গুরুত্বপূর্ণ:** `int()` দিয়ে convert করার সময় String-এর মধ্যে valid integer value থাকতে হবে।

---

## 5. Converting String into Float

একটি numeric String-কে Float-এ convert করার জন্য `float()` function ব্যবহার করা হয়।

**Syntax:**

```python
float(value)
```

উদাহরণ:

```python
number = "25.75"

result = float(number)

print(result)
print(type(result))
```

**Output:**

```text
25.75
<class 'float'>
```

আরেকটি উদাহরণ:

```python
a = "10.5"
b = "20.5"

result = float(a) + float(b)

print(result)
```

**Output:**

```text
31.0
```

এখানে String দুটিকে Float-এ convert করে যোগ করা হয়েছে।

**মনে রাখবে:** Decimal value থাকলে `float()` ব্যবহার করা যায়।

---

## 6. Converting Integer String into Float

Integer-এর মতো দেখতে কোনো String-কেও Float-এ convert করা যায়।

উদাহরণ:

```python
number = "100"

result = float(number)

print(result)
print(type(result))
```

**Output:**

```text
100.0
<class 'float'>
```

এখানে `"100"` একটি String ছিল। `float()` ব্যবহার করার কারণে এটি `100.0` হয়েছে।

**মনে রাখবে:** `float()` Integer String এবং Decimal String উভয়কেই Float-এ convert করতে পারে।

---

## 7. Converting Float into Integer

Float-কে Integer-এ convert করার জন্য `int()` function ব্যবহার করা হয়।

উদাহরণ:

```python
number = 25.75

result = int(number)

print(result)
print(type(result))
```

**Output:**

```text
25
<class 'int'>
```

এখানে `int()` Decimal অংশ বাদ দিয়েছে।

আরেকটি উদাহরণ:

```python
a = 19.99
b = 10.50

print(int(a))
print(int(b))
```

**Output:**

```text
19
10
```

**গুরুত্বপূর্ণ:** `int()` Float-এর Decimal অংশ বাদ দেয়। এটি সাধারণ rounding করে না।

Negative number-এর ক্ষেত্রেও এটি শূন্যের দিকে truncate করে।

```python
number = -12.8

print(int(number))
```

**Output:**

```text
-12
```

---

## 8. Converting Integer into Float

Integer-কে Float-এ convert করার জন্য `float()` function ব্যবহার করা হয়।

উদাহরণ:

```python
number = 50

result = float(number)

print(result)
print(type(result))
```

**Output:**

```text
50.0
<class 'float'>
```

এখানে Integer `50` Float `50.0` হয়েছে।

আরেকটি উদাহরণ:

```python
a = 10
b = 5

result = float(a) / b

print(result)
```

**Output:**

```text
2.0
```

---

## 9. Converting Values into Boolean

কোনো value-কে Boolean-এ convert করার জন্য `bool()` function ব্যবহার করা হয়।

Boolean-এর দুটি value:

- `True`
- `False`

উদাহরণ:

```python
print(bool(1))
print(bool(0))
print(bool(100))
print(bool(-5))
```

**Output:**

```text
True
False
True
True
```

এখানে:

- `0` হলে `False` পাওয়া যায়।
- Non-zero number হলে `True` পাওয়া যায়।

String-এর ক্ষেত্রেও:

```python
print(bool("Hello"))
print(bool("Python"))
print(bool(""))
```

**Output:**

```text
True
True
False
```

এখানে:

- Empty String (`""`) হলে `False`।
- Non-empty String হলে `True`।

আরও কিছু উদাহরণ:

```python
print(bool(None))
print(bool([]))
print(bool([1, 2, 3]))
```

**Output:**

```text
False
False
True
```

**মনে রাখবে:** নিচের value-গুলো Python-এ False হিসেবে বিবেচিত হয়:

- `0`
- `0.0`
- `False`
- `None`
- `""`
- `[]`
- `()`
- `{}`
- `set()`

এগুলো ছাড়া সাধারণত অন্য value-গুলো `True` হিসেবে বিবেচিত হয়।

---

## 10. Converting String into List

String-কে List-এ convert করার জন্য `list()` function ব্যবহার করা হয়।

এটি String-এর প্রতিটি character-কে List-এর আলাদা element হিসেবে রাখে।

উদাহরণ:

```python
text = "Python"

result = list(text)

print(result)
print(type(result))
```

**Output:**

```text
['P', 'y', 't', 'h', 'o', 'n']
<class 'list'>
```

আরেকটি উদাহরণ:

```python
text = "Hello"

characters = list(text)

print(characters)
print(len(characters))
```

**Output:**

```text
['H', 'e', 'l', 'l', 'o']
5
```

**মনে রাখবে:** `list()` ব্যবহার করে String-কে character-এর List-এ convert করা যায়।

---

## 11. Converting String into Tuple

String-কে Tuple-এ convert করার জন্য `tuple()` function ব্যবহার করা হয়।

উদাহরণ:

```python
text = "Python"

result = tuple(text)

print(result)
print(type(result))
```

**Output:**

```text
('P', 'y', 't', 'h', 'o', 'n')
<class 'tuple'>
```

এখানে String-এর প্রতিটি character Tuple-এর আলাদা element হয়েছে।

**মনে রাখবে:** `tuple()` String-এর character-গুলোকে Tuple-এর element হিসেবে রাখে।

---

## 12. Converting String into Set

String-কে Set-এ convert করার জন্য `set()` function ব্যবহার করা হয়।

Set duplicate element রাখে না।

উদাহরণ:

```python
text = "banana"

result = set(text)

print(result)
```

**Possible Output:**

```text
{'b', 'a', 'n'}
```

এখানে:

- String-এ `a` একাধিকবার রয়েছে।
- কিন্তু Set duplicate character রাখে না।

**মনে রাখবে:** Set-এ duplicate value থাকে না এবং এর element-এর নির্দিষ্ট order নেই।

---

## 13. Converting List into String

List-এর element-গুলোকে একটি String-এ যুক্ত করার জন্য `join()` method ব্যবহার করা যায়।

**Syntax:**

```python
"separator".join(iterable)
```

উদাহরণ:

```python
letters = ['P', 'y', 't', 'h', 'o', 'n']

result = "".join(letters)

print(result)
```

**Output:**

```text
Python
```

এখানে `""` ব্যবহার করায় character-গুলোর মাঝে কোনো separator নেই।

Space দিয়ে যুক্ত করার উদাহরণ:

```python
words = ["I", "Love", "Python"]

result = " ".join(words)

print(result)
```

**Output:**

```text
I Love Python
```

Comma দিয়ে যুক্ত করার উদাহরণ:

```python
fruits = ["Apple", "Mango", "Banana"]

result = ", ".join(fruits)

print(result)
```

**Output:**

```text
Apple, Mango, Banana
```

**মনে রাখবে:** `join()` ব্যবহার করে String-এর iterable element-গুলোকে একটি String-এ যুক্ত করা যায়। Element-গুলো String হতে হবে।

---

## 14. Converting Other Values into String

`str()` function ব্যবহার করে বিভিন্ন ধরনের value-কে String-এ convert করা যায়।

উদাহরণ:

```python
a = 100
b = 25.5
c = True
d = None

print(str(a))
print(str(b))
print(str(c))
print(str(d))
```

**Output:**

```text
100
25.5
True
None
```

Data type পরীক্ষা:

```python
number = 100

result = str(number)

print(type(result))
```

**Output:**

```text
<class 'str'>
```

**মনে রাখবে:** `str()` কোনো value-এর String representation তৈরি করে।

---

## 15. Type Conversion in User Input

Python-এ `input()` function সবসময় String return করে।

তাই User-এর কাছ থেকে number input নিয়ে mathematical calculation করতে চাইলে সেটিকে Integer অথবা Float-এ convert করতে হয়।

উদাহরণ:

```python
age = input("Enter your age: ")

print(type(age))
```

**Example Input:**

```text
22
```

**Output:**

```text
<class 'str'>
```

এখানে `22` input দেওয়া হলেও এটি String।

সঠিকভাবে Integer-এ convert করা:

```python
age = int(input("Enter your age: "))

print(age)
print(type(age))
```

**Example Input:**

```text
22
```

**Output:**

```text
22
<class 'int'>
```

দুটি Number যোগ করার উদাহরণ:

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

result = a + b

print("Sum:", result)
```

**Example Input:**

```text
Enter first number: 10
Enter second number: 20
```

**Output:**

```text
Sum: 30
```

Decimal number input নেওয়ার ক্ষেত্রে:

```python
price = float(input("Enter price: "))

print("Price:", price)
```

**Example Input:**

```text
Enter price: 99.5
```

**Output:**

```text
Price: 99.5
```

**মনে রাখবে:** `input()` সবসময় String return করে। প্রয়োজন অনুযায়ী `int()` অথবা `float()` ব্যবহার করতে হবে।

---

## 16. Type Conversion vs Type Casting

Python-এ Type Conversion এবং Type Casting বলতে সাধারণত এক data type থেকে অন্য data type-এ পরিবর্তন করাকে বোঝানো হয়।

Type Conversion-এর দুটি সাধারণ ধরন রয়েছে:

### 1. Implicit Type Conversion

যখন Python নিজে থেকেই একটি data type-কে অন্য data type-এ convert করে, তখন তাকে Implicit Type Conversion বলে।

উদাহরণ:

```python
a = 10
b = 2.5

result = a + b

print(result)
print(type(result))
```

**Output:**

```text
12.5
<class 'float'>
```

এখানে Python Integer `10`-কে calculation-এর সময় Float হিসেবে ব্যবহার করেছে।

### 2. Explicit Type Conversion

যখন Programmer নিজে `int()`, `float()`, `str()` ইত্যাদি function ব্যবহার করে data type পরিবর্তন করে, তখন তাকে Explicit Type Conversion বলে।

উদাহরণ:

```python
number = "100"

result = int(number)

print(result)
print(type(result))
```

**Output:**

```text
100
<class 'int'>
```

এখানে Programmer নিজে String-কে Integer-এ convert করেছে।

### Difference Between Implicit and Explicit Conversion

| Implicit Conversion | Explicit Conversion |
|---|---|
| Python নিজে convert করে | Programmer convert করে |
| Automatic conversion | Manual conversion |
| সাধারণত compatible type-এর মধ্যে হয় | Built-in conversion function ব্যবহার হয় |
| Example: `10 + 2.5` | Example: `int("100")` |

---

## 17. Common Mistakes

### Mistake 1: Invalid String into Integer

```python
number = "Hello"

result = int(number)

print(result)
```

**Output:**

```text
ValueError
```

কারণ `"Hello"` একটি valid integer number নয়।

সঠিক উদাহরণ:

```python
number = "100"

result = int(number)

print(result)
```

**Output:**

```text
100
```

### Mistake 2: Adding Two Numeric Strings

```python
a = "10"
b = "20"

print(a + b)
```

**Output:**

```text
1020
```

কারণ দুটি value-ই String। তাই `+` এখানে যোগ না করে concatenate করেছে।

সঠিক পদ্ধতি:

```python
a = "10"
b = "20"

print(int(a) + int(b))
```

**Output:**

```text
30
```

### Mistake 3: Converting Decimal String into Integer

```python
number = "25.5"

result = int(number)

print(result)
```

**Output:**

```text
ValueError
```

কারণ Decimal String-কে সরাসরি `int()` দিয়ে convert করা যায় না।

সঠিক পদ্ধতি:

```python
number = "25.5"

result = int(float(number))

print(result)
```

**Output:**

```text
25
```

### Mistake 4: Forgetting input() Returns String

```python
age = input("Enter age: ")

print(age + 5)
```

**Output:**

```text
TypeError
```

কারণ `input()` String return করে।

সঠিক পদ্ধতি:

```python
age = int(input("Enter age: "))

print(age + 5)
```

**Example Input:**

```text
20
```

**Output:**

```text
25
```

### Mistake 5: Converting Float into Integer and Expecting Rounding

```python
number = 19.99

print(int(number))
```

**Output:**

```text
19
```

কারণ `int()` Decimal অংশ বাদ দেয়। এটি rounding করে না।

---

## 18. Important Rules to Remember

1. `str()` যেকোনো উপযুক্ত value-কে String-এ convert করে।
2. `int()` numeric String-কে Integer-এ convert করে।
3. `float()` numeric String-কে Float-এ convert করে।
4. `int()` Float-এর Decimal অংশ বাদ দেয়।
5. `float()` Integer-কে Float-এ convert করে।
6. `bool()` কোনো value-এর Boolean result দেয়।
7. `list()` String-কে character-এর List-এ convert করে।
8. `tuple()` String-কে character-এর Tuple-এ convert করে।
9. `set()` String-কে unique character-এর Set-এ convert করে।
10. `join()` List-এর String element-গুলোকে একটি String-এ যুক্ত করে।
11. `input()` সবসময় String return করে।
12. Implicit Conversion Python নিজে করে।
13. Explicit Conversion Programmer নিজে করে।
14. Invalid conversion করলে `ValueError` বা `TypeError` হতে পারে।

---

## 19. Practice Exercises

### Practice 1: Integer to String

একটি Integer-কে String-এ convert করো।

**Solution:**

```python
number = 500

result = str(number)

print(result)
print(type(result))
```

**Output:**

```text
500
<class 'str'>
```

### Practice 2: String to Integer

একটি numeric String-কে Integer-এ convert করো।

**Solution:**

```python
number = "250"

result = int(number)

print(result)
print(type(result))
```

**Output:**

```text
250
<class 'int'>
```

### Practice 3: String to Float

একটি Decimal String-কে Float-এ convert করো।

**Solution:**

```python
number = "45.75"

result = float(number)

print(result)
print(type(result))
```

**Output:**

```text
45.75
<class 'float'>
```

### Practice 4: Float to Integer

একটি Float number-কে Integer-এ convert করো।

**Solution:**

```python
number = 35.89

result = int(number)

print(result)
```

**Output:**

```text
35
```

### Practice 5: Convert Number into Boolean

নিচের value-গুলোকে Boolean-এ convert করো।

**Solution:**

```python
print(bool(0))
print(bool(1))
print(bool(""))
print(bool("Python"))
```

**Output:**

```text
False
True
False
True
```

### Practice 6: String to List

একটি String-কে List-এ convert করো।

**Solution:**

```python
text = "Python"

result = list(text)

print(result)
```

**Output:**

```text
['P', 'y', 't', 'h', 'o', 'n']
```

### Practice 7: List to String

একটি List-এর character-গুলোকে String-এ convert করো।

**Solution:**

```python
letters = ['H', 'e', 'l', 'l', 'o']

result = "".join(letters)

print(result)
```

**Output:**

```text
Hello
```

### Practice 8: Add Two User Inputs

User-এর কাছ থেকে দুটি Integer input নিয়ে যোগ করো।

**Solution:**

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print("Sum:", a + b)
```

**Example Input:**

```text
Enter first number: 15
Enter second number: 25
```

**Output:**

```text
Sum: 40
```

### Practice 9: Convert String into Different Types

একটি String থেকে Integer, Float এবং Boolean তৈরি করো।

**Solution:**

```python
value = "100"

a = int(value)
b = float(value)
c = bool(value)

print(a, type(a))
print(b, type(b))
print(c, type(c))
```

**Output:**

```text
100 <class 'int'>
100.0 <class 'float'>
True <class 'bool'>
```

### Practice 10: Join Words with a Separator

একটি List-এর শব্দগুলোকে comma দিয়ে যুক্ত করো।

**Solution:**

```python
words = ["Python", "Java", "C++"]

result = ", ".join(words)

print(result)
```

**Output:**

```text
Python, Java, C++
```

---

## 20. Chapter Summary

এই topic-এ আমরা শিখেছি:

- Type Conversion কী।
- Integer থেকে String তৈরি করা।
- Float থেকে String তৈরি করা।
- String থেকে Integer তৈরি করা।
- String থেকে Float তৈরি করা।
- Float থেকে Integer তৈরি করা।
- Integer থেকে Float তৈরি করা।
- `bool()` দিয়ে Boolean তৈরি করা।
- String থেকে List, Tuple এবং Set তৈরি করা।
- List থেকে String তৈরি করতে `join()` ব্যবহার করা।
- User Input-এর data type convert করা।
- Implicit এবং Explicit Type Conversion-এর পার্থক্য।
- Type Conversion-এর Common Mistakes।

---

## 21. Self-Assessment Checklist

নিজেকে যাচাই করো:

- [ ] Type Conversion কী বুঝতে পেরেছি।
- [ ] `str()` ব্যবহার করতে পারি।
- [ ] `int()` ব্যবহার করতে পারি।
- [ ] `float()` ব্যবহার করতে পারি।
- [ ] `bool()` ব্যবহার করতে পারি।
- [ ] Float থেকে Integer convert করতে পারি।
- [ ] String থেকে List, Tuple এবং Set তৈরি করতে পারি।
- [ ] `join()` ব্যবহার করে List থেকে String তৈরি করতে পারি।
- [ ] `input()`-এর value convert করতে পারি।
- [ ] Implicit এবং Explicit Conversion-এর পার্থক্য বুঝতে পেরেছি।
- [ ] Common Type Conversion errors বুঝতে পেরেছি।

---

## 22. Next Topic

পরবর্তী topic-এ আমরা শিখব:

**43. String Methods for Searching and Checking**

এখানে String-এর মধ্যে কোনো word বা character খোঁজা এবং বিভিন্ন condition পরীক্ষা করার জন্য `find()`, `index()`, `count()`, `startswith()`, `endswith()` ইত্যাদি method শিখব।
