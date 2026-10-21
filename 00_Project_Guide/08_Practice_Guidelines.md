# 08. Practice Guidelines

## 1. Introduction

Python শেখার জন্য শুধু documentation পড়া বা অন্যের code দেখা যথেষ্ট নয়। Programming ভালোভাবে শিখতে হলে নিজে code লিখতে হবে, program run করতে হবে, problem solve করতে হবে এবং ভুল থেকে শিখতে হবে।

এই repository-তে practice-কে learning process-এর একটি গুরুত্বপূর্ণ অংশ হিসেবে বিবেচনা করা হবে।

এই ফাইলের উদ্দেশ্য হলো একটি কার্যকর practice system তৈরি করা, যা beginner থেকে advanced learner পর্যন্ত Python programming দক্ষতা উন্নত করতে সাহায্য করবে।

---

## 2. Why Practice Is Important

নিয়মিত practice করার মাধ্যমে:

- Python syntax ভালোভাবে মনে রাখা যায়।
- Programming concepts বাস্তবে কীভাবে কাজ করে তা বোঝা যায়।
- Logical thinking এবং problem-solving skill উন্নত হয়।
- Error খুঁজে বের করার দক্ষতা তৈরি হয়।
- নতুন problem সমাধানের আত্মবিশ্বাস বাড়ে।
- নিজের code নিজে লেখার অভ্যাস তৈরি হয়।
- বড় project তৈরি করার জন্য প্রয়োজনীয় foundation গড়ে ওঠে।

শুধু code মুখস্থ করলে নতুন problem এলে আটকে যাওয়ার সম্ভাবনা থাকে। তাই code কেন এবং কীভাবে কাজ করে তা বুঝে practice করা জরুরি।

---

## 3. Follow the Learning Cycle

প্রতিটি নতুন topic শেখার সময় নিচের learning cycle অনুসরণ করা যেতে পারে।

1. **Learn:** Documentation থেকে concept পড়ো।
2. **Understand:** Concept-টি নিজের ভাষায় বোঝার চেষ্টা করো।
3. **Predict:** Code run করার আগে সম্ভাব্য output অনুমান করো।
4. **Write:** Example না দেখে নিজে code লেখো।
5. **Run:** Code execute করো।
6. **Debug:** Error হলে কারণ খুঁজে বের করো।
7. **Modify:** Code-এ পরিবর্তন এনে behavior পর্যবেক্ষণ করো।
8. **Practice:** একই concept ব্যবহার করে নতুন problem solve করো।
9. **Review:** পরে আবার topic-টি revise করো।

এই cycle-এর উদ্দেশ্য শুধু code চালানো নয়; code-এর behavior বুঝে স্বাধীনভাবে program লেখার দক্ষতা তৈরি করা।

---

## 4. Read, Understand, Then Code

নতুন topic শেখার সময় সরাসরি complex code লেখা শুরু করা উচিত নয়।

প্রথমে concept বুঝতে হবে, তারপর ছোট example দিয়ে practice করতে হবে।

উদাহরণ হিসেবে, `if` statement শেখার সময়:

### Step 1: Understand the Concept

`if` statement ব্যবহার করে কোনো condition সত্য হলে নির্দিষ্ট code execute করা যায়।

### Step 2: Study an Example

```python
age = 20

if age >= 18:
    print("Adult")
```

Output:

```text
Adult
```

### Step 3: Write It Yourself

Example দেখে বা মনে রেখে নিজে code লেখো।

### Step 4: Change the Values

`age`-এর value `15`, `18` এবং `25` করে output পর্যবেক্ষণ করো।

### Step 5: Create a New Problem

একটি number positive, negative নাকি zero—তা নির্ধারণ করার program লেখো।

এভাবে একটি concept থেকে একাধিক problem solve করার দক্ষতা তৈরি হবে।

---

## 5. Practice Without Copying

অন্যের code দেখে শেখা উপকারী, কিন্তু সব সময় copy-paste করলে নিজের programming skill যথেষ্ট উন্নত হয় না।

Practice-এর সময় নিচের নিয়ম অনুসরণ করো:

1. প্রথমে example মনোযোগ দিয়ে পড়ো।
2. প্রতিটি line কী করে তা বোঝো।
3. Code বন্ধ করে নিজে লেখার চেষ্টা করো।
4. Code run করে output মিলিয়ে দেখো।
5. আটকে গেলে শুধু প্রয়োজনীয় অংশটি আবার দেখো।
6. এরপর example না দেখে পুনরায় code লেখো।

কোনো code দেখে লিখতে পারা এবং concept বুঝে নতুন code তৈরি করতে পারা এক বিষয় নয়।

লক্ষ্য হবে ধীরে ধীরে নিজের knowledge ব্যবহার করে code লিখতে শেখা।

---

## 6. Predict the Output Before Running Code

Code execute করার আগে output অনুমান করার অভ্যাস তৈরি করো।

উদাহরণ:

```python
x = 5
y = 2

print(x + y)
print(x / y)
print(x // y)
print(x % y)
```

Code run করার আগে চারটি output লিখে ফেলো।

এরপর program execute করে নিজের prediction-এর সঙ্গে actual output তুলনা করো।

এই practice-এর মাধ্যমে:

- Operators-এর behavior বোঝা যায়।
- Data types সম্পর্কে ধারণা পরিষ্কার হয়।
- Code line-by-line অনুসরণ করার দক্ষতা তৈরি হয়।
- নিজের ভুল ধারণা শনাক্ত করা যায়।

বিশেষ করে loop, function, recursion, list এবং conditional statement শেখার সময় এই পদ্ধতি কার্যকর।

---

## 7. Modify Existing Examples

একটি example একবার চালিয়েই থেমে যাওয়া উচিত নয়। Code-এর বিভিন্ন অংশ পরিবর্তন করে পরীক্ষা করা দরকার।

উদাহরণ:

```python
price = 100
quantity = 3

total = price * quantity

print(total)
```

এখন নিচের পরিবর্তনগুলো করো:

- `price`-এর value পরিবর্তন করো।
- `quantity`-এর value পরিবর্তন করো।
- Multiplication-এর পরিবর্তে addition ব্যবহার করো।
- একটি discount যোগ করো।
- Final result সুন্দরভাবে format করে দেখাও।

প্রতিটি পরিবর্তনের পর output পর্যবেক্ষণ করো।

এই পদ্ধতিকে experimental learning বলা যেতে পারে—অর্থাৎ পরিবর্তন করে দেখে concept শেখা।

---

## 8. Solve Problems in Increasing Difficulty

Practice problem সহজ থেকে কঠিন ক্রমে solve করা উচিত।

| Difficulty | Practice Focus | Example |
|---|---|---|
| Basic | Syntax ও basic concept | দুটি সংখ্যার যোগফল |
| Intermediate | একাধিক concept ব্যবহার | List থেকে maximum value বের করা |
| Advanced | Complex logic ও problem decomposition | একটি data processing program |
| Project Level | একাধিক feature একত্র করা | Student management application |

প্রতিটি level-এর problem পুরোপুরি শেষ না করেও পরের level-এ যাওয়া যায়, তবে foundation দুর্বল থাকলে আগের concept revise করতে হবে।

Advanced problem সমাধান করতে না পারলে নিজেকে ব্যর্থ মনে করার প্রয়োজন নেই। Problem-টিকে ছোট অংশে ভাগ করে ধাপে ধাপে এগোতে হবে।

---

## 9. Use a Problem-Solving Process

কোনো programming problem সমাধান করার সময় নিচের process অনুসরণ করো।

### Step 1: Understand the Problem

Problem statement মনোযোগ দিয়ে পড়ো।

নিজেকে প্রশ্ন করো:

- কী করতে বলা হয়েছে?
- কী input দেওয়া হবে?
- কী output দিতে হবে?
- কোনো special condition আছে কি?

### Step 2: Identify the Inputs and Outputs

উদাহরণ:

Problem: দুটি সংখ্যা নিয়ে তাদের যোগফল বের করতে হবে।

- Input: দুটি সংখ্যা
- Processing: সংখ্যাগুলো যোগ করা
- Output: যোগফল

### Step 3: Break the Problem into Smaller Steps

```text
1. Read the first number.
2. Read the second number.
3. Add the two numbers.
4. Display the result.
```

### Step 4: Write the Logic

