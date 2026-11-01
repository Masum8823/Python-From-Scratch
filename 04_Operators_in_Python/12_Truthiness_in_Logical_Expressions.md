# 12. Truthiness in Logical Expressions

## 1. Introduction to Truthiness

Python-এ প্রতিটি Value সরাসরি Boolean Value না হলেও Condition-এর মধ্যে সেটি **Truthy** অথবা **Falsy** হিসেবে বিবেচিত হতে পারে।

- **Truthy:** যে Value Condition-এর মধ্যে `True` হিসেবে কাজ করে।
- **Falsy:** যে Value Condition-এর মধ্যে `False` হিসেবে কাজ করে।

Example:

```python
print(bool(10))
print(bool(0))
print(bool("Python"))
print(bool(""))
```

Output:

```text
True
False
True
False
```

ব্যাখ্যা:

- `10` একটি Non-zero Number, তাই এটি Truthy।
- `0` Falsy।
- `"Python"` একটি Non-empty String, তাই এটি Truthy।
- `""` একটি Empty String, তাই এটি Falsy।

**মনে রাখবে:** Truthiness হলো কোনো Value-কে Boolean Context-এ কীভাবে মূল্যায়ন করা হয়, সেই ধারণা।

---

## 2. Understanding the `bool()` Function

Python-এর `bool()` Function কোনো Value-এর Truth Value নির্ধারণ করে `True` অথবা `False` Return করে।

Syntax:

```python
bool(value)
```

Example:

```python
print(bool(1))
print(bool(100))
print(bool(-5))
print(bool(0))
```

Output:

```text
True
True
True
False
```

ব্যাখ্যা:

- Positive Number Truthy।
- Negative Number Truthy।
- Zero Falsy।

আরও কিছু Example:

```python
print(bool("Hello"))
print(bool("0"))
print(bool("False"))
print(bool(""))
```

Output:

```text
True
True
True
False
```

খেয়াল করো, `"0"` এবং `"False"` হলো Non-empty String। তাই এগুলো Truthy।

অন্যদিকে, `0` এবং `False` হলো Falsy Value।

---

## 3. Falsy Values in Python

Python-এ কয়েকটি গুরুত্বপূর্ণ Value রয়েছে, যেগুলো Falsy হিসেবে বিবেচিত হয়।

| Value | Data Type | Truth Value |
|---|---|---|
| `False` | Boolean | Falsy |
| `None` | NoneType | Falsy |
| `0` | Integer | Falsy |
| `0.0` | Float | Falsy |
| `0j` | Complex | Falsy |
| `""` | String | Falsy |
| `[]` | List | Falsy |
| `()` | Tuple | Falsy |
| `{}` | Dictionary | Falsy |
| `set()` | Set | Falsy |
| `range(0)` | Range | Falsy |

Example:

```python
print(bool(False))
print(bool(None))
print(bool(0))
print(bool(0.0))
print(bool(""))
print(bool([]))
print(bool(()))
print(bool({}))
print(bool(set()))
print(bool(range(0)))
```

Output:

```text
False
False
False
False
False
False
False
False
False
False
```

**সহজ নিয়ম:** সাধারণভাবে Zero, Empty Collection, Empty String, `False` এবং `None` হলো Falsy।

---

## 4. Truthy Values in Python

যে Value-গুলো Falsy নয়, সেগুলো সাধারণত Truthy।

Example:

```python
print(bool(True))
print(bool(1))
print(bool(-10))
print(bool(3.14))
print(bool("Python"))
print(bool([1, 2]))
print(bool((1, 2)))
print(bool({"name": "Masum"}))
print(bool({1, 2}))
```

Output:

```text
True
True
True
True
True
True
True
True
True
```

ব্যাখ্যা:

- Non-zero Number Truthy।
- Non-empty String Truthy।
- Non-empty List, Tuple, Set এবং Dictionary Truthy।

এমনকি Collection-এর ভেতরে Falsy Value থাকলেও Collection-টি Empty না হলে সাধারণত Truthy হবে।

```python
print(bool([0]))
print(bool([""]))
print(bool([None]))
```

Output:

```text
True
True
True
```

