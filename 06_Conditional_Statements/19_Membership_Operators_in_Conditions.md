# 19. Membership Operators in Conditions

## 1. Membership Operators কী?

Python-এ **Membership Operators** ব্যবহার করে কোনো collection বা sequence-এর মধ্যে নির্দিষ্ট value আছে কি না, তা পরীক্ষা করা হয়।

Python-এ দুটি Membership Operator রয়েছে:

| Operator | অর্থ |
|---|---|
| `in` | কোনো value-এর উপস্থিতি পরীক্ষা করে |
| `not in` | কোনো value-এর অনুপস্থিতি পরীক্ষা করে |

সাধারণত result হিসেবে `True` অথবা `False` পাওয়া যায়।

উদাহরণ:

```python
numbers = [10, 20, 30, 40]

print(20 in numbers)
print(50 in numbers)
```

Output:

```text
True
False
```

কারণ `20` list-এর মধ্যে আছে, কিন্তু `50` নেই।

## 2. `in` Operator কীভাবে কাজ করে?

`in` operator পরীক্ষা করে বাম পাশের value ডান পাশের collection বা sequence-এর মধ্যে আছে কি না।

Syntax:

```python
value in collection
```

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango"]

print("Apple" in fruits)
print("Mango" in fruits)
print("Orange" in fruits)
```

Output:

```text
True
True
False
```

এখানে:

- `"Apple"` list-এ আছে।
- `"Mango"` list-এ আছে।
- `"Orange"` list-এ নেই।

## 3. `not in` Operator কীভাবে কাজ করে?

`not in` পরীক্ষা করে কোনো value collection-এর মধ্যে নেই কি না।

Syntax:

```python
value not in collection
```

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

কারণ:

- `"Orange"` list-এ নেই, তাই result `True`।
- `"Apple"` list-এ আছে, তাই result `False`।

সহজভাবে মনে রাখবে:

- `in` → আছে কি না পরীক্ষা করে।
- `not in` → নেই কি না পরীক্ষা করে।

## 4. `if` Statement-এ Membership Operators

Membership Operators conditional statement-এ খুবই কাজে লাগে।

উদাহরণ:

```python
fruits = ["Apple", "Banana", "Mango"]
fruit = "Banana"

if fruit in fruits:
    print("Fruit found")
else:
    print("Fruit not found")
```

Output:

```text
Fruit found
```

ব্যাখ্যা:

1. `fruit` variable-এর value হলো `"Banana"`।
2. Python পরীক্ষা করে `"Banana" in fruits`।
3. Condition `True` হওয়ায় `if` block execute হয়।

এবার value পরিবর্তন করি:

```python
fruit = "Orange"

if fruit in fruits:
    print("Fruit found")
else:
    print("Fruit not found")
```

Output:

```text
Fruit not found
```

কারণ `"Orange"` list-এর মধ্যে নেই।

## 5. String-এর মধ্যে Membership Check

String-এর মধ্যে কোনো character বা substring আছে কি না, তা পরীক্ষা করতে `in` এবং `not in` ব্যবহার করা যায়।

উদাহরণ:

```python
text = "Python Programming"

print("Python" in text)
print("Program" in text)
print("Java" in text)
```

Output:

```text
True
True
False
```

এখানে `"Program"` হলো string `"Python Programming"`-এর একটি substring।

আরেকটি উদাহরণ:

```python
text = "Hello World"

if "World" in text:
    print("Word found")
else:
    print("Word not found")
```

Output:

```text
Word found
```

### গুরুত্বপূর্ণ: String Case-Sensitive

Python-এ string comparison case-sensitive। অর্থাৎ uppercase এবং lowercase আলাদা হিসেবে বিবেচিত হয়।

```python
text = "Python Programming"

print("Python" in text)
print("python" in text)
```

Output:

```text
True
False
```

Case-insensitive search করতে চাইলে:

```python
text = "Python Programming"

if "python" in text.lower():
    print("Word found")
