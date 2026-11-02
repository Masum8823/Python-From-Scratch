# 07. Newlines and Escape Sequences in Python

## 1. Introduction

Python-এ string-এর মধ্যে অনেক সময় নতুন লাইন তৈরি করা, শব্দের মাঝে অতিরিক্ত জায়গা দেওয়া, quotation mark দেখানো বা backslash print করার প্রয়োজন হয়।

এই কাজগুলো করার জন্য Python-এ **Escape Sequences** ব্যবহার করা হয়।

Escape sequence হলো backslash (`\`) দিয়ে শুরু হওয়া বিশেষ character combination, যা string-এর মধ্যে নির্দিষ্ট কাজ করে।

উদাহরণ:

```python
print("Hello\nWorld")
```

Output:

```text
Hello
World
```

এখানে `\n` একটি নতুন লাইন তৈরি করেছে।

## 2. What Is an Escape Sequence?

Escape sequence হলো backslash (`\`) এবং তার পরের একটি বা একাধিক character-এর সমন্বয়, যা string-এর মধ্যে বিশেষ অর্থ প্রকাশ করে।

সাধারণভাবে:

```python
"Text\character"
```

এখানে `\`-এর পরে থাকা character অনুযায়ী Python নির্দিষ্ট কাজ করে।

### Example

```python
print("Hello\nPython")
print("Hello\tPython")
```

Output:

```text
Hello
Python
Hello	Python
```

প্রথম লাইনে `\n` নতুন লাইন তৈরি করেছে। দ্বিতীয় লাইনে `\t` একটি horizontal tab যোগ করেছে।

**মনে রাখবে:** Escape sequence-এর মধ্যে backslash (`\`) ব্যবহার করা হয়, forward slash (`/`) নয়।

## 3. Newline Escape Sequence (`\n`)

`\n`-এর অর্থ newline। এটি string-এর পরবর্তী অংশকে নতুন লাইনে দেখায়।

### Example 1: Simple Newline

```python
print("Hello\nWorld")
```

Output:

```text
Hello
World
```

### Example 2: Multiple Newlines

```python
print("Python\nJava\nC++")
```

Output:

```text
Python
Java
C++
```

এখানে তিনটি language তিনটি আলাদা লাইনে দেখা যাচ্ছে।

### Example 3: Creating a Blank Line

```python
print("First Line\n\nThird Line")
```

Output:

```text
First Line

Third Line
```

দুটি `\n` পরপর ব্যবহারের ফলে মাঝখানে একটি blank line তৈরি হয়েছে।

### Example 4: Newline Inside a Sentence

```python
print("My name is Masum.\nI study CSE.")
```

Output:

```text
My name is Masum.
I study CSE.
```

একটি string-এর মধ্যেই `\n` দিয়ে একাধিক লাইন তৈরি করা যায়।

## 4. Tab Escape Sequence (`\t`)

`\t` একটি horizontal tab তৈরি করে। এটি সাধারণত text-এর মধ্যে ফাঁকা জায়গা রেখে তথ্য সাজাতে সাহায্য করে।

### Example 1: Simple Tab

```python
print("Name\tDepartment")
```

Output:

```text
Name	Department
```

`Name` এবং `Department`-এর মাঝে একটি tab character রয়েছে।

### Example 2: Tab Between Values

```python
print("Masum\tCSE\tNUB")
```

Output:

```text
Masum	CSE	NUB
```

এখানে তিনটি value tab দিয়ে আলাদা করা হয়েছে।

### Example 3: Simple Table

```python
print("ID\tName\tMarks")
print("01\tRahim\t85")
print("02\tKarim\t90")
```

Output:

```text
ID	Name	Marks
01	Rahim	85
02	Karim	90
```

এই পদ্ধতি দিয়ে সাধারণ text table তৈরি করা যায়।

**গুরুত্বপূর্ণ:** Tab-এর দৃশ্যমান প্রস্থ editor বা terminal অনুযায়ী আলাদা হতে পারে। তাই `\t` সব পরিস্থিতিতে নিখুঁত column alignment নিশ্চিত করে না।

## 5. Backslash Escape Sequence (`\\`)

Python string-এর মধ্যে একটি literal backslash (`\`) দেখাতে চাইলে `\\` ব্যবহার করতে হয়।

কারণ একটি single backslash escape sequence শুরু করতে পারে।

### Example 1

```python
print("C:\\Users\\Masum")
```

Output:

```text
C:\Users\Masum
```

এখানে প্রতিটি `\\` output-এ একটি backslash হিসেবে দেখা যাচ্ছে।

### Example 2: File Path

```python
print("C:\\Python\\Projects\\main.py")
```

Output:

```text
C:\Python\Projects\main.py
```

### Why Do We Need `\\`?

সাধারণ string-এ backslash বিশেষ অর্থ বহন করতে পারে। তাই literal backslash দেখাতে দুটি backslash ব্যবহার করা হয়।

Windows file path-এর ক্ষেত্রে এটি বিশেষভাবে কাজে লাগে।

আরেকটি বিকল্প হলো raw string:

```python
print(r"C:\Python\Projects\main.py")
```

Output:

```text
C:\Python\Projects\main.py
```

Raw string সম্পর্কে পরবর্তী সময়ে বিস্তারিত আলোচনা করা হবে।

## 6. Single Quote Escape Sequence (`\'`)

String-এর মধ্যে single quotation mark (`'`) দেখাতে `\'` ব্যবহার করা যায়।

### Example

```python
print('It\'s Python')
```

Output:

```text
It's Python
```

এখানে `\'`-এর কারণে single quote-টিকে string-এর শেষ হিসেবে ধরা হয়নি।

### Alternative Method

String-এর বাইরে double quotation mark ব্যবহার করলেও একই কাজ করা যায়।

```python
print("It's Python")
```

Output:

```text
It's Python
```

দুটি পদ্ধতিই সঠিক। পরিস্থিতি অনুযায়ী সহজ পদ্ধতিটি বেছে নেওয়া যায়।

## 7. Double Quote Escape Sequence (`\"`)

String-এর মধ্যে double quotation mark (`"`) দেখাতে `\"` ব্যবহার করা যায়।

### Example

```python
print("He said, \"Hello!\"")
```

Output:

```text
He said, "Hello!"
```

এখানে `\"` দিয়ে quotation mark-গুলোকে string-এর অংশ হিসেবে দেখানো হয়েছে।

### Alternative Method

বাইরের string-এ single quotation mark ব্যবহার করা যায়।

```python
print('He said, "Hello!"')
```

Output:

```text
He said, "Hello!"
```

এখানে escape sequence প্রয়োজন হয়নি, কারণ বাইরের string single quote দিয়ে তৈরি।

## 8. Carriage Return (`\r`)

`\r` হলো carriage return character। এটি text cursor-কে বর্তমান লাইনের শুরুতে ফিরিয়ে নেয়। এরপর নতুন text লেখা হলে আগের text-এর কিছু অংশ overwrite হতে পারে।

### Example

```python
print("Hello\rPython")
```

কিছু terminal-এ সম্ভাব্য output:

```text
Python
```

কারণ `\r` cursor-কে লাইনের শুরুতে ফিরিয়ে নেয় এবং `Python` আগের text-এর ওপর লেখা হয়।

**মনে রাখবে:** `\r`-এর আচরণ output environment-এর ওপর নির্ভর করতে পারে। তাই সাধারণ নতুন লাইন তৈরির জন্য `\n` ব্যবহার করাই সহজ।

## 9. Backspace (`\b`)

`\b` হলো backspace character। এটি সাধারণত text cursor-কে এক অবস্থান পেছনে নেওয়ার নির্দেশ দেয়।

### Example

```python
print("ABC\bD")
```

কিছু terminal-এ output হতে পারে:

```text
ABD
```

এখানে cursor `C`-এর অবস্থানে ফিরে গিয়ে `D` লিখলে `C`-এর জায়গায় `D` দেখা যেতে পারে।

তবে সব terminal বা output viewer-এ একই ফল নাও দেখা যেতে পারে। তাই `\b`-কে সাধারণ text editing-এর নির্ভরযোগ্য পদ্ধতি হিসেবে ব্যবহার করা উচিত নয়।

## 10. Form Feed (`\f`)

`\f` হলো form feed character। ঐতিহাসিকভাবে এটি printer-এ নতুন page শুরু করার কাজে ব্যবহৃত হতো।

### Example

```python
print("Page 1\fPage 2")
```

এখানে `\f` string-এর মধ্যে form feed character যোগ করে।

এর দৃশ্যমান ফল terminal, editor বা output viewer অনুযায়ী ভিন্ন হতে পারে। আধুনিক সাধারণ Python programming-এ এটি খুব বেশি ব্যবহার করা হয় না।

## 11. Null Character (`\0`)

`\0` একটি null character বোঝায়।

### Example

```python
text = "A\0B"

print(len(text))
print(repr(text))
```

Output:

```text
3
'A\x00B'
```

এখানে:

- `\0` string-এর মধ্যে একটি null character যোগ করেছে।
- `len(text)`-এর ফল `3`, কারণ string-এ তিনটি character রয়েছে।
- `repr()` null character-টিকে `\x00` আকারে দেখিয়েছে।

**গুরুত্বপূর্ণ:** Python string-এ null character থাকতে পারে। এটি string-এর শেষ নির্দেশ করে না।

## 12. Escape Sequences Summary Table

| Escape sequence | কাজ | উদাহরণ |
|---|---|---|
| `\n` | নতুন লাইন | `"A\nB"` |
| `\t` | Horizontal tab | `"A\tB"` |
| `\\` | Literal backslash | `"C:\\Python"` |
| `\'` | Single quote | `'It\'s'` |
| `\"` | Double quote | `"Say \"Hi\""` |
| `\r` | Carriage return | `"A\rB"` |
| `\b` | Backspace | `"ABC\bD"` |
| `\f` | Form feed | `"A\fB"` |
| `\0` | Null character | `"A\0B"` |

এই টেবিলের মধ্যে `\n`, `\t`, `\\`, `\'` এবং `\"` সবচেয়ে বেশি কাজে লাগবে।

## 13. Other Important Escape Sequences

Python-এ আরও কিছু escape sequence রয়েছে, যেগুলো বিশেষ ধরনের character প্রকাশ করে।

### 13.1 Unicode Escape: `\u`

`\u` ব্যবহার করে চারটি hexadecimal digit-এর মাধ্যমে Unicode character লেখা যায়।

```python
print("\u2764")
```

Output:

```text
❤
```

এখানে `\u2764` একটি heart symbol প্রকাশ করেছে।

### 13.2 Unicode Escape: `\U`

`\U` ব্যবহার করে আটটি hexadecimal digit দিয়ে Unicode code point প্রকাশ করা যায়।

```python
print("\U0001F600")
```

Output:

```text
😀
```

এখানে Unicode code point `U+1F600` একটি grinning face emoji প্রকাশ করেছে।

### 13.3 Hexadecimal Escape: `\x`

`\x`-এর পরে দুটি hexadecimal digit ব্যবহার করা হয়।

```python
print("\x41")
```

Output:

```text
A
```

এখানে hexadecimal value `41` হলো character `A`-এর code point।

## 14. Escape Sequences vs Normal Characters

কিছু character string-এর মধ্যে সাধারণভাবে লেখা যায়। আবার কিছু ক্ষেত্রে escape sequence ব্যবহার করতে হয়।

### Example 1: Normal Text

```python
print("Python is easy")
```

Output:

```text
Python is easy
```

এখানে কোনো escape sequence নেই।

### Example 2: Newline

```python
print("Python\nis easy")
```

Output:

```text
Python
is easy
```

এখানে `\n` নতুন লাইন তৈরি করেছে।

### Example 3: Literal Backslash

```python
print("A\\B")
```

Output:

```text
A\B
```

এখানে `\\` একটি backslash হিসেবে print হয়েছে।

**মূল ধারণা:** Escape sequence শুধু দুইটি character-এর সাধারণ লেখা নয়; Python string-এর মধ্যে এটি বিশেষ অর্থ প্রকাশ করতে পারে।

## 15. What Happens with Invalid Escape Sequences?

Python string-এ ভুল বা অপরিচিত escape sequence ব্যবহার করলে সতর্কতা বা অন্য সমস্যা হতে পারে। কিছু ক্ষেত্রে এটি সাধারণ character হিসেবেও থেকে যেতে পারে, কিন্তু তার ওপর নির্ভর করা উচিত নয়।

### Example

```python
text = "Hello\q"
print(text)
```

আধুনিক Python version-এ এ ধরনের অপরিচিত escape sequence-এর জন্য `SyntaxWarning` দেখা যেতে পারে। সাধারণত `\q` অপরিবর্তিতভাবে string-এ থাকে।

Output সাধারণত:

```text
Hello\q
```

এ ধরনের warning এড়াতে সঠিক escape sequence ব্যবহার করো। যদি backslash-সহ text হুবহু রাখতে চাও, raw string ব্যবহার করা যেতে পারে।

## 16. Raw Strings: `r"..."`

Raw string তৈরি করতে string-এর আগে `r` বা `R` লেখা হয়। এতে অধিকাংশ escape sequence সাধারণ character হিসেবে রাখা হয়।

### Example 1: Windows Path

```python
path = r"C:\Users\Masum\Documents"
print(path)
```

Output:

```text
C:\Users\Masum\Documents
```

Raw string ব্যবহার করায় প্রতিটি backslash-এর জন্য আলাদাভাবে `\\` লিখতে হয়নি।

### Example 2: Newline Sequence as Literal Text

```python
text = r"Hello\nWorld"
print(text)
```

Output:

```text
Hello\nWorld
```

এখানে `\n` নতুন লাইন তৈরি করেনি; এটি backslash এবং `n` হিসেবেই দেখা গেছে।

**সতর্কতা:** Raw string-এর শেষে বিজোড় সংখ্যক backslash রাখা যায় না। যেমন `r"C:\Folder\"` বৈধ raw string literal নয়। Raw string-এ `r` থাকার অর্থ এই নয় যে সব ধরনের escaping পুরোপুরি বন্ধ হয়ে যায়; quotation mark ও backslash-এর কিছু নিয়ম এখনও প্রযোজ্য।

## 17. Combining Escape Sequences

একটি string-এ একাধিক escape sequence ব্যবহার করা যায়।

### Example 1: Newline and Tab

```python
print("Name:\tMasum\nDepartment:\tCSE")
```

Output:

```text
Name:	Masum
Department:	CSE
```

এখানে:

- `\t` tab যোগ করেছে।
- `\n` নতুন লাইন তৈরি করেছে।

### Example 2: Quotes and Newline

```python
print("He said, \"Hello!\"\nThen he left.")
```

Output:

```text
He said, "Hello!"
Then he left.
```

### Example 3: A Simple Student Profile

```python
print("Student Information")
print("Name:\tMasum")
print("Department:\tCSE")
print("University:\tNUB")
```

Output:

```text
Student Information
Name:	Masum
Department:	CSE
University:	NUB
```

এভাবে escape sequence ব্যবহার করে output আরও পরিষ্কারভাবে সাজানো যায়।

## 18. Difference Between `\n` and `end="\n"`

দুটি পদ্ধতিতেই নতুন লাইন তৈরি করা যায়, কিন্তু কাজ করার জায়গা আলাদা।

### Using `\n` Inside a String

```python
print("Hello\nWorld")
```

Output:

```text
Hello
World
```

এখানে একটি string-এর ভেতরে newline character রয়েছে।

### Using `end="\n"`

```python
print("Hello", end="\n")
print("World")
```

Output:

```text
Hello
World
```

এখানে প্রথম `print()`-এর output-এর শেষে newline যোগ করা হয়েছে।

### Main Difference

- `\n` string-এর যেকোনো অবস্থানে নতুন লাইন তৈরি করতে পারে।
- `end="\n"` `print()`-এর output-এর শেষে newline নির্ধারণ করে।
- `print()`-এর default `end` ইতিমধ্যেই `'\n'`।

তাই সাধারণ ক্ষেত্রে নিচের code-টিও একই output দেবে:

```python
print("Hello")
print("World")
```

## 19. Common Mistakes

### Mistake 1: Forward Slash ব্যবহার করা

ভুল ধারণা:

```python
print("Hello/nWorld")
```

Output:

```text
Hello/nWorld
```

এখানে `/n` সাধারণ text, newline নয়।

সঠিক code:

```python
print("Hello\nWorld")
```

Output:

```text
Hello
World
```

### Mistake 2: Windows Path-এ Backslash ভুলভাবে লেখা

সমস্যাজনক উদাহরণ:

```python
path = "C:\new\test"
print(path)
```

এখানে `\n` এবং `\t` escape sequence হিসেবে কাজ করতে পারে। ফলে path প্রত্যাশামতো দেখা যাবে না।

সঠিক পদ্ধতি:

```python
path = "C:\\new\\test"
print(path)
```

অথবা:

```python
path = r"C:\new\test"
print(path)
```

### Mistake 3: String-এর মধ্যে Quote ব্যবহার করতে গিয়ে সমস্যা তৈরি করা

সমস্যাজনক code:

```python
print("He said, "Hello"")
```

এটি `SyntaxError` তৈরি করবে।

সঠিক পদ্ধতি:

```python
print("He said, \"Hello\"")
```

Output:

```text
He said, "Hello"
```

### Mistake 4: `\n`-কে সাধারণ Text হিসেবে দেখাতে চাওয়া

```python
print("Hello\nWorld")
```

এখানে `\n` newline হিসেবে কাজ করবে।

যদি আক্ষরিকভাবে `\n` দেখাতে চাও:

```python
print(r"Hello\nWorld")
```

Output:

```text
Hello\nWorld
```

## 20. Practical Programs

### Program 1: Print a Multiline Address

```python
print("Masum")
print("CSE Department")
print("Northern University Bangladesh")
```

Output:

```text
Masum
CSE Department
Northern University Bangladesh
```

### Program 2: Print Using Newline Escape Sequence

```python
print("Masum\nCSE Department\nNUB")
```

Output:

```text
Masum
CSE Department
NUB
```

দুটি পদ্ধতির output একই, তবে দ্বিতীয় পদ্ধতিতে একটি string-এর মধ্যে একাধিক লাইন রয়েছে।

### Program 3: Display a Simple Table

```python
print("ID\tName\tMarks")
print("01\tRahim\t85")
print("02\tKarim\t90")
print("03\tNadia\t95")
```

Output:

```text
ID	Name	Marks
01	Rahim	85
02	Karim	90
03	Nadia	95
```

### Program 4: Display Quotation Marks

```python
message = "Python"
print("I am learning \"Python\".")
```

Output:

```text
I am learning "Python".
```

### Program 5: Display a Windows Path

```python
path = r"C:\Python\Projects\main.py"
print(path)
```

Output:

```text
C:\Python\Projects\main.py
```

## 21. Practice Exercises

নিজে code লেখার চেষ্টা করো। প্রথমে output অনুমান করবে, তারপর code চালিয়ে যাচাই করবে।

### Exercise 1

নিচের output তৈরি করো:

```text
Hello
World
```

একটি `print()` statement ব্যবহার করবে।

### Exercise 2

নিচের output তৈরি করো:

```text
Name: Masum
Department: CSE
```

`\n` এবং `\t` ব্যবহার করবে।

### Exercise 3

Output কী হবে?

```python
print("A\nB\nC")
```

### Exercise 4

Output কী হবে?

```python
print("Python\tJava")
```

### Exercise 5

নিচের output তৈরি করো:

```text
He said, "Python is easy."
```

### Exercise 6

Output কী হবে?

```python
print("C:\\Python\\main.py")
```

### Exercise 7

নিচের output তৈরি করো:

```text
Hello\nWorld
```

এখানে নতুন লাইন তৈরি করা যাবে না।

### Exercise 8

নিচের code-এর সমস্যাটি চিহ্নিত করে ঠিক করো:

```python
path = "C:\new\test"
print(path)
```

লক্ষ্য: `C:\new\test`-কে একটি path হিসেবে দেখানো।

### Exercise 9

Output কী হবে?

```python
print("One\n\nThree")
```

### Exercise 10

নিচের output তৈরি করো:

```text
Student Information
Name: Masum
Department: CSE
University: NUB
```

একটি `print()` statement ব্যবহার করে `\n` দিয়ে লাইনগুলো আলাদা করবে।

## 22. Practice Answer Key

### Answer 1

```python
print("Hello\nWorld")
```

### Answer 2

```python
print("Name:\tMasum\nDepartment:\tCSE")
```

### Answer 3

```text
A
B
C
```

প্রতিটি `\n` নতুন লাইন তৈরি করেছে।

### Answer 4

```text
Python	Java
```

`Python` এবং `Java`-এর মাঝে একটি horizontal tab রয়েছে।

### Answer 5

```python
print("He said, \"Python is easy.\"")
```

### Answer 6

```text
C:\Python\main.py
```

প্রতিটি `\\` একটি literal backslash হিসেবে দেখা গেছে।

### Answer 7

```python
print(r"Hello\nWorld")
```

Output:

```text
Hello\nWorld
```

### Answer 8

সমাধান ১:

```python
path = "C:\\new\\test"
print(path)
```

সমাধান ২:

```python
path = r"C:\new\test"
print(path)
```

দুটি পদ্ধতিতেই প্রত্যাশিত path দেখা যাবে।

### Answer 9

```text
One

Three
```

দুটি newline-এর কারণে একটি blank line তৈরি হয়েছে।

### Answer 10

```python
print("Student Information\nName: Masum\nDepartment: CSE\nUniversity: NUB")
```

## 23. Chapter Summary

এই topic-এ আমরা শিখেছি:

1. Escape sequence হলো backslash দিয়ে শুরু হওয়া বিশেষ character combination।
2. `\n` নতুন লাইন তৈরি করে।
3. `\t` horizontal tab তৈরি করে।
4. `\\` একটি literal backslash দেখায়।
5. `\'` এবং `\"` quotation mark দেখাতে সাহায্য করে।
6. `\r`, `\b` এবং `\f`-এর দৃশ্যমান আচরণ environment অনুযায়ী ভিন্ন হতে পারে।
7. `\0` string-এর মধ্যে null character যোগ করে।
8. `\u`, `\U` এবং `\x` দিয়ে নির্দিষ্ট Unicode বা hexadecimal character প্রকাশ করা যায়।
9. Raw string (`r"..."`) backslash-যুক্ত path ও literal text লেখার ক্ষেত্রে সুবিধাজনক।
10. `\n` string-এর ভেতরে কাজ করে, আর `end="\n"` `print()`-এর output-এর শেষে newline নির্ধারণ করে।

## 24. Self-Assessment Checklist

- [ ] Escape sequence কী, তা বুঝি।
- [ ] `\n` দিয়ে নতুন লাইন তৈরি করতে পারি।
- [ ] `\t` দিয়ে tab ব্যবহার করতে পারি।
- [ ] `\\` দিয়ে literal backslash দেখাতে পারি।
- [ ] Single ও double quote-এর escape sequence ব্যবহার করতে পারি।
- [ ] Windows path-এর জন্য raw string বা escaped backslash ব্যবহার করতে পারি।
- [ ] `\n` এবং `end="\n"`-এর পার্থক্য বুঝি।
- [ ] Output দেখে escape sequence শনাক্ত করতে পারি।
- [ ] Practice exercises নিজে সমাধান করতে পারি।

**Next Topic:** `08_Formatting_Output_with_print.md` — এখানে `print()` ব্যবহার করে output সুন্দরভাবে সাজানো, value-এর মাঝে space রাখা এবং তথ্য readable format-এ দেখানো শিখব।