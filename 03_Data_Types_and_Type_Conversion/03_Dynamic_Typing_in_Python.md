# 03. Dynamic Typing in Python

## 1. What Is Dynamic Typing?

**Dynamic Typing** হলো এমন একটি বৈশিষ্ট্য, যেখানে variable-এর data type আগে থেকে declare করতে হয় না। Program চলার সময় variable যে object-কে refer করে, তার type অনুযায়ী Python কাজ করে।

Python একটি dynamically typed programming language।

Example:

```python
x = 100

print(x)
print(type(x))
```

Output:

```text
100
<class 'int'>
```

এখানে `x`-এর জন্য আলাদাভাবে `int` declare করতে হয়নি। Python বুঝতে পেরেছে যে `100` একটি integer।

এবার variable-টিতে string assign করি:

```python
x = "Python"

print(x)
print(type(x))
```

Output:

```text
Python
<class 'str'>
```

এখন `x` একটি string object-কে refer করছে।

**মনে রাখবে:** Python-এ variable-এর type স্থায়ীভাবে নির্ধারিত থাকে না; variable অন্য type-এর object-কে refer করতে পারে।

## 2. How Does Dynamic Typing Work?

Python-এ variable এবং object-এর মধ্যে সম্পর্ক বুঝতে হবে।

সহজভাবে:

- **Object:** Memory-তে থাকা value এবং তার সংশ্লিষ্ট information।
- **Variable:** Object-কে access করার জন্য ব্যবহৃত একটি নাম।
- **Type:** Object কী ধরনের এবং তার কী ধরনের behavior আছে, তা নির্ধারণ করে।

Example:

```python
x = 50
```

এই statement execute হলে `x` নামটি integer object `50`-কে refer করে।

এবার:

```python
x = "Hello"
```

এখন `x` string object `"Hello"`-কে refer করে।

এখানে variable `x`-এর type আলাদাভাবে পরিবর্তন করা হয়নি। বরং `x` এখন অন্য type-এর object-কে refer করছে।

এটি বোঝার জন্য নিচের example দেখো:

```python
value = 25
print(type(value))

value = 3.14
print(type(value))

value = "Python"
print(type(value))

value = True
print(type(value))
```

Output:

```text
<class 'int'>
<class 'float'>
<class 'str'>
<class 'bool'>
```

একই variable name ব্যবহার করে ভিন্ন type-এর object assign করা হয়েছে।

## 3. Dynamic Typing vs Static Typing

Programming language-এর typing system সাধারণভাবে বোঝার জন্য Dynamic Typing এবং Static Typing-এর পার্থক্য জানা প্রয়োজন।

| Dynamic Typing | Static Typing |
|---|---|
| Variable-এর type আলাদাভাবে declare করা সাধারণত প্রয়োজন হয় না | সাধারণত type declaration বা type annotation প্রয়োজন হয় |
| Runtime-এ object-এর type অনুযায়ী operation হয় | অনেক type-related error compilation বা static checking-এর সময় শনাক্ত করা যায় |
| Python একটি dynamically typed language | C ও Java সাধারণভাবে statically typed language |
| Variable ভিন্ন type-এর object-কে refer করতে পারে | Variable-এর declared type সাধারণত নির্দিষ্ট থাকে |

উদাহরণ হিসেবে Python:

```python
value = 10
value = "Hello"
```

Python-এ এটি valid।

Java-তে একই `int` variable-এ সরাসরি string assign করা যাবে না:

```java
int value = 10;
// value = "Hello"; // Type error
```

**Important:** Static typing থাকলেই সব error compile time-এ ধরা পড়বে, এমন নয়। আবার dynamic typing থাকলেই type-related error হবেই, এমনও নয়। Language-এর type system এবং checking-এর নিয়ম অনুযায়ী বিষয়টি নির্ধারিত হয়।

## 4. Dynamic Typing Does Not Mean No Types

