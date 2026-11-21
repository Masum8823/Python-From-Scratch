
# 32. String Testing Methods in Python (isalpha(), isdigit(), etc.)

## 1. Introduction to String Testing Methods

Python-এ বিভিন্ন String Testing Method ব্যবহার করে একটি String-এর মধ্যে কী ধরনের Character রয়েছে তা পরীক্ষা করা যায়।

এই Method-গুলো সাধারণত `True` অথবা `False` Return করে।

**Example:**

```python
text = "Python123"

print(text.isalpha())
print(text.isdigit())
print(text.isalnum())
```

**Output:**

```text
False
False
True
```

**Explanation:**

- `isalpha()` পরীক্ষা করে String-এ শুধু Alphabet আছে কি না।
- `isdigit()` পরীক্ষা করে String-এ শুধু Digit আছে কি না।
- `isalnum()` পরীক্ষা করে String-এ শুধু Alphabet অথবা Digit আছে কি না।
- `"Python123"`-এ Alphabet এবং Digit দুটোই রয়েছে। তাই শুধু `isalnum()` True হয়েছে।

## 2. isalpha() Method

String-এর সব Character Alphabet কি না তা পরীক্ষা করতে `isalpha()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.isalpha()
```

**Example:**

```python
name = "Masum"

print(name.isalpha())
```

**Output:**

```text
True
```

**Explanation:**

String-টিতে শুধু Alphabet রয়েছে। তাই `True` Return করেছে।

**Another Example:**

```python
print("Python".isalpha())
print("Python123".isalpha())
print("Python Programming".isalpha())
```

**Output:**

```text
True
False
False
```

**Explanation:**

- `"Python"`-এ শুধু Alphabet রয়েছে।
- `"Python123"`-এ Digit রয়েছে।
- `"Python Programming"`-এ Space রয়েছে।

তাই দ্বিতীয় এবং তৃতীয় ক্ষেত্রে `False` এসেছে।

## 3. isdigit() Method

String-এর সব Character Digit কি না তা পরীক্ষা করতে `isdigit()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.isdigit()
```

**Example:**

```python
number = "12345"

print(number.isdigit())
```

**Output:**

```text
True
```

**Explanation:**

String-টিতে শুধু Digit রয়েছে। তাই `True` Return করেছে।

**Another Example:**

```python
print("12345".isdigit())
print("123abc".isdigit())
print("12.50".isdigit())
print("-123".isdigit())
```

**Output:**

```text
True
False
False
False
```

**Explanation:**

- `"12345"`-এ শুধু Digit রয়েছে।
- `"123abc"`-এ Alphabet রয়েছে।
- `"12.50"`-এ Decimal Point রয়েছে।
- `"-123"`-এ Negative Sign রয়েছে।

তাই শেষের তিনটি ক্ষেত্রে `False` এসেছে।

## 4. isalnum() Method

String-এর সব Character Alphabet অথবা Digit কি না তা পরীক্ষা করতে `isalnum()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.isalnum()
```

**Example:**

```python
text = "Python123"

print(text.isalnum())
```

**Output:**

```text
True
```

**Explanation:**

এখানে Alphabet এবং Digit দুটোই রয়েছে। কিন্তু কোনো Space বা Special Character নেই। তাই `True` Return করেছে।

**Another Example:**

```python
print("Python".isalnum())
print("12345".isalnum())
print("Python123".isalnum())
print("Python 123".isalnum())
print("Python@123".isalnum())
```

**Output:**

```text
True
True
True
False
False
```

**Explanation:**

- Alphabet থাকলে `True`।
- Digit থাকলে `True`।
- Alphabet এবং Digit একসঙ্গে থাকলেও `True`।
- Space থাকলে `False`।
- Special Character থাকলে `False`।

## 5. isspace() Method

String-এর সব Character Whitespace কি না তা পরীক্ষা করতে `isspace()` method ব্যবহার করা হয়।

Whitespace বলতে Space, Tab এবং Newline-এর মতো Character বোঝায়।

**Syntax:**

```python
string.isspace()
```

**Example:**

```python
text = "   "

print(text.isspace())
```

**Output:**

```text
True
```

**Explanation:**

String-টিতে শুধু Space রয়েছে। তাই `True` Return করেছে।

**Another Example:**

```python
print("   ".isspace())
print("\t".isspace())
print("\n".isspace())
print("Hello World".isspace())
print("".isspace())
```

**Output:**

```text
True
True
True
False
False
```

**Explanation:**

