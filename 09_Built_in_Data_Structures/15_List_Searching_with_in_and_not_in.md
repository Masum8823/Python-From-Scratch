# 15. Searching Lists with in and not in in Python

## 1. Introduction

Python List-এর মধ্যে কোনো নির্দিষ্ট element আছে কি না, তা পরীক্ষা করার জন্য `in` এবং `not in` Membership Operators ব্যবহার করা হয়।

এই Operators দুটি কোনো element List-এর মধ্যে আছে কি না পরীক্ষা করে এবং ফলাফল হিসেবে `True` অথবা `False` return করে।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print("Mango" in fruits)
print("Grapes" in fruits)
```

Output:

```text
True
False
```

এখানে:

- `"Mango"` List-এর মধ্যে আছে, তাই `True`।
- `"Grapes"` List-এর মধ্যে নেই, তাই `False`।

## 2. Understanding the in Operator

`in` Operator ব্যবহার করে কোনো element List-এর মধ্যে আছে কি না পরীক্ষা করা হয়।

Syntax:

```python
element in list_name
```

Element List-এর মধ্যে থাকলে `True` return করে। অন্যথায় `False` return করে।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

print(20 in numbers)
print(40 in numbers)
print(100 in numbers)
```

Output:

```text
True
True
False
```

এখানে `20` এবং `40` List-এর মধ্যে রয়েছে। কিন্তু `100` নেই।

## 3. Understanding the not in Operator

`not in` Operator ব্যবহার করে কোনো element List-এর মধ্যে নেই কি না পরীক্ষা করা হয়।

Syntax:

```python
element not in list_name
```

Element List-এর মধ্যে না থাকলে `True` return করে। আর থাকলে `False` return করে।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango"]

print("Orange" not in fruits)
print("Apple" not in fruits)
```

Output:

```text
True
False
```

এখানে:

- `"Orange"` List-এ নেই, তাই `True`।
- `"Apple"` List-এ আছে, তাই `False`।

## 4. Difference Between in and not in

`in` এবং `not in` একে অপরের বিপরীত কাজ করে।

| in | not in |
|---|---|
| Element আছে কি না পরীক্ষা করে। | Element নেই কি না পরীক্ষা করে। |
| থাকলে `True` দেয়। | না থাকলে `True` দেয়। |
| না থাকলে `False` দেয়। | থাকলে `False` দেয়। |

উদাহরণ:

```python
numbers = [10, 20, 30]

print(20 in numbers)
print(20 not in numbers)
```

Output:

```text
True
False
```

## 5. Searching for String Elements

String-এর List-এর মধ্যেও `in` এবং `not in` ব্যবহার করা যায়।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print("Apple" in fruits)
print("Grapes" not in fruits)
```

Output:

```text
True
True
```

এখানে দুটি condition-ই সত্য।

## 6. Searching for Numeric Elements

Integer এবং Float-এর List-এও Membership Operators ব্যবহার করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40.5, 50]

print(30 in numbers)
print(40.5 in numbers)
print(100 not in numbers)
```

Output:

```text
True
True
True
```

## 7. Using in Operator with if Statement

`in` Operator-এর সঙ্গে `if` Statement ব্যবহার করে কোনো element পাওয়া গেলে নির্দিষ্ট কাজ করা যায়।

উদাহরণ:

```python
students = ["Masum", "Rahim", "Karim"]

if "Masum" in students:
    print("Student Found")
else:
    print("Student Not Found")
```

Output:

```text
Student Found
```

এখানে `"Masum"` List-এর মধ্যে আছে, তাই `if` Block execute হয়েছে।

## 8. Using not in Operator with if Statement

`not in` Operator ব্যবহার করে কোনো element List-এর মধ্যে না থাকলে নির্দিষ্ট কাজ করা যায়।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango"]

if "Grapes" not in fruits:
    print("Fruit Not Found")
else:
    print("Fruit Found")
```

Output:

```text
Fruit Not Found
```

এখানে `"Grapes"` List-এর মধ্যে নেই। তাই `if` Block execute হয়েছে।

## 9. Searching for Multiple Elements

একটি List-এর মধ্যে একাধিক element আছে কি না, তা একসঙ্গে পরীক্ষা করা যায়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40, 50]

print(10 in numbers and 20 in numbers)
print(10 in numbers and 100 in numbers)
print(10 in numbers or 100 in numbers)
```

Output:

```text
True
False
True
```

এখানে:

- `and` ব্যবহার করলে দুটি condition-ই `True` হতে হবে।
- `or` ব্যবহার করলে যেকোনো একটি condition `True` হলেই ফলাফল `True` হবে।

## 10. Using Membership Operators with a Loop

Loop-এর মধ্যে `in` ব্যবহার করে কোনো element আছে কি না পরীক্ষা করা যায়।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

search_item = "Mango"

for fruit in fruits:
    if fruit == search_item:
        print("Found:", fruit)
```

