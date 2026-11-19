# String Concatenation

## 1. What is String Concatenation?

Python-এ একাধিক String একসঙ্গে যুক্ত করে একটি নতুন String তৈরি করাকে **String Concatenation** বলা হয়।

String Concatenation করার জন্য Python-এ `+` operator ব্যবহার করা হয়।

সহজভাবে, দুই বা তার বেশি String একসঙ্গে যোগ করাই হলো String Concatenation।

**Example:**

```python
first_name = "Abdulla"
last_name = "Masum"

full_name = first_name + last_name

print(full_name)
```

**Output:**

```text
AbdullaMasum
```

**ব্যাখ্যা:**

এখানে `first_name` এবং `last_name` দুটি String।

`+` operator ব্যবহার করে দুটি String যুক্ত করা হয়েছে।

তবে এখানে কোনো space দেওয়া হয়নি। তাই দুটি নাম একসঙ্গে যুক্ত হয়েছে।

## 2. String Concatenation Using + Operator

Python-এ `+` operator ব্যবহার করে দুই বা তার বেশি String যুক্ত করা যায়।

**Syntax:**

```python
string1 + string2
```

**Example:**

```python
text1 = "Hello"
text2 = "World"

result = text1 + text2

print(result)
```

**Output:**

```text
HelloWorld
```

এখানে `+` operator দুটি String যুক্ত করে নতুন String তৈরি করেছে।

## 3. Adding Space Between Strings

দুটি String যুক্ত করার সময় প্রয়োজন অনুযায়ী মাঝখানে space যোগ করা যায়।

**Example:**

```python
first_name = "Abdulla"
last_name = "Masum"

full_name = first_name + " " + last_name

print(full_name)
```

**Output:**

```text
Abdulla Masum
```

**ব্যাখ্যা:**

এখানে `" "` একটি space-সম্বলিত String।

তাই তিনটি অংশ যুক্ত হয়েছে:

- `"Abdulla"`
- `" "`
- `"Masum"`

ফলে সম্পূর্ণ নামের মাঝে একটি space এসেছে।

## 4. Concatenating Multiple Strings

একাধিক String একসঙ্গে যুক্ত করতেও `+` operator ব্যবহার করা যায়।

**Example:**

```python
text1 = "I"
text2 = "am"
text3 = "learning"
text4 = "Python"

result = text1 + " " + text2 + " " + text3 + " " + text4

print(result)
```

**Output:**

```text
I am learning Python
```

এখানে চারটি String এবং তিনটি space যুক্ত করে একটি সম্পূর্ণ sentence তৈরি করা হয়েছে।

## 5. Concatenating Strings with Variables

Variable-এর মধ্যে থাকা String-গুলোও `+` operator দিয়ে যুক্ত করা যায়।

**Example:**

```python
name = "Masum"
country = "Bangladesh"

message = "My name is " + name + " and I live in " + country

print(message)
```

**Output:**

```text
My name is Masum and I live in Bangladesh
```

**ব্যাখ্যা:**

এখানে:

- `"My name is "` একটি String।
- `name` একটি String variable।
- `" and I live in "` আরেকটি String।
- `country` আরেকটি String variable।

সবগুলো `+` operator দিয়ে যুক্ত করে একটি নতুন sentence তৈরি করা হয়েছে।

## 6. String Concatenation with User Input

`input()` থেকে পাওয়া String-গুলোও Concatenation করা যায়।

**Example:**

```python
first_name = input("Enter your first name: ")
last_name = input("Enter your last name: ")

full_name = first_name + " " + last_name

print("Full Name:", full_name)
```

**Sample Input:**

```text
Enter your first name: Abdulla
Enter your last name: Masum
```

**Output:**

```text
Full Name: Abdulla Masum
```

**ব্যাখ্যা:**

- `input()` ব্যবহার করে দুটি নাম নেওয়া হয়েছে।
- দুটি নাম String হিসেবে সংরক্ষিত হয়েছে।
- `+` operator দিয়ে নাম দুটি যুক্ত করা হয়েছে।
- শেষে সম্পূর্ণ নাম print করা হয়েছে।

## 7. Concatenating Strings with Different Data Types

String Concatenation করার সময় একটি গুরুত্বপূর্ণ বিষয় মনে রাখতে হবে।

Python-এ `+` operator দিয়ে সরাসরি String এবং Integer বা Float যুক্ত করা যায় না।

**Incorrect Example:**

```python
name = "Masum"
age = 22

result = name + age

print(result)
```

**Output:**

```text
TypeError: can only concatenate str (not "int") to str
```

**ব্যাখ্যা:**

এখানে:

- `name` হলো String।
- `age` হলো Integer।

