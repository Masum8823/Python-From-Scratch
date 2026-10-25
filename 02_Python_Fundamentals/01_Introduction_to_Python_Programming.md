# Chapter 02: Python Fundamentals

## 1. Introduction

এই chapter-এ Python programming-এর মৌলিক বিষয়গুলো শেখানো হবে। যারা একেবারে নতুন এবং আগে programming করেনি, তারাও ধাপে ধাপে এই chapter অনুসরণ করতে পারবে।

Python-এর advanced topic শেখার আগে basic concepts পরিষ্কার থাকা জরুরি। কারণ variables, data, statements, expressions এবং program execution-এর ধারণাগুলো পরবর্তী প্রায় সব topic-এ ব্যবহার হবে।

এই chapter-এর প্রতিটি topic আলাদা Markdown file-এ বিস্তারিতভাবে ব্যাখ্যা করা হবে।

## 2. Learning Objectives

এই chapter শেষ করার পর তুমি পারবে:

- Python program-এর basic structure বুঝতে।
- Python syntax ও statements চিনতে।
- `print()` ব্যবহার করে output দেখাতে।
- Comments লিখতে।
- Variables তৈরি ও ব্যবহার করতে।
- Keywords এবং identifiers-এর পার্থক্য বুঝতে।
- Literals ও expressions চিনতে।
- Basic operators ব্যবহার করতে।
- Assignment statement বুঝতে।
- Python-এর indentation ও code block সম্পর্কে জানতে।
- Simple Python program লিখতে ও execute করতে।
- সাধারণ syntax error শনাক্ত করতে।

## 3. Chapter File Structure

```text
02_Python_Fundamentals/
│
├── README.md
│
├── 01_Introduction_to_Python_Programming.md
├── 02_Understanding_Python_Syntax.md
├── 03_Structure_of_a_Python_Program.md
├── 04_Your_First_Python_Program.md
├── 05_Print_Function_and_Output.md
├── 06_Comments_in_Python.md
├── 07_Statements_and_Expressions.md
├── 08_Python_Keywords_and_Reserved_Words.md
├── 09_Identifiers_and_Naming_Rules.md
├── 10_Variables_in_Python.md
├── 11_Variable_Assignment_and_Reassignment.md
├── 12_Multiple_Assignment_and_Unpacking.md
├── 13_Literals_and_Constants.md
├── 14_Basic_Expressions_in_Python.md
├── 15_Introduction_to_Operators.md
├── 16_Operator_Precedence_and_Associativity.md
├── 17_Indentation_and_Code_Blocks.md
├── 18_Case_Sensitivity_and_Whitespace.md
├── 19_Basic_Input_and_Output.md
├── 20_Understanding_Errors_and_Debugging_Basics.md
├── 21_Writing_Clean_and_Readable_Code.md
├── 22_Python_Fundamentals_Practice_Exercises.md
└── 23_Chapter_Review_and_Self_Assessment.md
```

## 4. Topic List

### Part 1: Introduction and Syntax

| No. | File | Topics |
|---|---|---|
| 01 | Introduction to Python Programming | Programming কী, Python code কীভাবে কাজ করে, source code ও execution |
| 02 | Understanding Python Syntax | Syntax, syntax rules, valid ও invalid code |
| 03 | Structure of a Python Program | Python file, program structure, execution order |
| 04 | Your First Python Program | প্রথম program লেখা, run করা ও output বোঝা |
| 05 | Print Function and Output | `print()`, multiple values, `sep` ও `end` |

### Part 2: Basic Programming Concepts

| No. | File | Topics |
|---|---|---|
| 06 | Comments in Python | Single-line comment, documentation-এর প্রাথমিক ধারণা |
| 07 | Statements and Expressions | Statement, expression, evaluation ও execution |
| 08 | Python Keywords and Reserved Words | Keywords কী, `keyword` module, reserved words |
| 09 | Identifiers and Naming Rules | Variable ও function-এর নাম, naming rules |
| 10 | Variables in Python | Variable, value, object ও reference-এর প্রাথমিক ধারণা |
| 11 | Variable Assignment and Reassignment | `=`, assignment, reassignment, chained assignment |
| 12 | Multiple Assignment and Unpacking | একাধিক variable assignment, unpacking-এর পরিচিতি |
| 13 | Literals and Constants | Numeric, string, Boolean, `None` literal ও constants |

