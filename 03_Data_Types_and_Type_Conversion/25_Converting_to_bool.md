# 25. Converting to `bool()` in Python

## 1. Introduction to `bool()`

Python-এ `bool()` হলো একটি built-in function, যা কোনো value-কে Boolean value-তে convert করে।

Python-এ Boolean-এর দুটি value রয়েছে:

- `True`
- `False`

সাধারণত কোনো condition সত্য কি না, কোনো value আছে কি না, অথবা কোনো collection খালি কি না—এসব পরীক্ষা করতে Boolean value ব্যবহার করা হয়।

Example:

```python
print(bool(1))
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

এখানে `bool()` প্রতিটি value-কে `True` অথবা `False`-এ convert করেছে।

## 2. Syntax of `bool()`

`bool()` function-এর সাধারণ syntax:

```python
bool(value)
```

এখানে `value` হলো যে value-টিকে Boolean-এ convert করতে চাই।

Example:

```python
a = bool(10)
b = bool(0)

print(a)
print(b)

print(type(a))
print(type(b))
```

Output:

```text
True
False
<class 'bool'>
<class 'bool'>
```

**মনে রাখবে:** `bool()`-এর result সব সময় Boolean value—`True` অথবা `False`।

## 3. Truthy and Falsy Values

Python-এ Boolean conversion বোঝার জন্য দুটি গুরুত্বপূর্ণ term জানতে হবে।

**Truthy value:** যে value-কে `bool()` করলে `True` পাওয়া যায়।

**Falsy value:** যে value-কে `bool()` করলে `False` পাওয়া যায়।

Example:

```python
print(bool(100))
print(bool(-5))
print(bool("Hello"))
print(bool([1, 2, 3]))
```

Output:

```text
True
True
True
True
```

এগুলো truthy value।

অন্যদিকে:

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

এগুলো falsy value।

## 4. Converting Integer to Boolean

Integer-এর ক্ষেত্রে:

- `0` → `False`
- অন্য যেকোনো Integer → `True`

Example:

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

Negative Integer-ও truthy।

**Important:** `bool(-1)` হলো `True`, কারণ এটি শূন্য নয়।

## 5. Converting Float to Boolean

Float-এর ক্ষেত্রেও নিয়ম একই:

- `0.0` → `False`
- অন্য যেকোনো Float → `True`

Example:

```python
print(bool(0.0))
print(bool(0.5))
print(bool(-2.5))
```

Output:

```text
False
True
True
```

এখানে `0.0` falsy, কিন্তু `0.5` ও `-2.5` truthy।

## 6. Converting String to Boolean

String-এর ক্ষেত্রে সবচেয়ে গুরুত্বপূর্ণ নিয়ম:

- Empty String `""` → `False`
- Non-empty String → `True`

Example:

```python
print(bool(""))
print(bool("Python"))
print(bool("Hello"))
print(bool("0"))
print(bool("False"))
```

Output:

```text
False
True
True
True
True
```

এখানে `"0"` এবং `"False"`—দুটিই String এবং দুটিই non-empty। তাই দুটির result `True`।

**মনে রাখবে:** `bool()` String-এর অর্থ যাচাই করে না; String খালি কি না, সেটি বিবেচনা করে।

### 6.1 Whitespace-Only String

```python
print(bool(" "))
print(bool("   "))
```

Output:

```text
True
True
```

Whitespace-যুক্ত String-ও non-empty হওয়ায় truthy।

যদি whitespace-কে empty input হিসেবে বিবেচনা করতে চাও, তাহলে `strip()` ব্যবহার করতে পারো।

```python
text = "   "

