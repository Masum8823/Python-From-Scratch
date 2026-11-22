
# 36. String Formatting with f-Strings in Python

## 1. Introduction to f-Strings

Python-এ String-এর মধ্যে Variable-এর value সহজে বসানোর জন্য **f-String (Formatted String Literal)** ব্যবহার করা হয়।

f-String ব্যবহার করলে String-এর মধ্যে সরাসরি Variable এবং Expression লেখা যায়।

f-String তৈরি করতে String-এর শুরুতে `f` অথবা `F` ব্যবহার করতে হয়।

### Example

```python
name = "Masum"
age = 22

message = f"My name is {name} and I am {age} years old."

print(message)
```

**Output:**

```text
My name is Masum and I am 22 years old.
```

এখানে:

- `f` দিয়ে f-String তৈরি করা হয়েছে।
- `{name}` এর জায়গায় `Masum` বসেছে।
- `{age}` এর জায়গায় `22` বসেছে।

---

## 2. Syntax of f-Strings

f-String লেখার নিয়ম:

```python
f"Text {variable}"
```

অথবা

```python
F"Text {variable}"
```

Variable-এর নাম Curly Braces `{}`-এর মধ্যে লিখতে হয়।

### Example

```python
language = "Python"

print(f"I am learning {language}.")
```

**Output:**

```text
I am learning Python.
```

---

## 3. Using Multiple Variables in f-Strings

একটি f-String-এর মধ্যে একাধিক Variable ব্যবহার করা যায়।

### Example

```python
name = "Masum"
department = "CSE"
university = "NUB"

print(f"My name is {name}.")
print(f"I study {department} at {university}.")
```

**Output:**

```text
My name is Masum.
I study CSE at NUB.
```

এখানে একই f-String-এর মধ্যে একাধিক Variable ব্যবহার করা হয়েছে।

---

## 4. Using Expressions inside f-Strings

f-String-এর মধ্যে শুধু Variable নয়, সরাসরি Mathematical Expression-ও ব্যবহার করা যায়।

### Example 1: Addition

```python
a = 10
b = 20

print(f"Sum = {a + b}")
```

**Output:**

```text
Sum = 30
```

### Example 2: Multiplication

```python
length = 10
width = 5

print(f"Area = {length * width}")
```

**Output:**

```text
Area = 50
```

### Example 3: Comparison

```python
a = 15
b = 10

print(f"Is a greater than b? {a > b}")
```

**Output:**

```text
Is a greater than b? True
```

---

## 5. Calling Functions inside f-Strings

f-String-এর মধ্যে Function Call করেও তার Return Value দেখানো যায়।

### Example

```python
name = "masum"

print(f"Uppercase: {name.upper()}")
print(f"Length: {len(name)}")
```

**Output:**

```text
Uppercase: MASUM
Length: 5
```

এখানে:

- `upper()` String-কে Uppercase করেছে।
- `len()` String-এর length বের করেছে।

---

## 6. Using Conditional Expressions inside f-Strings

f-String-এর মধ্যে Conditional Expression ব্যবহার করা যায়।

### Example

```python
marks = 75

result = f"Result: {'Pass' if marks >= 40 else 'Fail'}"

print(result)
```

**Output:**

```text
Result: Pass
```

**ব্যাখ্যা:**

- যদি `marks >= 40` হয়, তাহলে `Pass` দেখাবে।
- অন্যথায় `Fail` দেখাবে।

---

## 7. Using Variables with Different Data Types

f-String-এর মধ্যে বিভিন্ন Data Type-এর Variable ব্যবহার করা যায়।

### Example

```python
name = "Masum"
age = 22
cgpa = 3.95
is_student = True

print(f"Name: {name}")
print(f"Age: {age}")
print(f"CGPA: {cgpa}")
print(f"Student: {is_student}")
```

**Output:**

```text
Name: Masum
Age: 22
CGPA: 3.95
Student: True
```

এখানে String, Integer, Float এবং Boolean Data Type ব্যবহার করা হয়েছে।

---

## 8. Formatting Values with f-Strings

f-String ব্যবহার করে Value-এর Display Format পরিবর্তন করা যায়।

Curly Braces-এর মধ্যে Variable-এর পরে Colon (`:`) ব্যবহার করে Formatting করা হয়।

### Basic Syntax

```python
f"{variable:format_specifier}"
```

এখানে:

- `variable` হলো যে Value Format করতে চাই।
- `format_specifier` হলো Formatting-এর নিয়ম।

### Example: Decimal Places

```python
price = 125.5678

print(f"Price: {price:.2f}")
```

**Output:**

```text
Price: 125.57
```

