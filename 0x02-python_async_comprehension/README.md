# 0x02. Python - Async Comprehension

## Back-end - Python

## Resources

- Read or watch:
  - [PEP 530 – Asynchronous Comprehensions](#)
  - [What’s New in Python: Asynchronous Comprehensions / Generators](#)
  - [Type-hints for generators](#)

## Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

- How to write an asynchronous generator
- How to use async comprehensions
- How to type-annotate generators

## Requirements

### General

- Allowed editors: vi, vim, emacs
- All your files will be interpreted/compiled on Ubuntu 18.04 LTS using python3 (version 3.7)
- All your files should end with a new line
- The first line of all your files should be exactly `#!/usr/bin/env python3`
- A README.md file, at the root of the folder of the project, is mandatory
- Your code should use the `pycodestyle` style (version 2.5.x)
- The length of your files will be tested using wc
- All your modules should have documentation (`python3 -c 'print(__import__("my_module").__doc__)'`)
- All your functions should have documentation (`python3 -c 'print(__import__("my_module").my_function.__doc__)'`)
  - A documentation is not a simple word, it’s a real sentence explaining what’s the purpose of the module, class, or method (the length of it will be verified)
- All your functions and coroutines must be type-annotated.

## Tasks

### 0. Async Generator (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Write a coroutine called `async_generator` that takes no arguments.

```python
#!/usr/bin/env python3

import asyncio

async_generator = __import__('0-async_generator').async_generator

async def print_yielded_values():
    result = []
    async for i in async_generator():
        result.append(i)
    print(result)

asyncio.run(print_yielded_values())
```

### 1. Async Comprehensions (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Import `async_generator` from the previous task and then write a coroutine called `async_comprehension` that takes no arguments.

```python
#!/usr/bin/env python3

import asyncio

async_comprehension = __import__('1-async_comprehension').async_comprehension

async def main():
    print(await async_comprehension())

asyncio.run(main())
```

### 2. Run time for four parallel comprehensions (mandatory)

- **Score: 0.0% (Checks completed: 0.0%)**
- Import `async_comprehension` from the previous file and write a `measure_runtime` coroutine that will execute `async_comprehension` four times in parallel using `asyncio.gather`.

```python
#!/usr/bin/env python3

import asyncio

measure_runtime = __import__('2-measure_runtime').measure_runtime

async def main():
    return await measure_runtime()

print(asyncio.run(main()))
```

---
