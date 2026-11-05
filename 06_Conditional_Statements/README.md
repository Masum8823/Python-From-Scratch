# Chapter 06: Conditional Statements in Python

## 1. Chapter Overview

এই chapter-এ Python-এর **Conditional Statements** বা decision-making system শেখানো হবে।

প্রোগ্রাম লেখার সময় অনেক ক্ষেত্রে কোনো condition সত্য নাকি মিথ্যা, তার ওপর ভিত্তি করে আলাদা কাজ করতে হয়। Python-এ `if`, `elif` এবং `else` ব্যবহার করে এই decision নেওয়া হয়।

উদাহরণ:

```python
age = int(input("Enter your age: "))

if age >= 18:
    print("You are an adult.")
else:
    print("You are not an adult yet.")
```

এখানে `age >= 18` condition সত্য হলে প্রথম message দেখাবে। অন্যথায় `else` block-এর message দেখাবে।

## 2. Learning Objectives

এই chapter শেষ করার পর তুমি পারবে:

- Conditional statements কী এবং কেন ব্যবহার করা হয় তা বুঝতে।
- `if`, `else` এবং `elif` ব্যবহার করতে।
- Comparison ও logical operators দিয়ে condition তৈরি করতে।
- একাধিক condition যাচাই করতে।
- Nested conditions লিখতে।
- Conditional expression বা ternary expression ব্যবহার করতে।
- Truthy ও falsy values দিয়ে condition evaluate করতে।
- Common conditional errors শনাক্ত ও সমাধান করতে।
- বাস্তব সমস্যার জন্য decision-based Python programs তৈরি করতে।

## 3. Chapter File Structure

প্রতিটি numbered file একটি নির্দিষ্ট topic বিস্তারিতভাবে ব্যাখ্যা করবে। উদাহরণ, code output, common mistakes এবং practice exercises থাকবে যেখানে প্রাসঙ্গিক।

```text
06_Conditional_Statements/
│
├── README.md
├── 01_Introduction_to_Conditional_Statements.md
├── 02_Why_Conditional_Statements_Are_Needed.md
├── 03_Conditions_and_Boolean_Expressions.md
├── 04_Comparison_Operators_in_Conditions.md
├── 05_The_if_Statement.md
├── 06_Indentation_and_Code_Blocks_in_Conditions.md
├── 07_The_if_else_Statement.md
├── 08_The_elif_Statement.md
├── 09_Multiple_Conditions_with_elif.md
├── 10_Nested_if_Statements.md
├── 11_Logical_Operators_in_Conditions.md
├── 12_Combining_Conditions_with_and.md
├── 13_Combining_Conditions_with_or.md
├── 14_Using_not_in_Conditions.md
├── 15_Operator_Precedence_in_Conditions.md
├── 16_Truthiness_and_Falsy_Values.md
├── 17_Conditional_Expressions_Ternary_Operator.md
├── 18_Nested_Conditional_Expressions.md
├── 19_Membership_Operators_in_Conditions.md
├── 20_Identity_Operators_in_Conditions.md
├── 21_Chained_Comparisons_in_Conditions.md
├── 22_Match_Case_Statement.md
├── 23_Choosing_between_if_elif_and_match_case.md
├── 24_Conditional_Statements_with_User_Input.md
├── 25_Input_Validation_with_Conditions.md
├── 26_Common_Conditional_Statement_Errors.md
├── 27_Debugging_Conditional_Logic.md
├── 28_Practical_Conditional_Programs.md
├── 29_Conditional_Problem_Solving_Techniques.md
├── 30_Conditional_Output_Prediction_Exercises.md
├── 31_Conditional_Programming_Exercises.md
└── 32_Chapter_Review_and_Self_Assessment.md
```

## 4. Topic Guide

### Section A: Fundamentals

| File | Topic                                     |
| ---- | ----------------------------------------- |
| 01   | Introduction to Conditional Statements    |
| 02   | Why Conditional Statements Are Needed     |
| 03   | Conditions and Boolean Expressions        |
| 04   | Comparison Operators in Conditions        |
| 05   | The `if` Statement                        |
| 06   | Indentation and Code Blocks in Conditions |
| 07   | The `if-else` Statement                   |
| 08   | The `elif` Statement                      |
| 09   | Multiple Conditions with `elif`           |

### Section B: Multiple and Logical Conditions

