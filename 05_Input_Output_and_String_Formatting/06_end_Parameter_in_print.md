# 06. `end` Parameter in `print()`

## 1. Introduction

Python-এর `print()` function-এ `end` parameter ব্যবহার করে output-এর শেষে কী থাকবে তা নির্ধারণ করা যায়।

সাধারণভাবে প্রতিটি `print()` statement-এর output নতুন লাইনে দেখা যায়। এর কারণ হলো `end`-এর default value হলো newline character (`'\n'`)।

### Example

```python
print("Hello")
print("Python")
```

Output:

```text
Hello
Python
```

এখানে `Hello` এবং `Python` আলাদা লাইনে এসেছে।

কিন্তু আমরা চাইলে `end` ব্যবহার করে একই লাইনে output দেখাতে পারি।

```python
print("Hello", end=" ")
print("Python")
```

Output:

```text
Hello Python
```

এখানে প্রথম `print()`-এর শেষে newline-এর পরিবর্তে একটি space দেওয়া হয়েছে।

## 2. Syntax of the `end` Parameter

`print()` function-এর সাধারণ syntax:

```python
print(*objects, sep=' ', end='\n', file=None, flush=False)
```

এখানে:

- `objects` হলো যেসব value print করতে চাই।
- `sep` নির্ধারণ করে object-গুলোর মাঝখানে কী থাকবে।
- `end` নির্ধারণ করে output-এর শেষে কী থাকবে।

### Basic Syntax

```python
print("Hello", end=" ")
```

এখানে `end=" "` দেওয়ার অর্থ হলো output-এর শেষে একটি space থাকবে, newline নয়।

**মনে রাখবে:** `end`-এর default value হলো `'\n'`।

## 3. Understanding the Default Value of `end`

`end` parameter না দিলে Python স্বয়ংক্রিয়ভাবে newline যোগ করে।

### Example 1

```python
print("Python")
print("Programming")
print("Language")
```

Output:

```text
Python
Programming
Language
```

প্রতিটি `print()`-এর শেষে newline যোগ হয়েছে।

### Example 2: Explicitly Using `end='\n'`

```python
print("Python", end="\n")
print("Programming", end="\n")
print("Language")
```

Output:

```text
Python
Programming
Language
```

এখানে প্রথম দুটি `print()`-এ newline স্পষ্টভাবে দেওয়া হয়েছে। শেষের `print()`-এ default newline ব্যবহৃত হয়েছে।

এই দুটি code-এর output একই।

## 4. Using `end=""` to Print Without a Newline

`end=""` দিলে output-এর শেষে কোনো character যোগ হয় না।

### Example

```python
print("Hello", end="")
print("Python")
```

Output:

```text
HelloPython
```

এখানে প্রথম `print()`-এর শেষে newline বা space কোনোটিই যোগ হয়নি। তাই পরের output ঠিক আগের output-এর পরেই এসেছে।

### Another Example

```python
print("Py", end="")
print("thon")
```

Output:

```text
Python
```

এখানে দুটি `print()` statement-এর output একসঙ্গে যুক্ত হয়েছে।

**সতর্কতা:** `end=""` ব্যবহার করলে শব্দের মাঝে space স্বয়ংক্রিয়ভাবে যোগ হয় না।

## 5. Using `end=" "` to Add a Space

একাধিক `print()`-এর output একই লাইনে রেখে শব্দের মাঝে space দিতে চাইলে `end=" "` ব্যবহার করা যায়।

### Example 1

```python
print("Hello", end=" ")
print("World")
```

Output:

```text
Hello World
```

### Example 2

```python
print("I", end=" ")
print("am", end=" ")
print("learning", end=" ")
print("Python")
```

Output:

```text
I am learning Python
```

প্রতিটি `print()`-এর শেষে একটি space দেওয়া হয়েছে। শেষের `print()` স্বাভাবিকভাবে newline যোগ করেছে।

### Example 3: Numbers

```python
print(10, end=" ")
print(20, end=" ")
print(30)
```

Output:

```text
10 20 30
```

এভাবে একাধিক value একই লাইনে দেখানো যায়।

## 6. Using a Custom String with `end`

`end`-এ শুধু space বা empty string নয়, যেকোনো string দেওয়া যায়।

### Example 1: Hyphen

```python
print("A", end="-")
print("B", end="-")
print("C")
```

Output:

```text
A-B-C
```

### Example 2: Vertical Bar

```python
print("Python", end=" | ")
print("Java", end=" | ")
print("C++")
```

Output:

```text
Python | Java | C++
```

### Example 3: Arrow

```python
print("Start", end=" -> ")
print("Process", end=" -> ")
print("End")
```

Output:

```text
Start -> Process -> End
```