এটি beginners-এর একটি সাধারণ ভুল ধারণা।

Dynamic typing-এর অর্থ Python-এ data type নেই—এমন নয়। Python-এ প্রতিটি object-এর type থাকে।

Example:

```python
a = 10
b = "10"

print(type(a))
print(type(b))
```

Output:

```text
<class 'int'>
<class 'str'>
```

এখানে `a` integer object-কে এবং `b` string object-কে refer করছে।

তাদের দেখতে একই রকম মনে হলেও তাদের type আলাদা।

আরেকটি example:

```python
number = "100"

print(number + "20")
```

Output:

```text
10020
```

কিন্তু:

```python
number = "100"

print(number + 20)
```

এখানে `TypeError` হবে, কারণ Python সাধারণভাবে string এবং integer-কে `+` দিয়ে একসঙ্গে যোগ করতে পারে না।

অর্থাৎ, Python dynamically typed হলেও operation-এর ক্ষেত্রে type compatibility গুরুত্বপূর্ণ।

## 5. Variable Reassignment in Dynamic Typing

একটি variable-এ নতুন value assign করাকে **Reassignment** বলা হয়।

Dynamic typing-এর কারণে reassignment-এর সময় variable অন্য type-এর object-কে refer করতে পারে।

Example:

```python
data = 10
print(data, type(data))

data = 20
print(data, type(data))

data = "Python"
print(data, type(data))
```

Output:

```text
10 <class 'int'>
20 <class 'int'>
Python <class 'str'>
```

প্রথমে `data` integer object `10`-কে refer করেছে। পরে integer `20` এবং শেষে string `"Python"`-কে refer করেছে।

Reassignment-এর সময় আগের object অন্য কোনো variable দিয়ে refer করা না থাকলে এবং program-এর অন্য কোনো অংশে ব্যবহারযোগ্য না থাকলে Python-এর memory management সেটিকে পরে পরিষ্কার করতে পারে।

## 6. Multiple Variables Can Refer to the Same Object

Python-এ একাধিক variable একই object-কে refer করতে পারে।

Example:

```python
a = 100
b = a

print(a)
print(b)
```

Output:

```text
100
100
```

এখানে `b = a` করার ফলে `b`-ও একই integer object-কে refer করে।

এবার:

```python
a = 200

print(a)
print(b)
```

Output:

```text
200
100
```

`a`-কে নতুন object assign করা হয়েছে। কিন্তু `b` আগের integer object `100`-কেই refer করছে।

এখানে মনে রাখতে হবে, immutable integer object-কে পরিবর্তন করা হয়নি। শুধু variable `a`-এর reference নতুন object-এর দিকে গেছে।

## 7. Dynamic Typing with Mutable Objects

Mutable object-এর ক্ষেত্রে একই object একাধিক variable দিয়ে refer করলে বিষয়টি একটু আলাদা হতে পারে।

Example:

```python
a = [10, 20]
b = a

a.append(30)

print(a)
print(b)
```

Output:

```text
[10, 20, 30]
[10, 20, 30]
```

কেন এমন হলো?

1. `a` একটি list object-কে refer করে।
2. `b = a` করার ফলে `b` একই list object-কে refer করে।
3. `a.append(30)` একই list object-কে পরিবর্তন করে।
4. তাই `a` এবং `b`—দুটির মাধ্যমে পরিবর্তিত list দেখা যায়।

এবার reassignment দেখো:

```python
a = [10, 20]
b = a

a = [100, 200]

print(a)
print(b)
```

Output:

```text
[100, 200]
[10, 20]
```

এবার `a`-কে নতুন list object assign করা হয়েছে। `b` এখনো আগের list object-কে refer করছে।

**মূল পার্থক্য:**

- `a.append(30)` আগের list object-কে পরিবর্তন করে।
- `a = [100, 200]` variable `a`-কে নতুন list object-এর সঙ্গে যুক্ত করে।

## 8. Dynamic Typing and Function Arguments

