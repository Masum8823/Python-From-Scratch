# 01. Introduction to Input and Output

## 1. Introduction

একটি program শুধু instruction execute করলেই হয় না। অনেক সময় program-কে user-এর কাছ থেকে data নিতে হয়, সেই data process করতে হয় এবং result দেখাতে হয়।

Python-এ user বা অন্য কোনো source থেকে data নেওয়াকে **Input** বলে এবং program-এর result বাইরে দেখানোকে **Output** বলে।

উদাহরণ:
- Calculator-এ দুটি সংখ্যা দেওয়া — Input
- সংখ্যা দুটি যোগ করা — Processing
- যোগফল দেখানো — Output

Python-এ সাধারণভাবে user input নেওয়ার জন্য `input()` এবং output দেখানোর জন্য `print()` ব্যবহার করা হয়।

## 2. What Is Input?

**Input** হলো সেই data বা information, যা একটি program কাজ করার জন্য গ্রহণ করে।

Input বিভিন্ন উৎস থেকে আসতে পারে:
- User-এর keyboard থেকে
- কোনো file থেকে
- Database থেকে
- কোনো website বা API থেকে
- অন্য কোনো program থেকে

### Example

```python
name = input("Enter your name: ")
```

এখানে user keyboard দিয়ে নিজের নাম লিখতে পারে। `input()` সেই information গ্রহণ করে এবং `name` variable-এ রাখে।

Possible interaction:

```text
Enter your name: Masum
```

এখানে `Masum` হলো user-এর দেওয়া input।

## 3. What Is Output?

**Output** হলো program-এর processing-এর পর পাওয়া result বা information, যা user বা অন্য কোনো system-এর কাছে পাঠানো হয়।

Output বিভিন্নভাবে দেওয়া যায়:
- Terminal বা screen-এ দেখিয়ে
- File-এ লিখে
- Database-এ save করে
- Website বা application-এ প্রদর্শন করে

### Example

```python
print("Hello, Python!")
```

Output:

```text
Hello, Python!
```

এখানে `print()` screen-এ message দেখিয়েছে। তাই message-টি হলো output।

## 4. What Is Processing?

**Processing** হলো input data-এর ওপর নির্দিষ্ট operation বা calculation করা।

উদাহরণ:

```python
a = 10
b = 20

total = a + b

print(total)
```

Output:

```text
30
```

এখানে:

- Input/Data: `10` এবং `20`
- Processing: `a + b`
- Output: `30`

এই উদাহরণে সংখ্যা দুটি program-এর মধ্যে আগে থেকেই দেওয়া আছে। তাই এখানে user-এর কাছ থেকে interactive input নেওয়া হয়নি।

## 5. The Input–Process–Output (IPO) Model

একটি program-এর কাজ বোঝার সহজ পদ্ধতি হলো **IPO Model**।

IPO-এর পূর্ণরূপ:

- **I — Input:** Data গ্রহণ করা।
- **P — Process:** Data-এর ওপর কাজ করা।
- **O — Output:** Result দেখানো বা সরবরাহ করা।

সাধারণ flow:

```text
       INPUT
          |
          v
       PROCESS
          |
          v
       OUTPUT
```

### Example: Addition Program

ধরা যাক, user দুটি সংখ্যা দিল এবং program তাদের যোগফল বের করল।

| Stage | কাজ |
|---|---|
| Input | 10 এবং 20 গ্রহণ করা |
| Process | 10 + 20 হিসাব করা |
| Output | 30 দেখানো |

IPO Model ব্যবহার করলে program লেখার আগেই বোঝা যায়, কোন data লাগবে, কী কাজ করতে হবে এবং কী result পাওয়া উচিত।

## 6. Input and Output in Real Life

বাস্তব জীবনের অনেক system-ই Input–Process–Output পদ্ধতিতে কাজ করে।

| System | Input | Process | Output |
|---|---|---|---|
| Calculator | দুটি সংখ্যা | যোগ করা | যোগফল |
| Student Result System | Marks | Result calculation | Total marks বা grade |
| ATM | PIN এবং amount | Account verification ও transaction processing | Cash বা transaction message |
| Online Shopping | Product ও order details | Order processing | Order confirmation |
| Weather Application | Weather data | Data analysis | Weather report |