- `"   "` শুধু Space।
- `"\t"` একটি Tab Character।
- `"\n"` একটি Newline Character।
- `"Hello World"`-এ Alphabet রয়েছে।
- Empty String-এ কোনো Character নেই।

তাই শেষের দুটি ক্ষেত্রে `False` এসেছে।

## 6. islower() Method

String-এর সব Alphabetic Character Lowercase কি না তা পরীক্ষা করতে `islower()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.islower()
```

**Example:**

```python
text = "hello python"

print(text.islower())
```

**Output:**

```text
True
```

**Another Example:**

```python
print("hello".islower())
print("Hello".islower())
print("HELLO".islower())
print("hello123".islower())
```

**Output:**

```text
True
False
False
True
```

**Explanation:**

- `"hello"`-তে সব Alphabet Lowercase।
- `"Hello"`-তে `H` Uppercase।
- `"HELLO"`-তে সব Alphabet Uppercase।
- `"hello123"`-তে সব Alphabet Lowercase।

**Important Note:** Digit এবং Special Character Lowercase বা Uppercase নয়। তাই এগুলো থাকলেও Result নির্ধারণে সমস্যা হয় না।

## 7. isupper() Method

String-এর সব Alphabetic Character Uppercase কি না তা পরীক্ষা করতে `isupper()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.isupper()
```

**Example:**

```python
text = "HELLO PYTHON"

print(text.isupper())
```

**Output:**

```text
True
```

**Another Example:**

```python
print("HELLO".isupper())
print("Hello".isupper())
print("hello".isupper())
print("HELLO123".isupper())
```

**Output:**

```text
True
False
False
True
```

**Explanation:**

যদি String-এর সব Alphabet Uppercase হয়, তাহলে `True` Return করে।

## 8. istitle() Method

String-এর প্রতিটি Word-এর প্রথম Alphabet Uppercase এবং বাকি Alphabet Lowercase কি না তা পরীক্ষা করতে `istitle()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.istitle()
```

**Example:**

```python
text = "Hello Python"

print(text.istitle())
```

**Output:**

```text
True
```

**Another Example:**

```python
print("Hello Python".istitle())
print("hello python".istitle())
print("HELLO PYTHON".istitle())
print("Python Programming".istitle())
```

**Output:**

```text
True
False
False
True
```

**Explanation:**

- `"Hello Python"` প্রতিটি Word Capital Letter দিয়ে শুরু হয়েছে।
- `"hello python"` ছোট হাতের Letter দিয়ে শুরু হয়েছে।
- `"HELLO PYTHON"` সব Letter Uppercase।
- `"Python Programming"` Title Case-এ রয়েছে।

## 9. isdecimal() Method

String-এর সব Character Decimal Digit কি না তা পরীক্ষা করতে `isdecimal()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.isdecimal()
```

**Example:**

```python
number = "12345"

print(number.isdecimal())
```

**Output:**

```text
True
```

**Another Example:**

```python
print("12345".isdecimal())
print("12.50".isdecimal())
print("123abc".isdecimal())
```

**Output:**

```text
True
False
False
```

**Explanation:**

`isdecimal()` শুধু Decimal Digit পরীক্ষা করে। তাই Decimal Point বা Alphabet থাকলে `False` Return করে।

## 10. isnumeric() Method

String-এর সব Character Numeric কি না তা পরীক্ষা করতে `isnumeric()` method ব্যবহার করা হয়।

**Syntax:**

```python
string.isnumeric()
```

**Example:**

```python
number = "12345"

print(number.isnumeric())
```

**Output:**

```text
True
```

**Explanation:**

String-টিতে শুধু Numeric Character রয়েছে। তাই `True` Return করেছে।

**Another Example:**

```python
print("12345".isnumeric())
print("12.50".isnumeric())
print("123abc".isnumeric())
print("²".isnumeric())
```

**Output:**

```text
True
False
False
True
```

**Important Note:** `isnumeric()` সাধারণ Decimal Digit ছাড়াও কিছু বিশেষ Numeric Character যেমন Superscript Digit পরীক্ষা করতে পারে।

## 11. Difference Between isdigit(), isdecimal() and isnumeric()

এই তিনটি Method দেখতে প্রায় একই রকম হলেও তাদের কাজের মধ্যে পার্থক্য রয়েছে।

| Method | কাজ |
|---|---|
| `isdecimal()` | Decimal Digit পরীক্ষা করে |
| `isdigit()` | Digit Character পরীক্ষা করে |
| `isnumeric()` | আরও বিস্তৃত Numeric Character পরীক্ষা করে |

