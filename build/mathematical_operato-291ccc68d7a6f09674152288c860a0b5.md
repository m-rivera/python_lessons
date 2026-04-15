# Mathematical operators
## Learning outcomes

*   Use standard Python mathematical operators 
*   Understand the implications of data types on the functioning of operators
*   Access non-standard operators

## Prerequisites

- [First steps](/first_steps/landing.md)
- [Data types](/variables/data_types.md)
- [Data types](/variables/lists.md)

## Arithmetic

Before accessing complicated operations, it's important to learn how to use Python as a simple calculator. There are seven standard mathematical operations that Python can do, though their notation might be slightly different to what you're used to (e.g. &times; is written as ``*`` in Python):

| Operation    | Mathematical Notation | Pythonic Notation |
| -------- | ------- | ------- |
| Addition  | $a + b$ | `a + b` |
| Subtraction | $a - b$ | `a - b` |
| Multiplication | $a \times b$ | `a * b` |
| Division | $a \div b$ | `a / b` |
| Exponent | $a ^ b$ | `a ** b` |
| Modulo | $a \textrm{ mod } b$ | `a % b` |
| Floored Division | $a // b$ | `a // b` |

The modulo and floored division operations may be new to you: 
- Modulo computes the remainder from the division of two numbers. For example, ``5 % 2`` returns ``1``, and ``19 % 4`` returns ``3``. 
- Floored division is the partner to modulo, and returns only the integer part of the division. For example. ``5 // 2`` returns ``2``, and ``19 // 4`` returns ``4``. 

````{admonition} Task
Fill in the gaps to make the following code print `2` twice:

```python
print(97 % □)
print(97 // □)
```
````

<details> <summary>Solution</summary>

There could be several solutions, but you could try:
```python
print(97 % 5)
print(97 // 45)
```

Where `97 = 19 * 5 + 2` and `97 = 42 * 2 + 7`.

</details>

Python can only perform maths on variables of the data type ``integer`` or ``float``. Mathematical operators acted on strings or lists will result in different, exotic, results (more on this later).

A single line of code may have many mathematical operations. In this event, Python will follow the standard order of mathematical operations: you might know this as [BODMAS](https://en.wikipedia.org/wiki/Order_of_operations#Mnemonics). Use round brackets `()` when coding your formulas to avoid ambiguity.

Mathematical operators can be used on variables, numbers, or combinations of both. This becomes useful when a number is very long to write or needs to be repeated many times in code. For example, instead of writing out &pi; or Avogadro's number each time it is used, we can store it at the beginning of the program and only call it by the name you have given it:

``` Python 
pi = 3.141592653589
avogadro = 6.02214e23

# evaluate four times pi times Avogadro's number
product = 4 * pi * avogadro
print(product)
```

Note that to represent standard form, Python uses the symbol `e` instead of <code>&times;10<sup>n</sup></code>.

### Printing mathematical results
There are several ways to display the result of a calculation in Python. As above, we can print a variable, or we could directly evaluate the result inside the print statement, as such:
``` Python 
pi = 3.141592653589
avogadro = 6.02214e23

print(4 * pi * avogadro)
```

We can perform a mathematical calculation and assign it to a variable, which can be called inside a print statement.

```Python
mass_H = 1.008 # g mol-1
mass_O = 15.999 # g mol-1

mass_H2O = 2 * mass_H + mass_O
print("The mass of water is: " , mass_H2O, " g mol-1") 
```

The output of this code is:<br>
<code>The mass of water is: 18.015 g mol-1</code>

Remember to separate objects in a print statement with commas, and always provide units for an output.

You can do mathematical calculations within the print statement.

```Python
mass_H = 1.008 # g mol-1
print("The mass of a hydrogen molecule is: ", 2 * mass_H, " g mol-1")
```

The output of this code is: <br>
<code> The mass of a hydrogen molecule is: 2.016 g mol-1 </code>

The value 2.016 has been calculated, but is not stored as a variable like it is in the previous example. If you wanted to do further calculations with the number 2.016, it would be better to store it as a variable.