এখানে `.2f` ব্যবহার করায় Decimal-এর পরে দুইটি digit দেখানো হয়েছে।

**Note:** f-String-এর মাধ্যমে আরও Number Formatting করা যায়। সেগুলো পরবর্তী topic-এ বিস্তারিত শিখব।

---

## 9. Using f-Strings for Debugging

Python-এ f-String-এর মধ্যে Variable-এর নাম এবং Value একসঙ্গে দেখানোর জন্য `=` ব্যবহার করা যায়।

এটি Debugging-এর ক্ষেত্রে অনেক উপকারী।

### Example

```python
name = "Masum"
age = 22

print(f"{name=}")
print(f"{age=}")
```

**Output:**

```text
name='Masum'
age=22
```

এখানে `name=` এবং `age=` লেখার কারণে Variable-এর নাম ও Value একসঙ্গে দেখানো হয়েছে।

---

## 10. Using Braces inside f-Strings

কখনো f-String-এর মধ্যে সরাসরি Curly Braces `{}` দেখানোর প্রয়োজন হতে পারে।

সেক্ষেত্রে Double Curly Braces `{{` এবং `}}` ব্যবহার করতে হয়।

### Example

```python
name = "Masum"

print(f"{{Hello, {name}}}")
```

**Output:**

```text
{Hello, Masum}
```

এখানে:

- `{{` একটি `{` দেখায়।
- `}}` একটি `}` দেখায়।
- `{name}` Variable-এর Value দেখায়।

---

## 11. Practical Example: Student Information

```python
name = "Masum"
student_id = 12345
department = "CSE"
cgpa = 3.95

print(f"Name: {name}")
print(f"Student ID: {student_id}")
print(f"Department: {department}")
print(f"CGPA: {cgpa}")
```

**Output:**

```text
Name: Masum
Student ID: 12345
Department: CSE
CGPA: 3.95
```

এখানে f-String ব্যবহার করে Student Information সুন্দরভাবে Display করা হয়েছে।

---

## 12. Practical Example: Simple Calculator

```python
num1 = 20
num2 = 10

print(f"First Number: {num1}")
print(f"Second Number: {num2}")
print(f"Addition: {num1 + num2}")
print(f"Subtraction: {num1 - num2}")
print(f"Multiplication: {num1 * num2}")
print(f"Division: {num1 / num2}")
```

**Output:**

```text
First Number: 20
Second Number: 10
Addition: 30
Subtraction: 10
Multiplication: 200
Division: 2.0
```

এখানে f-String-এর মধ্যে সরাসরি Mathematical Expression ব্যবহার করা হয়েছে।

---

## 13. Difference between f-Strings and Normal Strings

### Example

```python
name = "Masum"

normal = "My name is {name}."
formatted = f"My name is {name}."

print(normal)
print(formatted)
```

**Output:**

```text
My name is {name}.
My name is Masum.
```

| Normal String | f-String |
|---|---|
| Variable-এর Value সরাসরি বসায় না | Variable-এর Value বসায় |
| `f` ব্যবহার করতে হয় না | শুরুতে `f` ব্যবহার করতে হয় |
| `{name}` সাধারণ text হিসেবে থাকে | `{name}` Variable-এর Value দেখায় |
| Dynamic formatting-এর জন্য উপযুক্ত নয় | Dynamic formatting-এর জন্য উপযুক্ত |

---

## 14. Important Rules

1. f-String তৈরি করতে String-এর শুরুতে `f` অথবা `F` ব্যবহার করতে হয়।
2. Variable এবং Expression `{}`-এর মধ্যে লিখতে হয়।
3. একই f-String-এর মধ্যে একাধিক Variable ব্যবহার করা যায়।
4. Mathematical Expression ব্যবহার করা যায়।
5. Function Call ব্যবহার করা যায়।
6. Conditional Expression ব্যবহার করা যায়।
7. Formatting-এর জন্য Colon (`:`) ব্যবহার করা হয়।
8. Literal Curly Braces দেখানোর জন্য `{{` এবং `}}` ব্যবহার করতে হয়।
9. Debugging-এর জন্য `{variable=}` ব্যবহার করা যায়।
10. f-String Python 3.6 থেকে চালু হয়েছে।

---

## 15. Common Mistakes

### Mistake 1: Forgetting the f Prefix

```python
name = "Masum"

print("My name is {name}.")
```

**Output:**

```text
My name is {name}.
```

**কারণ:** String-এর শুরুতে `f` দেওয়া হয়নি।

**Correct Code:**

```python
name = "Masum"

print(f"My name is {name}.")
```

**Output:**

```text
My name is Masum.
```

