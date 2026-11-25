# Chapter 09: Built-in Data Structures in Python

## 1. Chapter Overview

এই chapter-এ Python-এর **Built-in Data Structures** নিয়ে basic থেকে advanced পর্যন্ত বিস্তারিত শেখানো হবে।

Data Structure হলো এমন একটি পদ্ধতি যার মাধ্যমে programming-এ data সংরক্ষণ, সাজানো এবং পরিচালনা করা হয়।

Python-এ চারটি গুরুত্বপূর্ণ built-in data structures রয়েছে:

1. **List:** একাধিক item একটি collection-এ সংরক্ষণ করে। এটি mutable।
2. **Tuple:** একাধিক item সংরক্ষণ করে। এটি immutable।
3. **Set:** Unique item সংরক্ষণ করে এবং duplicate item রাখে না।
4. **Dictionary:** Key-value pair আকারে data সংরক্ষণ করে।

উদাহরণ:

```python
# List
students = ["Masum", "Rahim", "Karim"]

# Tuple
coordinates = (10, 20, 30)

# Set
numbers = {1, 2, 3, 4}

# Dictionary
student = {
    "name": "Masum",
    "age": 22,
    "department": "CSE"
}
```

এই chapter-এ আমরা শিখব কীভাবে এই চারটি data structure তৈরি করতে হয়, data access ও modify করতে হয়, বিভিন্ন built-in method ব্যবহার করতে হয় এবং বাস্তব programming problem সমাধান করতে হয়।

---

## 2. Learning Objectives

এই chapter শেষ করার পর তুমি পারবে:

- Built-in Data Structures কী এবং কেন ব্যবহার করা হয় তা বুঝতে।
- List, Tuple, Set এবং Dictionary-এর মধ্যে পার্থক্য বুঝতে।
- List তৈরি, access, modify এবং delete করতে।
- Positive ও negative indexing ব্যবহার করতে।
- List slicing করতে।
- List-এর বিভিন্ন built-in method ব্যবহার করতে।
- List sorting এবং reversing করতে।
- Nested list তৈরি এবং ব্যবহার করতে।
- List comprehension ব্যবহার করতে।
- Tuple তৈরি এবং access করতে।
- Tuple unpacking করতে।
- Tuple-এর built-in methods ব্যবহার করতে।
- Set তৈরি এবং পরিচালনা করতে।
- Set-এর union, intersection, difference এবং symmetric difference করতে।
- Set methods ব্যবহার করতে।
- Dictionary তৈরি, access, update এবং delete করতে।
- Dictionary-এর keys, values এবং items ব্যবহার করতে।
- Dictionary methods ব্যবহার করতে।
- Nested dictionary তৈরি এবং পরিচালনা করতে।
- Dictionary comprehension ব্যবহার করতে।
- Mutable এবং immutable data structures বুঝতে।
- Shallow copy এবং deep copy-এর basic ধারণা বুঝতে।
- বিভিন্ন data structure-এর মধ্যে conversion করতে।
- বাস্তব programming problem সমাধান করতে।

---

## 3. Chapter File Structure