Output:

```text
Found: Mango
```

এখানে Loop প্রতিটি element পরীক্ষা করছে। `"Mango"` পাওয়া গেলে সেটি Print করছে।

তবে শুধু element আছে কি না পরীক্ষা করতে চাইলে সরাসরি `in` ব্যবহার করাই সহজ।

```python
fruits = ["Apple", "Banana", "Mango", "Orange"]

print("Mango" in fruits)
```

Output:

```text
True
```

## 11. Case Sensitivity in String Searching

Python-এ String Comparison Case-Sensitive।

অর্থাৎ, `"Apple"` এবং `"apple"` একই String নয়।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango"]

print("Apple" in fruits)
print("apple" in fruits)
```

Output:

```text
True
False
```

এখানে:

- `"Apple"` List-এ আছে।
- `"apple"` List-এ নেই।

Case-Insensitive Search করতে চাইলে `lower()` ব্যবহার করা যায়।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango"]

search_item = "apple"

found = any(fruit.lower() == search_item.lower() for fruit in fruits)

print(found)
```

Output:

```text
True
```

এখানে `lower()` ব্যবহার করে String-গুলোকে lowercase-এ পরিবর্তন করে তুলনা করা হয়েছে।

## 12. Searching in an Empty List

Empty List-এর মধ্যে কোনো element থাকে না।

তাই যেকোনো সাধারণ element পরীক্ষা করলে `in` False এবং `not in` True return করবে।

উদাহরণ:

```python
numbers = []

print(10 in numbers)
print(10 not in numbers)
```

Output:

```text
False
True
```

## 13. Searching in a Nested List

Nested List-এর ক্ষেত্রে `in` Operator সরাসরি শুধু Top-Level Elements পরীক্ষা করে।

উদাহরণ:

```python
numbers = [[10, 20], [30, 40], [50, 60]]

print([10, 20] in numbers)
print(10 in numbers)
```

Output:

```text
True
False
```

এখানে:

- `[10, 20]` একটি সম্পূর্ণ Nested List হিসেবে রয়েছে।
- কিন্তু `10` সরাসরি Outer List-এর element নয়।

Nested List-এর ভিতরে কোনো element খুঁজতে চাইলে আলাদাভাবে Inner List পরীক্ষা করতে হবে।

উদাহরণ:

```python
numbers = [[10, 20], [30, 40], [50, 60]]

print(10 in numbers[0])
print(40 in numbers[1])
```

Output:

```text
True
True
```

## 14. Practical Example: Checking a Student's Name

ধরো, একটি Class-এর Student List রয়েছে। কোনো Student-এর নাম List-এ আছে কি না পরীক্ষা করতে হবে।

উদাহরণ:

```python
students = ["Masum", "Rahim", "Karim", "Hasan"]

name = "Rahim"

if name in students:
    print(name, "is present in the class.")
else:
    print(name, "is not present in the class.")
```

Output:

```text
Rahim is present in the class.
```

## 15. Practical Example: Checking Available Products

ধরো, একটি Shop-এর Available Products List রয়েছে। Customer কোনো Product চাইলে সেটি Available কি না পরীক্ষা করতে হবে।

উদাহরণ:

```python
products = ["Laptop", "Mouse", "Keyboard", "Monitor"]

requested_product = "Mouse"

if requested_product in products:
    print("Product is available.")
else:
    print("Product is not available.")
```

Output:

```text
Product is available.
```

## 16. Common Mistakes

### Mistake 1: Using = Instead of in

ভুল:

```python
numbers = [10, 20, 30]

if 20 = numbers:
    print("Found")
```

এখানে `=` Assignment Operator। এটি Membership Check করার জন্য ব্যবহার করা যায় না।

Correct:

```python
numbers = [10, 20, 30]

if 20 in numbers:
    print("Found")
```

Output:

```text
Found
```

### Mistake 2: Ignoring Case Sensitivity

ভুল ধারণা:

```python
fruits = ["Apple", "Banana"]

print("apple" in fruits)
```

Output:

```text
False
```

কারণ Python-এ String Comparison Case-Sensitive।

Correct:

```python
fruits = ["Apple", "Banana"]

print("apple".lower() in [fruit.lower() for fruit in fruits])
```

Output:

```text
True
```

### Mistake 3: Searching for an Inner Element Directly in a Nested List

