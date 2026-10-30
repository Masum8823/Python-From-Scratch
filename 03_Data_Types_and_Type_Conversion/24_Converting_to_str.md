# 24. Converting to `str()` in Python

## 1. Introduction to `str()`

Python-এ `str()` হলো একটি built-in function, যা কোনো object-এর String representation তৈরি করে।

**String** হলো text data প্রকাশ করার জন্য ব্যবহৃত একটি data type।

Example:

```python
number = 100
text = str(number)

print(text)
print(type(text))
```

Output:

```text
100
<class 'str'>
```

এখানে Integer `100` String `"100"`-এ convert হয়েছে।

দেখতে একই রকম হলেও `100` এবং `"100"`-এর মধ্যে পার্থক্য রয়েছে:

- `100` হলো Integer।
- `"100"` হলো String।

## 2. Syntax of `str()`

`str()` function-এর সাধারণ syntax:

```python
str(object)
```

এখানে `object` হলো যে value বা object-এর String representation তৈরি করতে চাই।

Example:

```python
value = str(25.5)

print(value)
print(type(value))
```

Output:

```text
25.5
<class 'str'>
```

`str()`-এর মাধ্যমে তৈরি হওয়া result-এর type হলো `str`।

## 3. Converting Integer to String

Integer-কে String-এ convert করতে `str()` ব্যবহার করা হয়।

```python
age = 22
text = str(age)

print(text)
print(type(text))
```

Output:

```text
22
<class 'str'>
```

এখানে `age` Integer, কিন্তু `text` String।

### Practical Example

```python
age = 22

message = "My age is " + str(age)

print(message)
```

Output:

```text
My age is 22
```

এখানে `str(age)` ব্যবহার করা হয়েছে, কারণ String-এর সঙ্গে Integer সরাসরি `+` দিয়ে concatenate করা যায় না।

## 4. Converting Float to String

Float-কে String-এ convert করতেও `str()` ব্যবহার করা যায়।

```python
price = 125.75
text = str(price)

print(text)
print(type(text))
```

Output:

```text
125.75
<class 'str'>
```

### Example: Product Price

```python
price = 99.50

message = "Product price: " + str(price)

print(message)
```

Output:

```text
Product price: 99.5
```

এখানে গুরুত্বপূর্ণ বিষয় হলো, Python-এর Float representation-এ `99.50` সাধারণত `99.5` হিসেবে প্রকাশিত হয়।

যদি সব সময় দুই decimal places দেখাতে চাও, তাহলে f-string ব্যবহার করো:

```python
price = 99.50

message = f"Product price: {price:.2f}"

print(message)
```

Output:

```text
Product price: 99.50
```

**মনে রাখবে:** `str(price)` এবং `f"{price:.2f}"` একই কাজ করে না। দ্বিতীয়টি নির্দিষ্ট format-এ text তৈরি করে।

## 5. Converting Boolean to String

Boolean value `True` এবং `False`-কে String-এ convert করা যায়।

```python
a = str(True)
b = str(False)

print(a)
print(b)

print(type(a))
print(type(b))
```

Output:

```text
True
False
<class 'str'>
<class 'str'>
```

এখানে:

- `True` → `"True"`
- `False` → `"False"`

String হিসেবে convert করার পর এগুলো আর Boolean value থাকে না।

### Important Difference

```python
a = True
b = str(True)

print(type(a))
print(type(b))
```

Output:

```text
<class 'bool'>
<class 'str'>
```

দেখতে একই রকম হলেও তাদের data type আলাদা।

## 6. Converting `None` to String

Python-এর `None` হলো এমন একটি special value, যা সাধারণত কোনো value অনুপস্থিত বা নেই বোঝাতে ব্যবহৃত হয়।

```python
value = None
text = str(value)

print(text)
print(type(text))
```

Output:

```text
None
<class 'str'>
```

এখানে `str(None)` String `"None"` তৈরি করে।

**Important:** `None` এবং `"None"` এক নয়।

```python
a = None
b = str(None)

print(a is None)
print(b is None)
print(a == b)
```

