# Chapter 05: Input, Output & String Formatting

## 1. Chapter Overview

Python-এ Input ও Output হলো user-এর সঙ্গে program-এর যোগাযোগের অন্যতম প্রধান উপায়।

**Input** ব্যবহার করে program-এর বাইরে থেকে data নেওয়া হয়। আর **Output** ব্যবহার করে program-এর result বা information screen-এ দেখানো হয়।

Python-এ সাধারণত:

- `input()` function দিয়ে user input নেওয়া হয়।
- `print()` function দিয়ে output দেখানো হয়।
- String formatting দিয়ে text-এর মধ্যে variable ও value সুন্দরভাবে উপস্থাপন করা হয়।

এই chapter-এ আমরা basic input/output থেকে শুরু করে formatted output, alignment, number formatting এবং practical examples পর্যন্ত শিখব।

## 2. Learning Objectives

এই chapter শেষ করার পর তুমি পারবে:

- `print()` function ব্যবহার করতে।
- `input()` দিয়ে user-এর কাছ থেকে data নিতে।
- Input-এর data type বুঝতে এবং প্রয়োজনমতো convert করতে।
- একাধিক value একসঙ্গে print করতে।
- `sep` ও `end` parameter ব্যবহার করতে।
- Escape sequence দিয়ে newline, tab ও special character দেখাতে।
- String concatenation ও repetition করতে।
- f-string দিয়ে dynamic output তৈরি করতে।
- `str.format()` ও পুরোনো `%` formatting বুঝতে।
- Decimal places, alignment, width ও padding নিয়ন্ত্রণ করতে।
- User-friendly output তৈরি করতে।
- Input/output-সম্পর্কিত common error সমাধান করতে।

## 3. Complete Topic List

এই chapter-এ মোট ২৮টি planned file থাকবে, README-সহ।

| File No. | Filename | Topic |
|---:|---|---|
| 00 | `README.md` | Chapter Overview and Navigation |
| 01 | `01_Introduction_to_Input_and_Output.md` | Input ও Output-এর পরিচিতি |
| 02 | `02_Understanding_the_print_Function.md` | `print()` function |
| 03 | `03_Printing_Strings_Numbers_and_Variables.md` | String, Number ও Variable print করা |
| 04 | `04_Printing_Multiple_Values.md` | একসঙ্গে একাধিক value print করা |
| 05 | `05_sep_Parameter_in_print.md` | `sep` parameter |
| 06 | `06_end_Parameter_in_print.md` | `end` parameter |
| 07 | `07_Newlines_and_Escape_Sequences.md` | Newline ও Escape Sequence |
| 08 | `08_Formatting_Output_with_print.md` | `print()` দিয়ে output format করা |
| 09 | `09_Understanding_the_input_Function.md` | `input()` function |
| 10 | `10_Input_Returns_a_String.md` | Input কেন string return করে |
| 11 | `11_Type_Conversion_in_User_Input.md` | User input-এর type conversion |
| 12 | `12_Taking_Integer_and_Float_Input.md` | Integer ও Float input নেওয়া |
| 13 | `13_Taking_Multiple_Inputs.md` | একাধিক input নেওয়া |
| 14 | `14_Splitting_and_Unpacking_Input.md` | Input split ও unpack করা |
| 15 | `15_Input_Validation_Basics.md` | Input validation-এর প্রাথমিক ধারণা |
| 16 | `16_String_Concatenation_and_Repetition.md` | String concatenation ও repetition |
| 17 | `17_Introduction_to_String_Formatting.md` | String formatting-এর পরিচিতি |
| 18 | `18_f_Strings_in_Python.md` | f-string |
| 19 | `19_Expressions_and_Functions_in_f_Strings.md` | f-string-এ expression ও function |
| 20 | `20_Formatting_Numbers_with_f_Strings.md` | Number ও decimal formatting |
| 21 | `21_String_Alignment_Width_and_Padding.md` | Alignment, width ও padding |
| 22 | `22_str_format_Method.md` | `str.format()` method |
| 23 | `23_Old_Style_Percent_Formatting.md` | `%` formatting |
| 24 | `24_Formatting_Percentages_Currency_and_Large_Numbers.md` | Percentage, currency ও বড় সংখ্যা |
| 25 | `25_Common_Input_Output_Errors.md` | Input/output-এর common errors |
| 26 | `26_Practical_Input_Output_Programs.md` | বাস্তব উদাহরণ ও ছোট program |
| 27 | `27_Chapter_Practice_and_Self_Assessment.md` | Practice ও Self-assessment |

## 4. Folder Structure