`+` operator দিয়ে সরাসরি String এবং Integer যুক্ত করার চেষ্টা করায় `TypeError` হয়েছে।

### Solution: Using str() Function

`str()` function ব্যবহার করে Integer বা Float-কে String-এ convert করে Concatenation করা যায়।

**Example:**

```python
name = "Masum"
age = 22

result = name + " " + str(age)

print(result)
```

**Output:**

```text
Masum 22
```

**ব্যাখ্যা:**

- `str(age)` Integer `22`-কে String `"22"`-এ convert করেছে।
- এরপর দুটি String `+` operator দিয়ে যুক্ত হয়েছে।

## 8. String Concatenation Using += Operator

Python-এ `+=` assignment operator ব্যবহার করেও String Concatenation করা যায়।

এটি মূলত একটি String-এর সঙ্গে অন্য String যুক্ত করে Variable-এ নতুন ফলাফল assign করে।

**Example:**

```python
text = "Hello"

text += " World"

print(text)
```

**Output:**

```text
Hello World
```

**ব্যাখ্যা:**

নিচের দুটি statement একই ধরনের কাজ করে:

```python
text = text + " World"
```

```python
text += " World"
```

দুটিই আগের String-এর সঙ্গে নতুন String যুক্ত করে `text` variable-এ assign করে।

মনে রাখবে, String immutable। তাই `+=` ব্যবহার করলেও পুরোনো String object পরিবর্তন হয় না; নতুন String তৈরি হয়ে variable-এ assign হয়।

## 9. String Concatenation Using join()

Python-এ একাধিক String যুক্ত করার আরেকটি গুরুত্বপূর্ণ পদ্ধতি হলো `join()` method।

বিশেষ করে List বা অন্য কোনো iterable-এর মধ্যে থাকা String-গুলো একসঙ্গে যুক্ত করতে এটি ব্যবহার করা হয়।

**Syntax:**

```python
separator.join(iterable)
```

এখানে:

- `separator` → String-গুলোর মাঝে কী থাকবে।
- `iterable` → যে collection-এর String-গুলো যুক্ত করা হবে।

**Example 1: Using Empty Separator**

```python
words = ["Python", "is", "Easy"]

result = "".join(words)

print(result)
```

**Output:**

```text
PythonisEasy
```

এখানে empty string `""` separator হিসেবে ব্যবহার করা হয়েছে। তাই কোনো space ছাড়াই সব String যুক্ত হয়েছে।

**Example 2: Using Space Separator**

```python
words = ["Python", "is", "Easy"]

result = " ".join(words)

print(result)
```

**Output:**

```text
Python is Easy
```

এখানে `" "` separator হিসেবে ব্যবহার করা হয়েছে। তাই প্রতিটি String-এর মাঝে একটি space এসেছে।

**Example 3: Using Hyphen Separator**

```python
words = ["2026", "11", "05"]

result = "-".join(words)

print(result)
```

**Output:**

```text
2026-11-05
```

## 10. Difference Between + Operator and join()

দুটিই String যুক্ত করতে ব্যবহার করা হয়। তবে এদের ব্যবহারের ক্ষেত্রে কিছু পার্থক্য রয়েছে।

| `+` Operator | `join()` Method |
|---|---|
| সাধারণত দুই বা কয়েকটি String যুক্ত করতে ব্যবহার হয়। | Iterable-এর অনেকগুলো String যুক্ত করতে সুবিধাজনক। |
| নিজের মতো separator যোগ করতে হয়। | Separator নির্ধারণ করে দেওয়া যায়। |
| `str1 + str2` | `" ".join(words)` |
| String-এর সঙ্গে String যুক্ত করে। | Iterable-এর String-গুলো যুক্ত করে। |

**Example:**

```python
# Using + operator

first = "Hello"
second = "World"

print(first + " " + second)


# Using join()

words = ["Hello", "World"]

print(" ".join(words))
```

**Output:**

```text
Hello World
Hello World
```

## 11. Common Mistakes in String Concatenation

### Mistake 1: Concatenating String with Integer

**Incorrect Code:**

```python
name = "Masum"
age = 22

print(name + age)
```

**Error:**

```text
TypeError: can only concatenate str (not "int") to str
```

**Solution:**

```python
print(name + " " + str(age))
```

**Output:**

```text
Masum 22
```

### Mistake 2: Forgetting Spaces

**Incorrect Code:**

```python
first = "Hello"
second = "World"

print(first + second)
```

**Output:**

```text
HelloWorld
```

**Solution:**

```python
print(first + " " + second)
```

**Output:**

```text
Hello World
```

### Mistake 3: Using join() with Non-String Elements

