# 13. Truthy and Falsy Values in Python

## 1. Introduction to Truthy and Falsy Values

Python-এ প্রতিটি value-কে Boolean context-এ পরীক্ষা করলে সেটি সত্যের মতো (`True`) অথবা মিথ্যার মতো (`False`) আচরণ করে।

এই আচরণের ভিত্তিতে value-গুলোকে দুটি ভাগে ভাগ করা হয়:

- **Truthy:** যেসব value Boolean context-এ `True` হিসেবে বিবেচিত হয়।
- **Falsy:** যেসব value Boolean context-এ `False` হিসেবে বিবেচিত হয়।

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

এখানে:

- `10` হলো truthy।
- `0` হলো falsy।
- `"Python"` হলো truthy।
- `""` হলো falsy।

**মনে রাখবে:** Truthy বা falsy হওয়া মানে value-এর type `bool` হয়ে যাওয়া নয়। এটি শুধু Boolean context-এ value-টির আচরণ বোঝায়।

```python
value = 10

print(value)
print(type(value))
print(bool(value))
```

Output:

```text
10
<class 'int'>
True
```

এখানে `value` এখনো `int`; শুধু `bool(value)` একটি Boolean result দিয়েছে।

## 2. The `bool()` Function

`bool()` হলো Python-এর built-in function, যা কোনো value-এর truth value পরীক্ষা করে Boolean result দেয়।

Syntax:

```python
bool(value)
```

Example:

```python
print(bool(1))
print(bool(-5))
print(bool(0))

print(bool("Hello"))
print(bool(""))
```

Output:

```text
True
True
False
True
False
```

সাধারণ নিয়ম:

- Zero numeric value falsy।
- Non-zero numeric value truthy।
- Empty String falsy।
- Non-empty String truthy।

`bool()` ব্যবহার করে কোনো value condition-এ কীভাবে আচরণ করবে, তা সহজে পরীক্ষা করা যায়।

## 3. Common Falsy Values in Python

Python-এ কয়েকটি গুরুত্বপূর্ণ value স্বাভাবিকভাবেই falsy।

| Value | Type | Boolean result |
|---|---|---|
| `False` | `bool` | `False` |
| `None` | `NoneType` | `False` |
| `0` | `int` | `False` |
| `0.0` | `float` | `False` |
| `0j` | `complex` | `False` |
| `""` | `str` | `False` |
| `[]` | `list` | `False` |
| `()` | `tuple` | `False` |
| `{}` | `dict` | `False` |
| `set()` | `set` | `False` |
| `range(0)` | `range` | `False` |

Example:

```python
print(bool(False))
print(bool(None))
print(bool(0))
print(bool(0.0))
print(bool(0j))

print(bool(""))
print(bool([]))
print(bool(()))
print(bool({}))
print(bool(set()))
print(bool(range(0)))
```

প্রতিটি expression-এর result হবে `False`।

**গুরুত্বপূর্ণ:** Empty collection falsy, কিন্তু collection-এর মধ্যে falsy value থাকলেই collection falsy হয় না।

```python
print(bool([]))
print(bool([0]))
print(bool([False]))
print(bool([None]))
```

Output:

```text
False
True
True
True
```

কারণ দ্বিতীয়, তৃতীয় ও চতুর্থ list-এ অন্তত একটি element আছে। List খালি না হওয়ায় সেগুলো truthy।

## 4. Common Truthy Values in Python

সাধারণভাবে নিচের value-গুলো truthy:

| Value | Boolean result |
|---|---|
| `True` | `True` |
| `1` | `True` |
| `-1` | `True` |
| `3.14` | `True` |
| `"Python"` | `True` |
| `" "` | `True` |
| `[1, 2]` | `True` |
| `(0,)` | `True` |
| `{"name": "Masum"}` | `True` |
| `{0}` | `True` |

Example:

```python
print(bool(100))
print(bool(-10))
print(bool(0.01))

print(bool("False"))
print(bool("0"))
print(bool(" "))

print(bool([0]))
print(bool({"name": "Masum"}))
```

প্রতিটি expression-এর result হবে `True`।

এখানে কয়েকটি বিষয় মনে রাখা দরকার:

- `"False"` একটি non-empty String।
- `"0"` একটি non-empty String।
- `" "` একটি space-যুক্ত String।

তাই এগুলো truthy।

## 5. Truthiness of Numeric Values

Numeric value-এর ক্ষেত্রে সাধারণ নিয়ম হলো:

- Zero → falsy
- Non-zero → truthy

### Integer

```python
print(bool(0))
print(bool(1))
print(bool(-1))
print(bool(100))
```

Output:

```text
False
True
True
True
```

Negative integer-ও truthy, কারণ সেটি zero নয়।

### Float

```python
print(bool(0.0))
print(bool(0.1))
print(bool(-0.5))
```

Output:

```text
False
True
True
```

### Complex

```python
print(bool(0j))
print(bool(1 + 0j))
print(bool(0 + 2j))
```

Output:

```text
False
True
True
```

Complex number-এর real এবং imaginary অংশ দুটোই zero হলে সেটি falsy। অন্যথায় truthy।

## 6. Truthiness of Strings

String-এর ক্ষেত্রে মূল নিয়ম হলো:

- Empty String → falsy
- Non-empty String → truthy

Example:

```python
print(bool(""))
print(bool("Python"))
print(bool("Hello World"))
print(bool(" "))
```

Output:

```text
False
True
True
True
```

এখানে শুধু `""` empty String।

### Important: Text Does Not Determine Truthiness

Python String-এর ভেতরের text পড়ে তার অর্থ অনুযায়ী Boolean নির্ধারণ করে না।

```python
print(bool("False"))
print(bool("None"))
print(bool("0"))
print(bool("No"))
print(bool(" "))
```

Output:

```text
True
True
True
True
True
```

সবগুলোই non-empty String।

### Checking Whether a String Is Empty

```python
name = ""

if not name:
    print("Name is empty.")
```

Output:

```text
Name is empty.
```

এখানে `not name` সত্য, কারণ `name` empty String।

তবে whitespace-কে খালি হিসেবে ধরতে চাইলে `strip()` ব্যবহার করা যেতে পারে।

```python
name = "   "

if not name.strip():
    print("Name is empty or contains only spaces.")
```

Output:

```text
Name is empty or contains only spaces.
```

`strip()` String-এর শুরু ও শেষের whitespace সরিয়ে দেয়। এখানে শুধু space থাকায় result empty String হয়েছে।

## 7. Truthiness of Collections

Python-এর collection type-গুলোর ক্ষেত্রে সাধারণত:

- Empty collection → falsy
- Non-empty collection → truthy

### List

```python
print(bool([]))
print(bool([1, 2, 3]))
```

Output:

```text
False
True
```

### Tuple

```python
print(bool(()))
print(bool((1,)))
```

Output:

```text
False
True
```

মনে রাখবে, একটি element-যুক্ত tuple তৈরি করতে `(1,)` লিখতে হয়।

### Dictionary

```python
print(bool({}))
print(bool({"name": "Masum"}))
```

Output:

```text
False
True
```

### Set

```python
print(bool(set()))
print(bool({1, 2, 3}))
```

Output:

```text
False
True
```

### Checking Whether a Collection Is Empty

```python
students = []

if not students:
    print("No students found.")
```

Output:

```text
No students found.
```

এভাবে empty list বা dictionary পরীক্ষা করা যায়।

## 8. Using Truthy and Falsy Values in `if`

Python-এর `if` statement-এ সবসময় explicit Boolean expression লিখতে হয় না। Truthy বা falsy value-ও condition হিসেবে ব্যবহার করা যায়।

Example:

```python
name = "Masum"

if name:
    print("Name is available.")
```

Output:

```text
Name is available.
```

কারণ `"Masum"` একটি truthy String।

অন্যদিকে:

```python
name = ""

if name:
    print("Name is available.")
else:
    print("Name is missing.")
```

Output:

```text
Name is missing.
```

কারণ empty String falsy।

### Comparing Two Approaches

```python
students = []

if len(students) > 0:
    print("Students exist.")
else:
    print("No students found.")
```

এটি কাজ করে। তবে একই কাজ আরও সহজভাবে লেখা যায়:

```python
students = []

if students:
    print("Students exist.")
else:
    print("No students found.")
```

দুটি code-ই একই ফল দেয়। দ্বিতীয় পদ্ধতিটি Python-এ বেশি সরল এবং প্রচলিত।

## 9. Using `not` with Truthy and Falsy Values

`not` কোনো value-এর truth value উল্টে দেয়।

Example:

```python
print(not True)
print(not False)

print(not 0)
print(not 10)

print(not "")
print(not "Python")
```

Output:

```text
False
True
True
False
True
False
```

ব্যাখ্যা:

- `not 0` → `True`, কারণ `0` falsy।
- `not 10` → `False`, কারণ `10` truthy।
- `not ""` → `True`, কারণ empty String falsy।
- `not "Python"` → `False`, কারণ non-empty String truthy।

এটি condition-এ empty value পরীক্ষা করতে কাজে লাগে।

## 10. Truthiness and Logical Operators

Python-এর `and` ও `or` operator truthiness ব্যবহার করে।

তবে গুরুত্বপূর্ণ বিষয় হলো, এই operator-গুলো সবসময় `True` বা `False` return করে না। অনেক ক্ষেত্রে তারা operand-এর আসল value return করে।

### 10.1 The `and` Operator

`and` বাম পাশের operand falsy হলে সেটিই return করে। বাম পাশ truthy হলে ডান পাশের operand return করে।

```python
print(0 and 10)
print(5 and 10)
print("" and "Python")
print("Hello" and "Python")
```

Output:

```text
0
10

Python
```

তৃতীয় expression-এর result empty String, তাই output-এ ওই লাইনে কিছু দেখা যায় না।

### 10.2 The `or` Operator

`or` বাম পাশের operand truthy হলে সেটিই return করে। বাম পাশ falsy হলে ডান পাশের operand return করে।

```python
print(0 or 10)
print(5 or 10)
print("" or "Python")
print("Hello" or "Python")
```

Output:

```text
10
5
Python
Hello
```

### Summary

| Expression | Result | Reason |
|---|---|---|
| `0 and 10` | `0` | বাম operand falsy |
| `5 and 10` | `10` | বাম operand truthy |
| `0 or 10` | `10` | বাম operand falsy |
| `5 or 10` | `5` | বাম operand truthy |

## 11. Using `or` to Provide a Default Value

কোনো value falsy হলে বিকল্প value ব্যবহার করতে `or` operator কাজে লাগতে পারে।

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

এখানে `username` empty String, তাই `"Guest"` নেওয়া হয়েছে।

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

কারণ `"Masum"` truthy।

**সতর্কতা:** `or` শুধু `None` নয়, সব falsy value-এর ক্ষেত্রেই বিকল্প value বেছে নেয়।

```python
count = 0

result = count or 10

print(result)
```

Output:

```text
10
```

যদি `0` একটি valid value হয় এবং শুধু `None`-এর জন্য default দিতে চাও, তাহলে explicit check ব্যবহার করো।

```python
count = 0

if count is None:
    result = 10
else:
    result = count

print(result)
```

Output:

```text
0
```

## 12. Truthiness and User Input

Python-এর `input()` সবসময় String return করে। তাই user-এর input খালি কি না পরীক্ষা করার সময় truthiness ব্যবহার করা যায়।

Example:

```python
name = input("Enter your name: ")

if name:
    print("Hello,", name)
else:
    print("Name cannot be empty.")
```

User কিছু না লিখে Enter চাপলে empty String পাওয়া যায় এবং `else` block execute হয়।

তবে user শুধু space দিলে String-টি non-empty থাকবে। Space-ও বাদ দিতে চাইলে:

```python
name = input("Enter your name: ").strip()

if name:
    print("Hello,", name)
else:
    print("Name cannot be empty.")
```

এখানে `strip()` শুরু ও শেষের whitespace সরিয়ে দেয়।

### Important Example: Boolean-Like Input

```python
answer = input("Are you ready? ")

if answer:
    print("You entered something.")
else:
    print("You entered nothing.")
```

User `False` লিখলেও `"False"` non-empty String হওয়ায় প্রথম message দেখাবে।

অতএব, truthiness দিয়ে input খালি কি না পরীক্ষা করা যায়; কিন্তু input-এর অর্থ Boolean কি না, তা আলাদাভাবে validate করতে হবে।

## 13. Truthiness and `None`

`None` falsy হলেও `None` check এবং general falsiness check এক নয়।

```python
value = None

print(bool(value))
print(value is None)
```

Output:

```text
False
True
```

কিন্তু `value = 0` হলে:

```python
value = 0

print(bool(value))
print(value is None)
```

Output:

```text
False
False
```

দুই ক্ষেত্রেই `bool(value)` হলো `False`, কিন্তু শুধু প্রথম value-টি `None`।

**Best Practice:**

- শুধু `None` পরীক্ষা করতে `value is None` ব্যবহার করো।
- সব falsy value পরীক্ষা করতে `if not value` ব্যবহার করো।
- Empty collection পরীক্ষা করতে `if not collection` ব্যবহার করতে পারো।

