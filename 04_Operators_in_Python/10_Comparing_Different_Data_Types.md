# 10. Comparing Different Data Types in Python

## 1. Introduction

Python-এ Comparison Operator (`==`, `!=`, `<`, `>`, `<=`, `>=`) ব্যবহার করে দুটি Value তুলনা করা হয়।

তবে দুটি Value-এর Data Type আলাদা হলে সব ধরনের Comparison কাজ করবে না। কিছু Comparison বৈধ, আবার কিছু Comparison করলে `TypeError` হতে পারে।

Example:

```python
print(10 == 10.0)
print(10 == "10")
```

Output:

```text
True
False
```

ব্যাখ্যা:

- `10 == 10.0` → `True`, কারণ Integer ও Float-এর Numeric Value সমান।
- `10 == "10"` → `False`, কারণ Integer `10` এবং String `"10"` আলাদা Value।

**মনে রাখবে:** Comparison করার সময় শুধু Value নয়, Data Type-এর আচরণও বুঝতে হবে।

## 2. Comparing Integers and Floats

Integer এবং Float—দুটিই Numeric Data Type। তাই তাদের মধ্যে সাধারণ Numeric Comparison করা যায়।

Example:

```python
a = 10
b = 10.0

print(a == b)
print(a != b)
print(a < 15.5)
print(9.5 <= a)
```

Output:

```text
True
False
True
True
```

ব্যাখ্যা:

- `10 == 10.0` → `True`
- `10 != 10.0` → `False`
- `10 < 15.5` → `True`
- `9.5 <= 10` → `True`

Python Numeric Comparison-এর ক্ষেত্রে Integer ও Float-এর মান তুলনা করতে পারে।

## 3. Comparing Numbers and Strings

Python-এ String-এর মধ্যে লেখা Number এবং আসল Number একই Data Type নয়।

Example:

```python
number = 25
text = "25"

print(number == text)
print(number != text)
```

Output:

```text
False
True
```

কারণ:

- `25` হলো Integer।
- `"25"` হলো String।
- তাদের Value দেখতে একই রকম হলেও Data Type আলাদা।

### 3.1 Ordering Comparison

নিচের Code-টি চালালে Error হবে:

```python
print(25 < "30")
```

Error:

```text
TypeError
```

কারণ Python সাধারণভাবে Integer ও String-এর মধ্যে `<`, `>` বা এ ধরনের Ordering Comparison করতে দেয় না।

### 3.2 How to Compare Them Correctly

যদি String-এর মধ্যে Number থাকে এবং সেটিকে Numeric Value হিসেবে তুলনা করতে চাও, তাহলে উপযুক্ত Type-এ Convert করতে হবে।

```python
number = 25
text = "30"

print(number < int(text))
```

Output:

```text
True
```

এখানে `int(text)` String `"30"`-কে Integer `30`-এ Convert করেছে।

তবে String-এর মধ্যে বৈধ Integer লেখা না থাকলে `int()` ব্যবহার করলে `ValueError` হতে পারে।

Example:

```python
text = "hello"

# int(text)  # ValueError হবে
```

**গুরুত্বপূর্ণ:** Conversion করার আগে Input-টি বৈধ কি না, তা প্রয়োজন অনুযায়ী যাচাই করতে হবে।

## 4. Comparing Booleans and Numbers

Python-এ `bool` হলো `int`-এর একটি Subclass। তাই Numeric Comparison-এর ক্ষেত্রে:

- `False`-এর Numeric Value হলো `0`।
- `True`-এর Numeric Value হলো `1`।

Example:

```python
print(True == 1)
print(False == 0)
print(True > False)
print(True < 2)
```

Output:

```text
True
True
True
True
```

ব্যাখ্যা:

| Expression | Result | কারণ |
|---|---|---|
| `True == 1` | `True` | `True` Numeric Comparison-এ 1-এর সমান |
| `False == 0` | `True` | `False` Numeric Comparison-এ 0-এর সমান |
| `True > False` | `True` | 1, 0-এর চেয়ে বড় |
| `True < 2` | `True` | 1, 2-এর চেয়ে ছোট |

তবে `True` ও `False`-কে সাধারণত Boolean Value হিসেবেই ব্যবহার করা ভালো।

## 5. Comparing Strings

String-এর মধ্যে Text থাকে। Python String-এর Comparison Character-এর Unicode Code Point অনুযায়ী Lexicographical Order-এ করে।

Example:

```python
print("apple" == "apple")
print("apple" != "banana")
print("apple" < "banana")
```

Output:

```text
True
True
True
```

### 5.1 Case Sensitivity

Python-এর সাধারণ String Comparison Case-Sensitive।

Example:

```python
print("Python" == "python")
print("A" < "a")
```

Output:

```text
False
True
```

ব্যাখ্যা:

- `"Python"` এবং `"python"` সমান নয়, কারণ `P` ও `p` আলাদা Character।
- Unicode Code Point অনুযায়ী `"A"`-এর মান `"a"`-এর চেয়ে ছোট।

### 5.2 Case-Insensitive Comparison