Output:

```text
True
False
False
```

প্রথমটি আসল `None` value, আর দ্বিতীয়টি সাধারণ String।

## 7. Converting List to String

`str()` ব্যবহার করে List-এর String representation তৈরি করা যায়।

```python
numbers = [10, 20, 30]
text = str(numbers)

print(text)
print(type(text))
```

Output:

```text
[10, 20, 30]
<class 'str'>
```

এখানে `text` হলো একটি String, List নয়।

```python
numbers = [10, 20, 30]
text = str(numbers)

print(numbers[0])
print(text[0])
```

Output:

```text
10
[
```

কারণ:

- `numbers[0]` List-এর প্রথম Integer।
- `text[0]` String-এর প্রথম character।

**মনে রাখবে:** `str(list)` List-এর element-গুলোকে আলাদা আলাদা String-এ convert করে না; এটি পুরো List-এর textual representation তৈরি করে।

### List-এর Element-গুলোকে String-এ Convert করা

যদি প্রতিটি element-কে String-এ convert করতে চাও, তাহলে `map()` বা list comprehension ব্যবহার করা যায়।

```python
numbers = [10, 20, 30]

text_numbers = [str(number) for number in numbers]

print(text_numbers)
```

Output:

```text
['10', '20', '30']
```

এখানে প্রতিটি Integer আলাদাভাবে String হয়েছে।

## 8. Converting Tuple to String

Tuple-এর String representation তৈরি করতেও `str()` ব্যবহার করা যায়।

```python
data = (10, 20, 30)
text = str(data)

print(text)
print(type(text))
```

Output:

```text
(10, 20, 30)
<class 'str'>
```

এখানে `text` হলো String, Tuple নয়।

## 9. Converting Set to String

Set-এর String representation তৈরি করা যায়।

```python
numbers = {10, 20, 30}
text = str(numbers)

print(text)
print(type(text))
```

Output দেখতে এমন হতে পারে:

```text
{10, 20, 30}
<class 'str'>
```

Set-এর element-এর order নির্দিষ্ট নয়। তাই output-এর order ভিন্ন হতে পারে।

**মনে রাখবে:** `str(set_value)` Set-কে String-এ convert করে না এমন অর্থে যে Set-টাই অপরিবর্তিত থাকে; বরং Set-এর একটি textual representation তৈরি করে।

## 10. Converting Dictionary to String

Dictionary-কে String representation-এ রূপান্তর করা যায়।

```python
student = {
    "name": "Masum",
    "age": 22
}

text = str(student)

print(text)
print(type(text))
```

Output:

```text
{'name': 'Masum', 'age': 22}
<class 'str'>
```

এখানে পুরো Dictionary-এর String representation তৈরি হয়েছে।

যদি Dictionary-কে JSON format-এ String হিসেবে সংরক্ষণ বা API-তে পাঠাতে চাও, তাহলে `json.dumps()` বেশি উপযোগী হতে পারে।

```python
import json

student = {
    "name": "Masum",
    "age": 22
}

text = json.dumps(student)

print(text)
print(type(text))
```

Output:

```text
{"name": "Masum", "age": 22}
<class 'str'>
```

`str()` এবং `json.dumps()` এক নয়। JSON data interchange-এর জন্য নির্দিষ্ট format অনুসরণ করে।

## 11. Converting Complex Number to String

Complex number-কে String-এ convert করা যায়।

```python
number = 3 + 4j
text = str(number)

print(text)
print(type(text))
```

Output:

```text
(3+4j)
<class 'str'>
```

এখানে Complex number-এর textual representation তৈরি হয়েছে।

## 12. Converting Bytes to String

`bytes` object-কে `str()` দিয়ে String-এ convert করা যায়, কিন্তু এতে মূল text সরাসরি পাওয়া নাও যেতে পারে।

```python
data = b"Hello"
text = str(data)

print(text)
print(type(text))
```

Output:

```text
b'Hello'
<class 'str'>
```

এখানে `b'Hello'` হলো Bytes object-এর textual representation।

