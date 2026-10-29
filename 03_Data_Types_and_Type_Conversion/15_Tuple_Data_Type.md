# 15. Tuple Data Type in Python

## 1. What Is a Tuple?

Python-এ **Tuple হলো একটি built-in collection data type, যা একটি variable-এর মধ্যে একাধিক item সংরক্ষণ করতে পারে।**

Tuple দেখতে List-এর মতো হলেও প্রধান পার্থক্য হলো, **Tuple immutable**। অর্থাৎ Tuple তৈরি হওয়ার পর এর item সরাসরি পরিবর্তন, যোগ বা বাদ দেওয়া যায় না।

Tuple তৈরি করতে সাধারণত parentheses `()` ব্যবহার করা হয়।

```python
student = ("Masum", 22, 3.95)

print(student)
print(type(student))
```

Output:

```text
('Masum', 22, 3.95)
<class 'tuple'>
```

এখানে `student` একটি Tuple, যার মধ্যে তিনটি item রয়েছে।

## 2. Characteristics of Tuples

Python Tuple-এর গুরুত্বপূর্ণ বৈশিষ্ট্যগুলো হলো:

| Feature | Explanation |
|---|---|
| Ordered | Item-গুলোর নির্দিষ্ট position থাকে |
| Immutable | Tuple-এর item সরাসরি পরিবর্তন করা যায় না |
| Allows duplicates | একই value একাধিকবার থাকতে পারে |
| Allows mixed types | বিভিন্ন data type-এর item রাখা যায় |
| Indexed | Index দিয়ে item access করা যায় |
| Iterable | Loop দিয়ে item-গুলো ব্যবহার করা যায় |
| Supports nesting | Tuple-এর মধ্যে অন্য Tuple বা collection রাখা যায় |

Example:

```python
data = ("Python", 100, 3.5, True, "Python")

print(data)
```

Output:

```text
('Python', 100, 3.5, True, 'Python')
```

এখানে duplicate `"Python"` রয়েছে এবং বিভিন্ন data type-এর value একসঙ্গে রাখা হয়েছে।

## 3. Creating a Tuple

### 3.1 Tuple with Multiple Items

```python
fruits = ("Apple", "Banana", "Mango")

print(fruits)
```

Output:

```text
('Apple', 'Banana', 'Mango')
```

### 3.2 Empty Tuple

কোনো item ছাড়া Tuple তৈরি করতে:

```python
empty = ()

print(empty)
print(type(empty))
```

Output:

```text
()
<class 'tuple'>
```

### 3.3 Tuple with One Item

একটি item-এর Tuple তৈরি করার সময় comma দেওয়া বাধ্যতামূলক।

```python
a = (10,)

print(a)
print(type(a))
```

Output:

```text
(10,)
<class 'tuple'>
```

শুধু parentheses দিলে Tuple তৈরি হয় না।

```python
a = (10)

print(a)
print(type(a))
```

Output:

```text
10
<class 'int'>
```

কারণ এখানে `(10)` শুধু একটি Integer-কে parentheses-এর মধ্যে রেখেছে। এটি Tuple নয়।

**মনে রাখবে:** Single-item Tuple তৈরি করতে item-এর পরে comma দিতে হবে।

```python
a = (10,)
b = ("Python",)
c = (True,)

print(type(a))
print(type(b))
print(type(c))
```

Output:

```text
<class 'tuple'>
<class 'tuple'>
<class 'tuple'>
```

### 3.4 Tuple without Parentheses

Python-এ comma-separated value দিয়েও Tuple তৈরি করা যায়।

```python
student = "Masum", 22, 3.95

print(student)
print(type(student))
```

Output:

```text
('Masum', 22, 3.95)
<class 'tuple'>
```

এটি **Tuple Packing**-এর একটি উদাহরণ।

### 3.5 Using the `tuple()` Constructor

`tuple()` constructor ব্যবহার করে Tuple তৈরি করা যায়।

```python
numbers = tuple([10, 20, 30])

print(numbers)
print(type(numbers))
```

Output:

```text
(10, 20, 30)
<class 'tuple'>
```

এখানে একটি List-কে Tuple-এ রূপান্তর করা হয়েছে।

String থেকে Tuple:

```python
letters = tuple("Python")

print(letters)
```

Output:

```text
('P', 'y', 't', 'h', 'o', 'n')
```

String একটি iterable হওয়ায় এর প্রতিটি character Tuple-এর আলাদা item হয়েছে।

Empty Tuple তৈরির আরেকটি উপায়:

```python
empty = tuple()

print(empty)
```

Output:

```text
()
```

## 4. Accessing Tuple Items with Indexing

Tuple-এর item access করার নিয়ম List-এর মতোই।

Positive indexing `0` থেকে শুরু হয়।

```python
fruits = ("Apple", "Banana", "Mango", "Orange")

print(fruits[0])
print(fruits[1])
print(fruits[2])
```

Output:

```text
Apple
Banana
Mango
```

Negative indexing দিয়েও item access করা যায়।

```python
fruits = ("Apple", "Banana", "Mango", "Orange")

print(fruits[-1])
print(fruits[-2])
```

Output:

```text
Orange
Mango
```

Tuple-এর valid index-এর বাইরে access করলে `IndexError` হয়।

## 5. Finding the Length of a Tuple

`len()` function Tuple-এর মোট item-এর সংখ্যা return করে।

```python
numbers = (10, 20, 30, 40, 50)

print(len(numbers))
```

Output:

```text
5
```

Empty Tuple-এর length হলো `0`।

```python
empty = ()

print(len(empty))
```

Output:

```text
0
```

## 6. Tuple Slicing

Tuple থেকেও slicing ব্যবহার করে নির্দিষ্ট অংশ বের করা যায়।

Syntax:

```python
tuple[start:stop:step]
```

Example:

```python
numbers = (10, 20, 30, 40, 50, 60)

print(numbers[1:4])
print(numbers[:3])
print(numbers[2:])
print(numbers[::2])
print(numbers[::-1])
```

Output:

```text
(20, 30, 40)
(10, 20, 30)
(30, 40, 50, 60)
(10, 30, 50)
(60, 50, 40, 30, 20, 10)
```

Tuple slicing-এর result-ও একটি Tuple হয়।

## 7. Tuple Is Immutable

Tuple-এর সবচেয়ে গুরুত্বপূর্ণ বৈশিষ্ট্য হলো **immutability**।

Tuple তৈরি হওয়ার পর এর item সরাসরি পরিবর্তন করা যায় না।

```python
numbers = (10, 20, 30)

numbers[1] = 200

print(numbers)
```

এই code `TypeError` তৈরি করবে, কারণ Tuple-এর item assignment সমর্থিত নয়।

একইভাবে Tuple-এর মধ্যে সরাসরি নতুন item যোগ বা কোনো item বাদ দেওয়া যায় না।

```python
numbers = (10, 20, 30)

numbers.append(40)
```

এটি `AttributeError` তৈরি করবে, কারণ Tuple-এ `append()` method নেই।

### তাহলে Tuple পরিবর্তন করতে হলে কী করব?

Tuple-এর পরিবর্তে নতুন Tuple তৈরি করা যায়।

```python
numbers = (10, 20, 30)

numbers = numbers + (40,)

print(numbers)
```

Output:

```text
(10, 20, 30, 40)
```

এখানে আগের Tuple-কে পরিবর্তন করা হয়নি। দুটি Tuple যুক্ত করে নতুন Tuple তৈরি করা হয়েছে এবং `numbers`-কে সেটির সঙ্গে bind করা হয়েছে।

## 8. Tuple Packing

**Tuple Packing** হলো একাধিক value-কে একসঙ্গে একটি Tuple হিসেবে রাখা।

```python
student = "Masum", 22, 3.95

print(student)
```

Output:

```text
('Masum', 22, 3.95)
```

এখানে তিনটি value একটি Tuple-এ pack হয়েছে।

Parentheses ব্যবহার করেও করা যায়:

```python
student = ("Masum", 22, 3.95)

print(student)
```

Output:

```text
('Masum', 22, 3.95)
```

দুটি ক্ষেত্রেই `student` একটি Tuple।

## 9. Tuple Unpacking

**Tuple Unpacking** হলো Tuple-এর item-গুলোকে একাধিক variable-এর মধ্যে আলাদা করে assign করা।

```python
student = ("Masum", 22, 3.95)

name, age, cgpa = student

print(name)
print(age)
print(cgpa)
```

Output:

```text
Masum
22
3.95
```

এখানে:

- `name` পেয়েছে `"Masum"`।
- `age` পেয়েছে `22`।
- `cgpa` পেয়েছে `3.95`।

সাধারণ unpacking-এর ক্ষেত্রে variable-এর সংখ্যা এবং Tuple-এর item-এর সংখ্যা সমান হতে হবে।

```python
numbers = (10, 20, 30)

a, b, c = numbers

print(a, b, c)
```

Output:

```text
10 20 30
```

Variable-এর সংখ্যা না মিললে `ValueError` হয়।

### 9.1 Swapping Variables

Tuple unpacking ব্যবহার করে সহজে দুটি variable-এর value অদলবদল করা যায়।

```python
a = 10
b = 20

a, b = b, a

print(a)
print(b)
```

Output:

```text
20
10
```

এখানে temporary variable তৈরি করার প্রয়োজন হয়নি।

### 9.2 Unpacking with `*`

`*` ব্যবহার করে একাধিক item একসঙ্গে একটি List-এ সংগ্রহ করা যায়।

```python
numbers = (10, 20, 30, 40, 50)

first, *middle, last = numbers

print(first)
print(middle)
print(last)
```

Output:

```text
10
[20, 30, 40]
50
```

এখানে `middle` একটি List পেয়েছে, Tuple নয়।

## 10. Nested Tuples

একটি Tuple-এর মধ্যে আরেকটি Tuple রাখা হলে তাকে Nested Tuple বলা হয়।

```python
data = (
    ("Masum", 22),
    ("Ritu", 21),
    ("Tusher", 23)
)

print(data)
```

Output:

```text
(('Masum', 22), ('Ritu', 21), ('Tusher', 23))
```

Nested Tuple থেকে item access করতে একাধিক index ব্যবহার করা যায়।

```python
data = (
    ("Masum", 22),
    ("Ritu", 21),
    ("Tusher", 23)
)

print(data[0])
print(data[1][0])
print(data[2][1])
```

Output:

```text
('Masum', 22)
Ritu
23
```

এখানে `data[1][0]` দ্বিতীয় nested Tuple-এর প্রথম item return করেছে।

## 11. Tuple with Mutable Objects

Tuple immutable হলেও এর মধ্যে List-এর মতো mutable object রাখা যায়। সে ক্ষেত্রে Tuple-এর ভেতরের mutable object পরিবর্তন করা সম্ভব।

```python
data = (10, [20, 30], 40)

data[1].append(50)

print(data)
```

Output:

```text
(10, [20, 30, 50], 40)
```

এখানে Tuple-এর item-গুলোর position বা reference পরিবর্তন করা হয়নি। এর মধ্যে থাকা List-এর content পরিবর্তন হয়েছে।

কিন্তু সরাসরি Tuple-এর item-কে অন্য object দিয়ে replace করা যাবে না।

```python
data = (10, [20, 30], 40)

data[1] = [100, 200]
```

এই code `TypeError` তৈরি করবে।

**মনে রাখবে:** Tuple immutable মানে Tuple-এর item-গুলোকে সরাসরি reassign করা যায় না। এর মধ্যে থাকা mutable object-এর নিজস্ব content পরিবর্তিত হতে পারে।

## 12. Tuple Methods

Tuple immutable হওয়ায় এর modification method নেই। তবে দুটি গুরুত্বপূর্ণ method রয়েছে।

### 12.1 `count()`

`count()` কোনো value কতবার আছে, তা return করে।

```python
numbers = (10, 20, 10, 30, 10)

print(numbers.count(10))
print(numbers.count(20))
```

Output:

```text
3
1
```

### 12.2 `index()`

`index()` কোনো value-এর প্রথম occurrence-এর index return করে।

```python
fruits = ("Apple", "Banana", "Mango", "Banana")

print(fruits.index("Banana"))
```

Output:

```text
1
```

Value না থাকলে `ValueError` হয়।

## 13. Membership Testing

`in` এবং `not in` operator ব্যবহার করে Tuple-এর মধ্যে কোনো item আছে কি না পরীক্ষা করা যায়।

```python
fruits = ("Apple", "Banana", "Mango")

print("Apple" in fruits)
print("Orange" in fruits)
print("Orange" not in fruits)
```

Output:

```text
True
False
True
```

## 14. Iterating Through a Tuple

`for` loop ব্যবহার করে Tuple-এর সব item access করা যায়।

```python
fruits = ("Apple", "Banana", "Mango")

for fruit in fruits:
    print(fruit)
```

Output:

```text
Apple
Banana
Mango
```

Index এবং value একসঙ্গে পেতে `enumerate()` ব্যবহার করা যায়।

```python
fruits = ("Apple", "Banana", "Mango")

for index, fruit in enumerate(fruits):
    print(index, fruit)
```

Output:

```text
0 Apple
1 Banana
2 Mango
```

## 15. Tuple Concatenation and Repetition

### 15.1 Concatenation

