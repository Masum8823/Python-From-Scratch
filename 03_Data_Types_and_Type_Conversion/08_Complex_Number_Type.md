# 08. Complex Number Type (`complex`)

## 1. What Is a Complex Number?

Python-এ **Complex (`complex`)** হলো একটি built-in numeric data type, যা complex number প্রকাশ করতে ব্যবহৃত হয়।

গণিতে একটি complex number-এর সাধারণ রূপ:

\[
z = a + bj
\]

এখানে:

- \(a\) হলো **Real Part**।
- \(b\) হলো **Imaginary Part-এর coefficient**।
- \(j\) হলো imaginary unit, যার জন্য \(j^2=-1\)।

Python-এ mathematical notation-এর \(i\)-এর পরিবর্তে `j` ব্যবহার করা হয়।

Example:

```python
number = 3 + 4j

print(number)
print(type(number))
```

Output:

```text
(3+4j)
<class 'complex'>
```

এখানে `3` হলো real part এবং `4` হলো imaginary part-এর coefficient।

Complex number শুধু integer বা float-এর মতো সাধারণ সংখ্যা নয়; এটি real এবং imaginary অংশ একসঙ্গে প্রকাশ করতে পারে।

## 2. Creating Complex Numbers

Python-এ complex number তৈরির প্রধান দুটি পদ্ধতি রয়েছে।

### 2.1 Using `j` Notation

Complex number সরাসরি লিখতে `j` ব্যবহার করা যায়।

```python
a = 2 + 3j
b = 5 - 2j
c = 4j
d = 7 + 0j

print(a)
print(b)
print(c)
print(d)
```

Output:

```text
(2+3j)
(5-2j)
4j
(7+0j)
```

এখানে:

- `2 + 3j` একটি complex number।
- `5 - 2j` একটি complex number, যার imaginary অংশ ঋণাত্মক।
- `4j`-এর real part শূন্য।
- `7 + 0j`-এর imaginary অংশ শূন্য হলেও এর type `complex`।

### 2.2 Using the `complex()` Function

Python-এর built-in `complex()` function দিয়েও complex number তৈরি করা যায়।

Syntax:

```python
complex(real, imag)
```

এখানে:

- `real`: real part।
- `imag`: imaginary part-এর coefficient।

Example:

```python
number = complex(3, 4)

print(number)
print(type(number))
```

Output:

```text
(3+4j)
<class 'complex'>
```

আরেকটি example:

```python
a = complex(5, -2)
b = complex(3, 0)

print(a)
print(b)
```

Output:

```text
(5-2j)
(3+0j)
```

**মনে রাখবে:** `complex(3, 4)` মানে \(3+4j\), এখানে `4` হলো imaginary part-এর coefficient।

## 3. Real and Imaginary Parts

Complex number-এর real ও imaginary অংশ আলাদাভাবে বের করতে `.real` এবং `.imag` attributes ব্যবহার করা হয়।

Example:

```python
number = 3 + 4j

print(number.real)
print(number.imag)
```

Output:

```text
3.0
4.0
```

এখানে দুটি result-ই `float` হিসেবে পাওয়া যায়।

```python
number = 3 + 4j

print(type(number.real))
print(type(number.imag))
```

Output:

```text
<class 'float'>
<class 'float'>
```

এমনকি কোনো complex number-এর imaginary অংশ শূন্য হলেও `.imag` attribute float return করে।

```python
number = 7 + 0j

print(number.real)
print(number.imag)
```

Output:

```text
7.0
0.0
```

## 4. Understanding the Imaginary Unit

গণিতে imaginary unit-কে সাধারণত \(i\) দিয়ে প্রকাশ করা হয়:

\[
i^2=-1
\]

Python-এ একই ধারণার জন্য `j` ব্যবহার করা হয়:

\[
j^2=-1
\]

Example:

```python
number = 1j

print(number)
print(number * number)
```

Output:

```text
1j
(-1+0j)
```

Python-এ `1j * 1j`-এর result একটি complex number, যার মান \(-1\)।