### Mistake 2: Using Parentheses Instead of Curly Braces

```python
name = "Masum"

print(f"My name is (name).")
```

**Output:**

```text
My name is (name).
```

**কারণ:** f-String-এ Variable-এর জন্য Curly Braces `{}` ব্যবহার করতে হয়।

**Correct Code:**

```python
print(f"My name is {name}.")
```

**Output:**

```text
My name is Masum.
```

### Mistake 3: Forgetting Closing Curly Brace

```python
name = "Masum"

print(f"My name is {name.")
```

**Output:**

```text
SyntaxError
```

**কারণ:** Expression-এর Closing Curly Brace দেওয়া হয়নি।

**Correct Code:**

```python
print(f"My name is {name}.")
```

### Mistake 4: Using Quotes Incorrectly

```python
name = "Masum"

print(f"Name: {name}")
```

এটি সঠিক Code।

তবে একই ধরনের Quote ব্যবহার করার সময় সতর্ক থাকতে হবে।

**Example:**

```python
name = "Masum"

print(f"Name: {name.upper()}")
```

**Output:**

```text
Name: MASUM
```

---

## 16. Practice Exercises

### Exercise 1: Basic f-String

নিচের Variable ব্যবহার করে f-String দিয়ে নিজের Name এবং Department দেখাও।

```python
name = "Masum"
department = "CSE"
```

**Expected Output:**

```text
My name is Masum.
I study CSE.
```

### Exercise 2: Mathematical Expression

f-String ব্যবহার করে দুটি Number-এর যোগফল দেখাও।

```python
a = 25
b = 15
```

**Expected Output:**

```text
Sum = 40
```

### Exercise 3: Function inside f-String

একটি String-এর Uppercase এবং Length f-String ব্যবহার করে দেখাও।

```python
text = "python"
```

**Expected Output:**

```text
Uppercase: PYTHON
Length: 6
```

### Exercise 4: Conditional Expression

Marks `40` বা তার বেশি হলে `Pass`, অন্যথায় `Fail` দেখাও।

```python
marks = 75
```

**Expected Output:**

```text
Result: Pass
```

### Exercise 5: Debugging

নিচের Code-এর Output Predict করো।

```python
name = "Masum"
age = 22

print(f"{name=}")
print(f"{age=}")
print(f"Next year age: {age + 1}")
```

**Expected Output:**

```text
name='Masum'
age=22
Next year age: 23
```

### Exercise 6: Predict the Output

```python
x = 10
y = 5

print(f"Sum: {x + y}")
print(f"Product: {x * y}")
print(f"Result: {'Pass' if x > y else 'Fail'}")
```

**Expected Output:**

```text
Sum: 15
Product: 50
Result: Pass
```

---

## 17. Chapter Summary

এই topic-এ আমরা Python-এর f-String সম্পর্কে শিখেছি।

| বিষয় | Description |
|---|---|
| f-String | String-এর মধ্যে Variable-এর Value বসায় |
| `f` | f-String তৈরি করে |
| `{}` | Variable বা Expression লেখার জন্য ব্যবহৃত হয় |
| `{a + b}` | Mathematical Expression |
| `{name.upper()}` | Function Call |
| `{variable=}` | Variable-এর নাম ও Value দেখায় |
| `{{ }}` | Literal Curly Braces দেখায় |

**মনে রাখবে:**

```python
name = "Masum"

print(f"Hello {name}")
```

**Output:**

```text
Hello Masum
```

f-String হলো Python-এ String Formatting-এর সবচেয়ে সহজ এবং জনপ্রিয় পদ্ধতিগুলোর একটি।

---

## 18. Self-Assessment Checklist

- [ ] f-String কী বুঝতে পেরেছি।
- [ ] f-String-এর Syntax লিখতে পারি।
- [ ] f-String-এর মধ্যে Variable ব্যবহার করতে পারি।
- [ ] একাধিক Variable ব্যবহার করতে পারি।
- [ ] Mathematical Expression ব্যবহার করতে পারি।
- [ ] Function Call ব্যবহার করতে পারি।
- [ ] Conditional Expression ব্যবহার করতে পারি।
- [ ] Debugging-এর জন্য `{variable=}` ব্যবহার করতে পারি।
- [ ] Literal Curly Braces ব্যবহার করতে পারি।
- [ ] f-String-এর Output predict করতে পারি।

---

## 19. Next Topic

পরবর্তী topic:

**37. Formatting Numbers inside Strings in Python**

এখানে আমরা f-String ব্যবহার করে Decimal Places, Thousands Separator, Percentage, Number Alignment এবং অন্যান্য Number Formatting শিখব।
