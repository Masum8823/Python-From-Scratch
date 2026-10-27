# Chapter 03: Data Types & Type Conversion

## 1. Chapter Overview

Python-এ Data Types নির্ধারণ করে কোনো value কী ধরনের data প্রকাশ করে এবং সেই data-এর ওপর কী ধরনের operation করা যায়।

উদাহরণস্বরূপ, `25` একটি integer, `3.14` একটি floating-point number এবং `"Python"` একটি string।

```python
age = 25
cgpa = 3.95
name = "Masum"
is_student = True
```

এই chapter-এ আমরা Python-এর built-in data types, type checking, type conversion, mutability এবং data type-সংক্রান্ত common errors বিস্তারিতভাবে শিখব।

## 2. Learning Objectives

এই chapter শেষ করার পর তুমি পারবে:

- Python-এর বিভিন্ন built-in data type শনাক্ত করতে।
- Numeric, string এবং Boolean data নিয়ে কাজ করতে।
- `type()` এবং `isinstance()` ব্যবহার করতে।
- Implicit ও explicit type conversion বুঝতে।
- `int()`, `float()`, `str()` এবং `bool()` ব্যবহার করতে।
- List, tuple, set এবং dictionary-এর basic type-related behavior বুঝতে।
- Mutable ও immutable object-এর পার্থক্য ব্যাখ্যা করতে।
- Type conversion-সংক্রান্ত error শনাক্ত ও সমাধান করতে।
- প্রয়োজন অনুযায়ী সঠিক data type নির্বাচন করতে।

## 3. Complete Table of Contents

### Section A: Introduction to Data Types

| File | Topic |
|---|---|
| [01. Introduction to Python Data Types](01_Introduction_to_Python_Data_Types.md) | Data type কী, কেন প্রয়োজন এবং কীভাবে কাজ করে |
| [02. Overview of Built-in Data Types](02_Overview_of_Built_in_Data_Types.md) | Python-এর built-in data types-এর পরিচিতি |
| [03. Dynamic Typing in Python](03_Dynamic_Typing_in_Python.md) | Dynamic typing এবং variable-এর type পরিবর্তন |
| [04. Type Checking with type()](04_Type_Checking_with_type.md) | `type()` দিয়ে object-এর type দেখা |
| [05. Type Checking with isinstance()](05_Type_Checking_with_isinstance.md) | `isinstance()` দিয়ে type যাচাই |

### Section B: Numeric Data Types

| File | Topic |
|---|---|
| [06. Integer Type](06_Integer_Type.md) | `int`, integer values এবং integer operations |
| [07. Floating-Point Type](07_Floating_Point_Type.md) | `float`, decimal numbers এবং floating-point precision |
| [08. Complex Number Type](08_Complex_Number_Type.md) | `complex` এবং complex numbers-এর basic operations |
| [09. Numeric Type Operations and Limitations](09_Numeric_Type_Operations_and_Limitations.md) | Numeric operations, precision এবং limitations |

### Section C: Text and Logical Data Types

| File | Topic |
|---|---|
| [10. String Data Type](10_String_Data_Type.md) | `str` এবং text data |
| [11. Boolean Data Type](11_Boolean_Data_Type.md) | `bool`, `True` এবং `False` |
| [12. NoneType and None](12_NoneType_and_None.md) | `None` এবং absence of value |
| [13. Truthy and Falsy Values](13_Truthy_and_Falsy_Values.md) | কোন value truthy বা falsy হয় |

### Section D: Collection Data Types

| File | Topic |
|---|---|
| [14. List Data Type](14_List_Data_Type.md) | List-এর basic properties এবং element types |
| [15. Tuple Data Type](15_Tuple_Data_Type.md) | Tuple এবং immutable sequence |
| [16. Set Data Type](16_Set_Data_Type.md) | Set, unique elements এবং unordered collections |
| [17. Dictionary Data Type](17_Dictionary_Data_Type.md) | Key-value pairs এবং dictionary-এর basic behavior |
| [18. Bytes and Bytearray Types](18_Bytes_and_Bytearray_Types.md) | Binary data-এর পরিচিতি |

### Section E: Type Conversion

