# 11. Boolean Data Type in Python

## 1. What Is a Boolean?

Python-এ **Boolean (`bool`) হলো এমন একটি data type, যার মাত্র দুটি value রয়েছে: `True` এবং `False`।**

কোনো condition সত্য নাকি মিথ্যা, তা প্রকাশ করতে Boolean ব্যবহার করা হয়।

Example:

```python
is_student = True
is_graduated = False

print(is_student)
print(is_graduated)
```

Output:

```text
True
False
```

এখানে `is_student`-এর value `True`, কারণ এটি সত্য বোঝাচ্ছে। অন্যদিকে `is_graduated`-এর value `False`।

Boolean-এর type পরীক্ষা করা যায় `type()` দিয়ে।

```python
print(type(True))
print(type(False))
```

Output:

```text
<class 'bool'>
<class 'bool'>
```

**মনে রাখবে:** Python-এ Boolean value লেখার সময় প্রথম অক্ষর Capital হতে হবে।

```python
print(True)
print(False)
```

`true`, `false`, `TRUE` বা `FALSE` Python-এর Boolean literal নয়।

## 2. Boolean Values: `True` and `False`

Boolean value সাধারণত কোনো প্রশ্নের উত্তর বা condition-এর result প্রকাশ করে।

Example:

```python
print(10 > 5)
print(10 < 5)
print(10 == 10)
print(10 != 10)
```

Output:

```text
True
False
True
False
```

ব্যাখ্যা:

- `10 > 5` সত্য, তাই `True`।
- `10 < 5` মিথ্যা, তাই `False`।
- `10 == 10` সত্য, তাই `True`।
- `10 != 10` মিথ্যা, তাই `False`।

এখানে comparison operator-গুলো Boolean result তৈরি করে।

## 3. Boolean Variables

Boolean value variable-এর মধ্যে সংরক্ষণ করা যায়।

```python
is_raining = True
is_sunny = False

print(is_raining)
print(is_sunny)
```

Output:

```text
True
False
```

Boolean variable সাধারণত `is_`, `has_`, `can_` বা `should_`-এর মতো নাম দিয়ে লেখা হয়, যাতে variable-এর অর্থ সহজে বোঝা যায়।

Example:

```python
is_logged_in = True
has_permission = False
can_access = True
```

এই ধরনের naming convention code পড়তে সুবিধা দেয়।

## 4. Boolean from Comparison Operators

Comparison operator দুটি value-এর মধ্যে সম্পর্ক পরীক্ষা করে এবং Boolean result দেয়।

| Operator | Meaning | Example | Result |
|---|---|---|---|
| `==` | Equal to | `5 == 5` | `True` |
| `!=` | Not equal to | `5 != 3` | `True` |
| `>` | Greater than | `8 > 4` | `True` |
| `<` | Less than | `2 < 7` | `True` |
| `>=` | Greater than or equal to | `5 >= 5` | `True` |
| `<=` | Less than or equal to | `3 <= 2` | `False` |

Example:

```python
age = 22

print(age >= 18)
print(age < 18)
print(age == 22)
print(age != 22)
```

Output:

```text
True
False
True
False
```

এই operator-গুলো পরবর্তী সময়ে `if`, `while` এবং অন্যান্য conditional logic-এ ব্যবহার করা হবে।

## 5. Boolean from Logical Operators

Python-এ তিনটি প্রধান logical operator রয়েছে:

- `and`
- `or`
- `not`

এগুলো এক বা একাধিক condition নিয়ে কাজ করতে পারে।

### 5.1 The `and` Operator

`and`-এর ক্ষেত্রে সব condition সত্য হলে result `True` হয়।

| A | B | `A and B` |
|---|---|---|
| `True` | `True` | `True` |
| `True` | `False` | `False` |
| `False` | `True` | `False` |
| `False` | `False` | `False` |

Example:

```python
age = 22
has_id = True

print(age >= 18 and has_id)
```

Output:

```text
True
```