Python function-এ argument-এর type সাধারণত আগে থেকে declare করা বাধ্যতামূলক নয়।

Example:

```python
def display(value):
    print(value)
    print(type(value))


display(100)
display("Python")
display(3.14)
```

Output:

```text
100
<class 'int'>
Python
<class 'str'>
3.14
<class 'float'>
```

একই function ভিন্ন type-এর argument গ্রহণ করেছে।

তবে function-এর ভিতরে কোন operation করা হচ্ছে, তার ওপর নির্ভর করে সব type-এর argument গ্রহণ করা সম্ভব হবে কি না।

Example:

```python
def add_five(value):
    return value + 5


print(add_five(10))
```

Output:

```text
15
```

কিন্তু:

```python
print(add_five("10"))
```

এখানে `TypeError` হবে, কারণ string-এর সঙ্গে integer যোগ করা যাচ্ছে না।

অর্থাৎ, dynamic typing flexible হলেও function-এর expected input এবং supported operations বোঝা গুরুত্বপূর্ণ।

## 9. Type Hints Do Not Remove Dynamic Typing

Python-এ type hints ব্যবহার করে programmer জানাতে পারেন, কোনো variable বা function-এর জন্য কী ধরনের type প্রত্যাশিত।

Example:

```python
age: int = 22
```

এখানে `int` হলো type hint।

Function-এর ক্ষেত্রেও ব্যবহার করা যায়:

```python
def calculate_square(number: int) -> int:
    return number * number
```

এখানে:

- `number: int` বোঝায় `number`-এর জন্য integer প্রত্যাশিত।
- `-> int` বোঝায় function-এর return value integer হওয়ার কথা।

তবে Python সাধারণভাবে type hint-গুলো নিজে থেকে enforce করে না।

```python
age: int = "twenty"
print(age)
```

সাধারণ Python execution-এ এই code চলবে, যদিও type hint-এর সঙ্গে value মেলে না। Static type checker এমন mismatch শনাক্ত করতে পারে।

Type hints-এর বিস্তারিত আলোচনা থাকবে পরবর্তী advanced chapter-এ।

## 10. Advantages of Dynamic Typing

Dynamic typing-এর কয়েকটি সুবিধা:

### 10.1 Less Boilerplate Code

প্রতিটি variable-এর type আলাদাভাবে declare করতে হয় না।

```python
name = "Masum"
age = 22
```

### 10.2 Flexibility

একই variable বিভিন্ন সময়ে ভিন্ন type-এর object-কে refer করতে পারে।

```python
value = 10
value = "Hello"
```

### 10.3 Faster Prototyping

ছোট program, experiment এবং prototype দ্রুত লেখা যায়।

### 10.4 Easy to Start Learning

শুরুতে type declaration নিয়ে বেশি চিন্তা না করে programming logic শেখা যায়।

## 11. Limitations of Dynamic Typing

Dynamic typing-এর কিছু সীমাবদ্ধতাও আছে।

### 11.1 Runtime Type Errors

কিছু type-related error program execute করার সময় দেখা দেয়।

```python
age = "22"
print(age + 5)
```

এখানে `TypeError` হবে।

### 11.2 Type May Be Less Obvious

কোনো variable কী ধরনের value ধারণ করবে, তা শুধু তার নাম দেখে সবসময় বোঝা যায় না।

### 11.3 Large Projects Need Clear Contracts

বড় project-এ function-এর expected input ও output পরিষ্কার না হলে code বোঝা কঠিন হতে পারে।

এ সমস্যা কমাতে descriptive naming, documentation, tests এবং type hints ব্যবহার করা যায়।

## 12. Common Beginner Mistakes

### Mistake 1: Variable-এর Type স্থায়ী মনে করা

```python
value = 10
value = "Python"

print(value)
```

Output:

```text
Python
```

Python-এ variable অন্য type-এর object-কে refer করতে পারে।