print(bool(text.strip()))
```

Output:

```text
False
```

`strip()` শুরু ও শেষের whitespace সরিয়ে দেয়। ফলে এখানে Empty String তৈরি হয়েছে।

## 7. Converting List to Boolean

List-এর ক্ষেত্রে:

- Empty List `[]` → `False`
- Non-empty List → `True`

Example:

```python
print(bool([]))
print(bool([1]))
print(bool([1, 2, 3]))
```

Output:

```text
False
True
True
```

List-এর মধ্যে `0`, `False` বা `None` থাকলেও List নিজে non-empty হলে truthy হয়।

```python
print(bool([0]))
print(bool([False]))
print(bool([None]))
```

Output:

```text
True
True
True
```

কারণ এখানে List খালি নয়।

## 8. Converting Tuple to Boolean

Tuple-এর ক্ষেত্রেও একই নিয়ম:

- Empty Tuple `()` → `False`
- Non-empty Tuple → `True`

Example:

```python
print(bool(()))
print(bool((10,)))
print(bool((1, 2, 3)))
```

Output:

```text
False
True
True
```

একটি element-যুক্ত Tuple তৈরির সময় comma গুরুত্বপূর্ণ:

```python
data = (10,)

print(type(data))
print(bool(data))
```

Output:

```text
<class 'tuple'>
True
```

## 9. Converting Set to Boolean

Set-এর ক্ষেত্রে:

- Empty Set → `False`
- Non-empty Set → `True`

Example:

```python
print(bool(set()))
print(bool({1}))
print(bool({1, 2, 3}))
```

Output:

```text
False
True
True
```

Python-এ `{}` একটি Empty Dictionary, Empty Set নয়। তাই Empty Set তৈরির জন্য `set()` ব্যবহার করতে হয়।

## 10. Converting Dictionary to Boolean

Dictionary-এর ক্ষেত্রেও নিয়ম:

- Empty Dictionary `{}` → `False`
- Non-empty Dictionary → `True`

Example:

```python
print(bool({}))
print(bool({"name": "Masum"}))
print(bool({"a": 1, "b": 2}))
```

Output:

```text
False
True
True
```

Dictionary-তে কতগুলো key-value pair আছে, তার ওপর truthiness নির্ভর করে। Non-empty হলে truthy।

## 11. Converting `None` to Boolean

Python-এর `None` হলো একটি special value, যা সাধারণত value অনুপস্থিত বোঝায়।

```python
value = None

print(bool(value))
```

Output:

```text
False
```

`None` সব সময় falsy।

তবে কোনো variable-এর value `None` কি না পরীক্ষা করতে `bool()`-এর পরিবর্তে `is None` ব্যবহার করা ভালো।

```python
value = None

print(value is None)
```

Output:

```text
True
```

এভাবে বোঝা যায় variable-এ আসল `None` value আছে কি না।

## 12. Converting Boolean to Boolean

Boolean value-কে `bool()` দিলে সেটি একই Boolean value return করে।

```python
print(bool(True))
print(bool(False))
```

Output:

```text
True
False
```

## 13. Bytes and Bytearray to Boolean

Bytes ও Bytearray-এর ক্ষেত্রেও সাধারণ নিয়ম হলো:

- Empty object → `False`
- Non-empty object → `True`

Example:

```python
print(bool(b""))
print(bool(b"Hello"))

print(bool(bytearray()))
print(bool(bytearray(b"Hello")))
```

Output:

```text
False
True
False
True
```

এখানে object-এ data আছে কি না, সেটি গুরুত্বপূর্ণ।

## 14. Important Falsy Values in Python

Python-এর সাধারণ built-in falsy values মনে রাখা খুব গুরুত্বপূর্ণ।

| Value | Boolean Result |
|---|---|
| `False` | `False` |
| `None` | `False` |
| `0` | `False` |
| `0.0` | `False` |
| `0j` | `False` |
| `""` | `False` |
| `[]` | `False` |
| `()` | `False` |
| `set()` | `False` |
| `{}` | `False` |
| `range(0)` | `False` |

সাধারণভাবে, numeric zero, empty collection এবং empty String falsy।

অন্যদিকে, non-empty String ও collection এবং non-zero number truthy।

## 15. Using `bool()` in Conditional Statements

Boolean conversion `if` statement-এ খুব কাজে লাগে।

Example:

```python
name = "Masum"

if bool(name):
    print("Name is available.")
else:
    print("Name is empty.")