```

Output:

```text
Word found
```

এখানে `.lower()` মূল string-এর lowercase সংস্করণ তৈরি করে।

## 6. List-এর মধ্যে Membership Check

List-এর মধ্যে কোনো element আছে কি না, তা পরীক্ষা করতে `in` ব্যবহার করা যায়।

উদাহরণ:

```python
marks = [75, 80, 65, 90]

if 90 in marks:
    print("Mark found")
else:
    print("Mark not found")
```

Output:

```text
Mark found
```

এটি user input-এর সঙ্গেও ব্যবহার করা যায়:

```python
allowed_codes = [101, 102, 103]

code = int(input("Enter code: "))

if code in allowed_codes:
    print("Valid code")
else:
    print("Invalid code")
```

Input:

```text
102
```

Output:

```text
Valid code
```

এখানে `int()` ব্যবহার করা হয়েছে, কারণ input-কে integer হিসেবে পরীক্ষা করা হচ্ছে।

## 7. Tuple এবং Set-এর মধ্যে Membership Check

`in` ও `not in` শুধু list-এর জন্য নয়; tuple এবং set-এর ক্ষেত্রেও ব্যবহার করা যায়।

### Tuple Example

```python
days = ("Saturday", "Sunday", "Monday")

print("Sunday" in days)
print("Friday" not in days)
```

Output:

```text
True
True
```

### Set Example

```python
colors = {"Red", "Green", "Blue"}

print("Green" in colors)
print("Yellow" not in colors)
```

Output:

```text
True
True
```

Set-এ membership check সাধারণত দ্রুত হয়। তবে exact performance set-এর গঠন, data এবং পরিস্থিতির ওপর নির্ভর করে।

## 8. Dictionary-এর মধ্যে Membership Check

Dictionary-তে `in` এবং `not in` ব্যবহার করলে সাধারণত **keys** পরীক্ষা করা হয়, values নয়।

উদাহরণ:

```python
student = {
    "name": "Masum",
    "department": "CSE",
    "semester": 9
}

print("name" in student)
print("Masum" in student)
```

Output:

```text
True
False
```

কারণ `"name"` dictionary-র key, কিন্তু `"Masum"` একটি value।

### Dictionary-এর Value পরীক্ষা করা

Dictionary-এর values-এর মধ্যে কোনো value আছে কি না, তা পরীক্ষা করতে `.values()` ব্যবহার করতে পারো।

```python
student = {
    "name": "Masum",
    "department": "CSE",
    "semester": 9
}

print("Masum" in student.values())
print("EEE" in student.values())
```

Output:

```text
True
False
```

### Dictionary-এর Key ও Value দুটোই পরীক্ষা করা

```python
student = {
    "name": "Masum",
    "department": "CSE"
}

if "name" in student and "Masum" in student.values():
    print("Student information found")
```

Output:

```text
Student information found
```

## 9. Multiple Values Check করা

একাধিক সম্ভাব্য value পরীক্ষা করতেও Membership Operators কাজে লাগে।

উদাহরণ:

```python
day = "Friday"

if day in ("Friday", "Saturday"):
    print("Weekend")
else:
    print("Regular day")
```

Output:

```text
Weekend
```

এখানে condition পরীক্ষা করে `day`-এর value tuple-এর যেকোনো একটি element-এর সমান কি না।

একই কাজ `or` দিয়েও লেখা যায়:

```python
if day == "Friday" or day == "Saturday":
    print("Weekend")
```

কিন্তু অনেক value পরীক্ষা করতে হলে `in` ব্যবহার করা বেশি সংক্ষিপ্ত ও readable।

## 10. Membership Operators এবং User Input

ধরা যাক, একটি system-এ নির্দিষ্ট কিছু user role অনুমোদিত।

```python
allowed_roles = ["admin", "teacher", "student"]

role = input("Enter your role: ").strip().lower()

if role in allowed_roles:
    print("Role accepted")
else:
    print("Invalid role")