এখানে বয়সের condition এবং `has_id`—দুটিই সত্য, তাই result `True`।

### 5.2 The `or` Operator

`or`-এর ক্ষেত্রে অন্তত একটি condition সত্য হলে result `True` হয়।

| A | B | `A or B` |
|---|---|---|
| `True` | `True` | `True` |
| `True` | `False` | `True` |
| `False` | `True` | `True` |
| `False` | `False` | `False` |

Example:

```python
is_weekend = False
is_holiday = True

print(is_weekend or is_holiday)
```

Output:

```text
True
```

এখানে holiday condition সত্য, তাই পুরো expression-এর result `True`।

### 5.3 The `not` Operator

`not` একটি Boolean result-কে উল্টে দেয়।

| A | `not A` |
|---|---|
| `True` | `False` |
| `False` | `True` |

Example:

```python
is_logged_in = False

print(not is_logged_in)
```

Output:

```text
True
```

কারণ `is_logged_in`-এর value `False`, তাই `not` ব্যবহার করলে result হয় `True`।

## 6. Converting Values to Boolean with `bool()`

Python-এর built-in `bool()` function কোনো value-কে Boolean-এ রূপান্তর করে।

```python
print(bool(1))
print(bool(0))
print(bool("Hello"))
print(bool(""))
```

Output:

```text
True
False
True
False
```

সাধারণভাবে, কোনো value-কে Boolean-এ রূপান্তর করলে:

- **Falsy value** হলে `False` পাওয়া যায়।
- **Truthy value** হলে `True` পাওয়া যায়।

## 7. Truthy and Falsy Values

Python-এ কিছু value স্বাভাবিকভাবেই `False` হিসেবে বিবেচিত হয়। এগুলোকে **Falsy values** বলা হয়। অন্যদিকে যেসব value `True` হিসেবে বিবেচিত হয়, সেগুলো **Truthy values**।

প্রচলিত Falsy values:

| Value | Boolean result |
|---|---|
| `False` | `False` |
| `None` | `False` |
| `0` | `False` |
| `0.0` | `False` |
| `0j` | `False` |
| `""` | `False` |
| `[]` | `False` |
| `()` | `False` |
| `{}` | `False` |
| `set()` | `False` |

Example:

```python
print(bool(0))
print(bool(""))
print(bool([]))
print(bool(None))
```

Output:

```text
False
False
False
False
```

অন্যদিকে:

```python
print(bool(10))
print(bool(-5))
print(bool("Python"))
print(bool([1, 2]))
```

Output:

```text
True
True
True
True
```

**গুরুত্বপূর্ণ:** `"False"` একটি non-empty String, তাই `bool("False")`-এর result `True`। Python String-এর ভেতরের লেখা দেখে Boolean নির্ধারণ করে না; String খালি কি না, সেটি দেখে।

```python
print(bool("False"))
print(bool("0"))
```

Output:

```text
True
True
```

## 8. Boolean and Numeric Values

Python-এ `bool` হলো `int`-এর একটি subclass।

এই কারণে:

```python
print(isinstance(True, int))
print(isinstance(False, int))
```

Output:

```text
True
True
```

Python-এ Boolean value-এর numeric behavior-ও রয়েছে:

```python
print(True + True)
print(True + False)
print(False * 10)
```

Output:

```text
2
1
0
```

এখানে:

- `True` numeric context-এ `1`-এর মতো আচরণ করে।
- `False` numeric context-এ `0`-এর মতো আচরণ করে।

তবে সাধারণ program-এ Boolean-এর উদ্দেশ্য হলো সত্য-মিথ্যা প্রকাশ করা। তাই প্রয়োজন ছাড়া Boolean-কে সংখ্যা হিসেবে ব্যবহার না করাই ভালো।

### Comparing `bool` and `int`

```python
print(True == 1)
print(False == 0)

print(type(True))
print(type(1))
```

Output:

```text
True
True
<class 'bool'>
<class 'int'>
```

