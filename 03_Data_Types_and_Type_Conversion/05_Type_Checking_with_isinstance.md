# 05. Type Checking with `isinstance()`

## 1. What Is `isinstance()`?

Python-এ `isinstance()` হলো একটি built-in function, যা কোনো object নির্দিষ্ট class বা data type-এর instance কি না যাচাই করে।

সহজভাবে, কোনো value `int`, `str`, `list` বা অন্য কোনো type-এর কি না জানতে `isinstance()` ব্যবহার করা যায়।

**Syntax:**

```python
isinstance(object, classinfo)
```

এখানে:

- `object`: যে value বা object পরীক্ষা করতে চাও।
- `classinfo`: যে type বা class-এর সঙ্গে তুলনা করতে চাও।

Object নির্দিষ্ট type-এর হলে `True` return করে, অন্যথায় `False` return করে।

**Example:**

```python
age = 22

print(isinstance(age, int))
print(isinstance(age, str))
```

Output:

```text
True
False
```

এখানে `age` একটি integer, তাই প্রথম result `True`। এটি string নয়, তাই দ্বিতীয় result `False`।

## 2. Checking Different Data Types

`isinstance()` দিয়ে বিভিন্ন built-in data type check করা যায়।

### 2.1 Integer

```python
number = 100

print(isinstance(number, int))
```

Output:

```text
True
```

### 2.2 Float

```python
price = 99.5

print(isinstance(price, float))
```

Output:

```text
True
```

### 2.3 String

```python
name = "Masum"

print(isinstance(name, str))
```

Output:

```text
True
```

### 2.4 Boolean

```python
is_student = True

print(isinstance(is_student, bool))
```

Output:

```text
True
```

### 2.5 List, Tuple, Set and Dictionary

```python
numbers = [10, 20, 30]
coordinates = (10, 20)
unique_numbers = {1, 2, 3}
student = {"name": "Masum"}

print(isinstance(numbers, list))
print(isinstance(coordinates, tuple))
print(isinstance(unique_numbers, set))
print(isinstance(student, dict))
```

Output:

```text
True
True
True
True
```

### 2.6 NoneType

Python-এ `None` হলো এমন একটি special value, যা সাধারণত কোনো value অনুপস্থিত বা এখনো নির্ধারিত হয়নি বোঝাতে ব্যবহার করা হয়।

এর type হলো `NoneType`।

```python
result = None

print(isinstance(result, type(None)))
```

Output:

```text
True
```

এখানে `type(None)` দিয়ে `None`-এর type পাওয়া হয়েছে।

## 3. Checking Multiple Types at Once

`isinstance()`-এর দ্বিতীয় argument হিসেবে একাধিক type-এর একটি tuple দেওয়া যায়।

**Syntax:**

```python
isinstance(object, (type1, type2, type3))
```

Object tuple-এর যেকোনো একটি type-এর সঙ্গে মিলে গেলে `True` return করবে।

**Example:**

```python
value = 10.5

print(isinstance(value, (int, float)))
```

Output:

```text
True
```

কারণ `value` একটি `float`।

আরেকটি example:

```python
value = "Python"

print(isinstance(value, (int, float)))
```

Output:

```text
False
```

কারণ `"Python"` integer বা float নয়।

### Practical Example: Numeric Input Validation

```python
value = 25

if isinstance(value, (int, float)):
    print("The value is numeric.")
else:
    print("The value is not numeric.")
```

Output:

```text
The value is numeric.
```

এখানে একটি condition দিয়েই integer এবং float—দুই ধরনের value check করা হয়েছে।

**মনে রাখবে:** `bool` হলো `int`-এর subclass। তাই নিচের code-এ `True` result পাওয়া যাবে।

```python
print(isinstance(True, (int, float)))
```

Output:

```text
True
```

যদি Boolean-কে numeric input হিসেবে গ্রহণ করতে না চাও, তাহলে সেটিকে আলাদাভাবে বাদ দিতে হবে।

```python
value = True

if isinstance(value, (int, float)) and not isinstance(value, bool):
    print("Valid numeric value.")
else:
    print("Boolean or non-numeric value.")
```

Output:

```text
Boolean or non-numeric value.
```

## 4. Understanding `isinstance()` with Inheritance

`isinstance()`-এর সবচেয়ে গুরুত্বপূর্ণ সুবিধাগুলোর একটি হলো এটি **inheritance** বিবেচনা করে।

Inheritance হলো এমন একটি OOP feature, যার মাধ্যমে একটি class অন্য class-এর বৈশিষ্ট্য ও behaviour গ্রহণ করতে পারে।