| File | Topic |
|---|---|
| [19. Introduction to Type Conversion](19_Introduction_to_Type_Conversion.md) | Type conversion কী এবং কেন প্রয়োজন |
| [20. Implicit Type Conversion](20_Implicit_Type_Conversion.md) | Python-এর automatic type conversion |
| [21. Explicit Type Conversion](21_Explicit_Type_Conversion.md) | Programmer-এর মাধ্যমে type conversion |
| [22. Converting to int](22_Converting_to_int.md) | `int()` এবং integer conversion |
| [23. Converting to float](23_Converting_to_float.md) | `float()` এবং floating-point conversion |
| [24. Converting to str](24_Converting_to_str.md) | `str()` এবং string conversion |
| [25. Converting to bool](25_Converting_to_bool.md) | `bool()` এবং Boolean conversion |
| [26. Converting Between Collection Types](26_Converting_Between_Collection_Types.md) | List, tuple, set এবং dictionary conversion |
| [27. Type Conversion Errors](27_Type_Conversion_Errors.md) | `ValueError`, `TypeError` এবং common mistakes |

### Section F: Object Behavior and Best Practices

| File | Topic |
|---|---|
| [28. Mutable and Immutable Objects](28_Mutable_and_Immutable_Objects.md) | Mutability এবং object modification |
| [29. Type Compatibility and Common Errors](29_Type_Compatibility_and_Common_Errors.md) | Incompatible types এবং operation errors |
| [30. Choosing the Right Data Type](30_Choosing_the_Right_Data_Type.md) | কাজ অনুযায়ী data type নির্বাচন |
| [31. Data Types Best Practices](31_Data_Types_Best_Practices.md) | Readability, correctness এবং maintainability |

### Section G: Practice and Review

| File | Topic |
|---|---|
| [32. Data Types Practice Exercises](32_Data_Types_Practice_Exercises.md) | Basic থেকে challenging exercises |
| [33. Chapter Review and Self-Assessment](33_Chapter_Review_and_Self_Assessment.md) | Revision, comparison tables এবং self-test |

## 4. Learning Order

Chapter-টি নিচের ক্রমে পড়বে:

1. **Understand:** Data type কী এবং কেন দরকার।
2. **Identify:** `type()` ও `isinstance()` ব্যবহার করে type যাচাই।
3. **Learn:** Numeric, string, Boolean এবং collection types।
4. **Convert:** Implicit ও explicit conversion অনুশীলন।
5. **Understand behavior:** Mutable এবং immutable objects।
6. **Debug:** Type-related errors শনাক্ত ও সমাধান।
7. **Practice:** Exercises সমাধান করে self-assessment সম্পন্ন করা।

## 5. Important Learning Rules

- প্রতিটি code example নিজে execute করবে।
- প্রতিটি conversion-এর আগে ও পরে value এবং type যাচাই করবে।
- `input()` থেকে পাওয়া value সাধারণত string হয়—এটি মনে রাখবে।
- সব string-কে number-এ convert করা যায় না।
- `bool()`-এর result শুধু `True` বা `False` text-এর ওপর নির্ভর করে না; value-এর truthiness-এর ওপর নির্ভর করে।
- Mutable এবং immutable object-এর পার্থক্য example দিয়ে বুঝবে।
- কোনো error হলে error message পড়বে এবং কারণ খুঁজে বের করবে।

## 6. Chapter Completion Checklist

- [ ] Built-in data types বুঝেছি।
- [ ] `type()` ও `isinstance()` ব্যবহার করতে পারি।
- [ ] Numeric এবং text data নিয়ে কাজ করতে পারি।
- [ ] Boolean ও `None` বুঝি।
- [ ] Collection types-এর basic properties জানি।
- [ ] Implicit ও explicit conversion-এর পার্থক্য বুঝি।
- [ ] `int()`, `float()`, `str()` ও `bool()` ব্যবহার করতে পারি।
- [ ] Common type conversion errors সমাধান করতে পারি।
- [ ] Mutable ও immutable objects-এর পার্থক্য বুঝি।
- [ ] Practice exercises নিজে solve করেছি।

## 7. Next Step

প্রথমে পড়বে:

**`01_Introduction_to_Python_Data_Types.md`**

এই ফাইলে Data Type-এর ধারণা একেবারে basic level থেকে ব্যাখ্যা করা হবে, যাতে পরের topic-গুলো বুঝতে সমস্যা না হয়।