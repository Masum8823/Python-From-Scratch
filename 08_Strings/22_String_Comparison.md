
# 22. String Comparison in Python

## 1. Introduction to String Comparison

Python-এ দুটি String-এর মধ্যে তুলনা করার পদ্ধতিকে **String Comparison** বলা হয়।

দুটি String সমান কি না, কোনটি বড় বা ছোট এবং তাদের মধ্যে পার্থক্য কী, তা পরীক্ষা করার জন্য Comparison Operators ব্যবহার করা হয়।

Python-এ String Comparison করার জন্য নিচের Operators ব্যবহার করা হয়:

- `==` → Equal to
- `!=` → Not equal to
- `>` → Greater than
- `<` → Less than
- `>=` → Greater than or equal to
- `<=` → Less than or equal to

String Comparison-এর Result সবসময় `True` অথবা `False` হয়।

## 2. Comparing Strings Using ==

`==` operator ব্যবহার করে দুটি String সমান কি না পরীক্ষা করা যায়।

দুটি String-এর Content একই হলে Result `True` হয়।

**Example:**

```python
name1 = "Masum"
name2 = "Masum"

print(name1 == name2)
```

**Output:**

```text
True
```

**ব্যাখ্যা:**

এখানে `name1` এবং `name2`-এর Content একই।

তাই `==` operator `True` return করেছে।

**Example 2:**

```python
name1 = "Masum"
name2 = "Rahim"

print(name1 == name2)
```

**Output:**

```text
False
```

এখানে দুটি String-এর Content আলাদা।

তাই Result `False` হয়েছে।

## 3. Comparing Strings Using !=

`!=` operator ব্যবহার করে দুটি String সমান নয় কি না পরীক্ষা করা যায়।

দুটি String আলাদা হলে Result `True` হয়।

**Example:**

```python
name1 = "Python"
name2 = "Java"

print(name1 != name2)
```

**Output:**

```text
True
```

**ব্যাখ্যা:**

এখানে `"Python"` এবং `"Java"` আলাদা String।

তাই `!=` operator `True` return করেছে।

**Example 2:**

```python
text1 = "Hello"
text2 = "Hello"

print(text1 != text2)
```

**Output:**

```text
False
```

এখানে দুটি String একই হওয়ায় Result `False` হয়েছে।

## 4. Comparing Strings Using > and <

Python-এ `>` এবং `<` operator ব্যবহার করে দুটি String তুলনা করা যায়।

এক্ষেত্রে Python String-এর Character-গুলোর Unicode Value অনুযায়ী তুলনা করে।

**Example 1: Using Greater Than (>)**

```python
print("b" > "a")
print("z" > "a")
```

**Output:**

```text
True
True
```

**ব্যাখ্যা:**

Unicode Value অনুযায়ী `"b"` এবং `"z"`-এর Value `"a"`-এর চেয়ে বড়।

তাই দুটি Result-ই `True` হয়েছে।

**Example 2: Using Less Than (<)**

```python
print("a" < "b")
print("a" < "z")
```

**Output:**

```text
True
True
```

এখানে `"a"`-এর Unicode Value অন্য দুটি Character-এর চেয়ে ছোট।

তাই Result `True` হয়েছে।

## 5. Comparing Strings Using >= and <=

`>=` এবং `<=` operator ব্যবহার করে দুটি String-এর মধ্যে Greater Than, Less Than অথবা Equal Condition পরীক্ষা করা যায়।

**Example:**

```python
print("b" >= "a")
print("a" <= "b")
print("a" >= "a")
print("b" <= "a")
```

**Output:**

```text
True
True
True
False
```

**ব্যাখ্যা:**

- `"b" >= "a"` → True
- `"a" <= "b"` → True
- `"a" >= "a"` → True
- `"b" <= "a"` → False

এখানে Equal হলে `>=` এবং `<=` উভয় Condition-ই True হয়।

## 6. Understanding Lexicographical Comparison

Python-এ String তুলনা করার সময় Character-গুলো বাম দিক থেকে একে একে তুলনা করা হয়।

এই পদ্ধতিকে **Lexicographical Comparison** বলা হয়।

যে Position-এ প্রথম ভিন্ন Character পাওয়া যায়, সেই Character-এর Unicode Value অনুযায়ী তুলনার Result নির্ধারিত হয়।

**Example:**

```python
print("apple" < "banana")
print("cat" > "car")
print("hello" == "hello")
```