### Mistake 2: Dynamic Typing মানে Automatic Conversion মনে করা

```python
age = "22"

print(age + 5)
```

এখানে `TypeError` হবে। Python নিজে থেকে `"22"`-কে integer-এ convert করবে না।

সঠিক:

```python
age = int("22")
print(age + 5)
```

Output:

```text
27
```

### Mistake 3: Assignment-কে Object Modification মনে করা

```python
a = [1, 2]
b = a

a = [3, 4]

print(b)
```

Output:

```text
[1, 2]
```

`a`-কে নতুন list assign করা হয়েছে। আগের list-টি `b` refer করছে বলে সেটি অপরিবর্তিত রয়েছে।

### Mistake 4: Type Hint-কে Automatic Enforcement মনে করা

```python
age: int = "22"
```

Python-এর সাধারণ execution-এ এটি স্বয়ংক্রিয়ভাবে `TypeError` তৈরি করে না। Type checker-এর সাহায্যে এমন mismatch শনাক্ত করা যেতে পারে।

## 13. Practice Exercises

### Exercise 1: Predict the Output

```python
value = 10
print(type(value))

value = "Python"
print(type(value))

value = 5.5
print(type(value))
```

প্রতিটি line-এর output আগে লিখে তারপর code execute করো।

### Exercise 2: Understand Reassignment

```python
x = 100
y = x

x = "Hello"

print(x)
print(y)
```

প্রশ্ন:

1. `x` কী print করবে?
2. `y` কী print করবে?
3. কেন তাদের output আলাদা?

### Exercise 3: Mutable Object Behavior

```python
first = [1, 2, 3]
second = first

second.append(4)

print(first)
print(second)
```

দুটি variable-এর output কেন একই, তা নিজের ভাষায় ব্যাখ্যা করো।

### Exercise 4: Fix the Type Error

```python
number = "50"
result = number + 10

print(result)
```

Program-টিকে এমনভাবে সংশোধন করো, যাতে result হয় `60`।

### Exercise 5: Function and Dynamic Typing

একটি `show_type()` function লেখো, যা যেকোনো argument গ্রহণ করবে এবং তার value ও type print করবে।

Function-টি দিয়ে integer, string, float এবং Boolean value পরীক্ষা করো।

### Exercise 6: Type Hints

নিচের function-এ উপযুক্ত type hints যোগ করো:

```python
def multiply(a, b):
    return a * b
```

তারপর ব্যাখ্যা করো, type hints কী কাজে লাগে এবং Python নিজে থেকে এগুলো enforce করে কি না।

## 14. Key Takeaways

- Python একটি dynamically typed language।
- Variable-এর type আগে থেকে declare করা বাধ্যতামূলক নয়।
- Variable হলো object-কে access করার নাম; object-এর নিজস্ব type থাকে।
- একই variable ভিন্ন সময়ে ভিন্ন type-এর object-কে refer করতে পারে।
- Dynamic typing মানে Python-এ type নেই—এমন নয়।
- Python সব incompatible type-কে automatically convert করে না।
- একাধিক variable একই object-কে refer করতে পারে।
- Mutable object পরিবর্তন করলে একই object-কে refer করা অন্য variable-এর মাধ্যমেও পরিবর্তন দেখা যেতে পারে।
- Type hints code-এর intended types বোঝাতে সাহায্য করে, কিন্তু সাধারণ Python execution-এ নিজে থেকে enforce হয় না।
- Dynamic typing flexible, তবে reliable code-এর জন্য clear logic, tests এবং type awareness প্রয়োজন।

## 15. Next Topic

পরবর্তী ফাইল:

**`04_Type_Checking_with_type.md`**

সেখানে আমরা `type()` function বিস্তারিতভাবে শিখব—কীভাবে object-এর type দেখা যায়, কীভাবে output বুঝতে হয় এবং type checking-এর ক্ষেত্রে এর সীমাবদ্ধতা কী।