# 62. Loop-Based Menu Programs

## 1. Introduction

Menu-Based Program হলো এমন একটি program, যেখানে user-কে কয়েকটি option দেখানো হয় এবং user তার পছন্দ অনুযায়ী একটি option নির্বাচন করে।

উদাহরণ:

```text
===== Main Menu =====
1. Add Two Numbers
2. Subtract Two Numbers
3. Multiply Two Numbers
4. Exit

Enter your choice:
```

এখানে user `1` দিলে addition হবে, `2` দিলে subtraction হবে, `3` দিলে multiplication হবে এবং `4` দিলে program বন্ধ হবে।

কিন্তু একটি সমস্যা আছে। প্রতিবার কাজ শেষ হলে যদি পুরো menu আবার দেখাতে হয়, তাহলে একই code বারবার লিখতে হবে।

এই সমস্যা সমাধানের জন্য আমরা `while` loop ব্যবহার করব।

### Learning Objectives

এই Topic শেষে তুমি পারবে:

- Menu-based program-এর ধারণা বুঝতে।
- `while True` দিয়ে repeated menu তৈরি করতে।
- `if-elif-else` দিয়ে user-এর choice অনুযায়ী কাজ করতে।
- `break` দিয়ে program থেকে বের হতে।
- Simple calculator তৈরি করতে।
- Invalid choice handle করতে।
- Menu-based program-এর common mistakes শনাক্ত করতে।

## 2. Why Do We Need a Loop in Menu Programs?

ধরি, একটি calculator তৈরি করেছ।

User addition করল। এরপর subtraction করতে চাইলে আবার menu দেখতে হবে।

Loop ছাড়া program-টি একবারই menu দেখাতে পারে, যদি না menu আবার দেখানোর জন্য আলাদা করে code লেখা হয়।

Loop ব্যবহার করলে:

1. Menu দেখাবে।
2. User choice দেবে।
3. Choice অনুযায়ী কাজ হবে।
4. Menu আবার দেখাবে।
5. User Exit নির্বাচন না করা পর্যন্ত চলবে।

এই প্রক্রিয়াকে **repetition** বলা হয়।

## 3. Basic Menu Using `while True`

Python-এ `while True` একটি loop তৈরি করে, যা নিজে থেকে condition False হওয়ার কারণে শেষ হয় না। সাধারণত `break` দিয়ে এটি বন্ধ করা হয়।

### Code

```python
while True:
    print("\n===== Main Menu =====")
    print("1. Say Hello")
    print("2. Show a Message")
    print("3. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        print("Hello, Python learner!")

    elif choice == "2":
        print("Welcome to Python programming.")

    elif choice == "3":
        print("Program ended.")
        break

    else:
        print("Invalid choice. Try again.")
```

### Sample Output

```text
===== Main Menu =====
1. Say Hello
2. Show a Message
3. Exit
Enter your choice: 1
Hello, Python learner!

===== Main Menu =====
1. Say Hello
2. Show a Message
3. Exit
Enter your choice: 3
Program ended.
```

### Explanation

- `while True` menu-টিকে বারবার চালায়।
- `input()` user-এর choice নেয়।
- `if-elif-else` choice অনুযায়ী কাজ নির্বাচন করে।
- Choice `"3"` হলে `break` loop বন্ধ করে।
- ভুল choice দিলে `else`-এর message দেখায় এবং menu আবার আসে।

**গুরুত্বপূর্ণ:** `input()` string return করে। তাই এখানে `"1"`, `"2"` ও `"3"` ব্যবহার করা হয়েছে, integer `1`, `2` ও `3` নয়।

## 4. Understanding the Program Flow

Menu-based program-এর execution flow:

```text
Start
  |
  v
Display Menu
  |
  v
Take User Choice
  |
  v
Check the Choice
  |
  +---- Choice 1 ----> Perform Task 1 --+
  |                                     |
  +---- Choice 2 ----> Perform Task 2 --+--> Show Menu Again
  |                                     |
  +---- Invalid ----> Show Error -------+
  |
  +---- Choice 3 ----> Exit Program
```

এখানে Exit ছাড়া অন্য কোনো choice-এর পরে loop আবার menu দেখায়।