```

Input:

```text
Teacher
```

Output:

```text
Role accepted
```

এখানে:

- `.strip()` শুরু ও শেষের whitespace সরায়।
- `.lower()` input-কে lowercase করে।
- `in` পরীক্ষা করে role-টি অনুমোদিত তালিকায় আছে কি না।

এটি একটি সাধারণ demonstration। বাস্তব application-এ শুধু user input-এর ওপর নির্ভর করে access control করা নিরাপদ নয়; server-side authentication ও authorization প্রয়োজন।

## 11. Empty Collection-এর সঙ্গে Membership Check

Empty collection-এ কোনো element থাকে না। তাই কোনো সাধারণ value সেখানে পাওয়া যাবে না।

উদাহরণ:

```python
items = []

print(10 in items)
print(10 not in items)
```

Output:

```text
False
True
```

একইভাবে empty string:

```python
text = ""

print("Python" in text)
print("Python" not in text)
```

Output:

```text
False
True
```

তবে খালি string `""` যেকোনো string-এর মধ্যে substring হিসেবে পাওয়া যায়:

```python
text = "Python"

print("" in text)
```

Output:

```text
True
```

কারণ empty string প্রতিটি string-এর মধ্যে substring হিসেবে বিবেচিত হয়।

## 12. Membership Operators এবং Data Type

Membership পরীক্ষা করার সময় collection ও value-এর type গুরুত্বপূর্ণ।

উদাহরণ:

```python
numbers = [10, 20, 30]

print(10 in numbers)
print("10" in numbers)
```

Output:

```text
True
False
```

কারণ integer `10` এবং string `"10"` এক নয়।

যদি user input string হিসেবে পাওয়া যায়, তাহলে প্রয়োজন অনুযায়ী type conversion করতে হবে।

```python
numbers = [10, 20, 30]

value = int(input("Enter a number: "))

if value in numbers:
    print("Found")
else:
    print("Not found")
```

Input:

```text
20
```

Output:

```text
Found
```

মনে রাখবে, invalid input হলে `int()` থেকে `ValueError` হতে পারে।

## 13. Membership Operators বনাম Equality Operators

`in` এবং `==`-এর কাজ আলাদা।

| Operator | কাজ |
|---|---|
| `==` | দুটি value সমান কি না পরীক্ষা করে |
| `in` | কোনো collection-এর মধ্যে value আছে কি না পরীক্ষা করে |
| `!=` | দুটি value সমান নয় কি না পরীক্ষা করে |
| `not in` | কোনো collection-এর মধ্যে value নেই কি না পরীক্ষা করে |

উদাহরণ:

```python
number = 10
numbers = [10, 20, 30]

print(number == 10)
print(number in numbers)
```

Output:

```text
True
True
```

প্রথম condition-এ `number`-এর value `10`-এর সমান কি না পরীক্ষা করা হয়েছে।

দ্বিতীয় condition-এ `number`-এর value `numbers` list-এর মধ্যে আছে কি না পরীক্ষা করা হয়েছে।

## 14. Common Mistakes

### Mistake 1: Dictionary-তে `in` দিয়ে value খোঁজা

```python
student = {"name": "Masum"}

print("Masum" in student)
```

Output:

```text
False
```

কারণ `in student` dictionary-র keys পরীক্ষা করে।

সঠিক:

```python
print("Masum" in student.values())
```

Output:

```text
True
```

### Mistake 2: Case-Sensitivity ভুলে যাওয়া

```python
print("python" in "Python")
```

Output:

```text
False
```

কারণ uppercase `P` এবং lowercase `p` আলাদা।

### Mistake 3: String ও Number-এর পার্থক্য ভুলে যাওয়া

```python
print(5 in ["5", 10])
```

Output:

```text
False
```

কারণ list-এর `"5"` হলো string, integer `5` নয়।

### Mistake 4: `in`-কে সব ধরনের object-এর জন্য ব্যবহার করা

`in` ব্যবহার করার আগে নিশ্চিত হতে হবে ডান পাশের object membership পরীক্ষা সমর্থন করে কি না।

উদাহরণ:

```python
number = 10