**Important:** Python-এ `j` একা imaginary unit হিসেবে লেখা যায় না। Imaginary unit প্রকাশ করতে `1j` লিখতে হবে।

```python
number = 1j

print(type(number))
```

Output:

```text
<class 'complex'>
```

## 5. Complex Number Arithmetic

Python complex number-এর ওপর সাধারণ arithmetic operations সমর্থন করে।

ধরি:

\[
z_1=2+3j,\qquad z_2=4+5j
\]

### 5.1 Addition (`+`)

Real অংশের সঙ্গে real অংশ এবং imaginary অংশের সঙ্গে imaginary অংশ যোগ হয়।

\[
(2+3j)+(4+5j)=6+8j
\]

```python
a = 2 + 3j
b = 4 + 5j

print(a + b)
```

Output:

```text
(6+8j)
```

### 5.2 Subtraction (`-`)

\[
(2+3j)-(4+5j)=-2-2j
\]

```python
a = 2 + 3j
b = 4 + 5j

print(a - b)
```

Output:

```text
(-2-2j)
```

### 5.3 Multiplication (`*`)

Complex number গুণ করার সময় সাধারণ algebraic rules ব্যবহার করা হয়।

\[
(a+bj)(c+dj)=(ac-bd)+(ad+bc)j
\]

কারণ \(j^2=-1\)।

Example:

\[
(2+3j)(4+5j)=-7+22j
\]

```python
a = 2 + 3j
b = 4 + 5j

print(a * b)
```

Output:

```text
(-7+22j)
```

### 5.4 Division (`/`)

Python complex number-এর division-ও সমর্থন করে।

```python
a = 4 + 2j
b = 1 + 1j

print(a / b)
```

Output:

```text
(3-1j)
```

Complex number-কে শূন্য দিয়ে divide করলে `ZeroDivisionError` হয়।

### 5.5 Exponentiation (`**`)

Complex number-এর power হিসাব করতেও `**` ব্যবহার করা যায়।

```python
number = 1 + 1j

print(number ** 2)
```

Output:

```text
2j
```

কারণ:

\[
(1+j)^2=1+2j+j^2=2j
\]

### Arithmetic Summary

| Operator | Operation | Example |
|---|---|---|
| `+` | Addition | `(2+3j) + (4+5j)` |
| `-` | Subtraction | `(2+3j) - (4+5j)` |
| `*` | Multiplication | `(2+3j) * (4+5j)` |
| `/` | Division | `(4+2j) / (1+1j)` |
| `**` | Exponentiation | `(1+1j) ** 2` |

## 6. Conjugate of a Complex Number

Complex number-এর **conjugate** পেতে imaginary অংশের sign পরিবর্তন করা হয়।

যদি:

\[
z=a+bj
\]

তাহলে এর conjugate:

\[
\overline{z}=a-bj
\]

Python-এ `.conjugate()` method ব্যবহার করা যায়।

Example:

```python
number = 3 + 4j

print(number.conjugate())
```

Output:

```text
(3-4j)
```

আরেকটি example:

```python
number = 5 - 2j

print(number.conjugate())
```

Output:

```text
(5+2j)
```

Conjugate complex arithmetic, mathematical calculations এবং signal processing-এর মতো ক্ষেত্রে কাজে লাগে।

## 7. Magnitude of a Complex Number

Complex number-এর magnitude বা modulus হলো complex plane-এ origin থেকে সংখ্যাটির দূরত্ব।

যদি:

\[
z=a+bj
\]

তাহলে magnitude:

\[
|z|=\sqrt{a^2+b^2}
\]

Python-এ `abs()` function দিয়ে magnitude বের করা যায়।

Example:

```python
number = 3 + 4j

print(abs(number))
```

Output:

```text
5.0
```

কারণ:

\[
|z|=\sqrt{3^2+4^2}=\sqrt{25}=5
\]

আরেকটি example:

```python
number = 5 + 12j

print(abs(number))
```

Output:

```text
13.0
```

**মনে রাখবে:** `abs()` complex number-এর magnitude return করে, শুধু real অংশ নয়।

## 8. Comparing Complex Numbers

Complex number-এর equality পরীক্ষা করা যায়।