কারণ তিনটি List-এর প্রতিটিতে একটি করে Element রয়েছে। তাই List-গুলো Empty নয়।

---

## 5. Truthiness in `if` Statements

Condition-এর মধ্যে সরাসরি কোনো Value ব্যবহার করা যায়। সব সময় `== True` লিখতে হয় না।

### Example 1: Using a Number

```python
number = 10

if number:
    print("Number is truthy")
else:
    print("Number is falsy")
```

Output:

```text
Number is truthy
```

এখানে `number`-এর Value `10`, যা Truthy। তাই `if` Block Execute হয়েছে।

### Example 2: Using Zero

```python
number = 0

if number:
    print("Number is truthy")
else:
    print("Number is falsy")
```

Output:

```text
Number is falsy
```

এখানে `0` Falsy হওয়ায় `else` Block Execute হয়েছে।

### Example 3: Checking a String

```python
name = "Masum"

if name:
    print("Name is provided")
else:
    print("Name is empty")
```

Output:

```text
Name is provided
```

### Example 4: Checking an Empty String

```python
name = ""

if name:
    print("Name is provided")
else:
    print("Name is empty")
```

Output:

```text
Name is empty
```

এই পদ্ধতি Form Validation এবং User Input Checking-এর মতো কাজে ব্যবহার করা যায়।

---

## 6. Truthiness of Collections

List, Tuple, Set এবং Dictionary-এর ক্ষেত্রে Collection Empty কি না, তার ওপর Truthiness নির্ভর করে।

### Example 1: List

```python
numbers = [10, 20, 30]

if numbers:
    print("List contains elements")
else:
    print("List is empty")
```

Output:

```text
List contains elements
```

### Example 2: Empty List

```python
numbers = []

if numbers:
    print("List contains elements")
else:
    print("List is empty")
```

Output:

```text
List is empty
```

### Example 3: Dictionary

```python
student = {"name": "Masum"}

if student:
    print("Student data exists")
else:
    print("No student data")
```

Output:

```text
Student data exists
```

### Example 4: Empty Dictionary

```python
student = {}

if student:
    print("Student data exists")
else:
    print("No student data")
```

Output:

```text
No student data
```

**Best Practice:** কোনো Collection Empty কি না পরীক্ষা করতে সাধারণত `if collection:` অথবা `if not collection:` ব্যবহার করা যায়।

---

## 7. Truthiness with the `not` Operator

`not` Operator একটি Value-এর Truth Value উল্টে দেয়।

Example:

```python
print(not 10)
print(not 0)
print(not "Python")
print(not "")
print(not [])
```

Output:

```text
False
True
False
True
True
```

ব্যাখ্যা:

- `10` Truthy, তাই `not 10` হলো `False`।
- `0` Falsy, তাই `not 0` হলো `True`।
- `"Python"` Truthy, তাই `not "Python"` হলো `False`।
- Empty String এবং Empty List Falsy, তাই তাদের আগে `not` বসালে Result `True` হয়।

### Practical Example

```python
username = ""

if not username:
    print("Please enter your username")
else:
    print("Welcome")
```

Output:

```text
Please enter your username
```

এখানে `not username` পরীক্ষা করছে Username Empty বা অন্য কোনো Falsy Value কি না।

---

## 8. Truthiness with `and`

Python-এর `and` Operator প্রথম Falsy Operand খুঁজে পেলে সেটি Return করে। সব Operand Truthy হলে শেষ Operand Return করে।

এটি শুধু Boolean Logic নয়, Value Selection-এর কাজেও ব্যবহৃত হয়।

### Example 1: Both Values Are Truthy

```python
print("Hello" and "Python")
```

Output:

```text
Python
```

ব্যাখ্যা:

- `"Hello"` Truthy।
- তাই Python পরবর্তী Operand পরীক্ষা করে।
- `"Python"` শেষ Operand এবং Truthy।
- তাই `"Python"` Return হয়।

### Example 2: First Value Is Falsy

```python
print(0 and 100)
```

Output:

```text
0
```

ব্যাখ্যা:

- `0` Falsy।
- তাই Python পরবর্তী Operand Evaluate না করে `0` Return করে।

