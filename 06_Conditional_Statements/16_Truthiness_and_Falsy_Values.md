# 16. Truthiness and Falsy Values

## 1. Truthiness কী?

Python-এ কোনো value-কে condition-এর মধ্যে ব্যবহার করলে সেটি `True` হিসেবে বিবেচিত হবে, নাকি `False` হিসেবে বিবেচিত হবে—এই ধারণাকে **Truthiness** বলে।

সহজভাবে বললে, কোনো value সত্যের মতো কাজ করলে তাকে **Truthy** এবং মিথ্যার মতো কাজ করলে তাকে **Falsy** বলা হয়।

উদাহরণ:

```python
if 10:
    print("Condition is True")
```

Output:

```text
Condition is True
```

এখানে `10` সরাসরি `True` নয়, কিন্তু condition-এর মধ্যে এটি Truthy value হিসেবে কাজ করে।

আরেকটি উদাহরণ:

```python
if 0:
    print("Yes")
else:
    print("No")
```

Output:

```text
No
```

কারণ Python-এ `0` একটি Falsy value।

## 2. Truthy এবং Falsy Values-এর পার্থক্য

| বিষয় | Truthy | Falsy |
|---|---|---|
| অর্থ | `True`-এর মতো আচরণ করে | `False`-এর মতো আচরণ করে |
| উদাহরণ | `10`, `"Hello"`, `[1, 2]` | `0`, `""`, `[]` |
| Condition-এর ফল | Condition সত্য হিসেবে গণ্য হয় | Condition মিথ্যা হিসেবে গণ্য হয় |

মনে রাখবে, কোনো value Truthy হলেই সেটি Boolean value `True` হয়ে যায় না। এটি শুধু condition-এর মধ্যে `True` হিসেবে বিবেচিত হয়।

## 3. Python-এর প্রধান Falsy Values

Python-এ গুরুত্বপূর্ণ Falsy values হলো:

| Value | ব্যাখ্যা |
|---|---|
| `False` | Boolean false |
| `None` | কোনো value নেই বোঝায় |
| `0` | Integer zero |
| `0.0` | Floating-point zero |
| `0j` | Complex number zero |
| `""` | Empty string |
| `[]` | Empty list |
| `()` | Empty tuple |
| `{}` | Empty dictionary |
| `set()` | Empty set |
| `range(0)` | Empty range |

এগুলো condition-এর মধ্যে `False` হিসেবে কাজ করে।

উদাহরণ:

```python
if "":
    print("Truthy")
else:
    print("Falsy")
```

Output:

```text
Falsy
```

একইভাবে:

```python
if []:
    print("List has items")
else:
    print("List is empty")
```

Output:

```text
List is empty
```

**মনে রাখবে:** সাধারণভাবে empty collection এবং zero value Falsy।

## 4. কোন Values Truthy?

যেসব value Falsy নয়, সেগুলো সাধারণত Truthy।

উদাহরণ:

```python
if 5:
    print("Truthy")
```

Output:

```text
Truthy
```

আরও কিছু Truthy values:

```python
10
-5
0.5
-0.5
"Python"
" "
[1, 2, 3]
(10, 20)
{"name": "Masum"}
{1, 2, 3}
```

এখানে `" "` একটি space-যুক্ত string। এটি empty string `""` নয়, তাই Truthy।

উদাহরণ:

```python
text = " "

if text:
    print("Text is not empty")
```

Output:

```text
Text is not empty
```

যদিও string-টিতে শুধু space আছে, তবুও এটি non-empty string।

## 5. `bool()` Function দিয়ে Truthiness পরীক্ষা

Python-এর `bool()` function কোনো value-কে Boolean value `True` বা `False`-এ রূপান্তর করে।

Syntax:

```python
bool(value)
```

উদাহরণ:

```python
print(bool(10))
print(bool(0))
print(bool("Python"))
print(bool(""))
print(bool([1, 2]))
print(bool([]))
```

Output:

```text
True
False
True
False
True
False
```