| File | Topic                             |
| ---- | --------------------------------- |
| 10   | Nested `if` Statements            |
| 11   | Logical Operators in Conditions   |
| 12   | Combining Conditions with `and`   |
| 13   | Combining Conditions with `or`    |
| 14   | Using `not` in Conditions         |
| 15   | Operator Precedence in Conditions |
| 16   | Truthiness and Falsy Values       |

### Section C: Advanced Conditional Features

| File | Topic                                          |
| ---- | ---------------------------------------------- |
| 17   | Conditional Expressions (Ternary Operator)     |
| 18   | Nested Conditional Expressions                 |
| 19   | Membership Operators in Conditions             |
| 20   | Identity Operators in Conditions               |
| 21   | Chained Comparisons in Conditions              |
| 22   | `match-case` Statement                         |
| 23   | Choosing between `if`, `elif` and `match-case` |

### Section D: Practical Applications

| File | Topic                                   |
| ---- | --------------------------------------- |
| 24   | Conditional Statements with User Input  |
| 25   | Input Validation with Conditions        |
| 26   | Common Conditional Statement Errors     |
| 27   | Debugging Conditional Logic             |
| 28   | Practical Conditional Programs          |
| 29   | Conditional Problem-Solving Techniques  |
| 30   | Conditional Output Prediction Exercises |
| 31   | Conditional Programming Exercises       |
| 32   | Chapter Review and Self-Assessment      |

## 5. Prerequisites

এই chapter শুরু করার আগে আগের chapters-এর নিচের topics জানা থাকলে সুবিধা হবে:

- Variables and assignment
- Basic data types: `int`, `float`, `str`, `bool`
- Type conversion
- Comparison operators: `==`, `!=`, `>`, `<`, `>=`, `<=`
- Logical operators: `and`, `or`, `not`
- User input with `input()`
- Output formatting with `print()` and f-strings
- Indentation and basic Python syntax

কোনো topic পুরোপুরি মনে না থাকলে সংশ্লিষ্ট আগের notes দেখে নিতে পারো।

## 6. Recommended Learning Method

প্রতিটি topic শেখার সময় এই ধাপগুলো অনুসরণ করো:

1. প্রথমে concept ও syntax বুঝে নাও।
2. Code example নিজে টাইপ করে run করো।
3. Output দেখার আগে নিজে predict করার চেষ্টা করো।
4. Condition পরিবর্তন করে বিভিন্ন input দিয়ে পরীক্ষা করো।
5. Common mistakes দেখে ভুলগুলো বুঝে নাও।
6. Practice exercises সমাধান করো।
7. Topic শেষ হলে নিজের ভাষায় মূল ধারণাটি ব্যাখ্যা করার চেষ্টা করো।

## 7. Important Rules to Remember

- `if` condition-এর পরে colon (`:`) দিতে হয়।
- Condition সত্য হলে সংশ্লিষ্ট block execute হয়।
- Python-এ indentation code block নির্ধারণ করে।
- `elif` একাধিক alternative condition পরীক্ষা করতে সাহায্য করে।
- `else` কোনো আগের condition সত্য না হলে default block হিসেবে কাজ করে।
- `==` value equality পরীক্ষা করে; `=` assignment-এর জন্য ব্যবহৃত হয়।
- `and`, `or` ও `not` দিয়ে complex conditions তৈরি করা যায়।
- একাধিক condition থাকলে operator precedence বুঝতে হবে।
- `match-case` Python 3.10 বা পরবর্তী version-এ পাওয়া যায়।
- Input validation-এর সময় type ও allowed range—দুটিই বিবেচনা করতে হয়।

## 8. Chapter Completion Checklist

Chapter শেষ হলে নিশ্চিত হবে যে তুমি:

- [ ] `if`, `else` ও `elif` লিখতে পারো।
- [ ] একাধিক condition তৈরি করতে পারো।
- [ ] Nested conditions বুঝতে পারো।
- [ ] `and`, `or`, `not` ব্যবহার করতে পারো।
- [ ] Truthy ও falsy values চিনতে পারো।
- [ ] Ternary expression বুঝতে পারো।
- [ ] `match-case`-এর basic syntax জানো।
- [ ] Conditional logic-এর ভুল শনাক্ত করতে পারো।
- [ ] User input যাচাই করতে পারো।
- [ ] নিজে decision-based Python programs তৈরি করতে পারো।

## 9. Next Topic

প্রথম topic:

`01_Introduction_to_Conditional_Statements.md`

এই file-এ conditional statements-এর মূল ধারণা, বাস্তব জীবনের decision-making উদাহরণ, Python code, execution flow এবং practice exercises বিস্তারিতভাবে শেখানো হবে।
