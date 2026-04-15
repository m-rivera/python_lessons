# Mathematical operators
## Learning outcomes

*   Use standard Python mathematical operators 
*   Understand the implications of data types on the functioning of operators
*   Access non-standard operators

## Prerequisites

- [First steps](/first_steps/landing.md)
- [Data types](/variables/data_types.md)
- [Data types](/variables/lists.md)

## Mathematical operations on numbers

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

These methods are helpful to obtain a quick result, but if the final presentation is important, we can exert more control over the display of numbers by using more advanced features of the f-string:

```Python
mass_C = 12.008 # g mol-1
mass_H = 1.008 # g mol-1
mass_methane = mass_C + 4 * mass_H

# Calling up a variable that has already been calculated
print(f"The mass of methane is {mass_methane:.2f} g mol⁻¹.")
```

```{admonition} Task
Run the code cell above, and guess what the number `2` means in `:.2f` by changing its value.
```

<details> <summary>Solution</summary>

The syntax `:.2f` indicates that the number should be given to 2 decimal places.

</details>

More information on the formatting codes can be found [here](https://docs.python.org/3/library/string.html#formatspec).

```{admonition} Task

Using variables to store the atomic masses of hydrogen, carbon, oxygen, and nitrogen, write a program to calculate the molecular masses of the following species.

1. Ethanol (C<sub>2</sub>H<sub>6</sub>O), doing the calculation inside a print() statement
2. cyclohexanone (C<sub>6</sub>H<sub>10</sub>O), doing the calculation in a variable which you then print
3. Nitrobenzene (C<sub>6</sub>H<sub>5</sub>NO<sub>2</sub>), using an f string

The atomic masses are:
```Python
H = 1.008
C = 12.011
O = 15.999
N = 14.007
```

<details> <summary>Solution</summary>

Your code should look something like this:

```Python
# g mol-1
H = 1.008
C = 12.011
O = 15.999
N = 14.007

print("The mass of ethanol is " , 2 * C + 6 * H + O, "g mol⁻¹." )

mass_cyclohexanone = 6 * C + 10 * H + O
print("The mass of cyclohexanone is " , mass_cyclohexanone, "g mol⁻¹.")

mass_nitrobenzene = 6 * C + H * 5 + N + 2 * O
print(f"The mass of nitrobenzene is {mass_nitrobenzene:.2f} g mol⁻¹.")
```

You should have got the output:
```text
The mass of ethanol is:  46.069 g mol⁻¹.
The mass of cyclohexanone is:  98.145 g mol⁻¹.
The mass of nitrobenzene is: 123.11 g mol⁻¹.
```

We only have to define the masses once, and they can be reused for all three sums.

</details>

```{admonition} Task
The equilibrium constant of an equation

aA + bB ⇌ cC + dD

is given by

$ K_c = \frac{[C]^c \ [D]^d}{[A]^a \ [B]^b} $

For the following equation write a program which calculates the equilibrium constant to 3 decimal places.

2SO<sub>2(g)</sub> + O<sub>2(g)</sub> ⇌ 2SO<sub>3(g)</sub>

Concentrations at equilibrium:<br>
[SO<sub>2</sub>] = 3.0 × 10<sup>−3</sup> mol L<sup>−1</sup><br>
[O<sub>2</sub>] = 3.5 × 10<sup>−3</sup> mol L<sup>−1</sup><br>
[SO<sub>3</sub>] = 5.0 × 10<sup>−2</sup> mol L<sup>−1</sup><br>
```
<details> <summary>Solution</summary>
The numerical answer is <code>79365.079</code>. For a proposed Python code, keep reading:

```Python
# mol L-1
conc_SO2 = 3e-3
conc_O2 = 3.5e-3
conc_SO3 = 5e-2

K_c = conc_SO3**2 / (conc_SO2**2 * conc_O2)

print(f"The equilibrium constant is {K_c:.3f} mol⁻¹ L.")
```
</details>

## Mathematical operations on non-numerical data types