এখানে:

- `bool(10)` → `True`
- `bool(0)` → `False`
- `bool("Python")` → `True`
- `bool("")` → `False`
- `bool([1, 2])` → `True`
- `bool([])` → `False`

**Important:** `bool("False")`-এর result কিন্তু `False` নয়।

```python
print(bool("False"))
print(bool("0"))
```

Output:

```text
True
True
```

কারণ দুটি string-ই non-empty। String-এর ভেতরের text দেখে Python Truthiness নির্ধারণ করে না।

## 6. `if` Statement-এ Truthiness ব্যবহার

Condition-এর মধ্যে সরাসরি value ব্যবহার করা যায়।

উদাহরণ:

```python
number = 15

if number:
    print("Number is non-zero")
else:
    print("Number is zero")
```

Output:

```text
Number is non-zero
```

যদি `number = 0` হয়, তাহলে `else` block execute হবে।

এখানে:

```python
if number:
```

লেখা হয়েছে, কারণ zero হলে condition falsy হবে এবং non-zero হলে truthy হবে।

তবে এই পদ্ধতিতে শুধু zero ও non-zero আলাদা করা যায়। Positive এবং negative number আলাদা করতে চাইলে comparison ব্যবহার করতে হবে।

```python
if number > 0:
    print("Positive")
```

## 7. Empty String Check করা

User input বা কোনো text empty কি না, তা পরীক্ষা করতে Truthiness খুব কাজে লাগে।

উদাহরণ:

```python
name = input("Enter your name: ")

if name:
    print("Hello,", name)
else:
    print("Name cannot be empty")
```

Input:

```text
Masum
```

Output:

```text
Hello, Masum
```

কিন্তু input একেবারে empty হলে `name` হবে `""`, যা Falsy।

তখন output হবে:

```text
Name cannot be empty
```

তবে শুধু space দিলে `"   "` একটি non-empty string, তাই সেটি Truthy হবে।

Space-ও বাদ দিয়ে empty input পরীক্ষা করতে চাইলে:

```python
name = input("Enter your name: ").strip()

if name:
    print("Hello,", name)
else:
    print("Name cannot be empty")
```

`.strip()` string-এর শুরু ও শেষের whitespace সরিয়ে দেয়।

## 8. List Empty কি না পরীক্ষা করা

কোনো list-এর মধ্যে item আছে কি না, তা Truthiness দিয়ে সহজে পরীক্ষা করা যায়।

উদাহরণ:

```python
students = ["Masum", "Ritu"]

if students:
    print("Students found")
else:
    print("No students found")
```

Output:

```text
Students found
```

এবার list empty করি:

```python
students = []

if students:
    print("Students found")
else:
    print("No students found")
```

Output:

```text
No students found
```

এই পদ্ধতিটি নিচের পদ্ধতির সমতুল্য:

```python
if len(students) > 0:
    print("Students found")
```

Python-এ সরাসরি `if students:` লেখা সাধারণত বেশি সংক্ষিপ্ত ও readable।

## 9. `not` ব্যবহার করে Truthiness পরীক্ষা

`not` operator কোনো Truthy value-কে `False` এবং কোনো Falsy value-কে `True` করে।

উদাহরণ:

```python
name = ""

if not name:
    print("Name is missing")
```

Output:

```text
Name is missing
```

কারণ:

```python
bool(name)      # False
not bool(name)  # True
```

আরেকটি উদাহরণ:

```python
items = []

if not items:
    print("The list is empty")
```

Output:

```text
The list is empty
```

এই পদ্ধতিটি empty string, empty list বা অন্য Falsy value পরীক্ষা করার জন্য কাজে লাগে।

## 10. `and` ও `or`-এর সঙ্গে Truthiness

`and` এবং `or` শুধু `True` বা `False` return করে না; অনেক ক্ষেত্রে তারা সরাসরি কোনো operand-এর value return করে।

### `and` Operator

