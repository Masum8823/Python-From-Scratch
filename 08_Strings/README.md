# Chapter 08: Strings in Python

## 1. Chapter Overview

এই chapter-এ Python-এর **String** নিয়ে basic থেকে advanced পর্যন্ত বিস্তারিত শেখানো হবে।

String হলো এক বা একাধিক character-এর sequence। Python-এ text, name, message, email, password এবং অন্যান্য textual data সংরক্ষণের জন্য string ব্যবহার করা হয়।

উদাহরণ:

```python
name = "Masum"
message = "I am learning Python."
```

এখানে `"Masum"` এবং `"I am learning Python."` দুটিই string।

এই chapter-এ আমরা শিখব কীভাবে string তৈরি করতে হয়, character access করতে হয়, string slicing করতে হয়, বিভিন্ন string method ব্যবহার করতে হয় এবং বাস্তব programming problem সমাধান করতে হয়।

## 2. Learning Objectives

এই chapter শেষ করার পর তুমি পারবে:

- String কী এবং কীভাবে কাজ করে তা বুঝতে।
- Single, double এবং triple quotes ব্যবহার করে string তৈরি করতে।
- String indexing ও slicing করতে।
- Negative indexing ব্যবহার করতে।
- String-এর length নির্ণয় করতে।
- String concatenation ও repetition করতে।
- String-এর মধ্যে character বা substring খুঁজতে।
- বিভিন্ন built-in string method ব্যবহার করতে।
- String formatting এবং f-string ব্যবহার করতে।
- String-এর uppercase, lowercase এবং whitespace নিয়ন্ত্রণ করতে।
- String validation ও text processing করতে।
- Immutable string-এর ধারণা বুঝতে।
- Common string errors শনাক্ত ও সমাধান করতে।
- বাস্তব সমস্যা সমাধানে string ব্যবহার করতে।

## 3. Chapter File Structure

```text
08_Strings/
│
├── README.md
├── 01_Introduction_to_Strings.md
├── 02_Why_Strings_Are_Important.md
├── 03_Creating_Strings_in_Python.md
├── 04_Single_Double_and_Triple_Quotes.md
├── 05_Strings_with_Quotes_and_Escape_Characters.md
├── 06_Multiline_Strings.md
├── 07_String_Length_with_len.md
├── 08_String_Indexing.md
├── 09_Negative_String_Indexing.md
├── 10_Accessing_Characters_from_Strings.md
├── 11_String_Slicing_Basics.md
├── 12_String_Slicing_with_Start_and_Stop.md
├── 13_String_Slicing_with_Step.md
├── 14_Negative_Slicing_and_Reverse_Strings.md
├── 15_Common_String_Indexing_and_Slicing_Mistakes.md
├── 16_String_Immutability.md
├── 17_String_Concatenation.md
├── 18_String_Repetition.md
├── 19_Checking_Substrings_with_in_and_not_in.md
├── 20_Finding_Substrings_with_find_and_index.md
├── 21_Counting_Substrings_with_count.md
├── 22_String_Comparison.md
├── 23_String_Iteration_with_for_Loops.md
├── 24_String_Iteration_with_while_Loops.md
├── 25_Changing_Case_upper_lower_title_capitalize.md
├── 26_Case_Insensitive_String_Comparison.md
├── 27_Removing_Whitespace_with_strip_methods.md
├── 28_Replacing_Text_with_replace.md
├── 29_Splitting_Strings_with_split.md
├── 30_Joining_Strings_with_join.md
├── 31_String_Prefix_and_Suffix_Checking.md
├── 32_String_Testing_Methods_isalpha_isdigit_etc.md
├── 33_String_Alignment_and_Padding.md
├── 34_Escape_Sequences_in_Strings.md
├── 35_Raw_Strings_in_Python.md
├── 36_String_Formatting_with_f_Strings.md
├── 37_Formatting_Numbers_inside_Strings.md
├── 38_String_format_Method.md
├── 39_Old_Style_String_Formatting.md
├── 40_String_Encoding_and_Unicode_Basics.md
├── 41_Bytes_vs_Strings.md
├── 42_Converting_Between_Strings_and_Other_Types.md
├── 43_Parsing_and_Validating_Text.md
├── 44_Removing_or_Keeping_Specific_Characters.md
├── 45_Counting_Vowels_Consonants_and_Digits.md
├── 46_Reversing_and_Palindrome_Strings.md
├── 47_Finding_Duplicate_Characters.md
├── 48_Frequency_of_Characters.md
├── 49_Word_Counting_and_Word_Processing.md
├── 50_Extracting_Information_from_Strings.md
├── 51_String_Comprehensions_and_Generator_Expressions.md
├── 52_Regular_Expressions_Introduction.md
├── 53_Common_String_Errors_and_Debugging.md
├── 54_String_Performance_and_Best_Practices.md
├── 55_String_Output_Prediction_Exercises.md
├── 56_String_Programming_Exercises.md
└── 57_Chapter_Review_and_Self_Assessment.md
```

## 4. Topic Guide

### Section A: String Fundamentals

| File | Topic |
|---|---|
| 01 | Introduction to Strings |
| 02 | Why Strings Are Important |
| 03 | Creating Strings in Python |
| 04 | Single, Double and Triple Quotes |
| 05 | Strings with Quotes and Escape Characters |
| 06 | Multiline Strings |
| 07 | String Length with `len()` |

### Section B: Indexing, Slicing and Immutability