এগুলো থেকে বোঝা যায়, input ও output শুধু Python-এর বিষয় নয়; অধিকাংশ software system-এর গুরুত্বপূর্ণ অংশ।

## 7. Using `print()` for Output

Python-এর `print()` function ব্যবহার করে screen-এ text, number, variable-এর value বা calculation-এর result দেখানো যায়।

### Example 1: Printing Text

```python
print("Welcome to Python")
```

Output:

```text
Welcome to Python
```

### Example 2: Printing a Number

```python
print(100)
```

Output:

```text
100
```

### Example 3: Printing a Calculation

```python
print(15 + 5)
```

Output:

```text
20
```

এই topic-এ শুধু মনে রাখবে, `print()` হলো Python-এ সাধারণ output দেখানোর প্রধান function। এর parameter এবং ব্যবহার পরের file-এ বিস্তারিত আলোচনা করা হবে।

## 8. Using `input()` for Input

Python-এর `input()` function ব্যবহার করে user-এর কাছ থেকে keyboard input নেওয়া যায়।

### Example

```python
name = input("Enter your name: ")

print(name)
```

Possible interaction:

```text
Enter your name: Masum
Masum
```

এখানে:
1. `input()` user-কে নাম লিখতে বলেছে।
2. User `Masum` লিখেছে।
3. Input-টি `name` variable-এ রাখা হয়েছে।
4. `print(name)` নামটি output হিসেবে দেখিয়েছে।

**Important:** `input()` দিয়ে নেওয়া value সাধারণত string হিসেবে পাওয়া যায়। User যদি `25` লেখে, তাহলেও value-টি প্রথমে string `"25"` হবে। পরের topic-গুলোতে এটি বিস্তারিত শিখব।

## 9. A Simple Input–Process–Output Program

এবার তিনটি বিষয় একসঙ্গে ব্যবহার করি।

```python
number1 = int(input("Enter first number: "))
number2 = int(input("Enter second number: "))

total = number1 + number2

print("Total:", total)
```

Example interaction:

```text
Enter first number: 10
Enter second number: 20
Total: 30
```

### Program Explanation

**Step 1: Input**

```python
number1 = int(input("Enter first number: "))
number2 = int(input("Enter second number: "))
```

দুটি input নেওয়া হয়েছে। `int()` input-এর string value-কে integer-এ convert করার চেষ্টা করে।

**Step 2: Process**

```python
total = number1 + number2
```

দুটি সংখ্যার যোগফল বের করা হয়েছে।

**Step 3: Output**

```python
print("Total:", total)
```

যোগফল screen-এ দেখানো হয়েছে।

এই program-এ `input()`, `int()` এবং `print()` একসঙ্গে ব্যবহার করা হয়েছে। `int()`-এর বিস্তারিত ব্যবহার Data Types & Type Conversion chapter-এ আলোচনা করা হয়েছে এবং এখানে input-এর সঙ্গে এর ব্যবহার দেখানো হলো।

## 10. Fixed Data vs User Input

Program-এ data দেওয়ার দুটি সাধারণ উপায় বুঝে রাখা দরকার।

### A. Fixed Data

```python
name = "Masum"
print(name)
```

Output:

```text
Masum
```

এখানে নামটি code-এর মধ্যেই লেখা আছে। অন্য নাম ব্যবহার করতে হলে code পরিবর্তন করতে হবে।

### B. User Input

```python
name = input("Enter your name: ")
print(name)
```

যদি user `Rahim` লেখে, output হবে:

```text
Rahim
```

এখানে user নিজের পছন্দমতো নাম দিতে পারে। তাই program-টি আরও interactive।

| Fixed Data | User Input |
|---|---|
| Data code-এ আগে থেকে দেওয়া থাকে | Data user সরবরাহ করে |
| সাধারণত code পরিবর্তন করতে হয় | একই code-এ বিভিন্ন input নেওয়া যায় |
| Testing ও নির্দিষ্ট calculation-এ উপকারী | Interactive program-এ উপকারী |

## 11. Common Beginner Mistakes

### Mistake 1: `print`-এর spelling ভুল লেখা

ভুল:

```python
Print("Hello")
```

সঠিক:

```python
print("Hello")
```

Python case-sensitive, তাই `print` এবং `Print` এক নয়।

### Mistake 2: Text-এর quotation mark বাদ দেওয়া

ভুল:

```python
print(Hello)
```