`and` বাম পাশের operand Falsy হলে সেটিই return করে। অন্যথায় ডান পাশের operand return করে।

উদাহরণ:

```python
print(0 and 10)
print(5 and 10)
print("Python" and "Programming")
```

Output:

```text
0
10
Programming
```

ব্যাখ্যা:

- `0 and 10` → `0` Falsy, তাই `0` return হয়।
- `5 and 10` → `5` Truthy, তাই `10` return হয়।
- `"Python" and "Programming"` → প্রথম string Truthy, তাই দ্বিতীয় string return হয়।

### `or` Operator

`or` বাম পাশের operand Truthy হলে সেটিই return করে। অন্যথায় ডান পাশের operand return করে।

উদাহরণ:

```python
print(5 or 10)
print(0 or 10)
print("" or "Default")
```

Output:

```text
5
10
Default
```

ব্যাখ্যা:

- `5 or 10` → `5` Truthy, তাই `5` return হয়।
- `0 or 10` → `0` Falsy, তাই `10` return হয়।
- `"" or "Default"` → empty string Falsy, তাই `"Default"` return হয়।

## 11. Default Value দেওয়ার ক্ষেত্রে `or`

`or` ব্যবহার করে কোনো value না থাকলে default value দেওয়া যায়।

উদাহরণ:

```python
username = ""

display_name = username or "Guest"

print(display_name)
```

Output:

```text
Guest
```

কারণ `username` empty string হওয়ায় Falsy। তাই `or`-এর ডান পাশের value `"Guest"` return হয়েছে।

আরেকটি উদাহরণ:

```python
username = "Masum"

display_name = username or "Guest"

print(display_name)
```

Output:

```text
Masum
```

**সতর্কতা:** `or` দিয়ে default value দিলে `0`, `False` বা empty collection-এর মতো valid value-ও default দিয়ে প্রতিস্থাপিত হতে পারে।

যেমন:

```python
quantity = 0
quantity = quantity or 10

print(quantity)
```

Output:

```text
10
```

যদি `0`-কেও valid value হিসেবে রাখতে চাও এবং শুধু `None` হলে default দিতে চাও, তাহলে explicit check করো:

```python
quantity = 0

if quantity is None:
    quantity = 10

print(quantity)
```

Output:

```text
0
```

## 12. Truthiness এবং Explicit Comparison

অনেক ক্ষেত্রে Truthiness ব্যবহার করা সহজ, কিন্তু সব সময় এটিই সেরা পদ্ধতি নয়।

উদাহরণ:

```python
age = 0

if age:
    print("Age provided")
else:
    print("Age is zero or missing")
```

এখানে `age = 0` হলে condition Falsy হবে।

কিন্তু তুমি যদি নির্দিষ্টভাবে zero পরীক্ষা করতে চাও, তাহলে লিখতে পারো:

```python
if age == 0:
    print("Age is zero")
```

আবার `None` পরীক্ষা করতে:

```python
value = None

if value is None:
    print("No value assigned")
```

মনে রাখবে:

- `if value:` → value Truthy কি না পরীক্ষা করে।
- `if value == 0:` → value zero-এর সমান কি না পরীক্ষা করে।
- `if value is None:` → value `None` কি না পরীক্ষা করে।

কোন পরীক্ষাটি প্রয়োজন, তা বুঝে ব্যবহার করবে।

## 13. Common Mistakes

### Mistake 1: `"False"`-কে Falsy মনে করা

```python
print(bool("False"))
```

Output:

```text
True
```

কারণ এটি একটি non-empty string।

### Mistake 2: `"0"`-কে Falsy মনে করা

```python
print(bool("0"))
```

Output:

```text
True
```

কারণ `"0"` একটি string; এটি numeric zero `0` নয়।

### Mistake 3: Space-যুক্ত string-কে empty মনে করা

```python
text = " "

if text:
    print("Truthy")
```

Output:

```text
Truthy
```

কারণ string-এ একটি space আছে।

### Mistake 4: সব Falsy value-কে `None` মনে করা