Example:

```python
class Animal:
    pass


class Dog(Animal):
    pass


my_dog = Dog()

print(isinstance(my_dog, Dog))
print(isinstance(my_dog, Animal))
```

Output:

```text
True
True
```

ব্যাখ্যা:

- `my_dog` হলো `Dog` class-এর object।
- `Dog` class, `Animal` class থেকে inherit করেছে।
- তাই `my_dog` হলো `Dog` এবং `Animal`—দুই class-এর instance।

এখন একই code-এ `type()` ব্যবহার করলে:

```python
print(type(my_dog) == Dog)
print(type(my_dog) == Animal)
```

Output:

```text
True
False
```

কারণ `type()` object-এর exact type পরীক্ষা করে। `my_dog`-এর exact type হলো `Dog`, `Animal` নয়।

### Comparison Table

| `type()` | `isinstance()` |
|---|---|
| Exact type পরীক্ষা করে | Type এবং inheritance relationship বিবেচনা করে |
| `type(obj) == Parent` subclass object-এর জন্য `False` হতে পারে | `isinstance(obj, Parent)` subclass object-এর জন্য `True` হতে পারে |
| Exact type জানা প্রয়োজন হলে উপযোগী | সাধারণ type validation-এ বেশি flexible |

## 5. Checking Custom Classes

`isinstance()` শুধু built-in data types-এর জন্য নয়, নিজের তৈরি class-এর ক্ষেত্রেও ব্যবহার করা যায়।

Example:

```python
class Student:
    pass


class Teacher:
    pass


student = Student()
teacher = Teacher()

print(isinstance(student, Student))
print(isinstance(student, Teacher))
print(isinstance(teacher, Teacher))
```

Output:

```text
True
False
True
```

এখানে প্রতিটি object তার নিজস্ব class-এর instance কি না পরীক্ষা করা হয়েছে।

### Practical Example

```python
class Student:
    def __init__(self, name):
        self.name = name


def display_student(student):
    if isinstance(student, Student):
        print("Student name:", student.name)
    else:
        print("Invalid student object.")


s1 = Student("Masum")

display_student(s1)
display_student("Masum")
```

Output:

```text
Student name: Masum
Invalid student object.
```

এখানে function-এ পাঠানো argument একটি `Student` object কি না যাচাই করা হয়েছে।

এই ধরনের validation ভুল object ব্যবহারজনিত সমস্যা কমাতে সাহায্য করে।

## 6. Type Checking in Conditional Statements

`isinstance()`-এর result `True` অথবা `False` হওয়ায় এটি `if-else` statement-এ সহজেই ব্যবহার করা যায়।

Example:

```python
value = "Hello Python"

if isinstance(value, str):
    print("This is a string.")
else:
    print("This is not a string.")
```

Output:

```text
This is a string.
```

### Practical Example: Safe Processing

```python
age = 21

if isinstance(age, int) and not isinstance(age, bool):
    if age >= 18:
        print("Eligible.")
    else:
        print("Not eligible.")
else:
    print("Please provide an integer age.")
```

Output:

```text
Eligible.
```

এখানে প্রথমে type check করা হয়েছে। তারপর age-এর মান পরীক্ষা করা হয়েছে।

এভাবে validation করলে type ভুল হওয়ার কারণে comparison-সংক্রান্ত error এড়ানো যায়। তবে বাস্তব program-এ user input গ্রহণ করলে conversion এবং invalid input-এর error-ও handle করতে হবে।

## 7. `isinstance()` Does Not Convert Values

`isinstance()` শুধু type পরীক্ষা করে। এটি কোনো value-কে অন্য type-এ convert করে না।

Example:

```python
number = "100"

print(isinstance(number, int))
print(isinstance(number, str))
```

Output:

```text
False
True
```

এখানে `"100"` দেখতে সংখ্যার মতো হলেও এটি string।

Integer-এ convert করতে হলে `int()` ব্যবহার করতে হবে।

```python
number = int(number)

print(number)
print(isinstance(number, int))
```

Output:

```text
100
True
```

সুতরাং:

- `isinstance()` — type check করে।
- `int()` — integer-এ convert করার চেষ্টা করে।
- `float()` — float-এ convert করার চেষ্টা করে।
- `str()` — string representation তৈরি করে।

## 8. Common Beginner Mistakes

### Mistake 1: `isinstance()`-এর Argument-এর ক্রম ভুল করা

ভুল:

```python
value = 10

print(isinstance(int, value))
```