```text
09_Built_in_Data_Structures/
│
├── README.md
│
├── 01_Introduction_to_Built_in_Data_Structures.md
├── 02_Why_Data_Structures_Are_Important.md
├── 03_Types_of_Built_in_Data_Structures.md
├── 04_List_Tuple_Set_and_Dictionary_Comparison.md
│
├── 05_Introduction_to_Lists.md
├── 06_Creating_Lists_in_Python.md
├── 07_Accessing_List_Elements.md
├── 08_Positive_and_Negative_List_Indexing.md
├── 09_List_Slicing_Basics.md
├── 10_Modifying_List_Elements.md
├── 11_Adding_Elements_to_Lists_append_and_insert.md
├── 12_Extending_Lists_with_extend.md
├── 13_Removing_Elements_from_Lists.md
├── 14_List_Methods_remove_pop_and_clear.md
├── 15_List_Searching_with_in_and_not_in.md
├── 16_Finding_List_Elements_with_index.md
├── 17_Counting_List_Elements_with_count.md
├── 18_Sorting_Lists_with_sort_and_sorted.md
├── 19_Reversing_Lists.md
├── 20_Copying_Lists.md
├── 21_List_Concatenation_and_Repetition.md
├── 22_List_Iteration_with_for_and_while_Loops.md
├── 23_Nested_Lists_in_Python.md
├── 24_Accessing_Elements_from_Nested_Lists.md
├── 25_List_Comprehension_Basics.md
├── 26_List_Comprehension_with_Conditions.md
├── 27_Nested_List_Comprehension.md
├── 28_List_Unpacking.md
├── 29_List_Shortcuts_and_Common_Operations.md
│
├── 30_Introduction_to_Tuples.md
├── 31_Creating_Tuples_in_Python.md
├── 32_Accessing_Tuple_Elements.md
├── 33_Tuple_Indexing_and_Slicing.md
├── 34_Tuple_Immutability.md
├── 35_Tuple_Methods_count_and_index.md
├── 36_Tuple_Packing_and_Unpacking.md
├── 37_Tuple_Unpacking_with_Asterisk.md
├── 38_Swapping_Variables_with_Tuples.md
├── 39_Nested_Tuples_in_Python.md
├── 40_Using_Tuples_as_Dictionary_Keys.md
├── 41_Tuple_vs_List.md
│
├── 42_Introduction_to_Sets.md
├── 43_Creating_Sets_in_Python.md
├── 44_Unique_Elements_and_Duplicate_Removal.md
├── 45_Accessing_and_Iterating_Set_Elements.md
├── 46_Adding_Elements_to_Sets.md
├── 47_Removing_Elements_from_Sets.md
├── 48_Set_Methods_add_update_remove_and_discard.md
├── 49_Set_Union.md
├── 50_Set_Intersection.md
├── 51_Set_Difference.md
├── 52_Set_Symmetric_Difference.md
├── 53_Set_Comparison_and_Relationships.md
├── 54_Frozen_Sets_in_Python.md
├── 55_Set_Comprehension.md
├── 56_Set_vs_List_and_Tuple.md
│
├── 57_Introduction_to_Dictionaries.md
├── 58_Creating_Dictionaries_in_Python.md
├── 59_Accessing_Dictionary_Values.md
├── 60_Accessing_Keys_and_Values.md
├── 61_Adding_and_Updating_Dictionary_Items.md
├── 62_Removing_Dictionary_Items.md
├── 63_Dictionary_Methods_get_keys_values_and_items.md
├── 64_Dictionary_Methods_pop_popitem_and_clear.md
├── 65_Dictionary_Methods_update_setdefault_and_copy.md
├── 66_Checking_Dictionary_Membership.md
├── 67_Dictionary_Iteration_with_Loops.md
├── 68_Nested_Dictionaries_in_Python.md
├── 69_Accessing_and_Modifying_Nested_Dictionaries.md
├── 70_Dictionary_Comprehension.md
├── 71_Dictionary_Unpacking_and_Merging.md
├── 72_Dictionary_Sorting_and_Filtering.md
├── 73_Dictionary_vs_List_and_Tuple.md
│
├── 74_Mutable_vs_Immutable_Data_Structures.md
├── 75_Shallow_Copy_vs_Deep_Copy.md
├── 76_Converting_Between_Data_Structures.md
├── 77_Iterating_Through_Different_Data_Structures.md
├── 78_Nested_Data_Structures_in_Real_Programs.md
├── 79_Data_Structure_Performance_Basics.md
├── 80_Common_Data_Structure_Errors_and_Debugging.md
├── 81_Data_Structure_Best_Practices.md
├── 82_Data_Structure_Output_Prediction_Exercises.md
├── 83_Data_Structure_Programming_Exercises.md
└── 84_Chapter_Review_and_Self_Assessment.md
```

---

## 4. Topic Guide

### Section A: Introduction to Built-in Data Structures

| File | Topic |
|---|---|
| 01 | Introduction to Built-in Data Structures |
| 02 | Why Data Structures Are Important |
| 03 | Types of Built-in Data Structures |
| 04 | List, Tuple, Set and Dictionary Comparison |

### Section B: Lists in Python

| File | Topic |
|---|---|
| 05 | Introduction to Lists |
| 06 | Creating Lists in Python |
| 07 | Accessing List Elements |
| 08 | Positive and Negative List Indexing |
| 09 | List Slicing Basics |
| 10 | Modifying List Elements |
| 11 | Adding Elements with `append()` and `insert()` |
| 12 | Extending Lists with `extend()` |
| 13 | Removing Elements from Lists |
| 14 | `remove()`, `pop()` and `clear()` |
| 15 | Searching Lists with `in` and `not in` |
| 16 | Finding Elements with `index()` |
| 17 | Counting Elements with `count()` |
| 18 | Sorting Lists with `sort()` and `sorted()` |
| 19 | Reversing Lists |
| 20 | Copying Lists |
| 21 | List Concatenation and Repetition |
| 22 | List Iteration with `for` and `while` Loops |
| 23 | Nested Lists |
| 24 | Accessing Elements from Nested Lists |
| 25 | List Comprehension Basics |
| 26 | List Comprehension with Conditions |
| 27 | Nested List Comprehension |
| 28 | List Unpacking |
| 29 | List Shortcuts and Common Operations |