**Output:**

```text
True
True
True
```

**ব্যাখ্যা:**

- `"apple"` এবং `"banana"`-এর প্রথম Character আলাদা। `"a"`-এর Value ছোট, তাই Result `True`।
- `"cat"` এবং `"car"`-এর প্রথম দুটি Character একই। তৃতীয় Character-এ `"t"` এবং `"r"` তুলনা করা হয়েছে। `"t"` বড় হওয়ায় Result `True`।
- দুটি String একই হওয়ায় শেষ Result `True`।

## 7. Comparing Strings with Different Lengths

দুটি String-এর Length আলাদা হলেও Python তাদের তুলনা করতে পারে।

যদি একটি String অন্যটির সম্পূর্ণ অংশ হয়, তাহলে ছোট String-টিকে ছোট হিসেবে বিবেচনা করা হয়।

**Example:**

```python
print("apple" < "apples")
print("Python" > "Pytho")
print("cat" == "cats")
```

**Output:**

```text
True
True
False
```

**ব্যাখ্যা:**

- `"apple"` হলো `"apples"`-এর প্রথম অংশ। তাই ছোট String `"apple"` ছোট।
- `"Python"`-এর অতিরিক্ত একটি Character রয়েছে। তাই এটি `"Pytho"`-এর চেয়ে বড়।
- `"cat"` এবং `"cats"` সমান নয়।

## 8. Case-Sensitive String Comparison

Python-এর String Comparison Case-Sensitive।

অর্থাৎ Uppercase এবং Lowercase Character-কে আলাদা হিসেবে বিবেচনা করা হয়।

**Example:**

```python
print("Python" == "python")
print("Hello" == "hello")
print("A" == "a")
```

**Output:**

```text
False
False
False
```

**ব্যাখ্যা:**

এখানে প্রতিটি ক্ষেত্রে Uppercase এবং Lowercase Character আলাদা।

তাই সব Result `False` হয়েছে।

**Important:**

Python-এ `"A"` এবং `"a"` একই Character হিসেবে বিবেচিত হয় না।

## 9. Case-Insensitive String Comparison

দুটি String-এর মধ্যে Case বিবেচনা না করে তুলনা করতে চাইলে `lower()` অথবা `upper()` method ব্যবহার করা যায়।

**Example:**

```python
text1 = "Python"
text2 = "PYTHON"

print(text1.lower() == text2.lower())
```

**Output:**

```text
True
```

**ব্যাখ্যা:**

এখানে দুটি String-কে প্রথমে Lowercase করা হয়েছে।

তারপর তুলনা করায় Result `True` হয়েছে।

**Example 2:**

```python
text1 = "Hello"
text2 = "HELLO"

print(text1.upper() == text2.upper())
```

**Output:**

```text
True
```

এখানে দুটি String-কে Uppercase করে তুলনা করা হয়েছে।

## 10. Comparing Strings with if-else

String Comparison-এর Result ব্যবহার করে `if-else` statement-এর মাধ্যমে বিভিন্ন Decision নেওয়া যায়।

**Example:**

```python
password = "python123"

user_password = input("Enter password: ")

if user_password == password:
    print("Login successful.")
else:
    print("Incorrect password.")
```

**Sample Input 1:**

```text
Enter password: python123
```

**Output 1:**

```text
Login successful.
```

**Sample Input 2:**

```text
Enter password: python
```

**Output 2:**

```text
Incorrect password.
```

এখানে User-এর দেওয়া Password এবং সংরক্ষিত Password তুলনা করা হয়েছে।

দুটি একই হলে Login Successful দেখানো হয়েছে।

## 11. Comparing Strings with User Input

`input()` ব্যবহার করে User-এর কাছ থেকে দুটি String নিয়ে তাদের মধ্যে তুলনা করা যায়।

**Example:**

```python
text1 = input("Enter first text: ")
text2 = input("Enter second text: ")

if text1 == text2:
    print("Both strings are equal.")
else:
    print("Strings are different.")
```

**Sample Input 1:**

```text
Enter first text: Python
Enter second text: Python
```

**Output 1:**

```text
Both strings are equal.
```

**Sample Input 2:**

```text
Enter first text: Python
Enter second text: Java
```

**Output 2:**

```text
Strings are different.
```

## 12. Comparing Strings with Different Cases

যদি User বিভিন্ন Uppercase এবং Lowercase ব্যবহার করে Input দেয়, তাহলে `lower()` method দিয়ে Case-Insensitive Comparison করা যায়।

