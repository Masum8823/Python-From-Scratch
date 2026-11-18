# 05. Strings with Quotes and Escape Characters

## 1. Introduction

Python-এ String-এর মধ্যে অনেক সময় quotation marks, backslash অথবা special characters ব্যবহার করার প্রয়োজন হয়।

যেমন:

- `I'm learning Python.`
- `He said, "Hello!"`
- `C:\Users\Masum\Desktop`
- `Hello` এবং `World`-কে আলাদা লাইনে দেখানো।

এ ধরনের text সঠিকভাবে লেখার জন্য Python-এ **Escape Characters** ব্যবহার করা হয়।

Escape Character তৈরি করতে backslash (`\`) ব্যবহার করা হয়।

## 2. Understanding Backslash (\)

Backslash হলো `\` symbol। Python String-এর মধ্যে এটি কোনো character-এর বিশেষ অর্থ প্রকাশ করতে পারে।

উদাহরণ:

```python
print("Hello\nWorld")
```

**Output:**

```text
Hello
World
```

এখানে `\n` একটি newline তৈরি করেছে।

Backslash ব্যবহার করে quotation marks এবং অন্যান্য special characters-ও String-এর মধ্যে লেখা যায়।

## 3. Using Single Quotes Inside a String

String-এর মধ্যে apostrophe বা single quotation mark ব্যবহার করতে হলে দুটি উপায় রয়েছে।

### Method 1: Use Double Quotes Outside

```python
message = "I'm learning Python."

print(message)
```

**Output:**

```text
I'm learning Python.
```

এখানে বাইরের quotation marks হলো double quotes। তাই ভেতরের apostrophe নিয়ে কোনো সমস্যা হয়নি।

### Method 2: Use Escape Character

```python
message = 'I\'m learning Python.'

print(message)
```

**Output:**

```text
I'm learning Python.
```

এখানে `\'` ব্যবহার করে single quotation mark-কে escape করা হয়েছে।

## 4. Using Double Quotes Inside a String

String-এর মধ্যে double quotation mark ব্যবহার করতেও দুটি উপায় রয়েছে।

### Method 1: Use Single Quotes Outside

```python
message = 'He said, "Hello!"'

print(message)
```

**Output:**

```text
He said, "Hello!"
```

### Method 2: Use Escape Character

```python
message = "He said, \"Hello!\""

print(message)
```

**Output:**

```text
He said, "Hello!"
```

এখানে `\"` দিয়ে double quotation mark escape করা হয়েছে।

## 5. Using Both Single and Double Quotes

একই String-এর মধ্যে single এবং double quotation marks দুটোই থাকতে পারে।

```python
message = "He said, \"It's a beautiful day!\""

print(message)
```

**Output:**

```text
He said, "It's a beautiful day!"
```

এখানে:

- `\"` double quotation mark escape করেছে।
- `It's`-এর apostrophe স্বাভাবিকভাবেই লেখা হয়েছে।

## 6. Using Backslash Inside a String

String-এর মধ্যে সরাসরি backslash দেখাতে চাইলে `\\` ব্যবহার করতে হয়।

```python
text = "Python\\Programming"

print(text)
```

**Output:**

```text
Python\Programming
```

এখানে `\\` একটি single backslash তৈরি করেছে।

আরেকটি উদাহরণ:

```python
path = "C:\\Users\\Masum\\Desktop"

print(path)
```

**Output:**

```text
C:\Users\Masum\Desktop
```

Windows file path লেখার সময় এই বিষয়টি গুরুত্বপূর্ণ।

## 7. Common Escape Characters

Python-এ কয়েকটি গুরুত্বপূর্ণ Escape Character রয়েছে।

| Escape Character | কাজ |
|---|---|
| `\n` | New line তৈরি করে |
| `\t` | Horizontal tab তৈরি করে |
| `\\` | Backslash দেখায় |
| `\'` | Single quote দেখায় |
| `\"` | Double quote দেখায় |
| `\r` | Carriage return |
| `\b` | Backspace |
| `\f` | Form feed |
| `\v` | Vertical tab |
| `\a` | Alert বা bell character |
| `\0` | Null character |
| `\ooo` | Octal value দিয়ে character |
| `\xhh` | Hexadecimal value দিয়ে character |
| `\uXXXX` | Unicode character (4-digit code point) |
| `\UXXXXXXXX` | Unicode character (8-digit code point) |

## 8. Newline Character (\n)

`\n` ব্যবহার করে String-এর মধ্যে নতুন line তৈরি করা যায়।

```python
message = "Hello\nWelcome to Python"

print(message)
```

**Output:**

```text
Hello
Welcome to Python
```

আরেকটি উদাহরণ:

```python
text = "Name: Masum\nDepartment: CSE\nUniversity: NUB"

print(text)
```

**Output:**

```text
Name: Masum
Department: CSE
University: NUB
```

## 9. Tab Character (\t)

`\t` ব্যবহার করে tab space তৈরি করা হয়।

```python
text = "Name\tAge\tDepartment"

print(text)
```

**Output:**

```text
Name    Age    Department
```

Tab-এর exact visual width terminal বা editor অনুযায়ী ভিন্ন হতে পারে।

এটি সাধারণত text-এর মধ্যে spacing তৈরি করতে ব্যবহৃত হয়।

## 10. Carriage Return (\r)

`\r` হলো Carriage Return। এটি text cursor-কে বর্তমান লাইনের শুরুতে ফিরিয়ে নেয়।

```python
text = "Python\rHello"

print(text)
```

সাধারণ terminal-এ সম্ভাব্য Output:

```text
Hellon
```

কারণ `\r`-এর পরে `Hello` বর্তমান লাইনের শুরু থেকে লেখা হয় এবং আগের text-এর প্রথম পাঁচটি character overwrite করে।

তবে carriage return-এর দৃশ্যমান আচরণ terminal ও output environment অনুযায়ী ভিন্ন হতে পারে।

## 11. Backspace Character (\b)

`\b` হলো Backspace character। এটি cursor-কে এক position পিছিয়ে নেয়।

```python
text = "Helloo\b"

print(text)
```

কিছু terminal-এ শেষের `o` মুছে গিয়ে output দেখা যেতে পারে:

```text
Hello
```

তবে সব environment-এ একই visual result নিশ্চিত নয়।

## 12. Unicode Escape Characters

Unicode ব্যবহার করে বিভিন্ন ভাষার character, symbol এবং special character প্রকাশ করা যায়।

Python-এ:

- `\u` দিয়ে 4-digit Unicode code point লেখা যায়।
- `\U` দিয়ে 8-digit Unicode code point লেখা যায়।

উদাহরণ:

```python
print("\u0041")
print("\u03A9")
```

**Output:**

```text
A
Ω
```

এখানে:

- `\u0041` হলো `A`।
- `\u03A9` হলো `Ω`।

বাংলা Unicode character-এর উদাহরণ:

```python
print("\u0986\u09AE\u09BF")
```

**Output:**

```text
আমি
```

Unicode নিয়ে বিস্তারিত আলোচনা হবে `40_String_Encoding_and_Unicode_Basics.md` file-এ।

## 13. Octal and Hexadecimal Escape Characters

Octal এবং hexadecimal code ব্যবহার করেও character প্রকাশ করা যায়।

### Octal Escape

Octal escape-এর format হলো `\ooo`।

```python
print("\101")
```

**Output:**

```text
A
```

এখানে `101` হলো octal code, যা `A` character নির্দেশ করে।

### Hexadecimal Escape

Hexadecimal escape-এর format হলো `\xhh`।

```python
print("\x41")
```

**Output:**

```text
A
```

এখানে `41` হলো hexadecimal code, যা `A` character নির্দেশ করে।

## 14. Combining Multiple Escape Characters

একটি String-এর মধ্যে একাধিক Escape Character ব্যবহার করা যায়।

```python
message = "Name:\tMasum\nDepartment:\tCSE\nUniversity:\tNUB"

print(message)
```

**Output:**

```text
Name:   Masum
Department:    CSE
University:    NUB
```

এখানে `\t` tab এবং `\n` নতুন line তৈরি করেছে।

## 15. Common Mistakes

### Mistake 1: Escape Character ভুলে যাওয়া

ভুল:

```python
message = 'I'm learning Python'
```

এখানে apostrophe-এর কারণে `SyntaxError` হবে।

সঠিক:

```python
message = "I'm learning Python"
```

অথবা:

```python
message = 'I\'m learning Python'
```

### Mistake 2: Backslash একবার ব্যবহার করা

ভুল:

```python
path = "C:\Users\Masum"
```

এখানে `\U` একটি Unicode escape শুরু করার চেষ্টা করবে। কিন্তু সঠিক Unicode sequence না থাকায় `SyntaxError` হতে পারে।

সঠিক:

```python
path = "C:\\Users\\Masum"

print(path)
```

**Output:**

```text
C:\Users\Masum
```

### Mistake 3: `\n` এবং `/n` গুলিয়ে ফেলা

ভুল:

```python
print("Hello/nWorld")
```

Output:

```text
Hello/nWorld
```

সঠিক:

```python
print("Hello\nWorld")
```

Output:

```text
Hello
World
```

মনে রাখবে, Escape Character-এর জন্য backslash (`\`) ব্যবহার করতে হয়, forward slash (`/`) নয়।

### Mistake 4: Double Quotes Escape না করা

ভুল:

```python
message = "He said, "Hello!""
```

সঠিক:

```python
message = "He said, \"Hello!\""
```

### Mistake 5: `\\` এবং `\`-এর পার্থক্য না বোঝা

```python
print("A\nB")
print("A\\nB")
```

**Output:**

```text
A
B
A\nB
```

প্রথম ক্ষেত্রে `\n` newline তৈরি করেছে। দ্বিতীয় ক্ষেত্রে `\\` একটি backslash তৈরি করেছে, তাই `n` সাধারণ character হিসেবে দেখানো হয়েছে।

## 16. Practice Exercises

নিজে code লিখে সমাধান করার চেষ্টা করো।

1. `"I'm learning Python"` সঠিকভাবে print করো।
2. `He said, "Python is easy."` String তৈরি করো।
3. `C:\Users\Masum\Desktop` path সঠিকভাবে print করো।
4. `\n` ব্যবহার করে তিন লাইনের message তৈরি করো।
5. `\t` ব্যবহার করে Name, Age ও Department print করো।
6. `\\` ব্যবহার করে একটি backslash print করো।
7. `\u0041` ব্যবহার করে `A` print করো।
8. `\x41` ব্যবহার করে `A` print করো।
9. `\101` ব্যবহার করে `A` print করো।
10. একটি String-এ `\n`, `\t` এবং `\\` একসঙ্গে ব্যবহার করো।

## 17. Practice Solutions

### Solution 1

```python
print("I'm learning Python")
```

### Solution 2

```python
print('He said, "Python is easy."')
```

### Solution 3

```python
path = "C:\\Users\\Masum\\Desktop"

print(path)
```

**Output:**

```text
C:\Users\Masum\Desktop
```

### Solution 4

```python
message = "Hello\nWelcome to Python\nHappy Coding!"

print(message)
```

**Output:**

```text
Hello
Welcome to Python
Happy Coding!
```

### Solution 5

```python
print("Name\tAge\tDepartment")
print("Masum\t22\tCSE")
```

### Solution 6

```python
print("\\")
```

**Output:**

```text
\
```

### Solution 7

```python
print("\u0041")
```

### Solution 8

```python
print("\x41")
```

### Solution 9

```python
print("\101")
```

### Solution 10

```python
message = "Name:\tMasum\nPath:\tC:\\Users\\Masum"

print(message)
```

**Output:**

```text
Name:   Masum
Path:   C:\Users\Masum
```

## 18. Chapter Summary

- Escape Character তৈরি করতে backslash (`\`) ব্যবহার করা হয়।
- `\'` দিয়ে Single Quote এবং `\"` দিয়ে Double Quote লেখা যায়।
- `\\` দিয়ে একটি Backslash দেখানো যায়।
- `\n` নতুন line এবং `\t` tab তৈরি করে।
- `\r` carriage return এবং `\b` backspace নির্দেশ করে।
- `\u` ও `\U` Unicode character প্রকাশ করতে ব্যবহৃত হয়।
- `\ooo` Octal এবং `\xhh` Hexadecimal escape নির্দেশ করে।
- Windows path লেখার সময় backslash সঠিকভাবে ব্যবহার করতে হয়।

## 19. Self-Assessment Checklist

- [ ] Escape Character কী বুঝি।
- [ ] String-এর মধ্যে Single ও Double Quotes ব্যবহার করতে পারি।
- [ ] Backslash সঠিকভাবে ব্যবহার করতে পারি।
- [ ] `\n` ও `\t` ব্যবহার করতে পারি।
- [ ] Common Escape Characters চিনতে পারি।
- [ ] Unicode escape-এর basic ধারণা বুঝি।
- [ ] String-এর মধ্যে একাধিক Escape Character ব্যবহার করতে পারি।

## 20. Next Topic

পরবর্তী file: `06_Multiline_Strings.md`

এখানে Multiline String তৈরি, line break, triple quotes এবং multiline text নিয়ে বিস্তারিত আলোচনা করা হবে।