এখানে argument-এর order উল্টো। দ্বিতীয় argument-এ type বা class information দিতে হয়।

সঠিক:

```python
print(isinstance(value, int))
```

Output:

```text
True
```

### Mistake 2: Type-এর নাম String হিসেবে দেওয়া

ভুল:

```python
value = 10

print(isinstance(value, "int"))
```

এখানে `"int"` একটি string, class বা type নয়। ফলে `TypeError` হবে।

সঠিক:

```python
print(isinstance(value, int))
```

### Mistake 3: Boolean-কে Integer থেকে আলাদা মনে না রাখা

```python
print(isinstance(True, int))
```

Output:

```text
True
```

কারণ `bool` হলো `int`-এর subclass।

শুধু integer গ্রহণ করতে এবং Boolean বাদ দিতে:

```python
value = True

if isinstance(value, int) and not isinstance(value, bool):
    print("Integer accepted.")
else:
    print("Integer required.")
```

Output:

```text
Integer required.
```

### Mistake 4: Type Checking-কে Conversion মনে করা

```python
value = "25"

print(isinstance(value, int))
```

Output:

```text
False
```

Type check করার কারণে value integer হয়ে যায় না। Conversion আলাদাভাবে করতে হবে।

### Mistake 5: সবসময় Type Checking প্রয়োজন মনে করা

Python-এ সব function বা operation-এর আগে `isinstance()` ব্যবহার করা বাধ্যতামূলক নয়।

প্রয়োজন অনুযায়ী validation ব্যবহার করতে হয়। কখনো সরাসরি operation করে error handle করা বেশি উপযোগী হতে পারে। এটি program-এর উদ্দেশ্য ও design-এর ওপর নির্ভর করে।

## 9. Practice Exercises

### Exercise 1: Basic Type Checking

নিচের code-এর output অনুমান করো:

```python
a = 10
b = 5.5
c = "Python"
d = True
e = [1, 2, 3]

print(isinstance(a, int))
print(isinstance(b, float))
print(isinstance(c, str))
print(isinstance(d, bool))
print(isinstance(e, list))
```

### Exercise 2: Multiple Types

এমন একটি program লেখো, যা `value` integer অথবা float হলে `"Numeric"` এবং অন্যথায় `"Not numeric"` print করবে।

```python
value = 12.5
```

এরপর value পরিবর্তন করে `"Python"`, `20` এবং `True` দিয়ে test করো। Boolean-কে numeric হিসেবে গ্রহণ না করার condition-টিও যোগ করো।

### Exercise 3: Inheritance

নিচের code-এর output নির্ণয় করো:

```python
class Person:
    pass


class Student(Person):
    pass


student = Student()

print(isinstance(student, Student))
print(isinstance(student, Person))
print(type(student) == Person)
```

প্রতিটি result-এর কারণ ব্যাখ্যা করো।

### Exercise 4: Validate a Function Argument

একটি function লেখো, যার নাম `show_name()`। Function-টি argument হিসেবে string পেলে সেটি print করবে। অন্য type পেলে `"String required"` print করবে।

### Exercise 5: Check a Collection

নিচের values-এর type `isinstance()` দিয়ে পরীক্ষা করো:

```python
values = [10, 3.5, "Hello", True, None, (1, 2)]
```

প্রতিটি value integer, float, string, Boolean, `NoneType` অথবা tuple কি না নির্ধারণ করো।

### Exercise 6: Fix the Code

নিচের code-এ ভুলটি খুঁজে সংশোধন করো:

```python
age = 20

if isinstance(int, age):
    print("Valid age")
```

## 10. Key Takeaways

- `isinstance()` একটি built-in Python function।
- এটি object নির্দিষ্ট type বা class-এর instance কি না যাচাই করে।
- Result হিসেবে `True` অথবা `False` return করে।
- একাধিক type পরীক্ষা করতে tuple ব্যবহার করা যায়।
- এটি inheritance এবং subclass relationship বিবেচনা করে।
- `bool` হলো `int`-এর subclass; তাই `isinstance(True, int)` হলো `True`।
- `isinstance()` value convert করে না।
- সাধারণ type validation-এর জন্য এটি অনেক ক্ষেত্রে `type()`-এর চেয়ে বেশি flexible।

## 11. Next Topic

পরবর্তী ফাইল:

**`06_Integer_Type.md`**

সেখানে integer data type, positive ও negative integer, integer operations, বড় integer, ব্যবহার এবং সাধারণ ভুলগুলো বিস্তারিতভাবে শেখা হবে।