Numeric equality `True` হলেও `bool` এবং `int` আলাদা type।

## 9. Boolean in Conditional Logic

Boolean condition program-কে সিদ্ধান্ত নিতে সাহায্য করে।

Example:

```python
age = 20

if age >= 18:
    print("You are an adult.")
```

Output:

```text
You are an adult.
```

এখানে `age >= 18` expression-এর result `True`, তাই `if`-এর body execute হয়েছে।

আরেকটি উদাহরণ:

```python
is_logged_in = False

if is_logged_in:
    print("Welcome!")
else:
    print("Please log in.")
```

Output:

```text
Please log in.
```

এখানে condition `False`, তাই `else`-এর body execute হয়েছে।

`if` এবং `else`-এর বিস্তারিত ব্যবহার পরবর্তী Conditional Statements chapter-এ শেখা হবে।

## 10. Boolean with User Input

Python-এর `input()` function সবসময় String return করে। তাই user-এর কাছ থেকে `"True"` বা `"False"` লেখা নিলেই স্বয়ংক্রিয়ভাবে Boolean পাওয়া যায় না।

Example:

```python
answer = input("Are you a student? ")

print(answer)
print(type(answer))
```

User যদি `False` লেখে, Output হবে:

```text
Are you a student? False
False
<class 'str'>
```

এখানে `False` দেখতে Boolean-এর মতো হলেও এটি String।

### Converting User Input to Boolean Safely

User-এর input-কে সরাসরি `bool()` দিয়ে convert করা ঠিক নয়।

```python
answer = input("Are you a student? ")

print(bool(answer))
```

User যদি `False` লেখে, result হবে:

```text
True
```

কারণ `"False"` একটি non-empty String।

এর পরিবর্তে input-এর text পরীক্ষা করা যায়:

```python
answer = input("Are you a student? ").strip().lower()

if answer == "true":
    is_student = True
elif answer == "false":
    is_student = False
else:
    is_student = None

print(is_student)
```

এখানে:

- User `true` বা `True` লিখলে `True` হবে।
- User `false` বা `False` লিখলে `False` হবে।
- অন্য কিছু লিখলে `None` হবে, যা invalid input বোঝাতে ব্যবহার করা হয়েছে।

এই উদাহরণে `None` ব্যবহার করা হয়েছে কারণ invalid input-কে ভুলভাবে `True` বা `False` হিসেবে ধরে নেওয়া উচিত নয়।

## 11. Short-Circuit Evaluation

Python-এর `and` এবং `or` operator **short-circuit evaluation** ব্যবহার করে।

এর অর্থ, result নির্ধারণ করার জন্য যথেষ্ট তথ্য পাওয়া গেলে Python বাকি expression evaluate নাও করতে পারে।

### Example with `and`

```python
print(False and (10 / 0))
```

Output:

```text
False
```

এখানে প্রথম operand `False`, তাই `and`-এর result আর `True` হতে পারে না। ফলে `(10 / 0)` evaluate করা হয় না এবং `ZeroDivisionError` হয় না।

### Example with `or`

```python
print(True or (10 / 0))
```

Output:

```text
True
```

এখানে প্রথম operand `True`, তাই `or`-এর result ইতিমধ্যেই `True`। দ্বিতীয় expression evaluate করার প্রয়োজন হয় না।

**মনে রাখবে:** `and` ও `or` সব সময় `bool` return করে না; এগুলো যে operand-টি result নির্ধারণ করে, সেই operand-টিও return করতে পারে।

```python
print(5 and 10)
print(0 or 20)
```

Output:

```text
10
20
```

এখানে `5` এবং `20`-এর মতো value-গুলো truthiness অনুযায়ী বিবেচিত হয়েছে।

## 12. Common Beginner Mistakes

### Mistake 1: Writing `true` Instead of `True`

```python
is_active = true
```

এটি `NameError` তৈরি করবে, কারণ `true` নামে কোনো variable আগে define করা হয়নি।

সঠিক:

```python
is_active = True
```

