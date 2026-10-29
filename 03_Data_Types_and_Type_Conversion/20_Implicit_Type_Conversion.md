# 20. Implicit Type Conversion in Python

## 1. What Is Implicit Type Conversion?

**Implicit Type Conversion** হলো এমন একটি process, যেখানে Python নিজে থেকেই প্রয়োজন অনুযায়ী একটি data type-কে অন্য compatible data type-এ convert করে।

এখানে Programmer-কে সরাসরি `int()` বা `float()`-এর মতো conversion function ব্যবহার করতে হয় না।

Example:

```python
a = 10
b = 2.5

result = a + b

print(result)
print(type(result))
```

Output:

```text
12.5
<class 'float'>
```

এখানে:

- `a` হলো `int`।
- `b` হলো `float`।
- Python arithmetic operation-এর সময় `10`-কে `float` হিসেবে বিবেচনা করেছে।
- Result হয়েছে `12.5`, যার type `float`।

এই automatic conversion-ই Implicit Type Conversion-এর একটি উদাহরণ।

## 2. Why Does Python Perform Implicit Conversion?

Implicit Conversion-এর মূল উদ্দেশ্য হলো compatible data type-এর মধ্যে operation সহজ করা।

ধরো, একটি Integer এবং একটি Float যোগ করতে হবে।

```python
a = 5
b = 2.5

print(a + b)
```

Output:

```text
7.5
```

Python এখানে Integer ও Float-এর মধ্যে compatible numeric operation করতে পারে। তাই আলাদাভাবে conversion function ব্যবহার করার প্রয়োজন হয় না।

Implicit Conversion-এর সুবিধা:

- Compatible data type-এর মধ্যে operation সহজ হয়।
- Code ছোট ও readable থাকে।
- Numeric calculation সহজে করা যায়।

তবে Python সব data type-এর মধ্যে automatic conversion করে না।

## 3. Implicit Conversion Between Integer and Float

Python-এ Integer এবং Float-এর arithmetic operation-এর সময় সাধারণত Integer-কে Float-এ promote করা হয়।

### Example 1: Addition

```python
a = 10
b = 3.5

result = a + b

print(result)
print(type(result))
```

Output:

```text
13.5
<class 'float'>
```

### Example 2: Subtraction

```python
a = 10
b = 3.5

result = a - b

print(result)
print(type(result))
```

Output:

```text
6.5
<class 'float'>
```

### Example 3: Multiplication

```python
a = 4
b = 2.5

result = a * b

print(result)
print(type(result))
```

Output:

```text
10.0
<class 'float'>
```

লক্ষ্য করো, result `10` নয়, `10.0`। কারণ operation-এ Float ছিল।

### Example 4: Division

```python
a = 10
b = 2

result = a / b

print(result)
print(type(result))
```

Output:

```text
5.0
<class 'float'>
```

Python-এ `/` operator দিয়ে সাধারণ division করলে দুই operand Integer হলেও result Float হয়।

এটি Integer ও Float-এর automatic promotion-এর সঙ্গে সম্পর্কিত, তবে মনে রাখবে—`/` operator-এর নিজস্ব নিয়মও এখানে কাজ করে।

## 4. Implicit Conversion with Complex Numbers

Python-এর numeric type promotion-এ `complex` গুরুত্বপূর্ণ।

সাধারণ arithmetic operation-এ Integer ও Float-এর সঙ্গে Complex number ব্যবহার করলে result সাধারণত Complex type হয়।

### Example 1: Integer and Complex

```python
a = 5
b = 2 + 3j

result = a + b

print(result)
print(type(result))
```

Output:

```text
(7+3j)
<class 'complex'>
```

### Example 2: Float and Complex

```python
a = 2.5
b = 1 + 4j

result = a + b

print(result)
print(type(result))
```

Output:

```text
(3.5+4j)
<class 'complex'>
```

এখানে Python compatible numeric operation-এর মাধ্যমে Complex result তৈরি করেছে।

## 5. Numeric Type Promotion Order

Python-এর সাধারণ numeric arithmetic-এ type promotion-এর একটি সহজ pattern মনে রাখা যায়:

`int → float → complex`

অর্থাৎ, এই ধরনের arithmetic operation-এ:

- `int` ও `float` একসঙ্গে থাকলে result সাধারণত `float` হয়।
- `int` ও `complex` একসঙ্গে থাকলে result `complex` হয়।
- `float` ও `complex` একসঙ্গে থাকলে result `complex` হয়।

Example:

```python
print(type(5 + 2.5))
print(type(5 + 2j))
print(type(2.5 + 2j))
```

Output:

```text
<class 'float'>
<class 'complex'>
<class 'complex'>
```

**Important:** এটি সাধারণ numeric arithmetic-এর সহজ নিয়ম। Python-এর সব operator ও সব data type-এর জন্য একই conversion rule প্রযোজ্য নয়।

## 6. Implicit Conversion Does Not Mean Every Type Is Compatible

Python compatible numeric type-এর মধ্যে conversion করতে পারে। কিন্তু String ও Integer-এর মতো incompatible type-এর মধ্যে সব operation স্বয়ংক্রিয়ভাবে convert করে না।

Example:

```python
a = "10"
b = 5

print(a + b)
```

Output:

```text
TypeError
```

কারণ `"10"` হলো String এবং `5` হলো Integer। Python এখানে String-কে স্বয়ংক্রিয়ভাবে Integer-এ convert করে না।

সঠিক পদ্ধতি:

```python
a = "10"
b = 5

result = int(a) + b

print(result)
```

Output:

```text
15
```

এখানে Programmer নিজে `int()` ব্যবহার করেছে। তাই এটি Explicit Type Conversion।

আরেকটি উদাহরণ:

```python
a = "Hello"
b = " Python"

print(a + b)
```

Output:

```text
Hello Python
```

এখানে error হয়নি, কারণ দুটি operand-ই String এবং `+` String concatenation করেছে। কোনো numeric conversion হয়নি।

## 7. Implicit Conversion and Boolean Values

Python-এ `bool` হলো `int`-এর subclass। তাই Boolean value-গুলো অনেক numeric operation-এ Integer-এর মতো আচরণ করতে পারে।

Python-এ:

- `True`-এর numeric value `1`।
- `False`-এর numeric value `0`।

Example:

```python
print(True + 5)
print(False + 5)
print(True * 3)
```

Output:

```text
6
5
3
```

এখানে Boolean value numeric operation-এ অংশ নিয়েছে।

তবে সাধারণত arithmetic calculation-এ `True` ও `False` ব্যবহার না করে প্রয়োজন অনুযায়ী Integer ব্যবহার করলে code আরও পরিষ্কার হয়।

## 8. Implicit Conversion and Assignment

Implicit Type Conversion মানে এই নয় যে একটি variable-এর original value বা type সব সময় পরিবর্তিত হয়ে যায়।

Example:

```python
a = 10
b = 2.5

result = a + b

print(type(a))
print(type(b))
print(type(result))
```

Output:

```text
<class 'int'>
<class 'float'>
<class 'float'>
```

এখানে:

- `a` এখনও `int`।
- `b` এখনও `float`।
- `result` হলো `float`।

Python operation করার জন্য numeric value-গুলোকে compatibleভাবে ব্যবহার করেছে। কিন্তু `a` variable-কে স্থায়ীভাবে Float বানিয়ে দেয়নি।

এটি গুরুত্বপূর্ণ, কারণ operation-এর result-এর type এবং original variable-এর type আলাদা হতে পারে।

## 9. Implicit Conversion vs Explicit Conversion

| Feature | Implicit Conversion | Explicit Conversion |
|---|---|---|
| কে conversion করে? | Python নিজে | Programmer |
| Conversion function | সরাসরি প্রয়োজন হয় না | `int()`, `float()` ইত্যাদি ব্যবহার করা হয় |
| Example | `5 + 2.5` | `int("5")` |
| Main purpose | Compatible operation সহজ করা | প্রয়োজন অনুযায়ী type পরিবর্তন করা |
| Invalid conversion | Incompatible operation-এ error হতে পারে | Invalid input-এ error হতে পারে |

Example:

```python
# Implicit Conversion
a = 5
b = 2.5

print(a + b)
```

Output:

```text
7.5
```

```python
# Explicit Conversion
a = "5"

print(int(a) + 2)
```

Output:

```text
7
```

প্রথম উদাহরণে Python numeric operation-এর সময় compatible type promotion করেছে। দ্বিতীয় উদাহরণে Programmer `int()` ব্যবহার করে String-কে Integer-এ convert করেছে।