Code লেখার আগে সাধারণ ভাষায় solution-এর logic বোঝার চেষ্টা করো।

### Step 5: Implement the Code

Logic-কে Python syntax-এ রূপান্তর করো।

### Step 6: Test the Program

সাধারণ input-এর পাশাপাশি edge cases-ও পরীক্ষা করো।

### Step 7: Review the Solution

Code সঠিকভাবে কাজ করছে কি না, সহজে বোঝা যায় কি না এবং অপ্রয়োজনীয় complexity আছে কি না—তা যাচাই করো।

---

## 10. Learn to Debug Errors

Programming শেখার সময় error হওয়া স্বাভাবিক। Error মানেই তুমি programming পারো না—এমন নয়।

Error message পড়ে সমস্যার কারণ খুঁজে বের করার অভ্যাস তৈরি করতে হবে।

### Common Error Categories

| Error Type | সাধারণ কারণ |
|---|---|
| `SyntaxError` | Python syntax-এর নিয়ম ভঙ্গ করা |
| `NameError` | অজানা বা ভুল variable/function name ব্যবহার করা |
| `TypeError` | কোনো operation-এর জন্য অসামঞ্জস্যপূর্ণ type ব্যবহার করা |
| `ValueError` | সঠিক type হলেও অনুপযুক্ত value দেওয়া |
| `IndexError` | List বা sequence-এর বৈধ range-এর বাইরে index ব্যবহার করা |
| `KeyError` | Dictionary-তে অনুপস্থিত key access করা |
| `ZeroDivisionError` | শূন্য দিয়ে ভাগ করা |

### Debugging Process

1. Error message পড়ো।
2. কোন line-এ error হয়েছে তা দেখো।
3. Variable-এর value ও data type পরীক্ষা করো।
4. Code-এর relevant অংশ আলাদাভাবে পরীক্ষা করো।
5. একটি করে সম্ভাব্য সমস্যা ঠিক করো।
6. আবার program run করো।
7. কেন error হয়েছিল তা মনে রাখার জন্য সংক্ষিপ্ত note লেখো।

Error-এর কারণ না বুঝে শুধু code পরিবর্তন করলে একই ধরনের সমস্যা আবার হতে পারে।

---

## 11. Use Small Experiments

কোনো concept বুঝতে সমস্যা হলে ছোট experiment তৈরি করো।

উদাহরণ হিসেবে, list-এর behavior বুঝতে:

```python
numbers = [10, 20, 30]

print(numbers[0])

numbers.append(40)

print(numbers)
```

Output:

```text
10
[10, 20, 30, 40]
```

এখন পরীক্ষা করো:

- `numbers[1]` কী return করে?
- `numbers[3]` কী return করে?
- `append()` বাদ দিলে কী পরিবর্তন হয়?
- Empty list-এ `append()` ব্যবহার করলে কী হয়?

একটি বড় program-এর মধ্যে অনেক কিছু একসঙ্গে বোঝার চেষ্টা করার চেয়ে ছোট experiment দিয়ে একটি behavior পরীক্ষা করা অনেক সময় সহজ।

---

## 12. Practice Each Topic Before Moving Forward

পরবর্তী topic-এ যাওয়ার আগে আগের topic-এর basic understanding যাচাই করো।

### Topic Completion Checklist

- [ ] Concept নিজের ভাষায় explain করতে পারি।
- [ ] Basic syntax example না দেখে লিখতে পারি।
- [ ] Code-এর output অনুমান করতে পারি।
- [ ] Common errors-এর কারণ বুঝতে পারি।
- [ ] কয়েকটি practice problem solve করতে পারি।
- [ ] একই concept নতুন problem-এ ব্যবহার করতে পারি।

সবগুলো কাজ নিখুঁতভাবে করতে পারতেই হবে—এমন নয়। কোনো অংশ দুর্বল থাকলে সেটি চিহ্নিত করে পরে আবার practice করো।

---

## 13. Keep a Practice Log

নিয়মিত practice-এর অগ্রগতি track করার জন্য একটি practice log রাখা যেতে পারে।

উদাহরণ:

| Date | Topic | Problems Attempted | Problems Solved | Main Difficulty |
|---|---|---:|---:|---|
| 2026-10-01 | Variables | 5 | 4 | Naming |
| 2026-10-02 | Operators | 6 | 5 | Integer division |
| 2026-10-03 | Conditions | 5 | 3 | Nested conditions |

এটি শুধু একটি sample format। নিজের actual practice অনুযায়ী তথ্য লিখতে হবে।

### What to Record

- কোন topic practice করেছ।
- কতগুলো problem চেষ্টা করেছ।
- কতগুলো নিজে solve করতে পেরেছ।
- কোথায় আটকে গিয়েছিলে।
- কোন concept আবার revise করতে হবে।
- পরবর্তী practice session-এ কী করবে।

শুধু কত ঘণ্টা পড়েছ তা নয়, কী শিখেছ এবং কী নিজে করতে পারছ—সেটিও track করা গুরুত্বপূর্ণ।

---

## 14. Revise Previous Topics

একটি topic শেখার পর দীর্ঘদিন আর practice না করলে syntax ও concept ভুলে যাওয়া স্বাভাবিক।

তাই পুরোনো topic নিয়মিত revise করতে হবে।

একটি practical revision schedule হতে পারে:

- **Day 1:** Topic শেখা ও basic practice।
- **Day 2:** Example না দেখে পুনরায় code লেখা।
- **Day 4:** কয়েকটি নতুন problem solve করা।
- **Day 7:** ছোট revision test।
- **Day 14:** অন্য topic-এর সঙ্গে মিলিয়ে practice করা।

এটি একটি suggested schedule, বাধ্যতামূলক নিয়ম নয়। Topic-এর difficulty এবং নিজের progress অনুযায়ী সময় পরিবর্তন করা যাবে।

Revision-এর সময় শুধু notes পড়বে না। Memory থেকে syntax লেখা, output predict করা এবং problem solve করার চেষ্টা করবে।

---

## 15. Build Mini Projects

Basic concept শেখার পর ছোট project তৈরি করা উচিত।

Mini project-এ একাধিক concept একসঙ্গে ব্যবহার করার সুযোগ থাকে।

### Beginner Projects

- Simple Calculator
- Number Guessing Game
- Temperature Converter
- Unit Converter
- Even or Odd Checker
- Multiplication Table Generator

### Intermediate Projects

- Student Marks Management
- Contact Book
- To-Do List
- Expense Tracker
- Quiz Application
- File-Based Record Manager

### Advanced Projects

- Database-Driven Management System
- REST API Application
- Automated Data Processing Tool
- Web Application
- Machine Learning Project
- Asynchronous Task Processing System

এই project list একটি learning guide। প্রতিটি project-এর implementation complexity feature এবং design অনুযায়ী পরিবর্তিত হতে পারে।

### Project Development Process

1. Project-এর purpose নির্ধারণ করো।
2. Features-এর list তৈরি করো।
3. Problem-টিকে ছোট task-এ ভাগ করো।
4. Minimum working version তৈরি করো।
5. প্রতিটি feature পরীক্ষা করো।
6. Error handling যোগ করো।
7. Code refactor করো।
8. README ও documentation তৈরি করো।
9. Git ব্যবহার করে progress track করো।

---

## 16. Use Online Judges and Coding Platforms

Basic syntax ও problem-solving শেখার পর online coding platform ব্যবহার করা যেতে পারে।

কিছু পরিচিত platform:

- [HackerRank](https://www.hackerrank.com/) — beginner-friendly programming challenges।
- [LeetCode](https://leetcode.com/) — algorithms, data structures এবং interview-oriented problems।
- [Codewars](https://www.codewars.com/) — বিভিন্ন difficulty-এর programming challenges।
- [Exercism](https://exercism.org/) — language-specific practice ও feedback।
- [Project Euler](https://projecteuler.net/) — mathematical ও computational problem-solving।

### How to Use These Platforms

- প্রথমে সহজ problem বেছে নাও।
- Problem statement ভালোভাবে বোঝো।
- নিজে solution তৈরি করার চেষ্টা করো।
- আটকে গেলে hint বা documentation ব্যবহার করো।
- Solution accepted হওয়ার পর অন্য approach শেখার চেষ্টা করো।
- অন্যের solution দেখলে সেটি বুঝে নিজে পুনরায় implement করো।

একসঙ্গে অনেক platform ব্যবহার করার প্রয়োজন নেই। নিজের বর্তমান skill level অনুযায়ী একটি platform দিয়ে শুরু করাই যথেষ্ট।

---

## 17. Use AI and Documentation Responsibly

AI assistant এবং online documentation শেখার ক্ষেত্রে সহায়ক হতে পারে। তবে এগুলোর ওপর সম্পূর্ণ নির্ভরশীল হওয়া উচিত নয়।

### Recommended Approach

1. প্রথমে নিজে problem solve করার চেষ্টা করো।
2. আটকে গেলে error message বা নির্দিষ্ট concept সম্পর্কে প্রশ্ন করো।
3. Explanation চাও, শুধু final code নয়।
4. AI-এর দেওয়া code নিজে পড়ে বোঝো।
5. Code run করে output যাচাই করো।
6. Code-এর limitation ও edge cases পরীক্ষা করো।
7. তারপর example না দেখে নিজে code লেখার চেষ্টা করো।

### Avoid These Habits

- Problem না বুঝে সম্পূর্ণ solution copy করা।
- Code run না করে correct ধরে নেওয়া।
- Explanation না বুঝে code মুখস্থ করা।
- AI-এর প্রতিটি technical claim যাচাই ছাড়া বিশ্বাস করা।
- নিজের attempt ছাড়াই বারবার ready-made solution নেওয়া।

AI-কে learning assistant হিসেবে ব্যবহার করতে হবে, নিজের চিন্তার বিকল্প হিসেবে নয়।

---

## 18. Learn to Read Other People's Code

Programming skill উন্নত করার জন্য অন্যের code পড়াও গুরুত্বপূর্ণ।

Code পড়ার সময় লক্ষ্য করো:

- Variable এবং function কীভাবে name করা হয়েছে।
- Code কীভাবে ছোট function-এ ভাগ করা হয়েছে।
- Data কীভাবে process করা হয়েছে।
- Error handling কীভাবে করা হয়েছে।
- কোন built-in function বা library ব্যবহার করা হয়েছে।
- একই problem-এর alternative solution আছে কি না।

শুরুতে ছোট এবং readable code পড়বে। পরে GitHub repository ও open-source project-এর code বুঝতে চেষ্টা করতে পারো।

অন্যের code পড়ে শেখা এবং code না বুঝে copy করা এক বিষয় নয়।

---

## 19. Focus on Understanding, Not Speed

Beginner হিসেবে অন্যদের তুলনায় ধীরে code লেখা স্বাভাবিক।

Programming শেখার সময় প্রথম লক্ষ্য হওয়া উচিত:

- Concept বোঝা।
- সঠিক logic তৈরি করা।
- নিজের code explain করতে পারা।
- Error নিজে debug করার চেষ্টা করা।
- নতুন problem-এ শেখা concept ব্যবহার করা।

Speed ও confidence নিয়মিত practice-এর সঙ্গে ধীরে ধীরে বাড়তে পারে।

একটি problem solve করতে বেশি সময় লাগলে সেটিকে ছোট ধাপে ভাগ করো। প্রয়োজন হলে সহজ problem-এ ফিরে গিয়ে foundation শক্ত করো।

---

## 20. Common Practice Mistakes

| Mistake | Better Approach |
|---|---|
| শুধু tutorial দেখা | নিজে code লিখে practice করা |
| Code মুখস্থ করা | Logic ও behavior বোঝা |
| সব সময় copy-paste করা | Example না দেখে পুনরায় লেখা |
| Error দেখেই code বন্ধ করা | Error message পড়ে debug করা |
| শুধু সহজ problem solve করা | ধীরে ধীরে difficulty বাড়ানো |
| একসঙ্গে অনেক topic শেখা | একটি topic-এর foundation তৈরি করা |
| Practice log না রাখা | Progress ও weak areas track করা |
| শুধু accepted solution-এর ওপর নির্ভর করা | Alternative approach বোঝা |
| Project শুরু করেই বড় feature যোগ করা | Minimum working version থেকে শুরু করা |
| পুরোনো topic revise না করা | নিয়মিত retrieval practice করা |

---

## 21. Suggested Daily Practice Routine

সময় সীমিত থাকলেও একটি ছোট practice session কার্যকর হতে পারে।

### 30-Minute Routine

| Time | Activity |
|---|---|
| 5 minutes | আগের topic revise |
| 10 minutes | নতুন concept বোঝা |
| 10 minutes | নিজে code লেখা বা problem solve |
| 5 minutes | Error review ও progress log |

### 60-Minute Routine

| Time | Activity |
|---|---|
| 10 minutes | Previous topic revision |
| 15 minutes | New concept learning |
| 20 minutes | Coding practice |
| 10 minutes | Problem-solving বা debugging |
| 5 minutes | Summary ও next task |

সময়সূচি নিজের routine অনুযায়ী পরিবর্তন করা যাবে। কোনো দিন বেশি সময় না পেলেও অল্প practice চালিয়ে যাওয়া উপকারী হতে পারে।

---

## 22. Measure Your Progress

Python শেখার অগ্রগতি শুধু কতগুলো chapter পড়েছ তা দিয়ে বিচার করা উচিত নয়।

নিজেকে নিচের প্রশ্নগুলো করো:

- Example না দেখে basic program লিখতে পারি?
- Code run করার আগে output predict করতে পারি?
- Error message পড়ে সমস্যার কারণ খুঁজতে পারি?
- নতুন problem-কে ছোট ধাপে ভাগ করতে পারি?
- আগে শেখা concept একসঙ্গে ব্যবহার করতে পারি?
- নিজের code অন্যকে explain করতে পারি?
- Documentation দেখে নতুন feature শিখতে পারি?
- একটি ছোট project তৈরি ও test করতে পারি?

যে skill-গুলোতে দুর্বলতা থাকবে, সেগুলো পরবর্তী practice plan-এ অন্তর্ভুক্ত করো।

---

## 23. Final Practice Checklist

নিয়মিত practice করার সময় এই checklist অনুসরণ করা যেতে পারে।

### Learning

- [ ] Concept বুঝে পড়েছি।
- [ ] গুরুত্বপূর্ণ syntax practice করেছি।
- [ ] Code run করার আগে output predict করেছি।

### Problem Solving

- [ ] নিজে problem solve করার চেষ্টা করেছি।
- [ ] Problem-টিকে ছোট ধাপে ভাগ করেছি।
- [ ] Solution-এর logic explain করতে পারি।

### Debugging

- [ ] Error message পড়েছি।
- [ ] Error-এর কারণ বোঝার চেষ্টা করেছি।
- [ ] Corrected code আবার run করেছি।

### Progress

- [ ] Practice log update করেছি।
- [ ] Weak topic চিহ্নিত করেছি।
- [ ] প্রয়োজন অনুযায়ী পুরোনো topic revise করেছি।
- [ ] পরবর্তী practice task নির্ধারণ করেছি।

---

## 24. Conclusion

Python শেখার সবচেয়ে গুরুত্বপূর্ণ অংশ হলো ধারাবাহিকভাবে code লেখা, problem solve করা এবং নিজের ভুল থেকে শেখা।

মূল principles:

1. Concept বোঝার পর code লেখো।
2. Copy করার বদলে নিজে implement করার চেষ্টা করো।
3. Output predict করে program run করো।
4. Error message পড়ে debugging শেখো।
5. সহজ problem থেকে কঠিন problem-এ এগোও।
6. নিয়মিত revision করো।
7. Mini project তৈরি করো।
8. Progress track করো।
9. Documentation ও AI-কে learning tool হিসেবে ব্যবহার করো।
10. Speed-এর চেয়ে understanding-কে অগ্রাধিকার দাও।

এই guidelines অনুসরণ করলে ধীরে ধীরে Python syntax, logical thinking, debugging এবং project development-এর দক্ষতা তৈরি করা সম্ভব হবে।

---

## Next Step

পরবর্তী ফাইল: [09. Progress Tracking](09_Progress_Tracking.md)

সেখানে repository-তে শেখার অগ্রগতি কীভাবে track করতে হবে, chapter completion checklist কীভাবে ব্যবহার করতে হবে এবং নিজের skill development কীভাবে মূল্যায়ন করতে হবে, তা বিস্তারিতভাবে সাজানো হবে।