### Mistake 2: Confusing `=` and `==`

- `=` value assign করে।
- `==` দুটি value সমান কি না পরীক্ষা করে।

```python
age = 20

print(age == 20)
```

Output:

```text
True
```

### Mistake 3: Using `bool()` Directly on Text Input

```python
answer = "False"

print(bool(answer))
```

Output:

```text
True
```

কারণ String-টি খালি নয়।

### Mistake 4: Confusing `and` with `or`

```python
print(True and False)
print(True or False)
```

Output:

```text
False
True
```

`and`-এর জন্য সব condition সত্য হতে হয়; `or`-এর জন্য অন্তত একটি condition সত্য হলেই হয়।

### Mistake 5: Assuming `and` and `or` Always Return Boolean

```python
print("Python" and "Java")
print("" or "Python")
```

Output:

```text
Java
Python
```

কারণ Python truthiness অনুযায়ী operand return করে।

## 13. Practice Exercises

### Exercise 1: Boolean Basics

নিচের code-এর output অনুমান করো:

```python
print(type(True))
print(type(False))
print(10 > 5)
print(10 == 5)
print(7 != 3)
```

### Exercise 2: Comparison Operators

একটি `age` variable তৈরি করো। পরীক্ষা করো:

- বয়স ১৮ বা তার বেশি কি না।
- বয়স ৩০-এর কম কি না।
- বয়স ঠিক ২০ কি না।

### Exercise 3: Logical Operators

```python
a = True
b = False

print(a and b)
print(a or b)
print(not a)
print(not b)
```

Output নির্ণয় করো।

### Exercise 4: Truthy and Falsy

নিচের প্রতিটি value-এর `bool()` result বের করো:

```python
print(bool(0))
print(bool(-1))
print(bool(""))
print(bool("False"))
print(bool([]))
print(bool([0]))
print(bool(None))
```

প্রতিটি result-এর কারণ ব্যাখ্যা করো।

### Exercise 5: User Eligibility Checker

একটি program লেখো, যেখানে:

- `age` variable-এ বয়স থাকবে।
- `has_id` variable-এ Boolean value থাকবে।
- বয়স অন্তত ১৮ এবং `has_id` সত্য হলে eligibility `True` হবে।
- অন্যথায় eligibility `False` হবে।

### Exercise 6: Short-Circuit Evaluation

নিচের code-গুলোর output এবং কারণ ব্যাখ্যা করো:

```python
print(False and (1 / 0))
print(True or (1 / 0))
print(5 and 10)
print(0 or 10)
```

### Exercise 7: Mini Project — Login Status Checker

একটি program লেখো, যেখানে:

- `username` একটি String।
- `password_correct` একটি Boolean।
- Username খালি না হলে এবং password সঠিক হলে login successful দেখাবে।
- অন্যথায় login failed দেখাবে।

এখানে `and` operator ব্যবহার করো।

## 14. Key Takeaways

- Boolean-এর দুটি value: `True` এবং `False`।
- Boolean-এর type হলো `bool`।
- Comparison operator সাধারণত Boolean result দেয়।
- `and`, `or` এবং `not` logical operation-এর জন্য ব্যবহৃত হয়।
- `bool()` কোনো value-কে truthy বা falsy অনুযায়ী Boolean-এ convert করে।
- `0`, `None`, empty String এবং empty collection সাধারণত falsy।
- `"False"`-এর মতো non-empty String truthy।
- Python-এ `bool` হলো `int`-এর subclass।
- `and` ও `or` short-circuit evaluation ব্যবহার করে এবং Boolean ছাড়াও operand return করতে পারে।
- `input()` String return করে; তাই text থেকে Boolean তৈরি করতে input validation প্রয়োজন।

## 15. Next Topic

পরবর্তী ফাইল:

**`12_NoneType_and_None.md`**

সেখানে `None`, `NoneType`, missing value, function-এর return value এবং `None`-এর সঙ্গে সঠিক comparison শেখা হবে।