Case উপেক্ষা করে String তুলনা করতে `lower()` বা `casefold()` ব্যবহার করা যায়।

```python
a = "Python"
b = "PYTHON"

print(a.lower() == b.lower())
```

Output:

```text
True
```

আরও সাধারণ Unicode Case-Insensitive Comparison-এর জন্য `casefold()` উপযোগী হতে পারে।

```python
a = "Python"
b = "PYTHON"

print(a.casefold() == b.casefold())
```

Output:

```text
True
```

## 6. Comparing Lists and Tuples

List এবং Tuple-এর মধ্যে একই ধরনের Sequence Comparison করা যায়।

### 6.1 Equality Comparison

```python
list_a = [1, 2, 3]
list_b = [1, 2, 3]
tuple_a = (1, 2, 3)

print(list_a == list_b)
print(list_a == tuple_a)
```

Output:

```text
True
False
```

ব্যাখ্যা:

- দুটি List-এর Elements সমান এবং একই ক্রমে আছে, তাই Result `True`।
- List ও Tuple আলাদা Data Type, তাই তাদের Equality Comparison-এর Result `False`।

### 6.2 Lexicographical Comparison

List বা Tuple-এর Elements তুলনা করে Lexicographical Ordering করা যায়, যদি সংশ্লিষ্ট Elements-গুলো তুলনাযোগ্য হয়।

```python
print([1, 2, 3] < [1, 2, 4])
print((1, 2) < (1, 3))
```

Output:

```text
True
True
```

Python প্রথমে বাম দিকের Elements তুলনা করে। প্রথম যে Elements-এ পার্থক্য পাওয়া যায়, তার ভিত্তিতে Result নির্ধারিত হয়।

তবে List ও Tuple-এর মধ্যে Ordering Comparison করলে `TypeError` হতে পারে।

```python
# print([1, 2] < (1, 2))  # TypeError
```

## 7. Comparing `None` with Other Values

`None` সাধারণত কোনো Value অনুপস্থিত বা এখনো নির্ধারিত নয়—এমন বোঝাতে ব্যবহৃত হয়।

`None`-এর সঙ্গে Equality Comparison করা যায়।

```python
value = None

print(value == None)
print(value != 10)
```

Output:

```text
True
True
```

তবে Python-এ `None` যাচাই করার Recommended উপায় হলো `is` বা `is not` ব্যবহার করা।

```python
value = None

print(value is None)
print(value is not None)
```

Output:

```text
True
False
```

`None`-কে Integer বা String-এর সঙ্গে Ordering Comparison করা যায় না।

```python
# print(None < 10)  # TypeError
```

**Best Practice:** কোনো Variable-এর মান `None` কি না যাচাই করতে `value is None` ব্যবহার করো।

## 8. Comparing Different Collection Types

Dictionary এবং Set-এর Comparison-এর নিয়ম List ও Tuple থেকে আলাদা।

### 8.1 Dictionary Equality

দুটি Dictionary-এর Key-Value Pair সমান হলে তাদের Equality Comparison `True` হতে পারে।

```python
a = {"name": "Masum", "age": 22}
b = {"age": 22, "name": "Masum"}

print(a == b)
```

Output:

```text
True
```

Dictionary-এর Key-Value Pair-এর ক্রম আলাদা হলেও Equality Comparison-এ সমস্যা হয় না।

### 8.2 Set Equality

```python
a = {1, 2, 3}
b = {3, 2, 1}

print(a == b)
```

Output:

```text
True
```

Set-এ Element-এর ক্রম গুরুত্বপূর্ণ নয়। একই Elements থাকলে দুটি Set সমান।

### 8.3 Set Ordering

Set-এর `<` ও `>` সাধারণ Numeric Ordering নয়। এগুলো Subset ও Superset সম্পর্ক বোঝাতে পারে।

```python
a = {1, 2}
b = {1, 2, 3}

print(a < b)
print(b > a)
```

Output:

```text
True
True
```

এখানে `a` হলো `b`-এর Proper Subset।

## 9. Comparing Objects of Different Types

Python-এ বিভিন্ন Built-in Type-এর Equality Comparison অনেক সময় বৈধ হয়, কিন্তু Result `False` হতে পারে।

Example:

```python
print(10 == "10")
print([1, 2] == (1, 2))
print(5 == None)
```

Output:

```text
False
False
False
```

কিন্তু Ordering Comparison-এর ক্ষেত্রে সব Type একে অপরের সঙ্গে তুলনাযোগ্য নয়।

Example:

```python
# print(10 < "20")   # TypeError
# print(None < 5)    # TypeError
# print([1, 2] < (1, 2))  # TypeError
```

কোডের কোনো লাইনে `TypeError` হলে সেই লাইনটি স্বাভাবিকভাবে Evaluate সম্পন্ন করতে পারে না।

## 10. Type Conversion Before Comparison

কোনো Comparison-এর আগে Data Type Convert করা প্রয়োজন হতে পারে।

### Example 1: String to Integer

```python
age = "20"

print(int(age) >= 18)
```

Output:

```text
True
```