# 5 in number
```

এই expression চালালে `TypeError` হবে, কারণ integer-এর মধ্যে membership পরীক্ষা করা যায় না।

সঠিক ব্যবহার:

```python
numbers = [5, 10, 15]
print(10 in numbers)
```

### Mistake 5: `not in`-এর logic উল্টো করা

```python
fruits = ["Apple", "Banana"]

if "Orange" not in fruits:
    print("Orange is unavailable")
```

Output:

```text
Orange is unavailable
```

এখানে `"Orange"` list-এ নেই, তাই `not in` True হয়েছে।

## 15. Practice Exercises

প্রতিটি প্রশ্নের output নিজে predict করো।

### Question 1

```python
numbers = [10, 20, 30]

print(20 in numbers)
print(40 not in numbers)
```

### Question 2

```python
text = "Python Programming"

print("Python" in text)
print("python" in text)
```

### Question 3

```python
student = {"name": "Masum", "department": "CSE"}

print("name" in student)
print("CSE" in student)
print("CSE" in student.values())
```

### Question 4

```python
colors = {"Red", "Green", "Blue"}

if "Yellow" not in colors:
    print("Color not found")
else:
    print("Color found")
```

### Question 5

```python
items = []

print(1 in items)
print(1 not in items)
```

### Question 6

```python
day = "Saturday"

if day in ("Friday", "Saturday"):
    print("Weekend")
else:
    print("Regular day")
```

### Question 7

```python
numbers = [1, 2, 3]

print("2" in numbers)
print(2 in numbers)
```

### Question 8

```python
text = "Hello World"

if "world".lower() in text.lower():
    print("Found")
else:
    print("Not found")
```

## 16. Answer Key

### Answer 1

```text
True
True
```

`20` list-এ আছে এবং `40` নেই।

### Answer 2

```text
True
False
```

String search case-sensitive।

### Answer 3

```text
True
False
True
```

`"name"` একটি key। `"CSE"` value হওয়ায় সেটি সরাসরি dictionary-তে `in` দিয়ে পাওয়া যায় না; `.values()` ব্যবহার করলে পাওয়া যায়।

### Answer 4

```text
Color not found
```

`"Yellow"` set-এ নেই।

### Answer 5

```text
False
True
```

Empty list-এ `1` নেই।

### Answer 6

```text
Weekend
```

`day` tuple-এর একটি value-এর সমান।

### Answer 7

```text
False
True
```

String `"2"` এবং integer `2` আলাদা।

### Answer 8

```text
Found
```

দুই পাশেই lowercase conversion করা হয়েছে, তাই case-insensitive comparison হয়েছে।

## 17. Quick Revision

- `in` কোনো value collection-এর মধ্যে আছে কি না পরীক্ষা করে।
- `not in` কোনো value collection-এর মধ্যে নেই কি না পরীক্ষা করে।
- List, tuple, set, string এবং dictionary-তে Membership Operators ব্যবহার করা যায়।
- Dictionary-তে `in` সাধারণত keys পরীক্ষা করে।
- Dictionary-এর values পরীক্ষা করতে `.values()` ব্যবহার করা যায়।
- String membership check case-sensitive।
- `10` এবং `"10"` আলাদা data type।
- `in` এবং `not in` condition-এর সঙ্গে ব্যবহার করা যায়।

## 18. Self-Assessment Checklist

- [ ] `in` ও `not in`-এর কাজ বুঝি।
- [ ] List, tuple ও set-এর মধ্যে value খুঁজতে পারি।
- [ ] String-এর মধ্যে substring পরীক্ষা করতে পারি।
- [ ] Dictionary-এর key ও value-এর পার্থক্য বুঝি।
- [ ] User input-এর সঙ্গে Membership Operators ব্যবহার করতে পারি।
- [ ] Case-sensitivity এবং data type-এর সমস্যা শনাক্ত করতে পারি।
- [ ] Membership Operators ও Equality Operators-এর পার্থক্য বুঝি।

**পরবর্তী টপিক:** `20_Identity_Operators_in_Conditions.md`