## 10. Common Beginner Mistakes

### Mistake 1: Expecting String to Convert Automatically

```python
number = "20"

print(number + 5)
```

এখানে `TypeError` হবে। Python String-কে Integer-এ automatic conversion করে না।

Correct:

```python
number = "20"

print(int(number) + 5)
```

Output:

```text
25
```

### Mistake 2: Assuming Integer Division Always Returns an Integer

```python
print(8 / 2)
```

Output:

```text
4.0
```

Python-এর `/` operator সাধারণ division করে এবং result Float দেয়।

Integer result প্রয়োজন হলে এবং floor division-এর নিয়ম উপযুক্ত হলে `//` ব্যবহার করা যায়:

```python
print(8 // 2)
```

Output:

```text
4
```

### Mistake 3: Assuming the Original Variable Changes Type

```python
a = 10
b = 2.5

result = a + b

print(type(a))
```

Output:

```text
<class 'int'>
```

Operation-এর result Float হলেও `a` Integer-ই থাকে।

### Mistake 4: Assuming All Numeric Operations Have the Same Result Type

```python
print(type(5 + 2.5))
print(type(5 / 2))
print(type(5 // 2))
```

Output:

```text
<class 'float'>
<class 'float'>
<class 'int'>
```

এখানে operator-এর নিজস্ব নিয়মও result type নির্ধারণ করে। তাই শুধু operand-এর type দেখলেই হবে না; operator কীভাবে কাজ করে, সেটিও বুঝতে হবে।

## 11. Practice Exercises

### Exercise 1: Addition

```python
a = 15
b = 4.5
```

দুটি value যোগ করো এবং result-এর type পরীক্ষা করো।

### Exercise 2: Subtraction

```python
a = 20
b = 3.5
```

Subtraction করো এবং result-এর data type নির্ণয় করো।

### Exercise 3: Complex Number

```python
a = 5
b = 2 + 3j
```

দুটি value যোগ করো। Result-এর type কী হবে?

### Exercise 4: Identify the Error

```python
a = "25"
b = 5

print(a + b)
```

কেন error হচ্ছে? সঠিক code লেখো।

### Exercise 5: Boolean Arithmetic

```python
print(True + 4)
print(False * 10)
```

Output অনুমান করো এবং ব্যাখ্যা করো।

### Exercise 6: Check Variable Types

```python
a = 10
b = 2.5
c = a + b
```

`a`, `b` এবং `c`-এর type print করো। ব্যাখ্যা করো কেন `a`-এর type পরিবর্তিত হয়নি।

### Exercise 7: Operator Behavior

নিচের expression-গুলোর result এবং data type বের করো:

```python
print(9 / 3)
print(9 // 3)
print(9 + 3.0)
print(9 + 3j)
```

### Exercise 8: Implicit or Explicit?

নিচের কোনটি Implicit এবং কোনটি Explicit Type Conversion?

```python
a = 10 + 2.5
b = int("20")
c = 5 + 2j
d = float("3.5")
```

## 12. Key Takeaways

- Implicit Type Conversion-এ Python নিজে compatible data type-এর মধ্যে conversion করে।
- Integer ও Float-এর সাধারণ arithmetic operation-এ result সাধারণত Float হয়।
- Integer বা Float-এর সঙ্গে Complex number-এর arithmetic result সাধারণত Complex হয়।
- Numeric type promotion-এর সহজ pattern হলো `int → float → complex`।
- String ও Integer-এর মতো incompatible type সব operation-এ স্বয়ংক্রিয়ভাবে convert হয় না।
- `bool` হলো `int`-এর subclass; `True` ও `False` numeric operation-এ অংশ নিতে পারে।
- Operation-এর result-এর type এবং original variable-এর type আলাদা হতে পারে।
- Operator-এর নিজস্ব নিয়মও result-এর data type নির্ধারণ করে।

## 13. Next Topic

পরবর্তী ফাইল:

**`21_Explicit_Type_Conversion.md`**

সেখানে Programmer কীভাবে `int()`, `float()`, `str()` এবং অন্যান্য conversion function ব্যবহার করে নিজে data type পরিবর্তন করে, তা বিস্তারিত শেখা হবে।