| File | Topic |
|---|---|
| 08 | String Indexing |
| 09 | Negative String Indexing |
| 10 | Accessing Characters from Strings |
| 11 | String Slicing Basics |
| 12 | Slicing with Start and Stop |
| 13 | Slicing with Step |
| 14 | Negative Slicing and Reversing Strings |
| 15 | Common Indexing and Slicing Mistakes |
| 16 | String Immutability |

### Section C: Basic String Operations

| File | Topic |
|---|---|
| 17 | String Concatenation |
| 18 | String Repetition |
| 19 | Checking Substrings with `in` and `not in` |
| 20 | Finding Substrings with `find()` and `index()` |
| 21 | Counting Substrings with `count()` |
| 22 | String Comparison |
| 23 | String Iteration with `for` Loops |
| 24 | String Iteration with `while` Loops |

### Section D: Important String Methods

| File | Topic |
|---|---|
| 25 | `upper()`, `lower()`, `title()` and `capitalize()` |
| 26 | Case-Insensitive String Comparison |
| 27 | Removing Whitespace with `strip()` Methods |
| 28 | Replacing Text with `replace()` |
| 29 | Splitting Strings with `split()` |
| 30 | Joining Strings with `join()` |
| 31 | Prefix and Suffix Checking |
| 32 | String Testing Methods |
| 33 | String Alignment and Padding |

### Section E: Advanced String Concepts

| File | Topic |
|---|---|
| 34 | Escape Sequences |
| 35 | Raw Strings |
| 36 | String Formatting with f-Strings |
| 37 | Formatting Numbers Inside Strings |
| 38 | `str.format()` Method |
| 39 | Old-Style String Formatting |
| 40 | Encoding and Unicode Basics |
| 41 | Bytes vs Strings |
| 42 | Converting Between Strings and Other Types |

### Section F: String Problem Solving

| File | Topic |
|---|---|
| 43 | Parsing and Validating Text |
| 44 | Removing or Keeping Specific Characters |
| 45 | Counting Vowels, Consonants and Digits |
| 46 | Reversing and Checking Palindrome Strings |
| 47 | Finding Duplicate Characters |
| 48 | Character Frequency |
| 49 | Word Counting and Word Processing |
| 50 | Extracting Information from Strings |
| 51 | String Comprehensions and Generator Expressions |
| 52 | Introduction to Regular Expressions |

### Section G: Practice and Review

| File | Topic |
|---|---|
| 53 | Common String Errors and Debugging |
| 54 | String Performance and Best Practices |
| 55 | String Output Prediction Exercises |
| 56 | String Programming Exercises |
| 57 | Chapter Review and Self-Assessment |

## 5. Prerequisites

এই chapter শুরু করার আগে নিচের বিষয়গুলো জানা থাকলে সুবিধা হবে:

- Variables and assignment
- Basic data types
- `print()` and `input()`
- Type conversion
- Operators
- Conditional statements
- `for` and `while` loops
- Basic functions

কোনো topic পুরোপুরি মনে না থাকলে আগের chapter-এর notes দেখে নিতে পারো।

## 6. Recommended Learning Method

প্রতিটি topic শেখার সময়:

1. প্রথমে concept এবং syntax বুঝে নাও।
2. Code নিজে টাইপ করে run করো।
3. Output দেখার আগে predict করো।
4. String পরিবর্তন করে বিভিন্ন input দিয়ে পরীক্ষা করো।
5. Indexing ও slicing-এর ক্ষেত্রে প্রতিটি character-এর index লিখে practice করো।
6. Common mistakes বুঝে নাও।
7. Practice exercises নিজে সমাধান করো।

## 7. Important Rules to Remember

- Python-এ string হলো text-এর sequence।
- String single quotes (`' '`), double quotes (`" "`) অথবা triple quotes দিয়ে তৈরি করা যায়।
- Indexing শূন্য (`0`) থেকে শুরু হয়।
- Negative indexing শেষ character থেকে `-1` দিয়ে শুরু হয়।
- Slicing-এ stop index অন্তর্ভুক্ত হয় না।
- Python string immutable; তৈরি হওয়ার পরে string-এর character সরাসরি পরিবর্তন করা যায় না।
- `+` দিয়ে string concatenation এবং `*` দিয়ে repetition করা যায়।
- `in` দিয়ে substring আছে কি না পরীক্ষা করা যায়।
- String methods সাধারণত নতুন string ফেরত দেয়; মূল string পরিবর্তন করে না।
- `split()` string-কে list-এ ভাগ করে এবং `join()` iterable-এর string-গুলো যুক্ত করে।
- Python 3-এ string Unicode text সংরক্ষণ করে।
- String এবং bytes এক জিনিস নয়।

## 8. Chapter Completion Checklist

- [ ] String তৈরি করতে পারি।
- [ ] Indexing ও slicing বুঝি।
- [ ] String immutable কেন তা ব্যাখ্যা করতে পারি।
- [ ] String methods ব্যবহার করতে পারি।
- [ ] Text search, split ও join করতে পারি।
- [ ] f-string দিয়ে output format করতে পারি।
- [ ] Unicode এবং bytes-এর basic ধারণা বুঝি।
- [ ] String problem-solving programs লিখতে পারি।
- [ ] Output prediction ও programming exercises সমাধান করতে পারি।

## 9. First Topic

`01_Introduction_to_Strings.md`

পরবর্তী file-এ string-এর ধারণা, বাস্তব জীবনের ব্যবহার, character ও sequence-এর পার্থক্য এবং Python code example দিয়ে বিষয়টি একদম basic থেকে ব্যাখ্যা করা হবে।