```python
print(bool(None))
print(bool(0))
print(bool(""))
```

Output:

```text
False
False
False
```

তিনটিই Falsy, কিন্তু তিনটি আলাদা value। তাদের অর্থও আলাদা।

### Mistake 5: `or` দিয়ে valid zero হারিয়ে ফেলা

```python
score = 0
score = score or 50

print(score)
```

Output:

```text
50
```

এখানে zero Falsy হওয়ায় default value নেওয়া হয়েছে। Zero রাখতে চাইলে `is None` দিয়ে check করো, যদি সেটিই তোমার intended rule হয়।

## 14. Practice Exercises

নিজে output predict করো। তারপর Answer Key-এর সঙ্গে মিলিয়ে দেখো।

### Question 1

```python
print(bool(0))
print(bool(-1))
print(bool(""))
```

### Question 2

```python
print(bool("False"))
print(bool(" "))
```

### Question 3

```python
items = []

if items:
    print("A")
else:
    print("B")
```

### Question 4

```python
print(0 or 7)
print(4 or 7)
```

### Question 5

```python
print(0 and 7)
print(4 and 7)
```

### Question 6

```python
name = ""

if not name:
    print("Missing")
else:
    print("Available")
```

### Question 7

```python
value = None

if value is None:
    print("No value")
else:
    print("Has value")
```

### Question 8

```python
score = 0
result = score or 100

print(result)
```

## 15. Answer Key

### Answer 1

```text
False
True
False
```

`0` ও empty string Falsy; `-1` non-zero হওয়ায় Truthy।

### Answer 2

```text
True
True
```

দুটিই non-empty string।

### Answer 3

```text
B
```

Empty list Falsy।

### Answer 4

```text
7
4
```

`or` প্রথম Truthy operand return করে; প্রথম operand Falsy হলে দ্বিতীয়টি return করে।

### Answer 5

```text
0
7
```

`and` প্রথম Falsy operand return করে; প্রথম operand Truthy হলে দ্বিতীয়টি return করে।

### Answer 6

```text
Missing
```

Empty string Falsy, তাই `not name` True।

### Answer 7

```text
No value
```

`value` হলো `None`।

### Answer 8

```text
100
```

`score`-এর value `0`, যা Falsy। তাই `or`-এর ডান পাশের `100` return হয়।

## 16. Quick Revision

- **Truthiness:** কোনো value condition-এ `True` বা `False`-এর মতো কাজ করার নিয়ম।
- **Truthy:** যেমন `10`, `-1`, `"Python"`, `[1, 2]`।
- **Falsy:** যেমন `False`, `None`, `0`, `""`, `[]`, `{}`।
- **`bool(value)`:** value-এর Boolean result দেয়।
- **`if items:`:** collection-এ item থাকলে condition সাধারণত Truthy হবে।
- **`if not items:`:** collection empty হলে condition Truthy হবে।
- **`and`:** প্রথম Falsy operand অথবা শেষ operand return করে।
- **`or`:** প্রথম Truthy operand অথবা শেষ operand return করে।
- **Explicit comparison:** নির্দিষ্টভাবে zero বা `None` পরীক্ষা করতে `== 0` বা `is None` ব্যবহার করো।

## 17. Self-Assessment Checklist

- [ ] Truthiness ও Falsy-এর অর্থ বুঝি।
- [ ] Python-এর প্রধান Falsy values বলতে পারি।
- [ ] `bool()` দিয়ে Truthiness পরীক্ষা করতে পারি।
- [ ] Empty string ও empty list পরীক্ষা করতে পারি।
- [ ] `and` ও `or` কোন operand return করে বুঝি।
- [ ] Default value দেওয়ার সময় zero বা `False` হারিয়ে যাওয়ার ঝুঁকি বুঝি।
- [ ] Truthiness এবং explicit comparison-এর মধ্যে পার্থক্য বুঝি।

**পরবর্তী টপিক:** `17_Conditional_Expressions_Ternary_Operator.md`