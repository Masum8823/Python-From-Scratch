# Chapter 07: Loops & Iteration

## 1. Chapter Overview

Python-এ **Loop** ব্যবহার করে কোনো code block বারবার execute করা যায়। একই কাজ অনেকবার করতে হলে প্রতিবার একই code না লিখে loop ব্যবহার করা হয়।

উদাহরণস্বরূপ, ১ থেকে ১০ পর্যন্ত number print করতে ১০টি `print()` statement লেখার পরিবর্তে একটি loop ব্যবহার করা যায়।

```python
for number in range(1, 11):
    print(number)
```

এই chapter-এ আমরা basic loop থেকে শুরু করে nested loops এবং loop-based problem solving পর্যন্ত শিখব।

## 2. Learning Objectives

এই chapter শেষ করার পর তুমি পারবে:

- Loop ও iteration-এর ধারণা বুঝতে।
- `while` loop এবং `for` loop ব্যবহার করতে।
- `range()` function দিয়ে নির্দিষ্ট সংখ্যক iteration চালাতে।
- Loop-এর condition ও execution flow বুঝতে।
- `break`, `continue` এবং `pass` ব্যবহার করতে।
- Infinite loop শনাক্ত ও সমাধান করতে।
- Nested loops দিয়ে pattern তৈরি করতে।
- Loop ব্যবহার করে counting, summation ও searching করতে।
- User input-এর সঙ্গে loop ব্যবহার করতে।
- Loop-based programming problems নিজে solve করতে।

## 3. Chapter Topics

### Section A: Loop Fundamentals

1. Introduction to Loops and Iteration
2. Why Loops Are Needed
3. Understanding Repetition in Programming
4. Types of Loops in Python
5. Understanding Loop Execution Flow
6. Loop Control Variables
7. Entry-Controlled and Exit-Controlled Loops
8. Choosing the Right Loop

### Section B: The while Loop

9. Introduction to the while Loop
10. while Loop Syntax and Execution
11. Writing Your First while Loop
12. Loop Conditions and Boolean Expressions
13. Updating Variables Inside a Loop
14. Counter-Controlled while Loops
15. Sentinel-Controlled while Loops
16. Input Validation Using while
17. Infinite while Loops
18. Preventing and Fixing Infinite Loops
19. The else Clause in while Loops

### Section C: The for Loop and range()

20. Introduction to the for Loop
21. for Loop Syntax and Execution
22. Iterating Over Strings
23. Iterating Over Lists and Tuples
24. Iterating Over Sets and Dictionaries
25. Introduction to the range() Function
26. range() with One Argument
27. range() with Start and Stop
28. range() with Step
29. Counting Forward and Backward
30. Common range() Mistakes
31. The else Clause in for Loops

### Section D: Loop Control Statements

32. Introduction to Loop Control Statements
33. The break Statement
34. The continue Statement
35. The pass Statement in Loops
36. break vs continue vs pass
37. Nested Loops and Control Flow

### Section E: Nested Loops and Patterns

38. Introduction to Nested Loops
39. Nested for Loops
40. Nested while Loops
41. Understanding Inner and Outer Loops
42. Multiplication Tables Using Loops
43. Printing Star Patterns
44. Printing Number Patterns
45. Printing Alphabet Patterns
46. Controlling Nested Loops
47. Common Nested Loop Mistakes

### Section F: Practical Loop Programming

48. Counting and Accumulation
49. Finding the Sum of Numbers
50. Finding the Average of Numbers
51. Finding Maximum and Minimum Values
52. Counting Even and Odd Numbers
53. Multiplication Table Programs
54. Factorial Using Loops
55. Fibonacci Series Using Loops
56. Prime Number Checking Using Loops
57. Reversing a Number
58. Finding the Sum of Digits
59. Counting Digits in a Number
60. Palindrome Number Checking
61. Searching Using Loops
62. Loop-Based Menu Programs
63. Using Loops with User Input
64. Combining Loops with Conditional Statements

