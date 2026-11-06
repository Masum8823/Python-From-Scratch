# 06. Indentation and Code Blocks in Conditions

## 1. Introduction

Python-এ **Indentation** হলো code-এর শুরুতে space বা whitespace ব্যবহার করা।

অন্যান্য কিছু programming language-এ code block বোঝাতে `{}` ব্যবহার করা হয়। কিন্তু Python-এ `if`, `else`, `for`, `while` ইত্যাদির block নির্ধারণ করতে indentation ব্যবহার করা হয়।

Example:

```python
age = 20

if age >= 18:
    print("Eligible")
    print("Age requirement satisfied.")

print("Program finished.")
```

Output:

```text
Eligible
Age requirement satisfied.
Program finished.
```

এখানে প্রথম দুটি `print()` `if` block-এর মধ্যে আছে। শেষের `print()` block-এর বাইরে।

**মনে রাখবে:** Python-এ indentation program-এর structure নির্ধারণ করে।

## 2. What Is Indentation?

Indentation হলো একটি line-এর শুরুতে দেওয়া whitespace, যা code-এর block structure বোঝায়।

Example:

```python
if True:
    print("Hello")
```

এখানে `print("Hello")`-এর আগে চারটি space আছে। তাই এটি `if` block-এর অংশ।

একই code indentation ছাড়া লিখলে error হবে:

```python
if True:
print("Hello")
```

সম্ভাব্য error:

```text
IndentationError: expected an indented block after 'if' statement
```

কারণ Python আশা করছে `if`-এর পরের statement একটি indented block-এর মধ্যে থাকবে।

## 3. Why Is Indentation Important?

Indentation-এর প্রধান কাজগুলো হলো:

1. কোন statement কোন block-এর অংশ তা নির্ধারণ করা।
2. Conditional statements-এর structure বোঝানো।
3. Nested conditions-এর structure পরিষ্কার রাখা।
4. Code readable ও maintainable করা।
5. ভুল block structure থেকে তৈরি error এড়ানো।

Example:

```python
number = 10

if number > 0:
    print("Positive")
    print("Inside the if block")

print("Outside the if block")
```

Output:

```text
Positive
Inside the if block
Outside the if block
```

এখানে indentation অনুযায়ী প্রথম দুটি `print()` condition-এর অধীনে আছে।

## 4. The Standard Indentation Rule

Python-এর official style convention অনুযায়ী প্রতি indentation level-এ **চারটি space** ব্যবহার করা হয়।

Recommended:

```python
if age >= 18:
    print("Eligible")
```

আরও একটি level-এর indentation:

```python
if age >= 18:
    if age >= 21:
        print("Meets both age requirements")
```

এখানে:

- প্রথম `if`-এর block: 4 spaces।
- দ্বিতীয় `if`-এর block: 8 spaces।

Python-এ সব জায়গায় চারটি space বাধ্যতামূলক নয়; একই block-এর indentation consistent হতে হবে। তবে সাধারণ Python code-এ চারটি space-ই standard practice।

## 5. Indentation Defines a Code Block

একটি **code block** হলো একসঙ্গে থাকা statement-এর group, যা কোনো condition বা control structure-এর অধীনে execute হতে পারে।

Example:

```python
marks = 75

if marks >= 40:
    print("Pass")
    print("Congratulations")
    print("Result recorded")

print("Program ended")
```

Output:

```text
Pass
Congratulations
Result recorded
Program ended
```

প্রথম তিনটি `print()` একই block-এর মধ্যে আছে। তাই condition সত্য হলে তিনটিই execute হয়।

শেষের statement block-এর বাইরে থাকায় সেটি আলাদাভাবে execute হয়।

## 6. Same Indentation Level Means Same Block

একই block-এর statement-গুলো একই indentation level-এ লেখা হয়।

Example:

```python
if True:
    print("Line 1")
    print("Line 2")
    print("Line 3")
```

এখানে তিনটি statement একই block-এর অংশ।

কিন্তু indentation পরিবর্তন করলে block structure-ও বদলে যায়।

```python
if True:
    print("Line 1")
    print("Line 2")

    print("Line 3")
```

এখানেও চারটি space দিয়ে লেখা সব statement একই block-এর মধ্যে আছে। মাঝখানে blank line থাকা block পরিবর্তন করে না।