**Example:**

```python
text1 = input("Enter first text: ")
text2 = input("Enter second text: ")

if text1.lower() == text2.lower():
    print("Both strings are equal.")
else:
    print("Strings are different.")
```

**Sample Input:**

```text
Enter first text: Python
Enter second text: PYTHON
```

**Output:**

```text
Both strings are equal.
```

এখানে দুটি String-এর Case আলাদা হলেও `lower()` করার পর তারা একই হয়েছে।

তাই Result `True` হয়েছে।

## 13. Comparing Strings Using Unicode Values

Python-এ প্রতিটি Character-এর একটি Unicode Value রয়েছে।

`ord()` function ব্যবহার করে কোনো Character-এর Unicode Value বের করা যায়।

**Example:**

```python
print(ord("A"))
print(ord("a"))
print(ord("B"))
print(ord("b"))
```

**Output:**

```text
65
97
66
98
```

**ব্যাখ্যা:**

এখানে:

- `"A"`-এর Unicode Value `65`।
- `"a"`-এর Unicode Value `97`।
- `"B"`-এর Unicode Value `66`।
- `"b"`-এর Unicode Value `98`।

তাই:

```python
print("A" < "a")
print("B" < "b")
```

**Output:**

```text
True
True
```

এখানে Unicode Value অনুযায়ী Uppercase Character ছোট হওয়ায় Result `True` হয়েছে।

## 14. Common Mistakes in String Comparison

### Mistake 1: Confusing = with ==

**Incorrect Code:**

```python
name = "Masum"

if name = "Masum":
    print("Matched")
```

**Error:**

```text
SyntaxError
```

অনেকে Assignment Operator `=` এবং Comparison Operator `==` গুলিয়ে ফেলে।

**Solution:**

```python
name = "Masum"

if name == "Masum":
    print("Matched")
```

**Output:**

```text
Matched
```

### Mistake 2: Forgetting Case Sensitivity

**Example:**

```python
text1 = "Python"
text2 = "python"

print(text1 == text2)
```

**Output:**

```text
False
```

এখানে Case আলাদা হওয়ায় Result `False` হয়েছে।

**Solution:**

```python
print(text1.lower() == text2.lower())
```

**Output:**

```text
True
```

### Mistake 3: Comparing Strings Based on Length Only

**Example:**

```python
print("z" > "aaaa")
```

**Output:**

```text
True
```

অনেকে মনে করতে পারে `"aaaa"`-এর Length বেশি হওয়ায় এটি বড় হবে।

কিন্তু Python String Comparison করার সময় শুধু Length বিবেচনা করে না।

এখানে প্রথম Character `"z"` এবং `"a"` তুলনা করা হয়েছে।

Unicode Value অনুযায়ী `"z"` বড় হওয়ায় Result `True` হয়েছে।

### Mistake 4: Assuming Alphabetical Comparison Ignores Case

**Example:**

```python
print("apple" == "APPLE")
```

**Output:**

```text
False
```

Python স্বয়ংক্রিয়ভাবে Uppercase এবং Lowercase একই হিসেবে বিবেচনা করে না।

Case-Insensitive Comparison-এর জন্য `lower()` ব্যবহার করতে হয়।

## 15. Practical Examples

### Example 1: Check Whether Two Names Are Equal

```python
name1 = "Masum"
name2 = "Masum"

if name1 == name2:
    print("Names are equal.")
else:
    print("Names are different.")
```

**Output:**

```text
Names are equal.
```

### Example 2: Find the Greater String

```python
text1 = "Apple"
text2 = "Banana"

if text1 > text2:
    print("First string is greater.")
else:
    print("Second string is greater.")
```

**Output:**

```text
Second string is greater.
```

### Example 3: Compare Two Passwords

```python
password1 = input("Enter password: ")
password2 = input("Confirm password: ")

if password1 == password2:
    print("Password matched.")
else:
    print("Password did not match.")
```

**Sample Input:**

```text
Enter password: python123
Confirm password: python123
```

**Output:**

```text
Password matched.
```

### Example 4: Case-Insensitive Name Comparison

```python
name1 = "Masum"
name2 = "MASUM"

if name1.lower() == name2.lower():
    print("Same name.")
else:
    print("Different names.")
```

**Output:**

```text
Same name.
```

### Example 5: Check Alphabetical Order