### Part 3: Expressions and Code Rules

| No. | File | Topics |
|---|---|---|
| 14 | Basic Expressions in Python | Expression evaluation ও simple calculations |
| 15 | Introduction to Operators | Arithmetic, comparison, logical ও assignment operator-এর পরিচিতি |
| 16 | Operator Precedence and Associativity | Operator-এর priority, evaluation order ও parentheses |
| 17 | Indentation and Code Blocks | Indentation, block structure ও `IndentationError` |
| 18 | Case Sensitivity and Whitespace | Uppercase/lowercase, spaces, tabs ও readability |

### Part 4: Practice and Review

| No. | File | Topics |
|---|---|---|
| 19 | Basic Input and Output | `input()`, output, input-এর প্রাথমিক ব্যবহার |
| 20 | Understanding Errors and Debugging Basics | Syntax error, runtime error, error message পড়া |
| 21 | Writing Clean and Readable Code | Naming, spacing, comments ও readability |
| 22 | Python Fundamentals Practice Exercises | Basic coding problems ও hands-on practice |
| 23 | Chapter Review and Self Assessment | Revision, quiz, coding task ও self-check |

## 5. Recommended Learning Order

Topic-গুলো file number অনুযায়ী পড়বে। বিশেষ করে নিচের বিষয়গুলো ভালোভাবে বুঝে নেবে:

1. Python syntax ও program structure।
2. `print()` এবং comments।
3. Statements ও expressions।
4. Keywords ও identifiers।
5. Variables ও assignment।
6. Literals ও operators।
7. Indentation ও case sensitivity।
8. Input/output এবং basic debugging।

একটি topic না বুঝলে পরের topic-এ যাওয়ার আগে তার code নিজে run করে দেখবে।

## 6. How to Practice

প্রতিটি topic পড়ার পর এই পদ্ধতি অনুসরণ করো:

1. Example code নিজে VS Code-এ লিখবে।
2. Code run করে output দেখবে।
3. Variable বা input-এর value পরিবর্তন করে পরীক্ষা করবে।
4. একটি ছোট program নিজে লিখবে।
5. Error হলে message পড়ে কারণ বের করার চেষ্টা করবে।
6. গুরুত্বপূর্ণ concept নিজের ভাষায় লিখে রাখবে।

উদাহরণ:

```python
student_name = "Masum"
semester = 9

print("Student:", student_name)
print("Semester:", semester)
```

এই code-এ variable তৈরি করা, value assign করা এবং `print()` দিয়ে output দেখানোর প্রাথমিক ধারণা রয়েছে। পরবর্তী topic-গুলোতে প্রতিটি বিষয় আলাদাভাবে বিস্তারিতভাবে শেখানো হবে।

## 7. Chapter Completion Checklist

- [ ] Python syntax ও program structure বুঝি।
- [ ] একটি basic Python program লিখতে ও run করতে পারি।
- [ ] `print()` ও comments ব্যবহার করতে পারি।
- [ ] Statement ও expression-এর পার্থক্য বুঝি।
- [ ] Keywords ও identifiers চিনতে পারি।
- [ ] Variable তৈরি ও reassign করতে পারি।
- [ ] Literals ও constants-এর ধারণা বুঝি।
- [ ] Basic operators ও expressions বুঝি।
- [ ] Indentation ও case sensitivity বুঝি।
- [ ] সাধারণ syntax error শনাক্ত করতে পারি।
- [ ] নিজে basic Python program লিখতে পারি।

## 8. Next Topic

পরবর্তী file:

[`01_Introduction_to_Python_Programming.md`](01_Introduction_to_Python_Programming.md)

এখান থেকে Python programming কী, program কীভাবে execute হয় এবং Python code-এর মূল ধারণাগুলো বিস্তারিতভাবে শেখা শুরু হবে।