```

Output:

```text
Name is available.
```

তবে Python-এ `if` statement-এর মধ্যে সাধারণত `bool()` আলাদাভাবে লেখার প্রয়োজন নেই।

আরও সহজভাবে:

```python
name = "Masum"

if name:
    print("Name is available.")
else:
    print("Name is empty.")
```

দুটি code-ই একই ফলাফল দেয়।

## 16. Checking Whether a Collection Is Empty

কোনো List বা Dictionary খালি কি না পরীক্ষা করতে Boolean conversion ব্যবহার করা যায়।

Example:

```python
students = []

if not students:
    print("No students found.")
else:
    print("Students are available.")
```

Output:

```text
No students found.
```

এখানে Empty List falsy। তাই `not students`-এর result `True` হয়েছে।

Dictionary-এর ক্ষেত্রেও একইভাবে কাজ করে:

```python
student = {"name": "Masum"}

if student:
    print("Student information exists.")
else:
    print("Student information is empty.")
```

Output:

```text
Student information exists.
```

## 17. Using `bool()` with User Input

Python-এর `input()` সব সময় String return করে। তাই user `0` লিখলেও সেটি String `"0"` হিসেবে পাওয়া যায়।

Example:

```python
value = input("Enter something: ")

print(bool(value))
```

Input:

```text
0
```

Output:

```text
True
```

কারণ `"0"` একটি non-empty String।

### 17.1 Checking Empty Input

```python
name = input("Enter your name: ")

if name.strip():
    print("Name entered successfully.")
else:
    print("Name cannot be empty.")
```

Input:

```text
   [user enters only spaces]
```

Output:

```text
Name cannot be empty.
```

এখানে `strip()` whitespace সরিয়ে দেয়। ফলে শুধু space দিলে condition falsy হয়।

### 17.2 Converting User Input to a Boolean

যদি user `True` বা `False` লিখে Boolean input দিতে চায়, তাহলে সরাসরি `bool(input())` ব্যবহার করা ঠিক নয়।

ভালো পদ্ধতি:

```python
answer = input("Are you a student? (yes/no): ").strip().lower()

if answer == "yes":
    is_student = True
elif answer == "no":
    is_student = False
else:
    print("Invalid answer.")
    is_student = None

print(is_student)
```

এখানে user-এর দেওয়া text যাচাই করে Boolean value তৈরি করা হয়েছে।

**মনে রাখবে:** `bool("False")`-এর result `True`। তাই text-কে Boolean-এ রূপান্তর করতে হলে আগে text-এর অর্থ যাচাই করতে হবে।

## 18. Common Mistakes

### 18.1 Thinking `"False"` Is False

```python
print(bool("False"))
```

Output:

```text
True
```

কারণ `"False"` একটি non-empty String।

### 18.2 Thinking `"0"` Is False

```python
print(bool("0"))
```

Output:

```text
True
```

String `"0"` এবং numeric `0` এক নয়।

```python
print(bool(0))
print(bool("0"))
```

Output:

```text
False
True
```

### 18.3 Thinking a List with Zero Is Falsy

```python
print(bool([0]))
```

Output:

```text
True
```

List-এ একটি element আছে। তাই List non-empty।

### 18.4 Using `bool()` to Validate Numeric Input

```python
value = input("Enter a number: ")

if bool(value):
    print("Valid number")
```

এটি সঠিক numeric validation নয়। User `"hello"` দিলেও condition `True` হবে।

Numeric input যাচাই করতে উপযুক্ত conversion এবং error handling ব্যবহার করো।

```python
value = input("Enter a number: ")

try:
    number = float(value)
    print("Valid number:", number)
except ValueError:
    print("Invalid number.")
```

### 18.5 Confusing Boolean Conversion with Comparison

```python
print(bool(5))
print(5 > 0)
```

Output:

```text
True
True
```

দুটি result একই হলেও কাজ আলাদা:

- `bool(5)` পরীক্ষা করে `5` truthy কি না।
- `5 > 0` দুটি value-এর মধ্যে comparison করে।

## 19. Practical Examples

### Example 1: Check User Name

```python
name = input("Enter your name: ").strip()