সঠিক:

```python
print("Hello")
```

Text বা string সরাসরি লেখার সময় quotation marks ব্যবহার করতে হয়। তবে variable-এর নাম quotation marks ছাড়া লেখা হয়।

### Mistake 3: Input নেওয়া আর input ব্যবহার করা এক মনে করা

```python
name = input("Enter your name: ")
```

এই statement শুধু input গ্রহণ করে এবং variable-এ রাখে। আলাদাভাবে `print(name)` না লিখলে নামটি নিজে থেকে output হিসেবে দেখাবে না—যদিও prompt-এর মাধ্যমে input চাওয়ার message দেখা যাবে।

### Mistake 4: সব input-কে number মনে করা

```python
age = input("Enter your age: ")
```

এখানে user `20` লিখলেও `age`-এর value হবে string `"20"`। Numeric calculation করতে হলে প্রয়োজন অনুযায়ী `int()` বা `float()` ব্যবহার করতে হবে।

### Mistake 5: Output সব সময় একই হবে মনে করা

Interactive program-এর output user-এর input-এর ওপর নির্ভর করতে পারে। তাই example output-কে সম্ভাব্য output হিসেবে বুঝতে হবে।

## 12. Practice Exercises

নিজে code লিখে practice করো।

### Exercise 1: Simple Output

`print()` ব্যবহার করে নিজের নাম screen-এ দেখাও।

### Exercise 2: Two Messages

দুটি আলাদা `print()` statement দিয়ে দুটি message দেখাও।

### Exercise 3: User Name

User-এর নাম input হিসেবে নিয়ে তাকে greeting দেখাও।

Expected interaction:

```text
Enter your name: Masum
Hello, Masum
```

### Exercise 4: Addition

User-এর কাছ থেকে দুটি integer নিয়ে তাদের যোগফল দেখাও।

### Exercise 5: IPO Analysis

একটি temperature converter program-এর জন্য নিচের বিষয়গুলো চিহ্নিত করো:
- Input
- Process
- Output

**Hint:** Celsius থেকে Fahrenheit রূপান্তরের formula:

```text
Fahrenheit = (Celsius * 9 / 5) + 32
```

## 13. Answer Key

### Answer 1

```python
print("Masum")
```

### Answer 2

```python
print("I am learning Python.")
print("I will practice every day.")
```

### Answer 3

```python
name = input("Enter your name: ")
print("Hello,", name)
```

### Answer 4

```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))

print("Sum:", a + b)
```

### Answer 5

- **Input:** Temperature in Celsius
- **Process:** `(Celsius * 9 / 5) + 32`
- **Output:** Temperature in Fahrenheit

## 14. Chapter Summary

এই topic থেকে আমরা শিখেছি:

1. **Input:** Program-এর জন্য data গ্রহণ করা।
2. **Processing:** Data-এর ওপর operation বা calculation করা।
3. **Output:** Result বা information দেখানো বা সরবরাহ করা।
4. **IPO Model:** Input → Process → Output।
5. `input()` ব্যবহার করে সাধারণত user-এর কাছ থেকে keyboard input নেওয়া হয়।
6. `print()` ব্যবহার করে screen-এ output দেখানো হয়।
7. `input()` সাধারণত string return করে; numeric operation-এর জন্য type conversion লাগতে পারে।
8. Fixed data-এর তুলনায় user input program-কে আরও interactive করে।

## 15. Self-Assessment Checklist

নিচের প্রতিটি প্রশ্নের উত্তর দিতে পারলে topic-টি ভালোভাবে বুঝেছ।

- [ ] Input, Process এবং Output-এর পার্থক্য বুঝতে পারি।
- [ ] IPO Model ব্যাখ্যা করতে পারি।
- [ ] `print()` দিয়ে output দেখাতে পারি।
- [ ] `input()` দিয়ে user input নিতে পারি।
- [ ] Fixed data ও user input-এর পার্থক্য বুঝি।
- [ ] দুটি সংখ্যা নিয়ে যোগফল বের করার program লিখতে পারি।
- [ ] কেন `input()`-এর value numeric calculation-এর আগে convert করতে হতে পারে, তা বুঝি।

**Next Topic:** `02_Understanding_the_print_Function.md` — এখানে `print()` function-এর কাজ, syntax, arguments এবং ব্যবহার বিস্তারিত শিখব।