এখানে প্রতিটি `print()`-এর output-এর শেষে দেওয়া string পরের output-এর আগে দেখা যাচ্ছে।

### Example 4: Custom Message

```python
print("Loading", end="...")
print("Done")
```

Output:

```text
Loading...Done
```

এখানে প্রথম `print()`-এর শেষে তিনটি dot যোগ হয়েছে।

## 7. Using `end` with Multiple Values

একই `print()`-এ একাধিক object থাকলেও `end` ব্যবহার করা যায়।

### Example

```python
print("Python", "Java", "C++", end="!")
```

Output:

```text
Python Java C++!
```

এখানে:

- `sep` দেওয়া হয়নি, তাই object-গুলোর মাঝে default space রয়েছে।
- `end="!"` দেওয়ায় output-এর শেষে `!` এসেছে।
- এই statement-এর শেষে newline যোগ হয়নি।

### Combining `sep` and `end`

```python
print("Python", "Java", "C++", sep="-", end="!")
```

Output:

```text
Python-Java-C++!
```

এখানে `sep` object-গুলোর মাঝে এবং `end` সম্পূর্ণ output-এর শেষে কাজ করেছে।

## 8. Difference Between `sep` and `end`

এই দুটি parameter-এর কাজ আলাদা।

| বিষয় | `sep` | `end` |
|---|---|---|
| পূর্ণরূপ | Separator | End character/string |
| কাজ | Object-গুলোর মাঝে বসে | Output-এর শেষে বসে |
| Default value | একটি space (`' '`) | Newline (`'\n'`) |
| Example | `sep="-"` | `end="!"` |

### Example

```python
print("A", "B", sep="-", end="!")
```

Output:

```text
A-B!
```

এখানে `-` হলো object-গুলোর মাঝের separator, আর `!` হলো output-এর শেষের string।

**সহজভাবে মনে রাখো:**

- `sep` = মাঝখানে কী থাকবে।
- `end` = শেষে কী থাকবে।

## 9. How `end` Affects the Next `print()`

একটি `print()` statement-এর `end` নির্ধারণ করে পরের output কোথা থেকে শুরু হবে।

### Example 1: Default Behavior

```python
print("First")
print("Second")
```

Output:

```text
First
Second
```

### Example 2: Space at the End

```python
print("First", end=" ")
print("Second")
```

Output:

```text
First Second
```

### Example 3: No Separator at the End

```python
print("First", end="")
print("Second")
```

Output:

```text
FirstSecond
```

### Example 4: Newline After the First Output

```python
print("First", end="\n")
print("Second")
```

Output:

```text
First
Second
```

এখানে `end="\n"` ব্যবহার করায় default behavior-এর মতোই output এসেছে।

## 10. Using `end="\n\n"` for a Blank Line

একটি newline-এর পরিবর্তে দুটি newline দিলে output-এর মাঝে একটি blank line তৈরি হয়।

### Example

```python
print("Chapter 1", end="\n\n")
print("Chapter 2")
```

Output:

```text
Chapter 1

Chapter 2
```

এখানে প্রথম output-এর পর দুটি newline character রয়েছে। ফলে `Chapter 2`-এর আগে একটি খালি line দেখা যায়।

একই কাজ সাধারণভাবেও করা যায়:

```python
print("Chapter 1")
print()
print("Chapter 2")
```

Output:

```text
Chapter 1

Chapter 2
```

দুটি পদ্ধতিই কাজে লাগতে পারে, তবে code-এর readability অনুযায়ী পদ্ধতি বেছে নেওয়া উচিত।

## 11. Using `end` in Loops

Loop-এর মাধ্যমে একাধিক value print করার সময় `end` খুব কাজে লাগে।

### Example 1: Printing Numbers on One Line

```python
for i in range(1, 6):
    print(i, end=" ")
```

Output:

```text
1 2 3 4 5
```

এখানে loop পাঁচবার চলেছে। প্রতিবার `print()`-এর শেষে একটি space যোগ হয়েছে, তাই সব সংখ্যা একই লাইনে এসেছে।

### Example 2: Printing Stars

```python
for i in range(1, 6):
    print("*", end="")
```

Output:

```text
*****
```

প্রতিবার `*` print হয়েছে, কিন্তু শেষে newline যোগ হয়নি।

### Example 3: Printing a Number Sequence

```python
for i in range(2, 11, 2):
    print(i, end=", ")
```

Output:

```text
2, 4, 6, 8, 10, 
```

খেয়াল করো, শেষের `10`-এর পরেও comma ও space রয়েছে। কারণ প্রতিবারই `end=", "` যোগ করা হয়েছে।

শেষে অতিরিক্ত comma এড়াতে পরবর্তী সময়ে string formatting, `join()` অথবা অন্য উপযুক্ত পদ্ধতি ব্যবহার করা যায়।