```python
a = 2 + 3j
b = 2 + 3j
c = 2 + 4j

print(a == b)
print(a == c)
```

Output:

```text
True
False
```

তবে complex number-কে সাধারণ numeric ordering operator দিয়ে তুলনা করা যায় না।

যেমন:

```python
a = 2 + 3j
b = 4 + 5j

print(a < b)
```

এটি চালালে `TypeError` হবে।

কারণ complex number-এর জন্য Python সাধারণ সংখ্যার মতো `<`, `>` বা `<=` দিয়ে ordering সংজ্ঞায়িত করে না।

যদি magnitude অনুযায়ী তুলনা করতে চাও, তাহলে `abs()` ব্যবহার করা যায়।

```python
a = 2 + 3j
b = 4 + 5j

print(abs(a) < abs(b))
```

Output:

```text
True
```

এখানে complex number-দুটির magnitude তুলনা করা হয়েছে, complex value-গুলোর সরাসরি ordering নয়।

## 9. Type Conversion with Complex Numbers

`complex()` ব্যবহার করে উপযুক্ত numeric value থেকে complex number তৈরি করা যায়।

### 9.1 Integer to Complex

```python
number = complex(10)

print(number)
print(type(number))
```

Output:

```text
(10+0j)
<class 'complex'>
```

### 9.2 Float to Complex

```python
number = complex(3.5)

print(number)
```

Output:

```text
(3.5+0j)
```

### 9.3 String to Complex

উপযুক্ত format-এর string থেকেও complex number তৈরি করা যায়।

```python
number = complex("3+4j")

print(number)
```

Output:

```text
(3+4j)
```

Invalid format-এর string দিলে `ValueError` হতে পারে।

### 9.4 Complex to Integer

সরাসরি complex number-কে `int()` দিয়ে convert করা যায় না।

```python
number = 3 + 4j

print(int(number))
```

এটি `TypeError` তৈরি করবে।

যদি শুধু real অংশ প্রয়োজন হয়, তাহলে `.real` ব্যবহার করে সেটিকে convert করা যায়।

```python
number = 3 + 4j

print(int(number.real))
```

Output:

```text
3
```

তবে মনে রাখবে, এতে imaginary অংশ বাদ পড়ে যায়। এটি পুরো complex number-এর সমতুল্য conversion নয়।

### 9.5 Complex to Float

Complex number-কে সরাসরি `float()` দিয়েও convert করা যায় না।

```python
number = 3 + 4j

print(float(number))
```

এটি `TypeError` তৈরি করবে।

শুধু real অংশ দরকার হলে:

```python
print(float(number.real))
```

Output:

```text
3.0
```

## 10. Useful Functions and Attributes

| Function/Attribute | Purpose | Example |
|---|---|---|
| `complex()` | Complex number তৈরি করে | `complex(2, 3)` |
| `type()` | Type পরীক্ষা করে | `type(2+3j)` |
| `isinstance()` | Type বা class membership পরীক্ষা করে | `isinstance(2+3j, complex)` |
| `.real` | Real অংশ দেয় | `(2+3j).real` |
| `.imag` | Imaginary coefficient দেয় | `(2+3j).imag` |
| `.conjugate()` | Conjugate দেয় | `(2+3j).conjugate()` |
| `abs()` | Magnitude দেয় | `abs(3+4j)` |

Example:

```python
number = 3 + 4j

print(type(number))
print(isinstance(number, complex))
print(number.real)
print(number.imag)
print(number.conjugate())
print(abs(number))
```

Output:

```text
<class 'complex'>
True
3.0
4.0
(3-4j)
5.0
```

## 11. Common Beginner Mistakes

### Mistake 1: `j`-এর পরিবর্তে `i` ব্যবহার করা

Python-এ `3 + 4i` valid complex literal নয়।

সঠিক:

```python
number = 3 + 4j

print(number)
```

### Mistake 2: `j`-কে Variable ছাড়া ব্যবহার করা

ভুল:

```python
number = 3 + j
```

যদি `j` নামে variable define না করা থাকে, তাহলে `NameError` হবে।