যদি Bytes-এর মধ্যে থাকা text পেতে চাও, তাহলে `decode()` ব্যবহার করতে হবে।

```python
data = b"Hello"
text = data.decode("utf-8")

print(text)
```

Output:

```text
Hello
```

**মনে রাখবে:**

- `str(bytes_value)` → Bytes object-এর textual representation।
- `bytes_value.decode("utf-8")` → Bytes-এর encoded text-কে String-এ decode করে।

## 13. String Concatenation with `str()`

String-এর সঙ্গে অন্য data type-এর value যুক্ত করতে `str()` কাজে লাগে।

Example:

```python
name = "Masum"
age = 22

message = "My name is " + name + " and I am " + str(age) + " years old."

print(message)
```

Output:

```text
My name is Masum and I am 22 years old.
```

এখানে `age` Integer হওয়ায় সেটিকে `str(age)` দিয়ে String-এ convert করা হয়েছে।

### A Simpler Alternative: f-string

একই কাজ f-string দিয়েও করা যায়:

```python
name = "Masum"
age = 22

message = f"My name is {name} and I am {age} years old."

print(message)
```

Output:

```text
My name is Masum and I am 22 years old.
```

সাধারণ message তৈরি করার ক্ষেত্রে f-string প্রায়ই বেশি readable হয়।

## 14. `str()` vs `repr()`

Python-এ `str()` এবং `repr()` উভয়ই object-এর String representation তৈরি করে, কিন্তু তাদের উদ্দেশ্য আলাদা।

- `str()` সাধারণত মানুষের পড়ার উপযোগী representation দেওয়ার জন্য ব্যবহৃত হয়।
- `repr()` সাধারণত debugging এবং developer-এর কাছে object-এর representation পরিষ্কারভাবে দেখানোর জন্য ব্যবহৃত হয়।

Example:

```python
text = "Hello\nPython"

print(str(text))
print(repr(text))
```

Output:

```text
Hello
Python
'Hello\nPython'
```

প্রথম output-এ `\n` নতুন লাইন তৈরি করেছে।

দ্বিতীয় output-এ `repr()` newline character-টিকে `\n` হিসেবে দেখিয়েছে।

আরও একটি উদাহরণ:

```python
number = 10

print(str(number))
print(repr(number))
```

Output:

```text
10
10
```

অনেক built-in type-এর ক্ষেত্রে `str()` এবং `repr()` একই রকম output দিতে পারে।

## 15. Common Errors and Misconceptions

### 15.1 Assuming `str()` Preserves the Original Type

```python
number = 100
text = str(number)

print(type(number))
print(type(text))
```

Output:

```text
<class 'int'>
<class 'str'>
```

`str()` original variable-এর type পরিবর্তন করে না। এটি নতুন String value return করে।

### 15.2 Adding String and Integer Directly

```python
age = 22

print("Age: " + age)
```

এটি `TypeError` তৈরি করবে, কারণ String ও Integer সরাসরি এভাবে concatenate করা যায় না।

Correct:

```python
age = 22

print("Age: " + str(age))
```

অথবা:

```python
age = 22

print(f"Age: {age}")
```

### 15.3 Thinking `str()` Creates JSON

```python
data = {"name": "Masum"}

text = str(data)

print(text)
```

এটি Dictionary-এর String representation তৈরি করে; JSON serialization নিশ্চিত করে না।

JSON প্রয়োজন হলে:

```python
import json

text = json.dumps(data)
```

ব্যবহার করো।

### 15.4 Confusing String Conversion with Encoding

```python
text = "Hello"
```

এটি String।

```python
encoded = text.encode("utf-8")
```

এটি Bytes তৈরি করে।

```python
decoded = encoded.decode("utf-8")
```

এটি আবার String তৈরি করে।

String ও Bytes-এর পার্থক্য বোঝা file handling, networking এবং API development-এর জন্য গুরুত্বপূর্ণ।

## 16. Practical Examples

### Example 1: Generate a Student Message