**Important:** Blank line indentation level পরিবর্তন করে না; statement-এর indentation-ই এখানে গুরুত্বপূর্ণ।

## 7. Code Outside a Block

যে statement কোনো block-এর ভেতরে indent করা হয়নি, সেটি সেই block-এর বাইরে থাকে।

Example:

```python
number = -5

if number > 0:
    print("Positive number")

print("Checking completed")
```

Output:

```text
Checking completed
```

কারণ:

- `number > 0` মিথ্যা।
- তাই `print("Positive number")` execute হয়নি।
- `print("Checking completed")` block-এর বাইরে, তাই execute হয়েছে।

## 8. Indentation in `if-else` Structure

`if` এবং `else` একই indentation level-এ থাকে। তাদের অধীনে থাকা statement indent করা হয়।

Example:

```python
marks = 35

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

Output:

```text
Fail
```

Structure:

```text
if condition:
    statement inside if
else:
    statement inside else
```

এখানে `if` এবং `else`-এর আগে অতিরিক্ত indentation দেওয়া যাবে না।

Incorrect:

```python
if marks >= 40:
    print("Pass")
    else:
        print("Fail")
```

এটি invalid indentation structure এবং error তৈরি করবে।

Correct:

```python
if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

## 9. Indentation in `if-elif-else`

`if`, `elif` এবং `else` একই level-এ থাকে।

Example:

```python
marks = 75

if marks >= 80:
    print("A+")
elif marks >= 70:
    print("A")
else:
    print("Below A grade")
```

Output:

```text
A
```

সঠিক structure:

```python
if condition_1:
    statement_1
elif condition_2:
    statement_2
else:
    statement_3
```

এখানে তিনটি keyword একই indentation level-এ আছে। প্রতিটি block-এর statement চারটি space দিয়ে indent করা হয়েছে।

## 10. Nested `if` and Multiple Indentation Levels

একটি `if` block-এর মধ্যে আরেকটি `if` থাকলে তাকে **Nested `if` Statement** বলা হয়।

Example:

```python
age = 22
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
```

Output:

```text
Entry allowed
```

এখানে:

- বাইরের `if` block-এর indentation: 4 spaces।
- ভেতরের `if` block-এর indentation: 8 spaces।
- `print()` nested block-এর মধ্যে, তাই indentation 12 spaces।

### Visual Structure

```text
if age >= 18:          # Level 0
    if has_id:         # Level 1
        print(...)     # Level 2
```

প্রতিটি nested block-এর জন্য নতুন indentation level তৈরি হয়।

## 11. Indentation in Multiple Independent `if` Statements

একাধিক independent `if` statement একই indentation level-এ থাকতে পারে।

Example:

```python
number = 12

if number > 0:
    print("Positive")

if number % 2 == 0:
    print("Even")

if number > 10:
    print("Greater than 10")
```

Output:

```text
Positive
Even
Greater than 10
```

এখানে প্রতিটি `if` আলাদা statement। তাই একটি condition সত্য হওয়ার কারণে অন্য condition পরীক্ষা বন্ধ হয় না।

## 12. IndentationError vs SyntaxError

Indentation-এর ভুলে সাধারণত `IndentationError` হতে পারে। এটি `SyntaxError`-এর একটি subtype।

### 12.1 Missing Indentation

```python
if True:
print("Hello")
```

সম্ভাব্য error:

```text
IndentationError: expected an indented block
```

### 12.2 Unexpected Indentation

```python
    print("Hello")
```

যদি এটি কোনো block-এর বাইরে অপ্রয়োজনীয় indentation দিয়ে লেখা হয়, তাহলে `IndentationError: unexpected indent` হতে পারে।

### 12.3 Inconsistent Indentation

```python
if True:
    print("First")
  print("Second")
```

এখানে একই block-এর statement-এ indentation inconsistent। এটি `IndentationError` তৈরি করতে পারে।

**মনে রাখবে:** সব indentation-related error-এর exact message এক নয়। ভুলের ধরন ও code structure অনুযায়ী message পরিবর্তিত হতে পারে।

## 13. Tabs vs Spaces

Indentation দেওয়ার জন্য Tab অথবা Space ব্যবহার করা যায়। তবে একই code block-এ এগুলো মিশিয়ে ব্যবহার করলে সমস্যা হতে পারে।

Recommended style:

- প্রতি level-এ চারটি space ব্যবহার করা।
- একই file-এ indentation consistent রাখা।
- VS Code-এর মতো editor-এর indentation settings ব্যবহার করা।
- Tabs ও spaces মিশিয়ে লেখা এড়িয়ে চলা।

কখনো mixed indentation-এর কারণে Python `TabError` দেখাতে পারে।

Example of a common problem:

```python
if True:
    print("First")
	print("Second")
```

উপরের code-এ দ্বিতীয় statement-এর শুরুতে Tab থাকতে পারে, অথচ প্রথম statement-এ spaces ব্যবহার করা হয়েছে। এটি editor ও whitespace-এর ওপর নির্ভর করে indentation error তৈরি করতে পারে।

**Tip:** VS Code-এ সাধারণত `Tab` চাপলে configured indentation অনুযায়ী spaces insert করা যায়। তবে editor settings যাচাই করে নেওয়া ভালো।

## 14. Blank Lines and Indentation

Blank line readability বাড়ায়, কিন্তু নিজে থেকে code block তৈরি বা শেষ করে না।

Example:

```python
number = 5

if number > 0:

    print("Positive")

print("Finished")
```

Output:

```text
Positive
Finished
```

এখানে blank line থাকলেও `print("Positive")` `if` block-এর অংশ।

## 15. Indentation in Loops and Functions

Indentation শুধু conditional statements-এ নয়, loops ও functions-এও ব্যবহৃত হয়।

### Loop Example

```python
for number in range(3):
    print(number)

print("Loop finished")
```

Output:

```text
0
1
2
Loop finished
```

### Function Example

```python
def greet():
    print("Hello")
    print("Welcome")

greet()
```

Output:

```text
Hello
Welcome
```

এখানে loop ও function-এর block-ও indentation দিয়ে নির্ধারণ করা হয়েছে।

এই topic-এ আমরা শুধু basic ধারণা নিচ্ছি; loops ও functions-এর বিস্তারিত তাদের নিজস্ব chapter-এ শেখা হবে।

## 16. Common Indentation Mistakes

### Mistake 1: No Indentation After `if`

Incorrect:

```python
if age >= 18:
print("Eligible")
```

Correct:

```python
if age >= 18:
    print("Eligible")
```

### Mistake 2: Indenting `else` Incorrectly

Incorrect:

```python
if age >= 18:
    print("Eligible")
    else:
        print("Not eligible")
```

Correct:

```python
if age >= 18:
    print("Eligible")
else:
    print("Not eligible")
```

### Mistake 3: Accidentally Moving a Statement Outside the Block

```python
marks = 80

if marks >= 40:
    print("Pass")
print("Congratulations")
```

এখানে `Congratulations` condition-এর ওপর নির্ভর করে না; এটি block-এর বাইরে।

যদি দুইটি message-ই condition সত্য হলে দেখাতে চাও, তাহলে:

```python
marks = 80

if marks >= 40:
    print("Pass")
    print("Congratulations")
```

### Mistake 4: Extra Indentation

Incorrect:

```python
if True:
        print("Hello")
    print("Welcome")
```

এখানে indentation levels inconsistent, তাই error হতে পারে।

Correct:

```python
if True:
    print("Hello")
    print("Welcome")
```

### Mistake 5: Mixing Tabs and Spaces

একই block-এ Tab ও Space মিশিয়ে indentation দেওয়া এড়িয়ে চলো। Consistent চারটি space ব্যবহার করাই recommended।

## 17. Best Practices for Indentation

Clean Python code লেখার জন্য নিচের নিয়মগুলো অনুসরণ করো:

1. প্রতি indentation level-এ চারটি space ব্যবহার করো।
2. একই block-এর statement একই level-এ রাখো।
3. `if`, `elif` ও `else` সঠিকভাবে align করো।
4. Nested condition-এ প্রতিটি level-এর indentation পরিষ্কার রাখো।
5. Tab ও Space মিশিয়ে ব্যবহার কোরো না।
6. Code editor-এর auto-indentation সুবিধা ব্যবহার করো।
7. Block-এর ভেতরে কোন statement থাকবে, তা আগে বুঝে তারপর indentation দাও।
8. অপ্রয়োজনীয় nested block এড়িয়ে code সহজ রাখো।
9. Code format করার সময় program-এর intended logic পরিবর্তন হচ্ছে কি না যাচাই করো।