```python
name1 = "Apple"
name2 = "Banana"

if name1 < name2:
    print("Apple comes first.")
else:
    print("Banana comes first.")
```

**Output:**

```text
Apple comes first.
```

## 16. Important Rules to Remember

1. String Comparison-এর জন্য Comparison Operators ব্যবহার করা হয়।
2. `==` দুটি String সমান কি না পরীক্ষা করে।
3. `!=` দুটি String আলাদা কি না পরীক্ষা করে।
4. `>` এবং `<` দিয়ে দুটি String তুলনা করা যায়।
5. `>=` এবং `<=` Equal Condition-সহ তুলনা করে।
6. String Comparison-এর Result `True` অথবা `False` হয়।
7. Python String Comparison-এর ক্ষেত্রে Unicode Value ব্যবহার করে।
8. Character বাম দিক থেকে একে একে তুলনা করা হয়।
9. String Comparison Case-Sensitive।
10. Case-Insensitive Comparison-এর জন্য `lower()` বা `upper()` ব্যবহার করা যায়।
11. String-এর Length আলাদা হলেই বড় String-টি Comparison-এ বড় হবে এমন নয়।
12. `ord()` function দিয়ে Character-এর Unicode Value বের করা যায়।

## 17. Practice Problems

### Problem 1: Compare Two Strings

নিচের দুটি String সমান কি না পরীক্ষা করো।

```python
text1 = "Python"
text2 = "Python"
```

**Expected Output:**

```text
True
```

### Problem 2: Check Different Strings

নিচের দুটি String আলাদা কি না পরীক্ষা করো।

```python
text1 = "Python"
text2 = "Java"
```

**Expected Output:**

```text
True
```

### Problem 3: Use Greater Than

নিচের Comparison-এর Result বের করো।

```python
print("z" > "a")
```

**Expected Output:**

```text
True
```

### Problem 4: Use Less Than

নিচের Comparison-এর Result বের করো।

```python
print("apple" < "banana")
```

**Expected Output:**

```text
True
```

### Problem 5: Case-Insensitive Comparison

নিচের দুটি String Case-Insensitive ভাবে সমান কি না পরীক্ষা করো।

```python
text1 = "Python"
text2 = "PYTHON"
```

**Expected Output:**

```text
True
```

### Problem 6: Compare with User Input

User-এর কাছ থেকে দুটি String নিয়ে তারা সমান কি না পরীক্ষা করো।

**Sample Input:**

```text
Enter first text: Hello
Enter second text: Hello
```

**Expected Output:**

```text
Both strings are equal.
```

### Problem 7: Compare Passwords

User-এর কাছ থেকে দুটি Password নিয়ে তারা একই কি না পরীক্ষা করো।

**Sample Input:**

```text
Enter password: python123
Confirm password: python123
```

**Expected Output:**

```text
Password matched.
```

### Problem 8: Find Unicode Value

নিচের Character-গুলোর Unicode Value বের করো।

```python
print(ord("A"))
print(ord("a"))
```

**Expected Output:**

```text
65
97
```

### Problem 9: Predict the Output

```python
print("Python" == "python")
print("apple" < "banana")
print("z" > "a")
print("Hello" != "hello")
```

**Expected Output:**

```text
False
True
True
True
```

### Problem 10: Predict the Output

```python
text1 = "Python"
text2 = "PYTHON"

print(text1 == text2)
print(text1.lower() == text2.lower())
print(text1 != text2)
```

**Expected Output:**

```text
False
True
True
```

## 18. Summary

- String Comparison দিয়ে দুটি String-এর মধ্যে তুলনা করা যায়।
- `==` এবং `!=` দিয়ে String সমান বা আলাদা কি না পরীক্ষা করা যায়।
- `>` এবং `<` দিয়ে String-এর তুলনামূলক অবস্থান পরীক্ষা করা যায়।
- Python Lexicographical Comparison ব্যবহার করে।
- String Comparison Case-Sensitive।
- `lower()` এবং `upper()` দিয়ে Case-Insensitive Comparison করা যায়।
- `ord()` function দিয়ে Character-এর Unicode Value পাওয়া যায়।
- String Comparison-এর Result `True` অথবা `False` হয়।

String Comparison Python-এর একটি গুরুত্বপূর্ণ Concept, যা Password Checking, Name Matching, Text Validation এবং বিভিন্ন Decision-Making Program তৈরিতে ব্যবহার করা হয়।