`+` operator দিয়ে দুটি Tuple যুক্ত করা যায়।

```python
a = (1, 2)
b = (3, 4)

result = a + b

print(result)
```

Output:

```text
(1, 2, 3, 4)
```

এতে একটি নতুন Tuple তৈরি হয়।

### 15.2 Repetition

`*` operator দিয়ে Tuple-এর item repeat করা যায়।

```python
numbers = (1, 2)

print(numbers * 3)
```

Output:

```text
(1, 2, 1, 2, 1, 2)
```

এটিও একটি নতুন Tuple তৈরি করে।

## 16. Useful Built-in Functions

Tuple-এর item-এর ওপর কিছু built-in function ব্যবহার করা যায়।

```python
numbers = (10, 20, 30, 40, 50)

print(len(numbers))
print(min(numbers))
print(max(numbers))
print(sum(numbers))
```

Output:

```text
5
10
50
150
```

- `len()` মোট item-এর সংখ্যা দেয়।
- `min()` সবচেয়ে ছোট item দেয়।
- `max()` সবচেয়ে বড় item দেয়।
- `sum()` numeric item-গুলোর যোগফল দেয়।

## 17. List vs Tuple

List এবং Tuple-এর পার্থক্য Python শেখার একটি গুরুত্বপূর্ণ বিষয়।

| Feature | List | Tuple |
|---|---|---|
| Syntax | `[ ]` | `( )` সাধারণত |
| Mutability | Mutable | Immutable |
| Item update | সরাসরি করা যায় | সরাসরি করা যায় না |
| Add/remove methods | আছে | নেই |
| Duplicates | Allowed | Allowed |
| Indexing | Supported | Supported |
| Slicing | Returns a List | Returns a Tuple |
| Common use | পরিবর্তনশীল collection | স্থির collection বা grouped values |

Example:

```python
my_list = [10, 20, 30]
my_tuple = (10, 20, 30)

my_list[0] = 100

print(my_list)
print(my_tuple)
```

Output:

```text
[100, 20, 30]
(10, 20, 30)
```

List পরিবর্তন করা গেছে, কিন্তু Tuple-টি অপরিবর্তিত রয়েছে।

## 18. When Should You Use a Tuple?

যখন একাধিক value একসঙ্গে রাখতে হবে এবং collection-এর structure অপরিবর্তিত রাখা উপযুক্ত, তখন Tuple ব্যবহার করা যেতে পারে।

Tuple-এর কিছু সাধারণ ব্যবহার:

1. **Fixed grouped data:** যেমন একটি coordinate `(10, 20)`।
2. **Returning multiple values:** Function থেকে একাধিক value return করা।
3. **Unpacking:** একাধিক variable-এ value assign করা।
4. **Dictionary keys:** উপযুক্ত শর্ত পূরণ করলে Tuple key হিসেবে ব্যবহার করা যায়।
5. **Immutable structure:** যেখানে item-গুলোর reference পরিবর্তন করা উচিত নয়।

Example — Coordinates:

```python
point = (10, 20)

x, y = point

print("X:", x)
print("Y:", y)
```

Output:

```text
X: 10
Y: 20
```

### Can a Tuple Be a Dictionary Key?

Tuple dictionary key হতে পারে, যদি Tuple-এর সব item hashable হয়।

```python
locations = {
    (10, 20): "Point A",
    (30, 40): "Point B"
}

print(locations[(10, 20)])
```

Output:

```text
Point A
```

কিন্তু Tuple-এর মধ্যে List-এর মতো unhashable item থাকলে সেই Tuple dictionary key হিসেবে ব্যবহার করা যাবে না।

```python
key = (10, [20, 30])
```

এখানে `key` তৈরি করা সম্ভব, কিন্তু এটিকে Dictionary key হিসেবে ব্যবহার করলে `TypeError` হবে।

## 19. Common Beginner Mistakes

### Mistake 1: Forgetting the Comma in a Single-item Tuple

Incorrect:

```python
value = (10)

print(type(value))
```

Output:

```text
<class 'int'>
```

Correct:

```python
value = (10,)

print(type(value))
```

Output:

```text
<class 'tuple'>
```

### Mistake 2: Trying to Modify a Tuple

```python
numbers = (10, 20, 30)

numbers[0] = 100
```

এটি `TypeError` তৈরি করবে। নতুন Tuple তৈরি করতে হবে, অথবা পরিবর্তন প্রয়োজন হলে List ব্যবহার করা যেতে পারে।

### Mistake 3: Unpacking with the Wrong Number of Variables