সঠিক:

```python
number = 3 + 1j

print(number)
```

### Mistake 3: Complex Number-কে সরাসরি `int()` করা

ভুল:

```python
number = 3 + 4j

print(int(number))
```

এটি `TypeError` তৈরি করবে। শুধু real অংশ প্রয়োজন হলে `.real` ব্যবহার করো।

### Mistake 4: `<` বা `>` দিয়ে Complex Number তুলনা করা

ভুল:

```python
print((2 + 3j) < (4 + 5j))
```

এটি `TypeError` তৈরি করবে।

Magnitude তুলনা করতে চাইলে:

```python
print(abs(2 + 3j) < abs(4 + 5j))
```

### Mistake 5: Imaginary Part এবং Imaginary Coefficient গুলিয়ে ফেলা

```python
number = 3 + 4j

print(number.imag)
```

Output:

```text
4.0
```

এখানে `.imag` হলো imaginary অংশের coefficient, অর্থাৎ `4.0`; এটি আলাদা করে `j`-সহ `4j` return করে না।

## 12. Practice Exercises

### Exercise 1: Identify the Type

নিচের code-এর output নির্ণয় করো:

```python
a = 3 + 4j
b = 5 - 2j
c = 7 + 0j

print(type(a))
print(type(b))
print(type(c))
```

### Exercise 2: Real and Imaginary Parts

```python
number = 6 + 8j

print(number.real)
print(number.imag)
```

Output লিখে ব্যাখ্যা করো।

### Exercise 3: Arithmetic Operations

নিচের code-এর output নির্ণয় করো:

```python
a = 2 + 3j
b = 1 + 2j

print(a + b)
print(a - b)
print(a * b)
print(a / b)
```

### Exercise 4: Conjugate and Magnitude

```python
number = 3 + 4j

print(number.conjugate())
print(abs(number))
```

Output অনুমান করো এবং গাণিতিকভাবে ব্যাখ্যা করো।

### Exercise 5: Type Conversion

নিচের code-এর output নির্ণয় করো:

```python
print(complex(5))
print(complex(2.5))
print(complex("3+4j"))
```

### Exercise 6: Find the Errors

নিচের code-গুলোর কোনগুলো error তৈরি করবে এবং কেন?

```python
a = 3 + 4j

print(int(a))
print(float(a))
print(a < (5 + 6j))
print(a.real)
```

প্রতিটি statement আলাদাভাবে বিবেচনা করো।

### Exercise 7: Mini Project — Complex Number Analyzer

একটি program লেখো, যা `3 + 4j`-এর জন্য:

1. Complex number print করবে।
2. Real part দেখাবে।
3. Imaginary part দেখাবে।
4. Conjugate দেখাবে।
5. Magnitude দেখাবে।
6. Type পরীক্ষা করবে।

## 13. Key Takeaways

- `complex` হলো Python-এর built-in numeric data type।
- Complex number-এর সাধারণ রূপ `a + bj`।
- Python-এ imaginary unit-এর জন্য `j` ব্যবহার করা হয়।
- `.real` real অংশ এবং `.imag` imaginary coefficient দেয়।
- `complex()` দিয়ে complex number তৈরি করা যায়।
- Complex number-এর সঙ্গে `+`, `-`, `*`, `/` এবং `**` ব্যবহার করা যায়।
- `.conjugate()` conjugate এবং `abs()` magnitude দেয়।
- Complex number-এর equality পরীক্ষা করা যায়, কিন্তু সাধারণ `<` বা `>` comparison করা যায় না।
- Complex number-কে সরাসরি `int()` বা `float()` দিয়ে convert করা যায় না।
- শুধু real অংশ ব্যবহার করলে imaginary অংশ হারিয়ে যেতে পারে।

## 14. Next Topic

পরবর্তী ফাইল:

**`09_Numeric_Type_Operations_and_Limitations.md`**

সেখানে `int`, `float` এবং `complex`—এই তিনটি numeric type-এর মধ্যে পার্থক্য, common operations, type promotion, precision এবং numeric limitations একসঙ্গে আলোচনা করা হবে।