**Example:**

```python
text = "12345"

print(text.isdecimal())
print(text.isdigit())
print(text.isnumeric())
```

**Output:**

```text
True
True
True
```

**Another Example:**

```python
text = "²"

print(text.isdecimal())
print(text.isdigit())
print(text.isnumeric())
```

**Output:**

```text
False
True
True
```

**Explanation:**

- `²` Decimal Digit নয়।
- এটি Digit হিসেবে স্বীকৃত।
- এটি Numeric Character-ও।

তাই `isdecimal()` False এবং বাকি দুটি True।

**Important Rule:**

`isnumeric()` সবচেয়ে বেশি ধরনের Numeric Character গ্রহণ করে। `isdigit()` তার চেয়ে কিছুটা কম এবং `isdecimal()` সবচেয়ে সীমিত।

## 12. Checking Empty Strings

String Testing Method-এর একটি গুরুত্বপূর্ণ নিয়ম হলো Empty String-এর ক্ষেত্রে সাধারণত `False` Return করে।

**Example:**

```python
text = ""

print(text.isalpha())
print(text.isdigit())
print(text.isalnum())
print(text.isspace())
print(text.islower())
print(text.isupper())
```

**Output:**

```text
False
False
False
False
False
False
```

**Explanation:**

Empty String-এ কোনো Character নেই। তাই এই Method-গুলো `True` Return করে না।

## 13. Using String Testing Methods with if-else

String Testing Method ব্যবহার করে বিভিন্ন Condition তৈরি করা যায়।

**Example 1: Checking Alphabet**

```python
name = "Masum"

if name.isalpha():
    print("Only Alphabets")
else:
    print("Contains Other Characters")
```

**Output:**

```text
Only Alphabets
```

**Example 2: Checking Digits**

```python
number = "12345"

if number.isdigit():
    print("Valid Number")
else:
    print("Invalid Number")
```

**Output:**

```text
Valid Number
```

**Example 3: Checking Alphanumeric Text**

```python
username = "Masum123"

if username.isalnum():
    print("Valid Username")
else:
    print("Invalid Username")
```

**Output:**

```text
Valid Username
```

**Example 4: Checking Uppercase Text**

```python
text = "PYTHON"

if text.isupper():
    print("All Letters Are Uppercase")
else:
    print("Contains Lowercase Letters")
```

**Output:**

```text
All Letters Are Uppercase
```

## 14. Practical Examples

### Example 1: Checking Whether Input Contains Only Letters

```python
name = input("Enter your name: ")

if name.isalpha():
    print("Valid Name")
else:
    print("Name should contain only letters")
```

**Input:**

```text
Masum
```

**Output:**

```text
Valid Name
```

### Example 2: Checking Whether Input Contains Only Digits

```python
number = input("Enter a number: ")

if number.isdigit():
    print("Valid Integer Input")
else:
    print("Invalid Input")
```

**Input:**

```text
12345
```

**Output:**

```text
Valid Integer Input
```

### Example 3: Checking Username

```python
username = input("Enter username: ")

if username.isalnum():
    print("Username Accepted")
else:
    print("Username should not contain spaces or special characters")
```

**Input:**

```text
Masum123
```

**Output:**

```text
Username Accepted
```

### Example 4: Checking Password Uppercase Letters

```python
password = "MASUM123"

if password.isupper():
    print("All letters are uppercase")
else:
    print("Contains lowercase letters")
```

**Output:**

```text
All letters are uppercase
```

### Example 5: Checking Whether Input Contains Only Spaces

```python
text = "     "

if text.isspace():
    print("Only whitespace")
else:
    print("Contains other characters")
```

**Output:**

```text
Only whitespace
```

## 15. Common Mistakes in String Testing Methods

### Mistake 1: Using isalpha() with Spaces

**Incorrect Expectation:**

```python
text = "Hello World"

print(text.isalpha())
```

**Output:**

```text
False
```

**Why?**

String-এর মধ্যে Space রয়েছে। তাই সব Character Alphabet নয়।

**Correct Approach:**

```python
text = "HelloWorld"

print(text.isalpha())
```

**Output:**

```text
True
```

### Mistake 2: Using isdigit() with Decimal Numbers

**Example:**

```python
number = "12.50"

print(number.isdigit())
```

**Output:**

```text
False
```

**Why?**

Decimal Point (`.`) Digit নয়।

### Mistake 3: Using isalnum() with Special Characters

