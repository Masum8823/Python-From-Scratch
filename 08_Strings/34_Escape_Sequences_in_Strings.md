
# 34. Escape Sequences in Python Strings

## 1. Introduction to Escape Sequences

Python-এ String-এর মধ্যে কিছু special character ব্যবহার করার জন্য **Escape Sequences** ব্যবহার করা হয়।

Escape Sequence হলো এমন কিছু special combination, যা Backslash (`\`) দিয়ে শুরু হয় এবং String-এর মধ্যে বিশেষ কাজ করে।

উদাহরণ:

```python
print("Hello\nWorld")
```

**Output:**

```text
Hello
World
```

এখানে `\n` একটি Escape Sequence, যা নতুন line তৈরি করে।

---

## 2. Common Escape Sequences in Python

Python-এ ব্যবহৃত কিছু গুরুত্বপূর্ণ Escape Sequence নিচে দেওয়া হলো:

| Escape Sequence | কাজ |
|---|---|
| `\n` | New line তৈরি করে |
| `\t` | Horizontal tab তৈরি করে |
| `\\` | একটি Backslash (`\`) দেখায় |
| `\'` | Single quote দেখায় |
| `\"` | Double quote দেখায় |
| `\r` | Carriage return তৈরি করে |
| `\b` | Backspace তৈরি করে |
| `\f` | Form feed তৈরি করে |
| `\v` | Vertical tab তৈরি করে |
| `\a` | Alert বা bell character তৈরি করে |

---

## 3. New Line (\n)

`\n` ব্যবহার করে String-এর মধ্যে নতুন line তৈরি করা যায়।

### Example

```python
message = "Hello\nPython"

print(message)
```

**Output:**

```text
Hello
Python
```

এখানে `\n`-এর পরের text নতুন line-এ চলে গেছে।

### Practical Example

```python
print("Name: Masum\nAge: 22\nDepartment: CSE")
```

**Output:**

```text
Name: Masum
Age: 22
Department: CSE
```

---

## 4. Tab (\t)

`\t` ব্যবহার করে String-এর মধ্যে horizontal tab বা অতিরিক্ত spacing তৈরি করা যায়।

### Example

```python
print("Name\tAge")
print("Masum\t22")
print("Rahim\t21")
```

**Output:**

```text
Name    Age
Masum   22
Rahim   21
```

এখানে `\t` text-এর মধ্যে tab space তৈরি করেছে।

---

## 5. Backslash (\\)

একটি Backslash (`\`) সরাসরি String-এর মধ্যে দেখানোর জন্য `\\` ব্যবহার করতে হয়।

### Example

```python
print("Python\\Programming")
```

**Output:**

```text
Python\Programming
```

এখানে `\\` একটি Backslash হিসেবে প্রদর্শিত হয়েছে।

### Practical Example: File Path

```python
path = "C:\\Users\\Masum\\Documents"

print(path)
```

**Output:**

```text
C:\Users\Masum\Documents
```

---

## 6. Single Quote (\')

String-এর মধ্যে Single Quote (`'`) দেখানোর জন্য `\'` ব্যবহার করা যায়।

### Example

```python
print('It\'s Python')
```

**Output:**

```text
It's Python
```

এখানে `\'` Single Quote হিসেবে প্রদর্শিত হয়েছে।

---

## 7. Double Quote (\")

String-এর মধ্যে Double Quote (`"`) দেখানোর জন্য `\"` ব্যবহার করা যায়।

### Example

```python
print("He said, \"Hello Python!\"")
```

**Output:**

```text
He said, "Hello Python!"
```

এখানে `\"` Double Quote হিসেবে প্রদর্শিত হয়েছে।

**Note:** Single-quoted String-এর মধ্যে Double Quote এবং Double-quoted String-এর মধ্যে Single Quote সাধারণভাবেই ব্যবহার করা যায়।

উদাহরণ:

```python
print("It's Python")
print('He said "Hello"')
```

**Output:**

```text
It's Python
He said "Hello"
```

---

## 8. Carriage Return (\r)

`\r` হলো Carriage Return Escape Sequence।

এটি একই line-এর শুরুতে ফিরে যাওয়ার মতো কাজ করে। পরবর্তী text আগের text-এর কিছু অংশের জায়গায় লিখতে পারে।

### Example

```python
print("Hello\rPython")
```

**Output:**

```text
Python
```

এখানে `\r` cursor-কে line-এর শুরুতে নিয়ে যায়। এরপর `Python` আগের `Hello`-এর জায়গায় লেখা হয়।

**Note:** Output terminal বা environment অনুযায়ী কিছুটা ভিন্নভাবে দেখা যেতে পারে।

---

## 9. Backspace (\b)

`\b` ব্যবহার করে cursor এক position পেছনে নেওয়া হয়।

### Example

```python
print("Helloo\b")
```

**Output:**

```text
Hello
```

এখানে `\b` শেষের একটি `o`-এর জায়গায় cursor ফিরিয়ে নেয়। সাধারণ terminal-এ পরবর্তী character না থাকলে দৃশ্যমান ফলাফল environment অনুযায়ী ভিন্ন হতে পারে।

---

## 10. Form Feed (\f)

`\f` একটি Form Feed Escape Sequence।

এটি মূলত text formatting এবং page control-এর কাজে ব্যবহৃত হয়।

### Example

```python
print("Hello\fWorld")
```

**Note:** Form Feed-এর দৃশ্যমান output terminal বা environment অনুযায়ী পরিবর্তিত হতে পারে।

---

## 11. Vertical Tab (\v)

`\v` ব্যবহার করে Vertical Tab তৈরি করা হয়।

### Example

```python
print("Hello\vWorld")
```

এটি text-এর মধ্যে vertical spacing তৈরি করার জন্য ব্যবহৃত হয়।

**Note:** এর দৃশ্যমান output terminal বা environment অনুযায়ী ভিন্ন হতে পারে।

---

## 12. Alert (\a)

`\a` একটি Alert বা Bell Character তৈরি করে।

### Example

```python
print("\a")
```

এটি কিছু terminal-এ notification sound তৈরি করতে পারে।

**Note:** সব terminal বা system-এ sound শোনা যাবে এমন নিশ্চয়তা নেই।

---

## 13. Using Multiple Escape Sequences Together

একটি String-এর মধ্যে একাধিক Escape Sequence ব্যবহার করা যায়।

### Example

```python
student = "Name:\tMasum\nDepartment:\tCSE\nUniversity:\tNUB"

print(student)
```

**Output:**

```text
Name:   Masum
Department:    CSE
University:   NUB
```

এখানে:

- `\t` tab spacing তৈরি করেছে।
- `\n` নতুন line তৈরি করেছে।

---

## 14. Escape Sequences with Quotes

String-এর মধ্যে Quote ব্যবহার করার সময় Escape Sequence কাজে লাগে।

### Example 1

```python
message = "He said, \"Python is easy.\""

print(message)
```

**Output:**

```text
He said, "Python is easy."
```

### Example 2

```python
message = 'It\'s a beautiful day.'

print(message)
```

**Output:**

```text
It's a beautiful day.
```

---

## 15. Important Rules

1. Escape Sequence সাধারণত Backslash (`\`) দিয়ে শুরু হয়।
2. `\n` নতুন line তৈরি করে।
3. `\t` horizontal tab তৈরি করে।
4. `\\` একটি Backslash প্রদর্শন করে।
5. `\'` Single Quote প্রদর্শন করে।
6. `\"` Double Quote প্রদর্শন করে।
7. Escape Sequence String-এর special formatting এবং character display করতে সাহায্য করে।
8. Escape Sequence ব্যবহার করে একই String-এ একাধিক formatting করা যায়।
9. Escape Sequence-এর কিছু output terminal বা environment অনুযায়ী পরিবর্তিত হতে পারে।

---

## 16. Common Mistakes

### Mistake 1: Using Single Backslash for File Paths

```python
path = "C:\new\test"
print(path)
```

এখানে `\n` এবং `\t` Escape Sequence হিসেবে কাজ করতে পারে। ফলে File Path প্রত্যাশিতভাবে পাওয়া যাবে না।

**Correct Code:**

```python
path = "C:\\new\\test"

print(path)
```

**Output:**

```text
C:\new\test
```

### Mistake 2: Forgetting Backslash Before Quotes

```python
print("He said, "Hello"")
```

**Output:**

```text
SyntaxError
```

**কারণ:** Double Quote String-এর শুরু ও শেষ নির্দেশ করে। তাই ভেতরের Double Quote-কে Escape করতে হবে।

**Correct Code:**

```python
print("He said, \"Hello\"")
```

**Output:**

```text
He said, "Hello"
```

### Mistake 3: Confusing \n and \t

```python
print("Hello\nWorld")
print("Hello\tWorld")
```

**Output:**

```text
Hello
World
Hello   World
```

মনে রাখবে:

- `\n` = New Line
- `\t` = Tab Space

---

## 17. Practice Exercises

### Exercise 1: New Line

একটি String-এর মধ্যে `\n` ব্যবহার করে নিচের Output তৈরি করো।

**Expected Output:**

```text
My Name is Masum
I am learning Python
```

### Exercise 2: Tab

`\t` ব্যবহার করে নিচের Output তৈরি করো।

**Expected Output:**

```text
Name    Age
Masum   22
```

### Exercise 3: Backslash

একটি String-এর মধ্যে `\\` ব্যবহার করে নিচের Output তৈরি করো।

**Expected Output:**

```text
C:\Python\Projects
```

### Exercise 4: Single and Double Quotes

Escape Sequence ব্যবহার করে নিচের Output তৈরি করো।

**Expected Output:**

```text
It's Python.
He said, "Hello!"
```

### Exercise 5: Predict the Output

```python
print("Python\nProgramming")
print("Hello\tWorld")
print("I love \"Python\"")
print("C:\\Users\\Masum")
```

**Expected Output:**

```text
Python
Programming
Hello   World
I love "Python"
C:\Users\Masum
```

---

## 18. Chapter Summary

এই topic-এ আমরা Python-এর গুরুত্বপূর্ণ Escape Sequences সম্পর্কে শিখেছি।

| Escape Sequence | কাজ |
|---|---|
| `\n` | New Line |
| `\t` | Horizontal Tab |
| `\\` | Backslash |
| `\'` | Single Quote |
| `\"` | Double Quote |
| `\r` | Carriage Return |
| `\b` | Backspace |
| `\f` | Form Feed |
| `\v` | Vertical Tab |
| `\a` | Alert |

**সবচেয়ে গুরুত্বপূর্ণ Escape Sequence:**

- `\n`
- `\t`
- `\\`
- `\'`
- `\"`

---

## 19. Self-Assessment Checklist

- [ ] Escape Sequence কী বুঝতে পেরেছি।
- [ ] `\n` ব্যবহার করতে পারি।
- [ ] `\t` ব্যবহার করতে পারি।
- [ ] `\\` ব্যবহার করতে পারি।
- [ ] `\'` এবং `\"` ব্যবহার করতে পারি।
- [ ] File Path-এর মধ্যে Backslash ব্যবহার বুঝতে পেরেছি।
- [ ] একাধিক Escape Sequence একসঙ্গে ব্যবহার করতে পারি।
- [ ] Escape Sequence-এর output predict করতে পারি।

---

## 20. Next Topic

পরবর্তী topic:

**35. Raw Strings in Python**

এখানে আমরা Raw String কী, `r` prefix কীভাবে কাজ করে এবং File Path ও Regular Expression-এর ক্ষেত্রে Raw String কেন ব্যবহার করা হয়, তা শিখব।