### Section C: Tuples in Python

| File | Topic |
|---|---|
| 30 | Introduction to Tuples |
| 31 | Creating Tuples in Python |
| 32 | Accessing Tuple Elements |
| 33 | Tuple Indexing and Slicing |
| 34 | Tuple Immutability |
| 35 | Tuple Methods: `count()` and `index()` |
| 36 | Tuple Packing and Unpacking |
| 37 | Tuple Unpacking with Asterisk |
| 38 | Swapping Variables with Tuples |
| 39 | Nested Tuples |
| 40 | Using Tuples as Dictionary Keys |
| 41 | Tuple vs List |

### Section D: Sets in Python

| File | Topic |
|---|---|
| 42 | Introduction to Sets |
| 43 | Creating Sets in Python |
| 44 | Unique Elements and Duplicate Removal |
| 45 | Accessing and Iterating Set Elements |
| 46 | Adding Elements to Sets |
| 47 | Removing Elements from Sets |
| 48 | `add()`, `update()`, `remove()` and `discard()` |
| 49 | Set Union |
| 50 | Set Intersection |
| 51 | Set Difference |
| 52 | Set Symmetric Difference |
| 53 | Set Comparison and Relationships |
| 54 | Frozen Sets |
| 55 | Set Comprehension |
| 56 | Set vs List and Tuple |

### Section E: Dictionaries in Python

| File | Topic |
|---|---|
| 57 | Introduction to Dictionaries |
| 58 | Creating Dictionaries in Python |
| 59 | Accessing Dictionary Values |
| 60 | Accessing Keys and Values |
| 61 | Adding and Updating Dictionary Items |
| 62 | Removing Dictionary Items |
| 63 | `get()`, `keys()`, `values()` and `items()` |
| 64 | `pop()`, `popitem()` and `clear()` |
| 65 | `update()`, `setdefault()` and `copy()` |
| 66 | Checking Dictionary Membership |
| 67 | Dictionary Iteration with Loops |
| 68 | Nested Dictionaries |
| 69 | Accessing and Modifying Nested Dictionaries |
| 70 | Dictionary Comprehension |
| 71 | Dictionary Unpacking and Merging |
| 72 | Dictionary Sorting and Filtering |
| 73 | Dictionary vs List and Tuple |

### Section F: Advanced Data Structure Concepts

| File | Topic |
|---|---|
| 74 | Mutable vs Immutable Data Structures |
| 75 | Shallow Copy vs Deep Copy |
| 76 | Converting Between Data Structures |
| 77 | Iterating Through Different Data Structures |
| 78 | Nested Data Structures in Real Programs |
| 79 | Data Structure Performance Basics |
| 80 | Common Data Structure Errors and Debugging |
| 81 | Data Structure Best Practices |

### Section G: Practice and Review

| File | Topic |
|---|---|
| 82 | Data Structure Output Prediction Exercises |
| 83 | Data Structure Programming Exercises |
| 84 | Chapter Review and Self-Assessment |

---

## 5. Prerequisites

এই chapter শুরু করার আগে নিচের বিষয়গুলো জানা থাকলে সুবিধা হবে:

- Variables and Assignment
- Basic Data Types
- Numbers and Strings
- Input and Output
- Type Conversion
- Operators
- Conditional Statements
- `for` and `while` Loops
- Basic Functions
- String Indexing and Slicing

কোনো topic পুরোপুরি মনে না থাকলে আগের chapter-এর notes দেখে নিতে পারো।

---

## 6. Recommended Learning Method

প্রতিটি topic শেখার সময়:

1. প্রথমে concept এবং syntax বুঝে নাও।
2. Python code নিজে টাইপ করে run করো।
3. Output দেখার আগে predict করো।
4. List, Tuple, Set এবং Dictionary-এর মধ্যে পার্থক্য বোঝার চেষ্টা করো।
5. বিভিন্ন built-in method নিজে ব্যবহার করো।
6. Code পরিবর্তন করে বিভিন্ন input দিয়ে পরীক্ষা করো।
7. Nested data structures এবং comprehension practice করো।
8. Common mistakes বুঝে নাও।
9. Practice exercises নিজে solve করার চেষ্টা করো।

---

## 7. Important Rules to Remember