## 18. Practice Exercises

### Exercise 1: Fix the Indentation

নিচের code-এ indentation ঠিক করো:

```python
age = 20

if age >= 18:
print("Eligible")
print("Age requirement satisfied")
```

Expected output:

```text
Eligible
Age requirement satisfied
```

### Exercise 2: Identify the Block

```python
number = 5

if number > 0:
    print("A")
    print("B")

print("C")
```

কোন statement-গুলো `if` block-এর মধ্যে আছে?

### Exercise 3: Predict the Output

```python
number = -2

if number > 0:
    print("Positive")

print("Finished")
```

### Exercise 4: Fix the `if-else`

```python
marks = 30

if marks >= 40:
    print("Pass")
    else:
    print("Fail")
```

### Exercise 5: Nested Indentation

নিচের code-টি সঠিক indentation দিয়ে লেখো:

- প্রথম condition: `age >= 18`
- দ্বিতীয় condition: `has_id`
- উভয় condition সত্য হলে `Entry allowed` print করবে।

### Exercise 6: Find the Unexpected Behavior

```python
marks = 80

if marks >= 40:
    print("Pass")
print("Result checked")
```

`Result checked` কি শুধু condition সত্য হলে print হবে, নাকি condition মিথ্যা হলেও print হবে? কারণ ব্যাখ্যা করো।

### Exercise 7: Multiple Conditions

`number = 10` নিয়ে তিনটি independent `if` statement লেখো:

- Number positive হলে `Positive`
- Number even হলে `Even`
- Number 10 বা তার বেশি হলে `At least 10`

## 19. Practice Answer Key

### Answer 1

```python
age = 20

if age >= 18:
    print("Eligible")
    print("Age requirement satisfied")
```

### Answer 2

`print("A")` ও `print("B")` `if` block-এর মধ্যে আছে। `print("C")` block-এর বাইরে।

### Answer 3

Output:

```text
Finished
```

কারণ `number > 0` মিথ্যা।

### Answer 4

```python
marks = 30

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

### Answer 5

```python
age = 20
has_id = True

if age >= 18:
    if has_id:
        print("Entry allowed")
```

Output:

```text
Entry allowed
```

### Answer 6

`Result checked` condition সত্য বা মিথ্যা—দুই ক্ষেত্রেই print হবে, কারণ statement-টি `if` block-এর বাইরে।

### Answer 7

```python
number = 10

if number > 0:
    print("Positive")

if number % 2 == 0:
    print("Even")

if number >= 10:
    print("At least 10")
```

Output:

```text
Positive
Even
At least 10
```

## 20. Chapter Summary

- Indentation হলো line-এর শুরুতে দেওয়া whitespace।
- Python indentation দিয়ে code block নির্ধারণ করে।
- Standard style অনুযায়ী প্রতি level-এ চারটি space ব্যবহার করা হয়।
- একই block-এর statement একই indentation level-এ থাকে।
- Nested block-এর জন্য অতিরিক্ত indentation প্রয়োজন।
- `if`, `elif` ও `else` একই level-এ থাকে।
- Blank line নিজে থেকে code block তৈরি বা শেষ করে না।
- ভুল indentation থেকে `IndentationError` বা `TabError` হতে পারে।
- Consistent indentation code-কে readable ও maintainable করে।

## 21. Self-Assessment Checklist

- [ ] Indentation কী, তা ব্যাখ্যা করতে পারি।
- [ ] Python-এ indentation কেন প্রয়োজন, তা বুঝি।
- [ ] চারটি space ব্যবহার করে code block লিখতে পারি।
- [ ] `if`, `elif` ও `else` সঠিকভাবে align করতে পারি।
- [ ] Nested `if` statement-এর indentation লিখতে পারি।
- [ ] Block-এর ভেতরের ও বাইরের statement আলাদা করতে পারি।
- [ ] সাধারণ `IndentationError` শনাক্ত ও ঠিক করতে পারি।
- [ ] Tabs ও spaces মিশিয়ে ব্যবহার করা এড়িয়ে চলতে পারি।

## 22. Next Topic

পরবর্তী file:

`07_The_if_else_Statement.md`

সেখানে `if-else` statement ব্যবহার করে condition সত্য ও মিথ্যা—দুই অবস্থার জন্য আলাদা code execute করা শেখা হবে।