## 5. Creating a Simple Calculator

এবার menu ব্যবহার করে একটি calculator তৈরি করি।

### Code

```python
while True:
    print("\n===== Calculator =====")
    print("1. Addition")
    print("2. Subtraction")
    print("3. Multiplication")
    print("4. Division")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "5":
        print("Calculator closed.")
        break

    elif choice in ("1", "2", "3", "4"):
        num1 = float(input("Enter first number: "))
        num2 = float(input("Enter second number: "))

        if choice == "1":
            print("Result:", num1 + num2)

        elif choice == "2":
            print("Result:", num1 - num2)

        elif choice == "3":
            print("Result:", num1 * num2)

        elif choice == "4":
            if num2 != 0:
                print("Result:", num1 / num2)
            else:
                print("Cannot divide by zero.")

    else:
        print("Invalid choice.")
```

### Sample Output

```text
===== Calculator =====
1. Addition
2. Subtraction
3. Multiplication
4. Division
5. Exit
Enter your choice: 1
Enter first number: 10
Enter second number: 5
Result: 15.0
```

### Explanation

**Step 1:** Menu দেখানো হয়।

**Step 2:** User operation নির্বাচন করে।

**Step 3:** User `5` দিলে calculator বন্ধ হয়।

**Step 4:** User `1` থেকে `4`-এর মধ্যে choice দিলে দুটি number নেওয়া হয়।

**Step 5:** Nested `if-elif` দিয়ে operation নির্ধারণ করা হয়।

**Step 6:** Division-এর ক্ষেত্রে `num2 != 0` পরীক্ষা করা হয়, যাতে zero দিয়ে ভাগ করার চেষ্টা না হয়।

**Note:** এই উদাহরণে ধরে নেওয়া হয়েছে user valid numeric input দেবেন। ভুল text input দিলে `float()` থেকে `ValueError` হতে পারে।

## 6. Why Do We Check the Exit Choice First?

Calculator-এর code-এ:

```python
if choice == "5":
    print("Calculator closed.")
    break
```

এই অংশটি number input নেওয়ার আগেই রাখা হয়েছে।

কারণ user শুধু Exit করতে চাইলে তার কাছে দুটি number চাওয়ার প্রয়োজন নেই।

যদি number input নেওয়ার পর Exit check করা হতো, তাহলে Exit করতে গেলেও অপ্রয়োজনীয় input দিতে হতো।

তাই **Exit condition আগে check করা ভালো practice**, যখন Exit-এর জন্য অন্য কোনো input প্রয়োজন হয় না।

## 7. Using a `while` Condition Instead of `while True`

সব menu program-এ `while True` ব্যবহার করতেই হবে, এমন নয়।

Boolean variable ব্যবহার করেও menu চালানো যায়।

### Code

```python
running = True

while running:
    print("\n===== Menu =====")
    print("1. Show Message")
    print("2. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        print("Keep learning Python!")

    elif choice == "2":
        running = False
        print("Program ended.")

    else:
        print("Invalid choice.")
```

### Output

```text
===== Menu =====
1. Show Message
2. Exit
Enter your choice: 1
Keep learning Python!

===== Menu =====
1. Show Message
2. Exit
Enter your choice: 2
Program ended.
```

### Explanation

- `running = True` হলে loop চলবে।
- Exit নির্বাচন করলে `running = False` হবে।
- পরের condition check-এ loop বন্ধ হবে।

এখানে `break` ব্যবহার করা হয়নি। Boolean variable পরিবর্তন করে loop বন্ধ করা হয়েছে।

## 8. Menu Program for Even and Odd Checking

এবার এমন একটি menu তৈরি করি, যেখানে user number-এর parity পরীক্ষা করতে পারবে।

### Code

```python
while True:
    print("\n===== Number Checker =====")
    print("1. Check Even or Odd")
    print("2. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        number = int(input("Enter an integer: "))

        if number % 2 == 0:
            print("Even number")
        else:
            print("Odd number")

    elif choice == "2":
        print("Program ended.")
        break

    else:
        print("Invalid choice.")
```

### Sample Output

```text
===== Number Checker =====
1. Check Even or Odd
2. Exit
Enter your choice: 1
Enter an integer: 7
Odd number
```