- List হলো ordered এবং mutable।
- Tuple হলো ordered এবং immutable।
- Set duplicate elements রাখে না।
- Set-এর elements-এর কোনো fixed positional order নেই।
- Dictionary data-কে key-value pair আকারে সংরক্ষণ করে।
- Dictionary key unique এবং hashable হতে হয়।
- List এবং Tuple indexing support করে।
- Set indexing support করে না।
- List-এ একই element একাধিকবার থাকতে পারে।
- Tuple-এও duplicate element থাকতে পারে।
- Set-এ duplicate element রাখা যায় না।
- Dictionary-তে duplicate key রাখা যায় না।
- `append()` একটি element যোগ করে।
- `extend()` একটি iterable-এর elements যোগ করে।
- `insert()` নির্দিষ্ট position-এ element যোগ করে।
- `pop()` element remove করে এবং সেটি return করে।
- `remove()` নির্দিষ্ট value remove করে।
- `sort()` মূল list পরিবর্তন করে।
- `sorted()` একটি নতুন sorted list return করে।
- `copy()` দিয়ে shallow copy তৈরি করা যায়।
- `clear()` collection-এর সব element remove করে।
- `set()` দিয়ে list বা tuple থেকে unique elements তৈরি করা যায়।
- `dict()` দিয়ে dictionary তৈরি করা যায়।
- List comprehension দিয়ে সহজে নতুন list তৈরি করা যায়।
- Dictionary comprehension দিয়ে নতুন dictionary তৈরি করা যায়।
- Mutable object পরিবর্তন করা যায়, কিন্তু immutable object সরাসরি পরিবর্তন করা যায় না।

---

## 8. Comparison of Built-in Data Structures

| Feature | List | Tuple | Set | Dictionary |
|---|---|---|---|---|
| Syntax | `[]` | `()` | `{}` | `{key: value}` |
| Ordered | Yes | Yes | No fixed order | Yes |
| Mutable | Yes | No | Yes | Yes |
| Duplicates | Yes | Yes | No | Keys: No |
| Indexing | Yes | Yes | No | Key-based |
| Main Use | Collection | Fixed collection | Unique items | Key-value data |

**Note:** Dictionary-এর keys unique হতে হয়, তবে values duplicate হতে পারে।

---

## 9. Chapter Completion Checklist

### List

- [ ] List তৈরি করতে পারি।
- [ ] List indexing ও slicing বুঝি।
- [ ] List-এর element add, modify এবং delete করতে পারি।
- [ ] List-এর built-in methods ব্যবহার করতে পারি।
- [ ] List sorting এবং reversing করতে পারি।
- [ ] Nested list ব্যবহার করতে পারি।
- [ ] List comprehension লিখতে পারি।

### Tuple

- [ ] Tuple তৈরি করতে পারি।
- [ ] Tuple indexing ও slicing করতে পারি।
- [ ] Tuple immutability বুঝি।
- [ ] Tuple unpacking করতে পারি।
- [ ] Tuple methods ব্যবহার করতে পারি।
- [ ] List এবং Tuple-এর পার্থক্য বুঝি।

### Set

- [ ] Set তৈরি করতে পারি।
- [ ] Duplicate elements remove করতে পারি।
- [ ] Set-এর elements add এবং remove করতে পারি।
- [ ] Union এবং Intersection করতে পারি।
- [ ] Difference এবং Symmetric Difference করতে পারি।
- [ ] Frozen Set বুঝি।
- [ ] Set comprehension লিখতে পারি।

### Dictionary

- [ ] Dictionary তৈরি করতে পারি।
- [ ] Key ব্যবহার করে value access করতে পারি।
- [ ] Dictionary item add, update এবং delete করতে পারি।
- [ ] Dictionary methods ব্যবহার করতে পারি।
- [ ] Nested dictionary ব্যবহার করতে পারি।
- [ ] Dictionary comprehension লিখতে পারি।
- [ ] Dictionary iteration করতে পারি।

### Advanced Concepts

- [ ] Mutable এবং immutable বুঝি।
- [ ] Shallow copy এবং deep copy-এর পার্থক্য বুঝি।
- [ ] বিভিন্ন data structure-এর মধ্যে conversion করতে পারি।
- [ ] Nested data structures ব্যবহার করতে পারি।
- [ ] Common errors identify এবং debug করতে পারি।
- [ ] Data structure ব্যবহার করে programming problems solve করতে পারি।

---

## 10. First Topic

`01_Introduction_to_Built_in_Data_Structures.md`

পরবর্তী file-এ Python-এর Built-in Data Structures কী, কেন এগুলো ব্যবহার করা হয়, List, Tuple, Set এবং Dictionary কীভাবে কাজ করে এবং বাস্তব উদাহরণের মাধ্যমে এদের basic ধারণা বিস্তারিতভাবে ব্যাখ্যা করা হবে।

**Let's Start Learning Python Data Structures!**