### Example 3: Falsy Value in the Middle

```python
print("A" and 0 and "B")
```

Output:

```text
0
```

Python প্রথমে `"A"` পরীক্ষা করে, যা Truthy। এরপর `0` পরীক্ষা করে, যা Falsy। তাই `0` Return করে এবং `"B"` Evaluate করে না।

এই আচরণকে **Short-Circuit Evaluation** বলা হয়। এটি পরবর্তী Topic-এ বিস্তারিত আলোচনা করা হবে।

---

## 9. Truthiness with `or`

Python-এর `or` Operator প্রথম Truthy Operand খুঁজে পেলে সেটি Return করে। সব Operand Falsy হলে শেষ Operand Return করে।

### Example 1: First Value Is Truthy

```python
print("Python" or "Java")
```

Output:

```text
Python
```

কারণ `"Python"` Truthy। তাই Python পরবর্তী Operand Evaluate করে না।

### Example 2: First Value Is Falsy

```python
print("" or "Default Name")
```

Output:

```text
Default Name
```

কারণ Empty String Falsy। তাই `or` পরবর্তী Value `"Default Name"` Return করে।

### Example 3: All Values Are Falsy

```python
print(0 or "" or None)
```

Output:

```text
None
```

এখানে সব Operand Falsy। তাই শেষ Operand `None` Return হয়েছে।

---

## 10. Using `or` to Provide Default Values

`or` ব্যবহার করে কোনো Value Falsy হলে Default Value নেওয়া যায়।

Example:

```python
username = ""

display_name = username or "Guest"

print(display_name)
```

Output:

```text
Guest
```

ব্যাখ্যা:

- `username` Empty String।
- Empty String Falsy।
- তাই `or` `"Guest"` Return করে।

আরেকটি Example:

```python
name = "Masum"

display_name = name or "Guest"

print(display_name)
```

Output:

```text
Masum
```

এখানে `name` Truthy হওয়ায় `"Guest"` ব্যবহার হয়নি।

### Important Limitation

`or` ব্যবহার করলে শুধু Empty String নয়, `0`, `False` এবং `None`-এর মতো সব Falsy Value-ই Default Value দিয়ে Replace হতে পারে।

```python
marks = 0

result = marks or 50

print(result)
```

Output:

```text
50
```

এখানে Marks `0` হওয়া সত্ত্বেও `50` Return হয়েছে। কিন্তু বাস্তবে Zero Marks একটি Valid Value হতে পারে।

যদি শুধু `None` হলে Default Value দিতে চাও, তাহলে স্পষ্টভাবে পরীক্ষা করো:

```python
marks = 0

if marks is None:
    result = 50
else:
    result = marks

print(result)
```

Output:

```text
0
```

**মনে রাখবে:** Default Value নির্ধারণ করার সময় কোন Falsy Value-গুলো গ্রহণযোগ্য, তা বুঝে Code লিখতে হবে।

---

## 11. Truthiness vs Explicit Boolean Comparison

কোনো Variable Truthy কি না পরীক্ষা করার জন্য সাধারণত সরাসরি Condition-এ Variable ব্যবহার করাই যথেষ্ট।

### Less Preferred

```python
name = "Masum"

if name != "":
    print("Name exists")
```

### Cleaner Approach

```python
name = "Masum"

if name:
    print("Name exists")
```

দুটি Code-ই এখানে একই ফল দেয়। দ্বিতীয়টি ছোট এবং সাধারণ Python Style-এর সঙ্গে সামঞ্জস্যপূর্ণ।

একইভাবে:

```python
numbers = []

if not numbers:
    print("No numbers available")
```

Output:

```text
No numbers available
```

তবে মনে রাখবে, Truthiness এবং নির্দিষ্ট Value-এর সঙ্গে Equality Comparison এক বিষয় নয়।

উদাহরণস্বরূপ, `if number:` শুধু পরীক্ষা করে `number` Truthy কি না। এটি পরীক্ষা করে না যে `number` অবশ্যই `1`।

---

## 12. Common Mistakes

### Mistake 1: Thinking `"False"` Is Falsy