### Example 2: String to Float

```python
price = "99.50"

print(float(price) < 100)
```

Output:

```text
True
```

### Example 3: Convert to String

```python
number = 25
text = "25"

print(str(number) == text)
```

Output:

```text
True
```

এখানে Integer `25`-কে String `"25"`-এ Convert করা হয়েছে।

**মনে রাখবে:** কোন Type-এ Convert করবে, তা নির্ভর করে তুমি কী ধরনের Comparison করতে চাও তার ওপর।

## 11. Common Mistakes

### Mistake 1: Assuming Same-Looking Values Are Equal

```python
print(5 == "5")
```

Output:

```text
False
```

Integer ও String একই রকম দেখালেও তারা একই Value নয়।

### Mistake 2: Comparing Incompatible Types with `<`

```python
# print(5 < "10")  # TypeError
```

সঠিক পদ্ধতি:

```python
print(5 < int("10"))
```

Output:

```text
True
```

### Mistake 3: Assuming String Comparison Is Numeric

```python
print("100" < "20")
```

Output:

```text
True
```

এটি `True`, কারণ String-গুলো Lexicographical Order-এ তুলনা করা হয়েছে; Numeric Value হিসেবে নয়।

Numeric Comparison করতে:

```python
print(int("100") < int("20"))
```

Output:

```text
False
```

### Mistake 4: Using `==` Instead of `is` for `None`

```python
value = None

if value is None:
    print("No value available")
```

Output:

```text
No value available
```

`None` যাচাই করতে `is None` ব্যবহার করাই Recommended।

## 12. Practice Exercises

### Basic Level

1. `10 == 10.0`-এর Result কী?
2. `10 == "10"`-এর Result কী?
3. `True == 1`-এর Result কী?
4. `"apple" < "banana"`-এর Result কী?
5. `[1, 2] == (1, 2)`-এর Result কী?

### Intermediate Level

6. কেন `10 < "20"`-এ `TypeError` হয়?
7. কীভাবে String `"50"`-কে Integer-এ Convert করে 40-এর সঙ্গে Compare করবে?
8. `"100" < "20"` কেন `True` হয়?
9. `None` যাচাই করার Recommended পদ্ধতি কী?
10. Set `{1, 2}` এবং `{2, 1}` কি সমান?

### Output Prediction

```python
print(5 == 5.0)
print(5 == "5")
print(True == 1)
print("100" < "20")
print([1, 2] == [1, 2])
print({1, 2} == {2, 1})
```

### Answers

```text
True
False
True
True
True
True
```

## 13. Practical Challenge

একটি Program তৈরি করো, যেখানে User-এর কাছ থেকে বয়স String হিসেবে Input নেওয়া হবে। এরপর সেটিকে Integer-এ Convert করে বয়স 18 বা তার বেশি কি না পরীক্ষা করতে হবে।

```python
age_text = input("Enter your age: ")

age = int(age_text)

if age >= 18:
    print("You are an adult.")
else:
    print("You are under 18.")
```

Example Input:

```text
20
```

Output:

```text
You are an adult.
```

এই Program-এ `input()` String Return করে। তাই Numeric Comparison করার আগে `int()` ব্যবহার করা হয়েছে।

বাস্তব Program-এ User ভুল Input দিলে `ValueError` হতে পারে। পরবর্তী Exception Handling Chapter-এ এ ধরনের Error নিরাপদভাবে Handle করা শিখবে।

## 14. Chapter Summary

- Integer ও Float-এর Numeric Comparison করা যায়।
- Integer `10` এবং String `"10"` সমান নয়।
- Incompatible Type-এর Ordering Comparison করলে `TypeError` হতে পারে।
- Boolean Comparison-এ `True`-এর Numeric Value 1 এবং `False`-এর Numeric Value 0।
- String Comparison Case-Sensitive এবং Lexicographical Order অনুসরণ করে।
- List ও Tuple-এর Equality Comparison-এ Type গুরুত্বপূর্ণ।
- Set-এর Equality Comparison-এ Element-এর ক্রম গুরুত্বপূর্ণ নয়।
- Dictionary Equality নির্ভর করে Key-Value Pair-এর ওপর।
- `None` যাচাই করতে `is None` ব্যবহার করা ভালো।
- Numeric Comparison-এর আগে প্রয়োজনে `int()` বা `float()` ব্যবহার করতে হয়।

## 15. Self-Assessment Checklist

- [ ] Integer ও Float Compare করতে পারি।
- [ ] Number এবং String-এর Comparison বুঝি।
- [ ] `TypeError` কেন হয় বুঝি।
- [ ] Boolean ও Number-এর Comparison ব্যাখ্যা করতে পারি।
- [ ] String Comparison-এর Case Sensitivity বুঝি।
- [ ] List, Tuple, Set ও Dictionary-এর Equality Comparison বুঝি।
- [ ] `None` যাচাই করার সঠিক পদ্ধতি জানি।
- [ ] Comparison-এর আগে প্রয়োজনীয় Type Conversion করতে পারি।

**Next Topic:** `11_Logical_Operators.md`