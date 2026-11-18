
# 07. String Length with `len()`

## 1. Introduction

Python-এ কোনো String-এর মধ্যে মোট কতগুলো character আছে, তা জানার জন্য `len()` function ব্যবহার করা হয়।

`len` এর পূর্ণরূপ হলো **Length**।

এটি একটি built-in function, যা String-এর character সংখ্যা return করে।

**Syntax:**

```python
len(string)
```

এখানে `string` হলো যে String-এর দৈর্ঘ্য আমরা জানতে চাই।

## 2. Basic Example

```python
name = "Masum"

result = len(name)

print(result)
```

**Output:**

```text
5
```

**ব্যাখ্যা:**

`Masum` String-এ মোট ৫টি character আছে। তাই `len(name)` এর result হলো `5`।

## 3. Counting Characters with Spaces

String-এর মধ্যে থাকা space-ও একটি character হিসেবে গণনা করা হয়।

```python
text = "Hello World"

print(len(text))
```

**Output:**

```text
11
```

এখানে:

- `Hello` = 5 characters
- Space = 1 character
- `World` = 5 characters

Total = 11 characters।

## 4. Length of Different Strings

```python
text1 = "Python"
text2 = "Hello World"
text3 = "12345"
text4 = ""

print(len(text1))
print(len(text2))
print(len(text3))
print(len(text4))
```

**Output:**

```text
6
11
5
0
```

**মনে রাখবে:**

- Normal String-এর character গণনা করা হয়।
- Number লেখা থাকলেও String হলে সেগুলো character হিসেবে গণনা হবে।
- Empty String-এর length হলো `0`।

## 5. Special Characters and String Length

Special characters যেমন `\n`, `\t`-ও String-এর মধ্যে character হিসেবে গণনা হয়।

```python
text = "Hi\nPython"

print(len(text))
```

**Output:**

```text
9
```

এখানে:

- `Hi` = 2
- `\n` = 1
- `Python` = 6

Total = 9।

আরেকটি উদাহরণ:

```python
text = "A\tB"

print(len(text))
```

**Output:**

```text
3
```

এখানে `A`, `\t` এবং `B` — মোট ৩টি character।

## 6. Using len() with User Input

User-এর কাছ থেকে String input নিয়ে তার length বের করা যায়।

```python
name = input("Enter your name: ")

print("Name length:", len(name))
```

**Sample Input:**

```text
Masum
```

**Output:**

```text
Enter your name: Masum
Name length: 5
```

## 7. Using len() in Conditions

`len()` function ব্যবহার করে কোনো String-এর দৈর্ঘ্য অনুযায়ী condition তৈরি করা যায়।

```python
password = input("Enter password: ")

if len(password) >= 8:
    print("Password length is valid.")
else:
    print("Password is too short.")
```

**Sample Input:**

```text
123456
```

**Output:**

```text
Enter password: 123456
Password is too short.
```

এখানে Password-এর length ৮ বা তার বেশি কি না, তা পরীক্ষা করা হচ্ছে।

## 8. Important Rules

1. `len()` একটি built-in function।
2. String-এর মোট character সংখ্যা return করে।
3. Space এবং special characters-ও গণনা হয়।
4. Empty String-এর length `0`।
5. `len()` ব্যবহার করার সময় parentheses দিতে হয়।
6. এটি String-এর মূল value পরিবর্তন করে না।

**Important:**

`len()` একটি function, String method নয়।

সঠিক:

```python
text = "Python"
print(len(text))
```

ভুল:

```python
text = "Python"
print(text.len())
```

## 9. Common Mistakes

### Mistake 1: Parentheses ব্যবহার না করা

ভুল:

```python
text = "Python"
print(len text)
```

সঠিক:

```python
print(len(text))
```

### Mistake 2: String-এর পরিবর্তে ভুল variable ব্যবহার করা

```python
text = "Hello"
print(len(name))
```

এখানে `name` variable তৈরি করা হয়নি। তাই `NameError` হবে।

সঠিক:

```python
text = "Hello"
print(len(text))
```

### Mistake 3: Space গণনা করতে ভুলে যাওয়া

```python
text = "Hi Bro"
print(len(text))
```

Output:

```text
6
```

Space-ও একটি character।

## 10. Practice Exercises

### Exercise 1: Basic Length

একটি String তৈরি করে তার length বের করো।

### Exercise 2: User Input

User-এর কাছ থেকে নাম নিয়ে মোট character সংখ্যা দেখাও।

### Exercise 3: Word Length

দুটি Word input নিয়ে কোনটির length বেশি তা বের করো।

### Exercise 4: Password Validation

একটি Password input নাও। Password-এর length কমপক্ষে ৮ হলে `Valid`, অন্যথায় `Invalid` দেখাও।

## 11. Practice Solutions

### Solution 1

```python
text = "Programming"

print(len(text))
```

Output:

```text
11
```

### Solution 2

```python
name = input("Enter your name: ")

print("Length:", len(name))
```

### Solution 3

```python
word1 = input("Enter first word: ")
word2 = input("Enter second word: ")

if len(word1) > len(word2):
    print("First word is longer.")
elif len(word2) > len(word1):
    print("Second word is longer.")
else:
    print("Both words have equal length.")
```

### Solution 4

```python
password = input("Enter password: ")

if len(password) >= 8:
    print("Valid")
else:
    print("Invalid")
```

## 12. Chapter Summary

- `len()` দিয়ে String-এর length বের করা হয়।
- এটি একটি Python built-in function।
- Space এবং special characters-ও গণনা হয়।
- Empty String-এর length `0`।
- User input এবং conditional statements-এর সঙ্গে `len()` ব্যবহার করা যায়।

## 13. Self-Assessment Checklist

- [ ] `len()` function কী বুঝতে পারি।
- [ ] String-এর length বের করতে পারি।
- [ ] Space এবং special characters গণনা করতে পারি।
- [ ] User input-এর length বের করতে পারি।
- [ ] `len()` দিয়ে condition তৈরি করতে পারি।

## 14. Next Topic

`08_String_Indexing.md`

পরবর্তী topic-এ String Indexing শিখব, অর্থাৎ String-এর নির্দিষ্ট position থেকে কীভাবে একটি character access করতে হয়।