## 12. Using `end` for Simple Patterns

`end` ব্যবহার করে একই লাইনে pattern তৈরি করা যায়।

### Example 1: Horizontal Stars

```python
print("*", end="")
print("*", end="")
print("*", end="")
print("*")
```

Output:

```text
****
```

### Example 2: Horizontal Number Pattern

```python
print(1, end=" ")
print(2, end=" ")
print(3, end=" ")
print(4)
```

Output:

```text
1 2 3 4
```

### Example 3: Combining Multiple Lines

```python
print("A", end=" ")
print("B", end="\n")
print("C", end=" ")
print("D")
```

Output:

```text
A B
C D
```

এখানে `end="\n"` দ্বিতীয় output-এর পরে নতুন line শুরু করেছে।

## 13. `end` Does Not Change Variable Values

`end` শুধু output-এর format পরিবর্তন করে। এটি variable-এর value পরিবর্তন করে না।

### Example

```python
name = "Masum"

print(name, end="!")
print(name)
```

Output:

```text
Masum!Masum
```

এখানে `name`-এর value এখনও `"Masum"`। `!` শুধু প্রথম output-এর শেষে যোগ হয়েছে।

## 14. Important Behavior: `end` Does Not Add a Space Automatically

`end=""` দিলে Python নিজে থেকে space যোগ করে না।

### Example

```python
print("Hello", end="")
print("World")
```

Output:

```text
HelloWorld
```

যদি space প্রয়োজন হয়:

```python
print("Hello", end=" ")
print("World")
```

Output:

```text
Hello World
```

একইভাবে `end="-"` দিলে hyphen যোগ হবে:

```python
print("Hello", end="-")
print("World")
```

Output:

```text
Hello-World
```

Output-এর শেষে ঠিক কী থাকবে, তা `end`-এর string-এর ওপর নির্ভর করে।

## 15. Common Beginner Mistakes

### Mistake 1: `end` না দিলে output একই লাইনে থাকবে মনে করা

```python
print("A")
print("B")
```

Output:

```text
A
B
```

সঠিকভাবে একই লাইনে রাখতে:

```python
print("A", end=" ")
print("B")
```

Output:

```text
A B
```

### Mistake 2: `end=""` ব্যবহার করে space আশা করা

```python
print("Hello", end="")
print("Python")
```

Output:

```text
HelloPython
```

Space দরকার হলে:

```python
print("Hello", end=" ")
print("Python")
```

### Mistake 3: `sep` এবং `end` গুলিয়ে ফেলা

```python
print("A", "B", sep="-", end="!")
```

Output:

```text
A-B!
```

এখানে `-` মাঝখানে এবং `!` শেষে।

### Mistake 4: প্রতিটি loop iteration-এ separator যোগ করে ফেলা

```python
for i in range(1, 4):
    print(i, end=", ")
```

Output:

```text
1, 2, 3, 
```

এখানে শেষে অতিরিক্ত comma ও space রয়েছে। এটি `end` ব্যবহারের স্বাভাবিক ফল, syntax error নয়।

### Mistake 5: `end`-কে শুধু একটি character-এর জন্য ব্যবহার করা যায় মনে করা

```python
print("Hello", end=" ---> ")
print("World")
```

Output:

```text
Hello ---> World
```

`end`-এ একাধিক character-এর string দেওয়া যায়।

## 16. Practical Programs

### Program 1: Printing a Student Profile

```python
print("Name:", end=" ")
print("Masum")

print("Department:", end=" ")
print("CSE")

print("University:", end=" ")
print("NUB")
```

Output:

```text
Name: Masum
Department: CSE
University: NUB
```

এখানে label এবং value আলাদা `print()` statement দিয়ে একই লাইনে দেখানো হয়েছে।

### Program 2: Printing a Sequence

```python
for number in range(1, 11):
    print(number, end=" ")
```

Output:

```text
1 2 3 4 5 6 7 8 9 10 
```

### Program 3: Simple Progress Message

```python
print("Step 1", end=" -> ")
print("Step 2", end=" -> ")
print("Completed")
```

Output:

```text
Step 1 -> Step 2 -> Completed
```

### Program 4: Printing a Table Row

```python
print("ID", "Name", "Marks", sep=" | ")
print("01", "Rahim", 85, sep=" | ")
print("02", "Karim", 90, sep=" | ")
```

Output:

```text
ID | Name | Marks
01 | Rahim | 85
02 | Karim | 90
```

এখানে `sep` column-এর মাঝে separator দিয়েছে। প্রতিটি `print()`-এর default `end` পরের row-কে নতুন লাইনে রেখেছে।

## 17. Practice Exercises