```python
print(bool("False"))
```

Output:

```text
True
```

কারণ `"False"` একটি Non-empty String।

### Mistake 2: Thinking `[0]` Is Falsy

```python
print(bool([0]))
```

Output:

```text
True
```

কারণ List-টি Empty নয়।

### Mistake 3: Thinking `or` Always Returns `True` or `False`

```python
print(0 or 20)
```

Output:

```text
20
```

`or` এখানে Operand-এর Value Return করেছে।

### Mistake 4: Accidentally Replacing Zero with a Default

```python
quantity = 0

print(quantity or 1)
```

Output:

```text
1
```

Zero একটি Valid Value হলে এভাবে Default Value দেওয়া উচিত নয়।

### Mistake 5: Checking a Collection Incorrectly

```python
items = []

if items:
    print("Items available")
else:
    print("No items available")
```

Output:

```text
No items available
```

Empty Collection Falsy, তাই `else` Block Execute হয়েছে।

---

## 13. Practice Exercises

### Basic Level

1. `bool(0)`-এর Result কী?
2. `bool("0")`-এর Result কী?
3. `bool([])`-এর Result কী?
4. `bool([0])`-এর Result কী?
5. `not None`-এর Result কী?

### Intermediate Level

6. কেন `bool("False")` True Return করে?
7. Empty List পরীক্ষা করার সবচেয়ে সহজ পদ্ধতি কী?
8. `0 or 100` কী Return করবে?
9. `"Python" and "Java"` কী Return করবে?
10. Zero-কে Valid Value হিসেবে রেখে শুধু `None`-এর জন্য Default Value কীভাবে নির্ধারণ করবে?

### Output Prediction

```python
print(bool(""))
print(bool(" "))
print(bool({}))
print(bool({"x": 0}))
print(not [])
print(0 or 5)
print(10 and 20)
print("" or "Hello")
print("A" and 0 and "B")
print(None or False)
```

### Answers

```text
False
True
False
True
True
5
20
Hello
0
False
```

ব্যাখ্যা:

- `" "`-এ একটি Space Character আছে, তাই এটি Empty String নয়।
- `{"x": 0}`-এ একটি Key-Value Pair আছে, তাই Dictionary-টি Truthy।
- `None or False`-এ দুটি Operand-ই Falsy। তাই শেষ Operand `False` Return হয়।

---

## 14. Chapter Summary

- Truthiness হলো কোনো Value Boolean Context-এ True বা False হিসেবে কীভাবে কাজ করে।
- Zero, `None`, `False`, Empty String এবং Empty Collection সাধারণত Falsy।
- Non-zero Number এবং Non-empty Collection সাধারণত Truthy।
- `bool()` কোনো Value-এর Boolean Result দেখায়।
- `if value:` দিয়ে Truthy Value পরীক্ষা করা যায়।
- `if not value:` দিয়ে Falsy Value পরীক্ষা করা যায়।
- `and` প্রথম Falsy Operand অথবা সব Truthy হলে শেষ Operand Return করে।
- `or` প্রথম Truthy Operand অথবা সব Falsy হলে শেষ Operand Return করে।
- `or` দিয়ে Default Value দেওয়া যায়, তবে Zero বা অন্য Valid Falsy Value হারিয়ে যাচ্ছে কি না খেয়াল রাখতে হবে।
- শুধু `None` যাচাই করতে `is None` ব্যবহার করা ভালো।

## 15. Self-Assessment Checklist

- [ ] Truthy ও Falsy-এর পার্থক্য বুঝি।
- [ ] Python-এর সাধারণ Falsy Value-গুলো চিনি।
- [ ] String ও Collection-এর Truthiness ব্যাখ্যা করতে পারি।
- [ ] `if value` এবং `if not value` ব্যবহার করতে পারি।
- [ ] `and` ও `or` কীভাবে Value Return করে বুঝি।
- [ ] Default Value নির্ধারণের সময় সম্ভাব্য সমস্যা চিহ্নিত করতে পারি।
- [ ] Output Prediction Exercise সমাধান করতে পারি।

**Next Topic:** `13_Short_Circuit_Evaluation.md`