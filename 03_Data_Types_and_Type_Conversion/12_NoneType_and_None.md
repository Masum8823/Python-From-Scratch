# 12. NoneType and None in Python

## 1. What Is `None`?

Python-এ `None` হলো একটি special value, যা সাধারণত কোনো value না থাকা বা value অনুপস্থিত থাকা বোঝাতে ব্যবহৃত হয়।

Example:

```python
result = None

print(result)
print(type(result))
```

Output:

```text
None
<class 'NoneType'>
```

এখানে:

- `None` হলো special value।
- `NoneType` হলো `None`-এর data type।
- `result` variable-এ বর্তমানে `None` সংরক্ষিত আছে।

**মনে রাখবে:** Python-এ `None` নিজেই একটি value, কিন্তু এটি `0`, `False` বা empty String-এর সমান নয়।

## 2. Understanding `NoneType`

`NoneType` হলো `None`-এর type।

Example:

```python
value = None

print(type(value) == type(None))
print(type(value))
```

Output:

```text
True
<class 'NoneType'>
```

Python-এ `NoneType`-এর একটিমাত্র সাধারণ value রয়েছে: `None`।

`None` লেখার সময় প্রথম অক্ষর Capital হতে হবে।

```python
value = None

print(value)
```

Output:

```text
None
```

`none`, `NONE` বা `null` Python-এর `None`-এর বিকল্প নয়। এগুলো আলাদাভাবে define করা না থাকলে সাধারণত error তৈরি করবে।

## 3. `None` Is Not the Same as Zero

`0` একটি integer value, কিন্তু `None` একটি special value।

```python
a = 0
b = None

print(a)
print(b)

print(type(a))
print(type(b))
```

Output:

```text
0
None
<class 'int'>
<class 'NoneType'>
```

এখানে `0` একটি নির্দিষ্ট numeric value বোঝায়। অন্যদিকে `None` বোঝায় যে এখানে কোনো নির্দিষ্ট value দেওয়া হয়নি বা value অনুপস্থিত।

## 4. `None` Is Not the Same as `False`

`False` হলো Boolean value, কিন্তু `None` হলো `NoneType`-এর value।

```python
a = False
b = None

print(type(a))
print(type(b))

print(a == b)
```

Output:

```text
<class 'bool'>
<class 'NoneType'>
False
```

যদিও `False` এবং `None` উভয়ই falsy, তারা একই value নয়।

## 5. `None` Is Not the Same as an Empty String

Empty String হলো `""`। এতে কোনো character নেই, কিন্তু এটি একটি String value।

```python
a = ""
b = None

print(type(a))
print(type(b))

print(a == b)
```

Output:

```text
<class 'str'>
<class 'NoneType'>
False
```

একইভাবে, empty list `[]` এবং empty dictionary `{}`-ও `None` নয়।

```python
print([] == None)
print({} == None)
```

Output:

```text
False
False
```

**গুরুত্বপূর্ণ:** `None`, `False`, `0`, `""` এবং empty collection truthiness-এর দিক থেকে falsy হতে পারে, কিন্তু এগুলোর অর্থ এবং type আলাদা।

## 6. Checking for `None` with `is`

Python-এ কোনো value `None` কি না পরীক্ষা করার সবচেয়ে recommended উপায় হলো `is` operator ব্যবহার করা।

```python
result = None

print(result is None)
print(result is not None)
```

Output:

```text
True
False
```

এখানে:

- `result is None` পরীক্ষা করে `result` হলো `None` কি না।
- `result is not None` পরীক্ষা করে `result` `None` নয় কি না।

### Example with a Condition

```python
result = None

if result is None:
    print("No result available.")
else:
    print(result)
```

Output:

```text
No result available.
```

এ ধরনের check API response, optional value, database result এবং function-এর return value পরীক্ষা করতে কাজে লাগে।

## 7. Difference Between `is None` and `== None`

দুটিকে দেখতে কাছাকাছি মনে হলেও এদের কাজ আলাদা।

### Using `is None`

`is` পরীক্ষা করে দুটি reference একই object-কে নির্দেশ করছে কি না।

```python
value = None

print(value is None)
```

Output:

```text
True
```

### Using `== None`

`==` equality পরীক্ষা করে। Custom class-এর ক্ষেত্রে এর আচরণ override করা সম্ভব।

```python
value = None

print(value == None)
```

Output:

```text
True
```

সাধারণ `None`-এর ক্ষেত্রে দুটি expression-ই `True` দিচ্ছে। তবে Python-এর standard practice হলো:

```python
if value is None:
    print("Value is missing.")
```

**মনে রাখবে:** `None` check করার জন্য `is None` এবং `is not None` ব্যবহার করো।

## 8. `None` as a Default Value

কোনো variable বা function parameter-এর প্রাথমিক value হিসেবে `None` ব্যবহার করা যায়।

Example:

```python
username = None

if username is None:
    print("Username has not been provided.")
```

Output:

```text
Username has not been provided.
```

এখানে `None` বোঝাচ্ছে যে username এখনো দেওয়া হয়নি।

### Optional Function Parameter

```python
def greet(name=None):
    if name is None:
        print("Hello, Guest!")
    else:
        print("Hello,", name)


greet()
greet("Masum")
```

Output:

```text
Hello, Guest!
Hello, Masum
```

এখানে `name=None` থাকার কারণে function-টি argument ছাড়াও call করা যায়।

প্রথমবার `greet()` call করার সময় `name`-এর value `None`। দ্বিতীয়বার `"Masum"` দেওয়া হয়েছে।

## 9. Functions That Return `None`

Python-এর function যদি কোনো value স্পষ্টভাবে `return` না করে, তাহলে function call-এর result হয় `None`।

Example:

```python
def greet():
    print("Hello, Python!")


result = greet()

print(result)
```

Output:

```text
Hello, Python!
None
```

এখানে দুটি বিষয় ঘটেছে:

1. `greet()` function `"Hello, Python!"` print করেছে।
2. Function-টি কোনো value return করেনি, তাই `result`-এ `None` রাখা হয়েছে।

### Explicitly Returning `None`

Function থেকে স্পষ্টভাবেও `None` return করা যায়।

```python
def get_result():
    return None


result = get_result()

print(result)
```

Output:

```text
None
```

এখানে `return None` দিয়ে function-এর result স্পষ্টভাবে `None` করা হয়েছে।

**গুরুত্বপূর্ণ:** `print()` এবং `return` এক জিনিস নয়। `print()` screen-এ output দেখায়, আর `return` function থেকে value পাঠায়।

## 10. `None` in Conditional Statements

`None` ব্যবহার করে কোনো value পাওয়া গেছে কি না পরীক্ষা করা যায়।

```python
user = None

if user is None:
    print("User not found.")
else:
    print("User found.")
```

Output:

```text
User not found.
```

যদি `user`-এর মধ্যে কোনো value assign করা হয়:

```python
user = "Masum"

if user is None:
    print("User not found.")
else:
    print("User found.")
```

Output:

```text
User found.
```

এখানে `None` একটি missing value বোঝাতে ব্যবহৃত হয়েছে।

## 11. `None` and Truthiness

`None` একটি falsy value।

```python
value = None

print(bool(value))
```

Output:

```text
False
```

কিন্তু সব falsy value-কে `None` হিসেবে বিবেচনা করা ঠিক নয়।

```python
values = [None, False, 0, "", [], {}]

for value in values:
    print(value, bool(value))
```

Output:

```text
None False
False False
0 False
 False
[] False
{} False
```

এই উদাহরণে সব value-এর Boolean result `False`, কিন্তু সব value `None` নয়।

তাই নিচের check-গুলো এক নয়:

```python
value = 0

print(value is None)
print(not value)
```

Output:

```text
False
True
```

`value is None` পরীক্ষা করে value-টি `None` কি না। অন্যদিকে `not value` পরীক্ষা করে value-টি falsy কি না।

**Best Practice:** শুধু `None` শনাক্ত করতে `is None` ব্যবহার করো। সব falsy value শনাক্ত করতে চাইলে `if not value` ব্যবহার করা যেতে পারে—তবে সেটি প্রয়োজন অনুযায়ী সঠিক কি না নিশ্চিত হতে হবে।

## 12. `None` in Lists and Dictionaries

List এবং dictionary-এর মধ্যেও `None` রাখা যায়।

### In a List

```python
students = ["Masum", None, "Ritu"]

print(students)
print(students[1] is None)
```

Output:

```text
['Masum', None, 'Ritu']
True
```

এখানে দ্বিতীয় element-এ `None` রয়েছে, যা অনুপস্থিত বা এখনো নির্ধারিত নয় এমন value বোঝাতে পারে।

### In a Dictionary

```python
student = {
    "name": "Masum",
    "phone": None
}

print(student["name"])
print(student["phone"])
```

Output:

```text
Masum
None
```

এখানে phone number-এর value দেওয়া হয়নি, তাই `None` ব্যবহার করা হয়েছে।