if name:
    print("Welcome,", name)
else:
    print("Name is required.")
```

### Example 2: Check Shopping Cart

```python
cart = ["Book", "Pen", "Notebook"]

if cart:
    print("Cart contains items.")
else:
    print("Cart is empty.")
```

Output:

```text
Cart contains items.
```

### Example 3: Check Available Marks

```python
marks = []

if not marks:
    print("Marks are not available.")
else:
    print("Marks are available.")
```

Output:

```text
Marks are not available.
```

### Example 4: Check Account Status

```python
is_active = True

if is_active:
    print("Account is active.")
else:
    print("Account is inactive.")
```

Output:

```text
Account is active.
```

## 20. Practice Exercises

### Exercise 1: Basic Conversion

নিচের expression-গুলোর output অনুমান করো:

```python
print(bool(0))
print(bool(10))
print(bool(-5))
print(bool(""))
print(bool("Python"))
```

### Exercise 2: String Conversion

Output অনুমান করো:

```python
print(bool("0"))
print(bool("False"))
print(bool(" "))
print(bool("".strip()))
```

প্রতিটি result-এর কারণ ব্যাখ্যা করো।

### Exercise 3: Collection Conversion

নিচের code-এর output নির্ণয় করো:

```python
print(bool([]))
print(bool([0]))
print(bool(()))
print(bool((None,)))
print(bool({}))
print(bool({"a": None}))
```

### Exercise 4: `None` Checking

`value = None` দিয়ে পরীক্ষা করো:

```python
print(bool(value))
print(value is None)
```

দুটি expression-এর পার্থক্য ব্যাখ্যা করো।

### Exercise 5: User Input Validation

একটি program তৈরি করো, যা user-এর name নেবে। User খালি input অথবা শুধু whitespace দিলে error message দেখাবে।

### Exercise 6: Yes/No Input

User-এর কাছ থেকে `yes` অথবা `no` নাও। Input যাচাই করে যথাক্রমে `True` অথবা `False` তৈরি করো। অন্য input দিলে invalid message দেখাও।

### Exercise 7: Shopping Cart

একটি List-এ shopping cart-এর item রাখো। Cart খালি হলে `Cart is empty` এবং non-empty হলে `Items are available` দেখাও।

### Exercise 8: Mini Project — Simple Login Validation

একটি program তৈরি করো, যেখানে username এবং password input নেওয়া হবে।

শর্ত:

1. Username খালি হতে পারবে না।
2. Password খালি হতে পারবে না।
3. শুধু non-empty input পাওয়া গেলে `Input received` দেখাবে।
4. অন্যথায় `Username and password are required` দেখাবে।

এটি শুধু input validation-এর অনুশীলন; বাস্তব authentication system নয়।

## 21. Key Takeaways

- `bool()` যেকোনো object-এর truth value অনুযায়ী `True` অথবা `False` return করে।
- Numeric zero, `None`, Empty String এবং empty collection সাধারণত falsy।
- Non-zero number, non-empty String এবং non-empty collection সাধারণত truthy।
- `"False"` এবং `"0"` String হওয়ায় truthy।
- `[0]`-এর মতো non-empty collection-ও truthy।
- `if` statement-এ সাধারণত `bool()` না লিখেও সরাসরি value পরীক্ষা করা যায়।
- `bool(input())` দিয়ে numeric বা textual input-এর অর্থ যাচাই করা যায় না।
- `None` পরীক্ষা করতে `is None` ব্যবহার করা ভালো।
- Numeric input যাচাই করতে `int()` বা `float()`-এর সঙ্গে `try-except` ব্যবহার করা যায়।

## 22. Next Topic

পরবর্তী ফাইল:

**`26_Converting_Between_Collection_Types.md`**

সেখানে List, Tuple, Set, Dictionary এবং অন্যান্য collection-এর মধ্যে conversion, conversion-এর সময় data loss এবং common mistakes বিস্তারিতভাবে শেখা হবে।