## 14. Common Beginner Mistakes

### Mistake 1: Thinking `"False"` Is Falsy

```python
print(bool("False"))
```

Output:

```text
True
```

কারণ এটি non-empty String।

### Mistake 2: Thinking a List with `0` Is Falsy

```python
print(bool([0]))
```

Output:

```text
True
```

List-এ একটি element আছে, তাই এটি truthy।

### Mistake 3: Treating `0` and `None` as the Same

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

`0` falsy, কিন্তু `None` নয়।

### Mistake 4: Using `or` When Zero Is a Valid Value

```python
marks = 0

result = marks or 100

print(result)
```

Output:

```text
100
```

এখানে `0` falsy হওয়ায় `100` নেওয়া হয়েছে। Zero-কে valid value হিসেবে রাখতে হলে explicit `None` check করো।

### Mistake 5: Forgetting Whitespace in Input

```python
name = "   "

if name:
    print("Name provided.")
```

Output:

```text
Name provided.
```

Space-যুক্ত String non-empty, তাই truthy। Whitespace-only input প্রত্যাখ্যান করতে `strip()` ব্যবহার করো।

## 15. Practice Exercises

### Exercise 1: Identify Truthy and Falsy Values

নিচের প্রতিটি value-এর `bool()` result নির্ণয় করো:

```python
print(bool(0))
print(bool(-10))
print(bool(0.0))
print(bool(" "))
print(bool(""))
print(bool([]))
print(bool([0]))
print(bool({}))
print(bool(None))
```

### Exercise 2: Check an Empty List

একটি `students` list তৈরি করো।

- List খালি হলে `"No students found."` print করো।
- List-এ element থাকলে `"Students found."` print করো।

`len()` ব্যবহার না করে truthiness দিয়ে সমাধান করো।

### Exercise 3: Compare `not` and `is None`

```python
value = 0

print(not value)
print(value is None)
```

দুটি result কেন আলাদা, ব্যাখ্যা করো।

### Exercise 4: Default Username

একটি `username` variable-এ empty String রাখো। `or` ব্যবহার করে `"Guest"` default value হিসেবে নাও।

এরপর `username = "Masum"` দিয়ে আবার পরীক্ষা করো।

### Exercise 5: User Input Validation

একটি program লেখো, যা user-এর কাছ থেকে নাম নেবে। `strip()` ব্যবহার করে শুরু ও শেষের whitespace সরাবে। এরপর নাম খালি হলে error message এবং অন্যথায় greeting দেখাবে।

### Exercise 6: Logical Operators

নিচের expression-গুলোর result অনুমান করো:

```python
print(0 and 5)
print(3 and 5)
print(0 or 5)
print(3 or 5)
print(not [])
print(not [0])
```

### Exercise 7: Mini Project — Simple Data Availability Checker

একটি program লেখো, যেখানে:

```python
username = "Masum"
email = ""
phone = None
```

প্রতিটি value-এর জন্য পরীক্ষা করো:

- Username খালি কি না।
- Email দেওয়া হয়েছে কি না।
- Phone-এর value `None` কি না।

প্রতিটি ক্ষেত্রের জন্য উপযুক্ত message print করো।

## 16. Key Takeaways

- Truthy value Boolean context-এ `True` হিসেবে বিবেচিত হয়।
- Falsy value Boolean context-এ `False` হিসেবে বিবেচিত হয়।
- `0`, `None`, `False`, empty String এবং empty collection হলো প্রচলিত falsy value।
- Non-empty String এবং non-empty collection truthy, এমনকি তাদের ভেতরে `0` বা `False` থাকলেও।
- `bool()` কোনো value-এর truth value পরীক্ষা করে।
- `if value` এবং `if not value` দিয়ে truthiness ব্যবহার করা যায়।
- `and` ও `or` operand return করতে পারে; সবসময় Boolean নয়।
- `or` দিয়ে default value দেওয়া যায়, তবে zero বা empty value valid হলে সতর্ক থাকতে হবে।
- `None` পরীক্ষা করতে `is None` ব্যবহার করো।
- User input validation-এর সময় whitespace-এর জন্য `strip()` কাজে লাগে।

## 17. Next Topic

পরবর্তী ফাইল:

**`14_List_Data_Type.md`**

সেখানে Python-এর `list`, element, indexing, slicing, mutable behavior এবং list-এর basic operations শেখা হবে।