```text
05_Input_Output_and_String_Formatting/
│
├── README.md
├── 01_Introduction_to_Input_and_Output.md
├── 02_Understanding_the_print_Function.md
├── 03_Printing_Strings_Numbers_and_Variables.md
├── 04_Printing_Multiple_Values.md
├── 05_sep_Parameter_in_print.md
├── 06_end_Parameter_in_print.md
├── 07_Newlines_and_Escape_Sequences.md
├── 08_Formatting_Output_with_print.md
├── 09_Understanding_the_input_Function.md
├── 10_Input_Returns_a_String.md
├── 11_Type_Conversion_in_User_Input.md
├── 12_Taking_Integer_and_Float_Input.md
├── 13_Taking_Multiple_Inputs.md
├── 14_Splitting_and_Unpacking_Input.md
├── 15_Input_Validation_Basics.md
├── 16_String_Concatenation_and_Repetition.md
├── 17_Introduction_to_String_Formatting.md
├── 18_f_Strings_in_Python.md
├── 19_Expressions_and_Functions_in_f_Strings.md
├── 20_Formatting_Numbers_with_f_Strings.md
├── 21_String_Alignment_Width_and_Padding.md
├── 22_str_format_Method.md
├── 23_Old_Style_Percent_Formatting.md
├── 24_Formatting_Percentages_Currency_and_Large_Numbers.md
├── 25_Common_Input_Output_Errors.md
├── 26_Practical_Input_Output_Programs.md
└── 27_Chapter_Practice_and_Self_Assessment.md
```

## 5. Recommended Learning Sequence

বিষয়গুলো নিচের ক্রমে শিখবে:

### Phase 1: Output Basics

- `print()` function
- Strings, numbers ও variables print করা
- Multiple values
- `sep` ও `end`
- Escape sequences

### Phase 2: User Input

- `input()` function
- Input-এর data type
- `int()` ও `float()` দিয়ে conversion
- Multiple input
- Splitting ও unpacking
- Basic input validation

### Phase 3: String Formatting

- String concatenation ও repetition
- String formatting-এর প্রয়োজনীয়তা
- f-string
- Expressions ও function calls
- Number formatting
- Alignment, width ও padding
- `str.format()` ও `%` formatting

### Phase 4: Practical Application

- Percentage ও currency format করা
- User input-এর common error সমাধান
- ছোট বাস্তব program তৈরি
- Practice exercises ও self-assessment

## 6. Prerequisites

এই chapter শুরু করার আগে নিচের বিষয়গুলো জানা থাকলে সুবিধা হবে:

- Python variable
- Basic data types: `int`, `float`, `str`, `bool`
- Arithmetic operators
- Type conversion-এর প্রাথমিক ধারণা

এগুলো আগের chapter-গুলোতে আলোচনা করা হয়েছে। কোনো বিষয় ভুলে গেলে সংশ্লিষ্ট আগের note আবার দেখে নিতে পারবে।

## 7. Code Example Convention

এই repository-তে প্রতিটি code example-এর সঙ্গে প্রয়োজনমতো নিচের বিষয়গুলো থাকবে:

1. **Concept:** কী শেখানো হচ্ছে।
2. **Syntax:** কীভাবে লিখতে হয়।
3. **Code:** সম্পূর্ণ runnable example।
4. **Output:** Code চালালে কী দেখা যাবে।
5. **Explanation:** কেন এমন output এসেছে।
6. **Common Mistakes:** নতুনদের সাধারণ ভুল।
7. **Practice:** নিজের শেখা যাচাই করার প্রশ্ন।

`input()`-এর উদাহরণে user কী input দিয়েছে, তা উল্লেখ করা হবে। কারণ input-এর program output user-এর দেওয়া value-এর ওপর নির্ভর করে।

## 8. Important Notes Before Starting

- Python-এর `input()` function সাধারণত `str` return করে।
- Number নিয়ে calculation করতে চাইলে প্রয়োজনমতো `int()` বা `float()` ব্যবহার করতে হবে।
- f-string সাধারণত modern Python code-এ dynamic text তৈরি করার সবচেয়ে সুবিধাজনক উপায়।
- `print()`-এর `sep` parameter value-গুলোর মাঝের separator নিয়ন্ত্রণ করে।
- `end` parameter প্রতিটি `print()` call-এর শেষে কী থাকবে, তা নিয়ন্ত্রণ করে।
- Formatting-এর সময় rounding এবং displayed precision-এর পার্থক্য বুঝতে হবে।
- Currency formatting-এর ক্ষেত্রে শুধু symbol বসালেই currency conversion হয় না।

## 9. Chapter Completion Checklist

- [ ] `print()` দিয়ে output দেখাতে পারি।
- [ ] `input()` দিয়ে user input নিতে পারি।
- [ ] Input-এর type বুঝতে ও convert করতে পারি।
- [ ] একাধিক value input ও output করতে পারি।
- [ ] `sep`, `end` ও escape sequence ব্যবহার করতে পারি।
- [ ] f-string দিয়ে variable ও expression দেখাতে পারি।
- [ ] Decimal places, alignment ও padding format করতে পারি।
- [ ] Common input/output error শনাক্ত করতে পারি।
- [ ] User input ব্যবহার করে ছোট program লিখতে পারি।

## 10. Chapter Navigation

- Previous Chapter: [Chapter 04 — Operators in Python](../04_Operators_in_Python/README.md)
- Current Chapter: Input, Output & String Formatting
- Next Chapter: [Chapter 06 — Conditional Statements](../06_Conditional_Statements/README.md)

পরবর্তী ফাইল: `01_Introduction_to_Input_and_Output.md`

এই chapter-এর প্রতিটি topic ধারাবাহিকভাবে পড়বে, code নিজে run করবে এবং practice questions নিজে solve করার চেষ্টা করবে।