```python
name = "Masum"
student_id = 1350
cgpa = 3.95

message = (
    "Name: " + name
    + ", ID: " + str(student_id)
    + ", CGPA: " + str(cgpa)
)

print(message)
```

Output:

```text
Name: Masum, ID: 1350, CGPA: 3.95
```

### Example 2: Convert Multiple Values

```python
values = [10, 25.5, True, None]

for value in values:
    text = str(value)
    print(text, type(text))
```

Output:

```text
10 <class 'str'>
25.5 <class 'str'>
True <class 'str'>
None <class 'str'>
```

এখানে প্রতিটি value-এর String representation তৈরি হয়েছে।

### Example 3: Create a Simple Receipt

```python
product = "Notebook"
price = 45.50
quantity = 3

total = price * quantity

receipt = (
    "Product: " + product + "\n"
    + "Quantity: " + str(quantity) + "\n"
    + "Total: " + f"{total:.2f}"
)

print(receipt)
```

Output:

```text
Product: Notebook
Quantity: 3
Total: 136.50
```

এই উদাহরণে `str()` এবং f-string formatting দুটোই ব্যবহার করা হয়েছে।

## 17. Practice Exercises

### Exercise 1: Basic Conversion

নিচের value-গুলোকে String-এ convert করো এবং type পরীক্ষা করো।

```python
a = 100
b = 25.75
c = True
d = None
```

### Exercise 2: String Concatenation

নিচের variable-গুলো ব্যবহার করে একটি sentence তৈরি করো:

```python
name = "Masum"
age = 22
```

Sentence:

```text
My name is Masum and I am 22 years old.
```

প্রথমে `str()` ব্যবহার করো, তারপর f-string দিয়ে একই কাজ করো।

### Exercise 3: Collection Conversion

নিচের প্রতিটি object-কে String-এ convert করো:

```python
a = [1, 2, 3]
b = (4, 5, 6)
c = {7, 8, 9}
d = {"name": "Masum", "age": 22}
```

প্রতিটি result-এর type পরীক্ষা করো।

### Exercise 4: `str()` vs `repr()`

নিচের code-এর output অনুমান করো:

```python
text = "Python\nProgramming"

print(str(text))
print(repr(text))
```

দুটি output-এর পার্থক্য ব্যাখ্যা করো।

### Exercise 5: Bytes to String

নিচের code-এর output অনুমান করো:

```python
data = b"Hello"

print(str(data))
print(data.decode("utf-8"))
```

কেন output দুটি আলাদা, তা ব্যাখ্যা করো।

### Exercise 6: Student Information

একটি program তৈরি করো, যেখানে student-এর name, ID এবং CGPA variable-এ রাখা থাকবে। তারপর সেগুলো ব্যবহার করে একটি সুন্দর information message তৈরি করো।

### Exercise 7: Mini Project — Shopping Receipt

একটি ছোট receipt তৈরি করো, যেখানে থাকবে:

- Product name
- Unit price
- Quantity
- Total price

প্রয়োজন অনুযায়ী `str()` এবং f-string ব্যবহার করো। Total price দুই decimal places-এ দেখাও।

## 18. Key Takeaways

- `str()` একটি built-in function, যা object-এর String representation return করে।
- Integer, Float, Boolean, `None` এবং collection object-কে String representation-এ রূপান্তর করা যায়।
- `str()` ব্যবহার করলে original object-এর type পরিবর্তিত হয় না।
- String concatenation-এর আগে non-String value-কে `str()` দিয়ে convert করা যায়।
- f-string সাধারণত formatted message তৈরির সহজ উপায়।
- `str()` এবং `repr()`-এর উদ্দেশ্য এক নয়।
- `str(bytes_value)` এবং `bytes_value.decode()` আলাদা কাজ করে।
- JSON serialization-এর জন্য `json.dumps()` ব্যবহার করা যায়।

## 19. Next Topic

পরবর্তী ফাইল:

**`25_Converting_to_bool.md`**

সেখানে `bool()` function, বিভিন্ন data type-এর Boolean conversion, truthy ও falsy values এবং conversion-এর common mistakes বিস্তারিতভাবে শেখা হবে।