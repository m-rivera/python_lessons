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

Where \(\frac{97}{5} = 19 \times 5 + 2\) and $97 = 45 \times 2 + 7$.

</details>

Importantly, Python can only perform maths on variables of the data type ``integer`` or ``float``. Maths performed on strings or lists will result in strange outcomes (see below for some examples).

A single line of code may have many mathematical operations. In this event, Python will follow the standard order of mathematical operations: you might know this as [BODMAS](https://en.wikipedia.org/wiki/Order_of_operations#Mnemonics). Use round brackets "()" when coding your formulas to avoid ambiguity.

Maths can be done both with numbers and with variable, as long as the variable is of the correct type (integer or float). Storing numbers as variables becomes extremely useful when they are being used often, and when they are needed to a large number of significant figures. For example, instead of writing out &pi; or Avogadro's number each time it is used, you can store it at the beginning and only call it by the name you have given it.

``` Python 
pi = 3.141592653589
avogadro = 6.02214e23

product = pi * avogadro * 4
```

The value of the variable `product` is now that of 3.14 &times; 6.022&times;10<sup>-23</sup> &times; 4, which equals <tt> 7.567644313153783e+24 </tt>.

Note that to represent standard form, Python uses the symbol `en` instead of <code>&times;10<sup>n</sup></code>.