# 0x00. Python - Variable Annotations

## Back-end - Python

## Concepts

- For this project, we expect you to look at this concept:
  - Advanced Python

## Resources

- Read or watch:
  - [Python 3 typing documentation](#)
  - [MyPy cheat sheet](#)

## Learning Objectives

### General

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

- Type annotations in Python 3
- How you can use type annotations to specify function signatures and variable types
- Duck typing
- How to validate your code with mypy

## Requirements

### General

- Allowed editors: vi, vim, emacs
- All your files will be interpreted/compiled on Ubuntu 18.04 LTS using python3 (version 3.7)
- All your files should end with a new line
- The first line of all your files should be exactly `#!/usr/bin/env python3`
- A README.md file, at the root of the folder of the project, is mandatory
- Your code should use the `pycodestyle` style (version 2.5.)
- All your files must be executable
- The length of your files will be tested using wc
- All your modules should have documentation (`python3 -c 'print(__import__("my_module").__doc__)'`)
- All your classes should have documentation (`python3 -c 'print(__import__("my_module").MyClass.__doc__)'`)
- All your functions (inside and outside a class) should have documentation (`python3 -c 'print(__import__("my_module").my_function.__doc__)' and python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)'`)
  - A documentation is not a simple word, it’s a real sentence explaining what’s the purpose of the module, class or method (the length of it will be verified)

## Tasks

### 0. Basic annotations - add (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Write a type-annotated function `add` that takes a float `a` and a float `b` as arguments and returns their sum as a float.

```python
#!/usr/bin/env python3
add = __import__('0-add').add

print(add(1.11, 2.22) == 1.11 + 2.22)
print(add.__annotations__)
```

### 1. Basic annotations - concat (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Write a type-annotated function `concat` that takes a string `str1` and a string `str2` as arguments and returns a concatenated string.

```python
#!/usr/bin/env python3
concat = __import__('1-concat').concat

str1 = "egg"
str2 = "shell"

print(concat(str1, str2) == "{}{}".format(str1, str2))
print(concat.__annotations__)
```

### 2. Basic annotations - floor (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Write a type-annotated function `floor` which takes a float `n` as an argument and returns the floor of the float.

```python
#!/usr/bin/env python3

import math

floor = __import__('2-floor').floor

ans = floor(3.14)

print(ans == math.floor(3.14))
print(floor.__annotations__)
print("floor(3.14) returns {}, which is a {}".format(ans, type(ans)))
```

### 3. Basic annotations - to string (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Write a type-annotated function `to_str` that takes a float `n` as an argument and returns the string representation of the float.

```python
#!/usr/bin/env python3
to_str = __import__('3-to_str').to_str

pi_str = to_str(3.14)
print(pi_str == str(3.14))
print(to_str.__annotations__)
print("to_str(3.14) returns {} which is a {}".format(pi_str, type

(pi_str)))
```

### 4. Define variables (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Define and annotate the following variables with the specified values:
  - a, an integer with a value of 1
  - pi, a float with a value of 3.14
  - i_understand_annotations, a boolean with a value of True
  - school, a string with a value of “Holberton”

```python
#!/usr/bin/env python3

a = __import__('4-define_variables').a
pi = __import__('4-define_variables').pi
i_understand_annotations = __import__('4-define_variables').i_understand_annotations
school = __import__('4-define_variables').school

print("a is a {} with a value of {}".format(type(a), a))
print("pi is a {} with a value of {}".format(type(pi), pi))
print("i_understand_annotations is a {} with a value of {}".format(type(i_understand_annotations), i_understand_annotations))
print("school is a {} with a value of {}".format(type(school), school))
```

### 5. Complex types - list of floats (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Write a type-annotated function `sum_list` which takes a list `input_list` of floats as an argument and returns their sum as a float.

```python
#!/usr/bin/env python3

sum_list = __import__('5-sum_list').sum_list

floats = [3.14, 1.11, 2.22]
floats_sum = sum_list(floats)
print(floats_sum == sum(floats))
print(sum_list.__annotations__)
print("sum_list(floats) returns {} which is a {}".format(floats_sum, type(floats_sum)))
```

### 6. Complex types - mixed list (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Write a type-annotated function `sum_mixed_list` which takes a list `mxd_lst` of integers and floats and returns their sum as a float.

```python
#!/usr/bin/env python3

sum_mixed_list = __import__('6-sum_mixed_list').sum_mixed_list

print(sum_mixed_list.__annotations__)
mixed = [5, 4, 3.14, 666, 0.99]
ans = sum_mixed_list(mixed)
print(ans == sum(mixed))
print("sum_mixed_list(mixed) returns {} which is a {}".format(ans, type(ans)))
```

### 7. Complex types - string and int/float to tuple (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Write a type-annotated function `to_kv` that takes a string `k` and an int OR float `v` as arguments and returns a tuple. The first element of the tuple is the string `k`. The second element is the square of the int/float `v` and should be annotated as a float.

```python
#!/usr/bin/env python3

to_kv = __import__('7-to_kv').to_kv

print(to_kv.__annotations__)
print(to_kv("eggs", 3))
print(to_kv("school", 0.02))
```

### 8. Complex types - functions (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Write a type-annotated function `make_multiplier` that takes a float `multiplier` as an argument and returns a function that multiplies a float by `multiplier`.

```python
#!/usr/bin/env python3

make_multiplier = __import__('8-make_multiplier').make_multiplier
print(make_multiplier.__annotations__)
fun = make_multiplier(2.22)
print("{}".format(fun(2.22)))
```

### 9. Let's duck type an iterable object (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Annotate the below function’s parameters and return values with the appropriate types.

```python
#!/usr/bin/env python3

element_length = __import__('9-element_length').element_length

print(element_length.__annotations__)
```

### 10. Duck typing - first element of a sequence (advanced)

- **Score: 0.0% (Checks completed: 0.0%)**
- Augment the following code with the correct duck-typed annotations.

```python
#!/usr/bin/env python3

safe_first_element = __import__('100-safe_first_element').safe_first_element

print(safe_first_element.__annotations__)
```

### 11. More involved type annotations (advanced)

- **Score: 0.0% (Checks completed: 0.0%)**
- Given the parameters and the return values, add type annotations to the function.

```python
#!/usr/bin/env python3

safely_get_value = __import__('101-safely_get_value').safely_get_value
annotations = safely_get_value.__annotations__

print("Here's what the mappings should look like")
for k, v in annotations.items():
    print("{}: {}".format(k, v))
```

### 12. Type Checking (advanced)

- **Score: 0.0% (Checks completed: 0.0%)**
- Use mypy to validate the following piece of code and apply any necessary changes.

```python
#!/usr/bin/env python3

zoom_array = __import__('102-type_checking').zoom_array

print(zoom_array.__annotations__)
```

---