**মনে রাখবে:** Dictionary-তে key অনুপস্থিত থাকা এবং key-এর value `None` হওয়া আলাদা বিষয়।

```python
student = {"name": "Masum", "phone": None}

print("phone" in student)
print("email" in student)
```

Output:

```text
True
False
```

`phone` key আছে, কিন্তু তার value `None`। `email` key-টি dictionary-তে নেই।

## 13. Common Beginner Mistakes

### Mistake 1: Writing `none` Instead of `None`

```python
value = none
```

এটি `NameError` তৈরি করবে, যদি `none` নামে কোনো variable define করা না থাকে।

সঠিক:

```python
value = None
```

### Mistake 2: Using `==` Instead of `is` for a `None` Check

```python
if value == None:
    print("Missing")
```

এটি সাধারণ ক্ষেত্রে কাজ করলেও `None` check করার recommended style হলো:

```python
if value is None:
    print("Missing")
```

### Mistake 3: Treating All Falsy Values as `None`

```python
value = 0

if value is None:
    print("No value")
else:
    print("Value exists")
```

Output:

```text
Value exists
```

কারণ `0` হলো integer, `None` নয়।

### Mistake 4: Expecting `print()` to Return the Printed Value

```python
result = print("Hello")

print(result)
```

Output:

```text
Hello
None
```

`print()` output দেখায়, কিন্তু এর return value হলো `None`।

### Mistake 5: Performing Arithmetic with `None`

```python
value = None

print(value + 10)
```

এটি `TypeError` তৈরি করবে। `None`-কে integer ধরে arithmetic করা যায় না।

প্রয়োজনে আগে check করো:

```python
value = None

if value is not None:
    print(value + 10)
else:
    print("Value is not available.")
```

Output:

```text
Value is not available.
```

## 14. Practice Exercises

### Exercise 1: Identify the Types

নিচের code-এর output অনুমান করো:

```python
print(type(None))
print(type(False))
print(type(0))
print(type(""))
```

প্রতিটি value-এর type কেন আলাদা, ব্যাখ্যা করো।

### Exercise 2: Compare Values

```python
a = None
b = False
c = 0
d = ""

print(a is None)
print(b is None)
print(c is None)
print(d is None)
```

Output অনুমান করো।

### Exercise 3: `is None` vs `not`

```python
value = 0

print(value is None)
print(not value)
```

দুটি result কেন আলাদা, তা ব্যাখ্যা করো।

### Exercise 4: Function Return Value

```python
def show_message():
    print("Welcome")


result = show_message()

print(result)
```

Output কী হবে এবং কেন হবে?

### Exercise 5: Optional Parameter

একটি `greet()` function লেখো, যেখানে `name`-এর default value `None` থাকবে। Name দেওয়া না হলে `"Hello, Guest!"` এবং name দেওয়া হলে `"Hello, [name]!"` print করবে।

### Exercise 6: Dictionary Value Check

```python
student = {
    "name": "Masum",
    "email": None
}
```

পরীক্ষা করো:

1. `"email"` key আছে কি না।
2. `"email"`-এর value `None` কি না।
3. `"phone"` key আছে কি না।

### Exercise 7: Mini Project — Optional Marks Checker

একটি program লেখো, যেখানে `marks = None` দিয়ে শুরু হবে।

- Marks `None` হলে `"Marks not available"` print করবে।
- Marks দেওয়া থাকলে marks print করবে।
- Marks `0` হলে সেটিকে missing value হিসেবে গণ্য করবে না।

## 15. Key Takeaways

- `None` হলো Python-এর special value।
- `None`-এর type হলো `NoneType`।
- `None`, `False`, `0`, `""` এবং empty collection এক জিনিস নয়।
- `None` check করার জন্য `is None` এবং `is not None` ব্যবহার করা উচিত।
- কোনো function স্পষ্টভাবে value return না করলে সেটি `None` return করে।
- `print()` output দেখায়, কিন্তু নিজে `None` return করে।
- Function parameter-এর default value হিসেবে `None` ব্যবহার করা যায়।
- `if not value` সব falsy value শনাক্ত করে; শুধু `None` শনাক্ত করে না।
- Dictionary-তে key অনুপস্থিত থাকা এবং key-এর value `None` হওয়া আলাদা।

## 16. Next Topic

পরবর্তী ফাইল:

**`13_Truthy_and_Falsy_Values.md`**

সেখানে Python-এর truth-value testing, truthy ও falsy value, empty collection, এবং conditional expression-এ এগুলোর ব্যবহার আরও বিস্তারিতভাবে শেখা হবে।