```python
numbers = (10, 20, 30)

a, b = numbers
```

এখানে `ValueError` হবে, কারণ তিনটি item unpack করার জন্য মাত্র দুটি variable দেওয়া হয়েছে।

### Mistake 4: Confusing a Tuple with a List

```python
a = [10, 20]
b = (10, 20)
```

`a` একটি List এবং `b` একটি Tuple। দুটির mutability আলাদা।

### Mistake 5: Assuming a Tuple Makes Nested Objects Immutable

```python
data = ([1, 2], [3, 4])

data[0].append(5)

print(data)
```

Output:

```text
([1, 2, 5], [3, 4])
```

Tuple-এর ভেতরের List পরিবর্তিত হয়েছে। তাই Tuple-এর immutability এবং nested object-এর mutability আলাদা বিষয়।

## 20. Practice Exercises

### Exercise 1: Create a Tuple

পাঁচটি programming language-এর নাম দিয়ে একটি Tuple তৈরি করো। পুরো Tuple এবং এর length print করো।

### Exercise 2: Indexing and Slicing

```python
numbers = (10, 20, 30, 40, 50, 60)
```

নিচের expression-গুলোর output বের করো:

```python
print(numbers[0])
print(numbers[-1])
print(numbers[1:4])
print(numbers[::2])
print(numbers[::-1])
```

### Exercise 3: Single-item Tuple

একটি Integer-এর Tuple তৈরি করো। `type()` ব্যবহার করে নিশ্চিত হও যে এটি Tuple।

### Exercise 4: Tuple Packing and Unpacking

```python
student = ("Masum", 22, 3.95)
```

Tuple unpack করে `name`, `age` এবং `cgpa` variable তৈরি করো। এরপর প্রত্যেকটি print করো।

### Exercise 5: Variable Swapping

দুটি variable-এর value Tuple unpacking ব্যবহার করে swap করো।

### Exercise 6: Count and Index

```python
numbers = (10, 20, 10, 30, 10, 40)
```

`10` কতবার আছে এবং এর প্রথম occurrence-এর index বের করো।

### Exercise 7: List vs Tuple

একটি List এবং একটি Tuple তৈরি করো। List-এর item পরিবর্তন করো। Tuple-এর item পরিবর্তন করার চেষ্টা করে error-এর কারণ ব্যাখ্যা করো।

### Exercise 8: Nested Tuple

তিনজন শিক্ষার্থীর নাম এবং বয়স দিয়ে একটি Nested Tuple তৈরি করো। Indexing ব্যবহার করে দ্বিতীয় শিক্ষার্থীর নাম ও বয়স print করো।

### Exercise 9: Unpacking with `*`

```python
numbers = (10, 20, 30, 40, 50)
```

Unpacking ব্যবহার করে প্রথম item, মাঝের item-গুলো এবং শেষ item আলাদা করো।

### Exercise 10: Mini Project — Student Profile

একটি Tuple-এ শিক্ষার্থীর নাম, বয়স, বিভাগ এবং CGPA রাখো। Tuple unpacking ব্যবহার করে প্রতিটি তথ্য আলাদা variable-এ রাখো এবং সুন্দরভাবে print করো।

## 21. Key Takeaways

- Tuple হলো Python-এর একটি ordered collection data type।
- Tuple সাধারণত parentheses `()` দিয়ে তৈরি করা হয়।
- Single-item Tuple-এর জন্য comma প্রয়োজন।
- Tuple immutable; এর item সরাসরি reassign করা যায় না।
- Tuple duplicate এবং mixed data type-এর item support করে।
- Indexing ও slicing-এর নিয়ম List-এর মতো।
- Tuple Packing একাধিক value-কে Tuple-এ রাখে।
- Tuple Unpacking Tuple-এর item-গুলোকে একাধিক variable-এ assign করে।
- `count()` এবং `index()` Tuple-এর গুরুত্বপূর্ণ method।
- Tuple-এর ভেতরের mutable object-এর content পরিবর্তিত হতে পারে।
- `+` দিয়ে Tuple concatenation এবং `*` দিয়ে repetition করা যায়।
- Tuple উপযুক্ত ক্ষেত্রে function থেকে একাধিক value return এবং dictionary key হিসেবে ব্যবহৃত হতে পারে।

## 22. Next Topic

পরবর্তী ফাইল:

**`16_Set_Data_Type.md`**

সেখানে Python-এর Set, unique values, unordered collection, set operations, union, intersection, difference এবং symmetric difference শেখা হবে।