### Section G: Loop Problem Solving

65. Understanding Loop-Based Problems
66. Dry Running and Tracing Loops
67. Loop Invariants: Basic Introduction
68. Off-by-One Errors
69. Common Loop Errors and Debugging
70. Improving Loop Readability
71. Loop Performance Basics
72. Loop Output Prediction Exercises
73. Loop Programming Exercises
74. Chapter Review and Self-Assessment

## 4. Recommended Folder Structure

```text
07_Loops_and_Iteration/
│
├── README.md
│
├── 01_Introduction_to_Loops_and_Iteration.md
├── 02_Why_Loops_Are_Needed.md
├── 03_Understanding_Repetition_in_Programming.md
├── 04_Types_of_Loops_in_Python.md
├── 05_Understanding_Loop_Execution_Flow.md
├── 06_Loop_Control_Variables.md
├── 07_Entry_Controlled_and_Exit_Controlled_Loops.md
├── 08_Choosing_the_Right_Loop.md
│
├── 09_Introduction_to_the_while_Loop.md
├── 10_while_Loop_Syntax_and_Execution.md
├── 11_Writing_Your_First_while_Loop.md
├── 12_Loop_Conditions_and_Boolean_Expressions.md
├── 13_Updating_Variables_Inside_a_Loop.md
├── 14_Counter_Controlled_while_Loops.md
├── 15_Sentinel_Controlled_while_Loops.md
├── 16_Input_Validation_Using_while.md
├── 17_Infinite_while_Loops.md
├── 18_Preventing_and_Fixing_Infinite_Loops.md
├── 19_The_else_Clause_in_while_Loops.md
│
├── 20_Introduction_to_the_for_Loop.md
├── 21_for_Loop_Syntax_and_Execution.md
├── 22_Iterating_Over_Strings.md
├── 23_Iterating_Over_Lists_and_Tuples.md
├── 24_Iterating_Over_Sets_and_Dictionaries.md
├── 25_Introduction_to_the_range_Function.md
├── 26_range_with_One_Argument.md
├── 27_range_with_Start_and_Stop.md
├── 28_range_with_Step.md
├── 29_Counting_Forward_and_Backward.md
├── 30_Common_range_Mistakes.md
├── 31_The_else_Clause_in_for_Loops.md
│
├── 32_Introduction_to_Loop_Control_Statements.md
├── 33_The_break_Statement.md
├── 34_The_continue_Statement.md
├── 35_The_pass_Statement_in_Loops.md
├── 36_break_vs_continue_vs_pass.md
├── 37_Nested_Loops_and_Control_Flow.md
│
├── 38_Introduction_to_Nested_Loops.md
├── 39_Nested_for_Loops.md
├── 40_Nested_while_Loops.md
├── 41_Understanding_Inner_and_Outer_Loops.md
├── 42_Multiplication_Tables_Using_Loops.md
├── 43_Printing_Star_Patterns.md
├── 44_Printing_Number_Patterns.md
├── 45_Printing_Alphabet_Patterns.md
├── 46_Controlling_Nested_Loops.md
├── 47_Common_Nested_Loop_Mistakes.md
│
├── 48_Counting_and_Accumulation.md
├── 49_Finding_the_Sum_of_Numbers.md
├── 50_Finding_the_Average_of_Numbers.md
├── 51_Finding_Maximum_and_Minimum_Values.md
├── 52_Counting_Even_and_Odd_Numbers.md
├── 53_Multiplication_Table_Programs.md
├── 54_Factorial_Using_Loops.md
├── 55_Fibonacci_Series_Using_Loops.md
├── 56_Prime_Number_Checking_Using_Loops.md
├── 57_Reversing_a_Number.md
├── 58_Finding_the_Sum_of_Digits.md
├── 59_Counting_Digits_in_a_Number.md
├── 60_Palindrome_Number_Checking.md
├── 61_Searching_Using_Loops.md
├── 62_Loop_Based_Menu_Programs.md
├── 63_Using_Loops_with_User_Input.md
├── 64_Combining_Loops_with_Conditional_Statements.md
│
├── 65_Understanding_Loop_Based_Problems.md
├── 66_Dry_Running_and_Tracing_Loops.md
├── 67_Loop_Invariants_Basic_Introduction.md
├── 68_Off_by_One_Errors.md
├── 69_Common_Loop_Errors_and_Debugging.md
├── 70_Improving_Loop_Readability.md
├── 71_Loop_Performance_Basics.md
├── 72_Loop_Output_Prediction_Exercises.md
├── 73_Loop_Programming_Exercises.md
└── 74_Chapter_Review_and_Self_Assessment.md
```