### Explanation

- `% 2` দিয়ে number-এর remainder পরীক্ষা করা হয়।
- Remainder `0` হলে number even।
- অন্যথায় number odd।
- Operation শেষ হলে menu আবার দেখানো হয়।

এই code-এও valid integer input দেওয়া হবে ধরে নেওয়া হয়েছে।

## 9. Menu Program Using a Counter

কখনো menu কতবার ব্যবহার করা হয়েছে, সেটি গণনা করতে হতে পারে।

### Code

```python
count = 0

while True:
    print("\n===== Menu =====")
    print("1. Show Message")
    print("2. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        count += 1
        print("Python is fun!")

    elif choice == "2":
        print("Menu selected", count, "times.")
        break

    else:
        print("Invalid choice.")
```

### Sample Output

```text
Enter your choice: 1
Python is fun!

Enter your choice: 1
Python is fun!

Enter your choice: 2
Menu selected 2 times.
```

### Explanation

- `count = 0` দিয়ে শুরু করা হয়েছে।
- Choice `"1"` হলে `count += 1` হয়।
- Exit করার সময় মোট count দেখানো হয়।

এখানে শুধু সফলভাবে `"1"` নির্বাচন করার সংখ্যা গণনা করা হচ্ছে; menu দেখানোর সংখ্যা নয়।

## 10. Menu Program with a List

Menu ব্যবহার করে list-এর element-গুলোও দেখানো যায়।

### Code

```python
students = ["Masum", "Ritu", "Mahin", "Tusher"]

while True:
    print("\n===== Student Menu =====")
    print("1. Show All Students")
    print("2. Search Student")
    print("3. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        for student in students:
            print(student)

    elif choice == "2":
        target = input("Enter student name: ")

        found = False

        for student in students:
            if student.lower() == target.lower():
                found = True
                break

        if found:
            print("Student found")
        else:
            print("Student not found")

    elif choice == "3":
        print("Program ended.")
        break

    else:
        print("Invalid choice.")
```

### Explanation

এই program-এ দুটি loop রয়েছে:

- Outer `while` loop menu বারবার দেখায়।
- Inner `for` loop list-এর student-দের পরীক্ষা করে বা তাদের নাম print করে।

Search-এর ক্ষেত্রে `found` flag ব্যবহার করা হয়েছে। নাম পাওয়া গেলে `break` শুধু inner `for` loop বন্ধ করবে; outer menu loop চলতে থাকবে।

এটি **nested loop ও searching-এর practical example**।

## 11. Handling Invalid Menu Choices

User menu-তে নেই এমন value দিলে program-এর কী করা উচিত?

ধরি, menu-তে `1`, `2` ও `3` আছে, কিন্তু user `9` দিল।

তখন program-কে error message দেখিয়ে menu আবার দেখাতে হবে।

### Code

```python
while True:
    print("\n1. Start")
    print("2. Help")
    print("3. Exit")

    choice = input("Choose an option: ")

    if choice == "1":
        print("Starting...")

    elif choice == "2":
        print("Help information.")

    elif choice == "3":
        print("Goodbye!")
        break

    else:
        print("Invalid choice. Please select 1, 2, or 3.")
```

### Sample Output

```text
Choose an option: 9
Invalid choice. Please select 1, 2, or 3.
```

তারপর loop আবার menu দেখাবে।

**Best practice:** Invalid choice-এর জন্য `else` রাখবে। এতে user-এর ভুল input program-এর flow নষ্ট করবে না।

## 12. Using `continue` in a Menu Program

`continue` বর্তমান iteration-এর বাকি অংশ বাদ দিয়ে loop-এর পরবর্তী iteration শুরু করে।

### Code

```python
while True:
    print("\n1. Show Message")
    print("2. Exit")

    choice = input("Enter your choice: ")

    if choice not in ("1", "2"):
        print("Invalid choice.")
        continue

    if choice == "1":
        print("Welcome to Python!")

    elif choice == "2":
        print("Program ended.")
        break
```

### Explanation

যদি user `"9"` দেয়:

1. Invalid choice message দেখাবে।
2. `continue` execute হবে।
3. নিচের operation check বাদ যাবে।
4. Loop আবার menu দেখাবে।

এখানে `continue` ব্যবহার করা ঐচ্ছিক। আগের Topic-এ শেখা `if-elif-else` দিয়েও একই কাজ করা যায়।

## 13. Common Mistakes in Menu Programs

### Mistake 1: Forgetting the Loop

Loop ছাড়া menu সাধারণত একবারই দেখাবে। Repeated menu-এর জন্য `while` loop দরকার।

### Mistake 2: Forgetting `break`

ভুল:

```python
elif choice == "3":
    print("Program ended.")
```

এখানে `break` নেই। তাই Exit message দেখানোর পরও menu চলতে থাকবে।

সঠিক:

```python
elif choice == "3":
    print("Program ended.")
    break
```

### Mistake 3: Comparing String Input with Integers

ভুল:

```python
choice = input("Enter choice: ")

if choice == 1:
    print("Selected")
```

`input()` string দেয়, তাই `"1"` এবং `1` এক নয়।

সঠিক:

```python
if choice == "1":
    print("Selected")
```

অথবা integer conversion ব্যবহার করতে পারো, তবে invalid numeric input handle করতে হবে।

### Mistake 4: Forgetting to Update a Loop Condition

Boolean-controlled loop ব্যবহার করলে Exit-এর সময় `running = False` করতে হবে।

এটি বাদ দিলে loop চলতে থাকবে।

### Mistake 5: Dividing by Zero

Division করার আগে divisor zero কি না পরীক্ষা করো।

```python
if num2 != 0:
    print(num1 / num2)
else:
    print("Cannot divide by zero.")
```

### Mistake 6: Incorrect Indentation

`if`, `elif`, `else`, `while` ও `for`-এর block সঠিকভাবে indent করতে হবে।

ভুল indentation হলে `IndentationError` বা ভুল program behavior হতে পারে।

### Mistake 7: Putting Every Operation Outside the Menu Loop

Menu loop-এর ভেতরে operation selection রাখতে হবে। না হলে menu একবার চলার পর operation আবার চালানোর সুযোগ নাও থাকতে পারে।

## 14. Practice Exercises

### Exercise 1

`while True` দিয়ে এমন menu তৈরি করো:

```text
1. Say Hello
2. Say Goodbye
3. Exit
```

User Exit না করা পর্যন্ত menu চলবে।

### Exercise 2

Addition, subtraction, multiplication ও division-এর জন্য একটি calculator তৈরি করো।

### Exercise 3

একটি menu তৈরি করো, যেখানে user even/odd checking অথবা Exit নির্বাচন করতে পারবে।

### Exercise 4

একটি menu তৈরি করো, যেখানে:

- `1` দিলে `1` থেকে `10` পর্যন্ত number print হবে।
- `2` দিলে `1` থেকে `10` পর্যন্ত number-এর sum print হবে।
- `3` দিলে program বন্ধ হবে।

### Exercise 5

একটি list-এর student-দের নাম দেখানো এবং নির্দিষ্ট নাম search করার menu program লেখো।

### Exercise 6

নিচের code-এর output কী হবে?

```python
while True:
    choice = input("Enter choice: ")

    if choice == "1":
        print("One")

    elif choice == "2":
        print("Two")
        break

    else:
        print("Invalid")
```

Input sequence:

```text
1
9
2
```

### Exercise 7

নিচের code-এ ভুলটি খুঁজে বের করো:

```python
while True:
    print("1. Start")
    print("2. Exit")

    choice = input("Choice: ")

    if choice == "1":
        print("Started")

    elif choice == "2":
        print("Goodbye")
```

### Exercise 8

একটি menu program লেখো, যেখানে user কতবার `"1"` নির্বাচন করেছে, তা Exit-এর সময় দেখাবে।

## 15. Practice Answer Key

### Answer 1

```python
while True:
    print("\n1. Say Hello")
    print("2. Say Goodbye")
    print("3. Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        print("Hello!")

    elif choice == "2":
        print("Goodbye!")

    elif choice == "3":
        print("Program ended.")
        break

    else:
        print("Invalid choice.")
```

### Answer 2