প্রথমে output অনুমান করো, তারপর code চালিয়ে যাচাই করো।

### Exercise 1

Output কী হবে?

```python
print("Hello", end=" ")
print("World")
```

### Exercise 2

Output কী হবে?

```python
print("Python", end="")
print("Programming")
```

### Exercise 3

Output কী হবে?

```python
print("A", end="-")
print("B", end="-")
print("C")
```

### Exercise 4

Output কী হবে?

```python
print("One", "Two", sep=":", end="!")
print("Three")
```

### Exercise 5

দুটি `print()` statement ব্যবহার করে নিচের output তৈরি করো:

```text
Python is fun
```

### Exercise 6

Loop ব্যবহার করে `1` থেকে `5` পর্যন্ত সংখ্যা একই লাইনে দেখাও। সংখ্যাগুলোর মাঝে space থাকবে।

### Exercise 7

Output কী হবে?

```python
print("Start", end="\n\n")
print("End")
```

### Exercise 8

নিচের code-এর output-এ শেষে comma ও space কেন থাকবে?

```python
for i in range(1, 4):
    print(i, end=", ")
```

### Exercise 9

নিচের output তৈরি করো:

```text
Input -> Process -> Output
```

একাধিক `print()` statement ব্যবহার করে `end` প্রয়োগ করবে।

### Exercise 10

Output কী হবে?

```python
name = "Masum"
print(name, end="!")
print(name)
```

## 18. Practice Answer Key

### Answer 1

```text
Hello World
```

প্রথম output-এর শেষে space রয়েছে।

### Answer 2

```text
PythonProgramming
```

প্রথম `print()`-এর শেষে কোনো character যোগ হয়নি।

### Answer 3

```text
A-B-C
```

প্রথম দুটি statement-এর শেষে hyphen রয়েছে।

### Answer 4

```text
One:Two!Three
```

প্রথম statement-এ `sep=":"` object-গুলোর মাঝে colon বসিয়েছে এবং `end="!"` output-এর শেষে exclamation mark বসিয়েছে।

### Answer 5

```python
print("Python", end=" ")
print("is fun")
```

### Answer 6

```python
for i in range(1, 6):
    print(i, end=" ")
```

### Answer 7

```text
Start

End
```

দুটি newline-এর কারণে একটি blank line তৈরি হয়েছে।

### Answer 8

প্রতিটি iteration-এ `end=", "` যোগ হচ্ছে। শেষ iteration-এও একই separator যোগ হওয়ায় অতিরিক্ত comma ও space দেখা যাচ্ছে।

### Answer 9

```python
print("Input", end=" -> ")
print("Process", end=" -> ")
print("Output")
```

### Answer 10

```text
Masum!Masum
```

`end="!"` প্রথম output-এর শেষে `!` যোগ করেছে। Variable-এর value পরিবর্তন হয়নি।

## 19. Chapter Summary

এই topic থেকে আমরা শিখেছি:

1. `end` হলো `print()` function-এর একটি parameter।
2. এর default value হলো newline character (`'\n'`)।
3. `end=""` ব্যবহার করলে output-এর শেষে কোনো character যোগ হয় না।
4. `end=" "` ব্যবহার করলে output-এর শেষে একটি space যোগ হয়।
5. `end`-এ hyphen, arrow বা অন্য যেকোনো string দেওয়া যায়।
6. `sep` object-গুলোর মাঝখানে কাজ করে, আর `end` output-এর শেষে কাজ করে।
7. Loop-এর মাধ্যমে একই লাইনে sequence ও pattern print করতে `end` ব্যবহার করা যায়।
8. `end` output-এর format পরিবর্তন করে, variable-এর value নয়।
9. Loop-এ separator ব্যবহারের সময় অতিরিক্ত comma বা space হচ্ছে কি না খেয়াল রাখতে হয়।

## 20. Self-Assessment Checklist

- [ ] `end`-এর syntax ও default value বুঝি।
- [ ] `end=""` এবং `end=" "`-এর পার্থক্য বুঝি।
- [ ] একাধিক `print()` একই লাইনে দেখাতে পারি।
- [ ] Custom string দিয়ে output শেষ করতে পারি।
- [ ] `sep` এবং `end`-এর পার্থক্য বুঝি।
- [ ] Loop ব্যবহার করে একই লাইনে sequence print করতে পারি।
- [ ] Output দেখে অতিরিক্ত separator-এর কারণ শনাক্ত করতে পারি।

**Next Topic:** `07_Newlines_and_Escape_Sequences.md` — এখানে `\n`, `\t`, `\\`, `\"` এবং অন্যান্য escape sequence শিখব, যেগুলো দিয়ে string-এর মধ্যে নতুন লাইন, tab ও special character দেখানো যায়।s