`join()` ব্যবহার করার সময় iterable-এর প্রতিটি element String হতে হবে।

**Incorrect Code:**

```python
numbers = ["10", 20, "30"]

result = "-".join(numbers)

print(result)
```

**Error:**

```text
TypeError: sequence item 1: expected str instance, int found
```

**Solution:**

```python
numbers = ["10", 20, "30"]

result = "-".join(str(num) for num in numbers)

print(result)
```

**Output:**

```text
10-20-30
```

এখানে `str()` ব্যবহার করে প্রতিটি element-কে String-এ convert করা হয়েছে।

## 12. Practical Examples

### Example 1: Creating a Full Name

```python
first_name = "Abdulla"
middle_name = "Al"
last_name = "Masum"

full_name = first_name + " " + middle_name + " " + last_name

print("Full Name:", full_name)
```

**Output:**

```text
Full Name: Abdulla Al Masum
```

### Example 2: Creating a Welcome Message

```python
name = "Masum"
course = "Python Programming"

message = "Welcome " + name + "! You are learning " + course + "."

print(message)
```

**Output:**

```text
Welcome Masum! You are learning Python Programming.
```

### Example 3: Creating an Email Address

```python
username = "masum8823"
domain = "gmail.com"

email = username + "@" + domain

print(email)
```

**Output:**

```text
masum8823@gmail.com
```

## 13. Important Rules to Remember

1. String Concatenation অর্থ একাধিক String যুক্ত করা।
2. `+` operator ব্যবহার করে String যুক্ত করা যায়।
3. String-এর মাঝে space দিতে চাইলে `" "` ব্যবহার করতে হয়।
4. `+=` operator দিয়েও String Concatenation করা যায়।
5. String-এর সঙ্গে Integer বা Float সরাসরি Concatenate করা যায় না।
6. `str()` ব্যবহার করে অন্য Data Type-কে String-এ convert করা যায়।
7. `join()` ব্যবহার করে Iterable-এর অনেকগুলো String যুক্ত করা যায়।
8. `join()`-এর প্রতিটি element অবশ্যই String হতে হবে।
9. String immutable হওয়ায় Concatenation নতুন String তৈরি করে।

## 14. Practice Problems

### Problem 1: Join Two Strings

দুটি String যুক্ত করে একটি নতুন String তৈরি করো।

```python
first = "Python"
second = "Programming"
```

Expected Output:

```text
PythonProgramming
```

### Problem 2: Create Full Name

তিনটি variable ব্যবহার করে সম্পূর্ণ নাম তৈরি করো।

```python
first_name = "Abdulla"
middle_name = "Al"
last_name = "Masum"
```

Expected Output:

```text
Abdulla Al Masum
```

### Problem 3: Concatenate Different Data Types

String এবং Integer একসঙ্গে যুক্ত করো।

```python
name = "Masum"
age = 22
```

Expected Output:

```text
My name is Masum and I am 22 years old.
```

### Problem 4: Use += Operator

নিচের String-এর সঙ্গে `" Programming"` যুক্ত করো।

```python
text = "Python"
```

Expected Output:

```text
Python Programming
```

### Problem 5: Use join()

List-এর String-গুলো space দিয়ে যুক্ত করো।

```python
words = ["I", "Love", "Python"]
```

Expected Output:

```text
I Love Python
```

### Problem 6: Create an Email Address

দুটি String ব্যবহার করে একটি Email Address তৈরি করো।

```python
username = "masum8823"
domain = "gmail.com"
```

Expected Output:

```text
masum8823@gmail.com
```

### Problem 7: Predict the Output

```python
text = "Hello"

text += " Python"
text += " Programming"

print(text)
```

Expected Output:

```text
Hello Python Programming
```

## 15. Summary

- String Concatenation হলো একাধিক String যুক্ত করে নতুন String তৈরি করা।
- `+` operator দিয়ে String যুক্ত করা যায়।
- `" "` ব্যবহার করে String-এর মাঝে space দেওয়া যায়।
- `+=` operator দিয়েও String যুক্ত করা যায়।
- `str()` ব্যবহার করে Integer বা Float-কে String-এ convert করা যায়।
- `join()` ব্যবহার করে Iterable-এর অনেকগুলো String যুক্ত করা যায়।
- `+` এবং `join()`-এর ব্যবহার এক হলেও কাজ করার পদ্ধতি কিছুটা আলাদা।
- String Concatenation মূল String পরিবর্তন করে না; নতুন String তৈরি করে।

String Concatenation Python-এর একটি গুরুত্বপূর্ণ operation, যা Full Name, Message, Email Address এবং বিভিন্ন Text তৈরি করতে ব্যবহার করা হয়।