ভুল:

```python
numbers = [[10, 20], [30, 40]]

print(10 in numbers)
```

Output:

```text
False
```

কারণ `10` সরাসরি Outer List-এর element নয়।

Correct:

```python
numbers = [[10, 20], [30, 40]]

print(10 in numbers[0])
```

Output:

```text
True
```

### Mistake 4: Confusing in and not in

উদাহরণ:

```python
numbers = [10, 20, 30]

print(20 not in numbers)
```

Output:

```text
False
```

কারণ `20` List-এর মধ্যে আছে। তাই `20 not in numbers` False।

## 17. Important Rules

- `in` এবং `not in` হলো Membership Operators।
- `in` কোনো element আছে কি না পরীক্ষা করে।
- `not in` কোনো element নেই কি না পরীক্ষা করে।
- দুটিই Boolean Result (`True` অথবা `False`) return করে।
- String Search Case-Sensitive।
- Empty List-এর মধ্যে কোনো সাধারণ element থাকে না।
- Nested List-এর ক্ষেত্রে `in` সরাসরি Top-Level Elements পরীক্ষা করে।
- `and` এবং `or`-এর সঙ্গে Membership Operators ব্যবহার করা যায়।
- `if` Statement-এর সঙ্গে এগুলো খুব বেশি ব্যবহার করা হয়।
- Membership Operators শুধু List নয়, অন্যান্য Iterable-এর ক্ষেত্রেও ব্যবহার করা যায়।

## 18. Practice Exercises

### Exercise 1: Check Whether an Element Exists

নিচের List-এ `30` আছে কি না পরীক্ষা করো।

Solution:

```python
numbers = [10, 20, 30, 40, 50]

print(30 in numbers)
```

Output:

```text
True
```

### Exercise 2: Check Whether an Element Does Not Exist

নিচের List-এ `100` নেই কি না পরীক্ষা করো।

Solution:

```python
numbers = [10, 20, 30, 40, 50]

print(100 not in numbers)
```

Output:

```text
True
```

### Exercise 3: Use in with if-else

একটি Student List তৈরি করো। `"Masum"` থাকলে `"Found"` এবং না থাকলে `"Not Found"` Print করো।

Solution:

```python
students = ["Rahim", "Karim", "Masum", "Hasan"]

if "Masum" in students:
    print("Found")
else:
    print("Not Found")
```

Output:

```text
Found
```

### Exercise 4: Search in a Nested List

Nested List-এর দ্বিতীয় Inner List-এর মধ্যে `40` আছে কি না পরীক্ষা করো।

Solution:

```python
numbers = [[10, 20], [30, 40], [50, 60]]

print(40 in numbers[1])
```

Output:

```text
True
```

### Exercise 5: Predict the Output

নিচের Code-এর Output কী হবে?

```python
numbers = [10, 20, 30, 40]

print(20 in numbers)
print(50 in numbers)
print(30 not in numbers)
print(60 not in numbers)
```

Solution:

```text
True
False
False
True
```

## 19. Chapter Summary

এই Topic-এ আমরা শিখেছি:

- Membership Operators কী।
- `in` Operator-এর ব্যবহার।
- `not in` Operator-এর ব্যবহার।
- `in` এবং `not in`-এর পার্থক্য।
- String এবং Numeric List-এ Searching।
- `if-else` Statement-এর সঙ্গে Membership Operators ব্যবহার।
- Multiple Conditions-এর সঙ্গে Searching।
- Case-Sensitive Searching।
- Empty List এবং Nested List-এ Searching।
- Practical Examples এবং Common Mistakes।

## 20. Self-Assessment Checklist

- [ ] Membership Operators কী বুঝি।
- [ ] `in` Operator ব্যবহার করতে পারি।
- [ ] `not in` Operator ব্যবহার করতে পারি।
- [ ] `in` এবং `not in`-এর পার্থক্য বুঝি।
- [ ] `if-else`-এর সঙ্গে Searching করতে পারি।
- [ ] String-এর Case Sensitivity বুঝি।
- [ ] Empty List-এ Searching করতে পারি।
- [ ] Nested List-এর মধ্যে Searching করতে পারি।
- [ ] `and` এবং `or`-এর সঙ্গে Membership Operators ব্যবহার করতে পারি।
- [ ] Common Errors identify করতে পারি।

## 21. Next Topic

**16. Finding List Elements with index()**

পরবর্তী Topic-এ আমরা শিখব কীভাবে Python List-এর মধ্যে কোনো নির্দিষ্ট element-এর Index খুঁজে বের করতে হয়। এজন্য `index()` method ব্যবহার করব।