**Example:**

```python
text = "Python@123"

print(text.isalnum())
```

**Output:**

```text
False
```

**Why?**

`@` একটি Special Character। `isalnum()` শুধু Alphabet এবং Digit গ্রহণ করে।

### Mistake 4: Expecting Empty String to Return True

**Example:**

```python
text = ""

print(text.isalpha())
print(text.isdigit())
```

**Output:**

```text
False
False
```

**Why?**

Empty String-এ কোনো Character নেই।

### Mistake 5: Confusing islower() with lower()

**Example:**

```python
text = "HELLO"

print(text.lower())
print(text.islower())
```

**Output:**

```text
hello
False
```

**Explanation:**

- `lower()` String-কে Lowercase করে নতুন String Return করে।
- `islower()` পরীক্ষা করে String-এর Alphabetগুলো Lowercase কি না।

## 16. Important Rules to Remember

1. String Testing Method সাধারণত `True` অথবা `False` Return করে।
2. `isalpha()` শুধু Alphabet পরীক্ষা করে।
3. `isdigit()` Digit পরীক্ষা করে।
4. `isalnum()` Alphabet অথবা Digit পরীক্ষা করে।
5. `isspace()` Whitespace পরীক্ষা করে।
6. `islower()` Lowercase Alphabet পরীক্ষা করে।
7. `isupper()` Uppercase Alphabet পরীক্ষা করে।
8. `istitle()` Title Case পরীক্ষা করে।
9. `isdecimal()` Decimal Digit পরীক্ষা করে।
10. `isnumeric()` Numeric Character পরীক্ষা করে।
11. Space থাকলে `isalpha()` এবং `isalnum()` সাধারণত False Return করে।
12. Special Character থাকলে `isalnum()` False Return করে।
13. Empty String-এর ক্ষেত্রে এসব Method False Return করে।
14. এই Method-গুলো Original String পরিবর্তন করে না।
15. String Validation-এর ক্ষেত্রে এই Method-গুলো অনেক কাজে লাগে।

## 17. Practice Problems

### Problem 1: Check Alphabet

```python
text = "Python"

# Check whether the string contains only alphabets
```

**Expected Output:**

```text
True
```

### Problem 2: Check Digits

```python
number = "123456"

# Check whether the string contains only digits
```

**Expected Output:**

```text
True
```

### Problem 3: Check Alphanumeric String

```python
text = "Python123"

# Check whether the string contains only alphabets and digits
```

**Expected Output:**

```text
True
```

### Problem 4: Check Whitespace

```python
text = "    "

# Check whether the string contains only whitespace
```

**Expected Output:**

```text
True
```

### Problem 5: Check Lowercase

```python
text = "hello python"

# Check whether all alphabetic characters are lowercase
```

**Expected Output:**

```text
True
```

### Problem 6: Check Uppercase

```python
text = "HELLO PYTHON"

# Check whether all alphabetic characters are uppercase
```

**Expected Output:**

```text
True
```

### Problem 7: Check Title Case

```python
text = "Python Programming"

# Check whether the string is in title case
```

**Expected Output:**

```text
True
```

### Problem 8: Check Decimal Number

```python
number = "12345"

# Check whether all characters are decimal digits
```

**Expected Output:**

```text
True
```

### Problem 9: Check Numeric Characters

```python
number = "12345"

# Check whether all characters are numeric
```

**Expected Output:**

```text
True
```

### Problem 10: Validate Username

```python
username = "Masum123"

# Print "Valid Username" if the username contains only letters and digits
# Otherwise, print "Invalid Username"
```

**Expected Output:**

```text
Valid Username
```

## 18. Chapter Summary

এই Topic-এ আমরা Python-এর বিভিন্ন String Testing Method সম্পর্কে শিখেছি।

আমরা শিখেছি:

- `isalpha()` Method
- `isdigit()` Method
- `isalnum()` Method
- `isspace()` Method
- `islower()` Method
- `isupper()` Method
- `istitle()` Method
- `isdecimal()` Method
- `isnumeric()` Method
- Empty String Testing
- if-else-এর সঙ্গে String Testing Method ব্যবহার
- Practical Examples
- Common Mistakes এবং Important Rules

**Next Topic:**

`33_String_Alignment_and_Padding.md`

পরবর্তী Topic-এ আমরা `center()`, `ljust()`, `rjust()` এবং `zfill()` method ব্যবহার করে String-এর Alignment এবং Padding শেখার চেষ্টা করব।
