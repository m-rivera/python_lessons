# Functions
## Learning outcomes

*   Write a section of code that can be called with one keyword.
*   Understand the restrictions on variable naming within this code.

## Prerequisites

- [First steps](/first_steps/landing.md)
- [Variables](/variables/landing.md)
- [If statements](/control_flow/if_statements.md)
- [For loops](/control_flow/for_loops.md)

## Application and syntax

At this stage, we should be able to accomplish quite a lot with a Python program. We can see how, as the tasks become more complex, our programs become longer and more repetitive. This makes code more tedious to write and very hard to read or edit.

Thankfully, there is a key building block which can help us organise our code in a more logical way: **the function**. We have encountered functions already. Every time we have used a keyword followed by parentheses `()`, we have been using a function, as with `print("Hello")`, `math.sqrt(2)` or `molecules.append("H2O")`. In this lesson, we will learn how to define our own functions.

A function is an isolated capsule of code where some values are fed in, an operation is carried out, and new values are fed out. Here is the generic syntax:

```Python
def function_name(an_argument):
    Code block, e.g. doing maths on an_argument
    return an_output
```

- ``def`` indicates that we are about to define a new function. 
- ``function_name()`` is what we will use to call our function later on.
- ``(an_argument)`` is the variable that the function will act on, known as the function's <b>argument</b>. It could be a number, string, list, etc., but whatever it is, we need to make sure that we treat it like the correct variable type throughout the main code block. 
- ``:`` indicates the start of the code that will run whenever we call our function.
- ``Code block`` is a placeholder indicating the main body of the code. It can perform operations using `an_argument` as input data, or even using variables outside the function. All of these operations must be indented in order to belong to `function_name`.
- ``return`` indicates the end of the function.
- ``an_output`` is what this function will yield once it is finished. In a sense, it's the result of the function. For instance, the function `math.sqrt(4)` returns the square root of the argument (so 2). A function is also allowed not to return anything, like the `print()` function, in which case `return` is not followed by anything.

Once a function is defined, later in the code, it can be executed by writing its name and inserting any arguments it requires between parentheses. Following the naming above:
```Python
result = function_name(new_argument)
```
Note that we can call this function as many times as we want, with different arguments, and they don't need to be called the same. In the function definition, `an_argument` is a placeholder name, by which we will refer to the inputs in the function body.

Let's look at a real example:
```Python
def atomic_masses_sum(atom_masses):
    """
    Sum all the atomic masses together and return the result.

    Arguments
    ---------
    atom_masses : list of floats
        The masses to be summed.
    
    Returns
    -------
    total_mass : float
        The sum of atomic masses

    """
    total_mass = 0
    for atom_mass in atom_masses:
        total_mass = total_mass + atom_mass
    return total_mass

water_atomic_masses = [1.008, 1.008, 15.999]
water_total_mass = atomic_masses_sum(water_atomic_masses)

print(f"The total mass of water is {water_total_mass} u.")
```

Note that:
- Below the `def atomic_masses_sum()` line, there is a long multiline comment. A comment directly following a function definition is called a **docstring**. It's an optional inclusion, but it can help someone use the function in the future. For example, in this case, it's helpful to know that `atom_masses` should be a list.
- All of the names inside the function are chosen to be generic (making reference to any molecule). When we call the function, we are using it for the case of water, but we could later call it with a different molecule as an argument.
- The variable `total_mass` is defined within the function, but can't be referenced outside of it (try it!). This is a helpful feature: only the returned variables can be carried into the main body of code. This means, for example, that you can use this function in another program, which already has a function called `total_mass`, and there will be no conflict between the two variables. We say that `total_mass` is within the **namespace** of the function, but not the **namespace** of the program.

Try changing the masses in `water_atomic_masses` and ensure that the result is as you would expect.

```{admonition} Task
Edit the example above so that the function returns a total mass in grams. The conversion constant is:

$1 \text{u} = 1.66054 \times 10^{-24} \text{g}$
```