```python
while True:
    print("\n1. Addition")
    print("2. Subtraction")
    print("3. Multiplication")
    print("4. Division")
    print("5. Exit")

    choice = input("Enter choice: ")

    if choice == "5":
        print("Calculator closed.")
        break

    elif choice in ("1", "2", "3", "4"):
        a = float(input("Enter first number: "))
        b = float(input("Enter second number: "))

        if choice == "1":
            print("Result:", a + b)
        elif choice == "2":
            print("Result:", a - b)
        elif choice == "3":
            print("Result:", a * b)
        elif choice == "4":
            if b != 0:
                print("Result:", a / b)
            else:
                print("Cannot divide by zero.")

    else:
        print("Invalid choice.")
```

### Answer 3

```python
while True:
    print("\n1. Check Even/Odd")
    print("2. Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        number = int(input("Enter integer: "))

        if number % 2 == 0:
            print("Even")
        else:
            print("Odd")

    elif choice == "2":
        break

    else:
        print("Invalid choice.")
```

### Answer 4

```python
while True:
    print("\n1. Print Numbers")
    print("2. Sum Numbers")
    print("3. Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        for number in range(1, 11):
            print(number, end=" ")
        print()

    elif choice == "2":
        total = 0

        for number in range(1, 11):
            total += number

        print("Sum:", total)

    elif choice == "3":
        break

    else:
        print("Invalid choice.")
```

Output for option `2`:

```text
Sum: 55
```

### Answer 5

```python
students = ["Masum", "Ritu", "Mahin"]

while True:
    print("\n1. Show Students")
    print("2. Search Student")
    print("3. Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        for student in students:
            print(student)

    elif choice == "2":
        target = input("Enter name: ")
        found = False

        for student in students:
            if student.lower() == target.lower():
                found = True
                break

        if found:
            print("Student found")
        else:
            print("Student not found")

    elif choice == "3":
        break

    else:
        print("Invalid choice.")
```

### Answer 6

Output:

```text
Enter choice: 1
One
Enter choice: 9
Invalid
Enter choice: 2
Two
```

`"2"` নির্বাচন করলে `break` loop বন্ধ করে।

### Answer 7

Exit option-এর `elif` block-এ `break` নেই। তাই `"Goodbye"` দেখানোর পরও loop চলতে থাকবে।

সঠিক অংশ:

```python
elif choice == "2":
    print("Goodbye")
    break
```

### Answer 8

```python
count = 0

while True:
    print("\n1. Perform Action")
    print("2. Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        count += 1
        print("Action performed.")

    elif choice == "2":
        print("Option 1 selected:", count, "times")
        break

    else:
        print("Invalid choice.")
```

## 16. Chapter Summary

- Menu-based program user-কে বিভিন্ন option দেয়।
- `while True` দিয়ে menu বারবার দেখানো যায়।
- `input()` দিয়ে user-এর choice নেওয়া হয়।
- `if-elif-else` দিয়ে choice অনুযায়ী operation নির্বাচন করা হয়।
- `break` দিয়ে loop এবং menu বন্ধ করা যায়।
- Invalid choice handle করার জন্য `else` ব্যবহার করা হয়।
- Nested loop দিয়ে menu-এর মধ্যে searching বা list processing করা যায়।
- `continue` ব্যবহার করে invalid choice-এর পর সরাসরি পরবর্তী iteration-এ যাওয়া যায়।
- Calculator হলো loop-based menu program-এর একটি practical example।

## 17. Completion Checklist

- [ ] Repeated menu তৈরি করতে পারি।
- [ ] `while True` বুঝি।
- [ ] User-এর choice নিতে পারি।
- [ ] `if-elif-else` দিয়ে operation নির্বাচন করতে পারি।
- [ ] `break` দিয়ে Exit implement করতে পারি।
- [ ] Invalid choice handle করতে পারি।
- [ ] Menu-based calculator তৈরি করতে পারি।
- [ ] Menu-এর মধ্যে list search করতে পারি।
- [ ] Counter ব্যবহার করে selection গণনা করতে পারি।
- [ ] Common mistakes ঠিক করতে পারি।

**Next Topic:** `63_Using_Loops_with_User_Input.md`