**Note:** এখানে `...` দিয়ে মাঝের topic file-গুলো সংক্ষেপে দেখানো হয়েছে। সম্পূর্ণ topic list উপরের Section 3-এ দেওয়া আছে।

## 5. Learning Method

এই chapter ভালোভাবে শেখার জন্য নিচের পদ্ধতি অনুসরণ করবে:

1. **Understand:** প্রথমে loop কী এবং কেন দরকার, তা বুঝবে।
2. **Trace:** প্রতিটি iteration-এ variable-এর value কীভাবে পরিবর্তিত হচ্ছে, তা দেখবে।
3. **Run:** Code নিজে run করে output যাচাই করবে।
4. **Modify:** Code-এ condition, starting value বা step পরিবর্তন করে ফলাফল দেখবে।
5. **Practice:** প্রতিটি section শেষে নিজে problem solve করবে।
6. **Review:** ভুল হওয়া code আবার লিখবে এবং error-এর কারণ বুঝবে।

## 6. Important Learning Rules

- Loop-এর condition ভালোভাবে বুঝবে।
- `while` loop-এ প্রয়োজন অনুযায়ী control variable update করবে।
- `range()`-এর stop value সাধারণত অন্তর্ভুক্ত হয় না।
- `break` loop থেকে বের হয়ে যায়।
- `continue` বর্তমান iteration-এর বাকি অংশ skip করে পরবর্তী iteration-এ যায়।
- `pass` কোনো কাজ করে না; এটি placeholder হিসেবে ব্যবহৃত হয়।
- Nested loop-এ প্রতিটি inner loop কতবার চলে, তা আলাদাভাবে হিসাব করবে।
- Infinite loop এড়াতে termination condition নিশ্চিত করবে।

## 7. Chapter Completion Criteria

Chapter শেষ হয়েছে বলে ধরে নেওয়ার আগে নিশ্চিত করবে:

- [ ] `while` loop নিজে লিখতে পারি।
- [ ] `for` loop দিয়ে sequence-এর item iterate করতে পারি।
- [ ] `range()`-এর start, stop এবং step বুঝি।
- [ ] `break`, `continue` ও `pass`-এর পার্থক্য জানি।
- [ ] Nested loops দিয়ে simple pattern তৈরি করতে পারি।
- [ ] Sum, average, factorial ও multiplication table-এর মতো problem solve করতে পারি।
- [ ] Loop-এর output manually trace করতে পারি।
- [ ] Infinite loop এবং off-by-one error শনাক্ত করতে পারি।
- [ ] Practice exercises-এর অধিকাংশ নিজে solve করতে পারি।

## 8. Final Note

Loops হলো programming-এর অন্যতম গুরুত্বপূর্ণ foundation। Data processing, automation, algorithms, searching, pattern generation এবং আরও অনেক ক্ষেত্রে loop ব্যবহার করা হয়।

শুরুতে loop-এর প্রতিটি iteration হাতে trace করবে। Practice বাড়লে loop-এর flow এবং variable update স্বাভাবিকভাবেই বুঝতে পারবে।

**Next Topic:** `01_Introduction_to_Loops_and_Iteration.md`
