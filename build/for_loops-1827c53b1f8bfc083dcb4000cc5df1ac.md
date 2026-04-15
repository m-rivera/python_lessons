# For loops
## Learning outcomes

*   Write pieces of code that run multiple times (loops).
*   End loops in a predictable way.
*   Make predictable changes to each iteration of the code.

## Prerequisites

- [First steps](/first_steps/landing.md)
- [Variables](/variables/landing.md)
- [If statements](/variables/if_statements.md)

## For loops over lists

When programming, we may want to repeat the same (or almost the same) operation hundreds of times. Instead of writing hundreds of line of code, our preferred solution in Python is the `for` loop.

We will start with the most common scenario: you have a list of values and want to act on each element of the list.

Just like with ``if`` statements, ``for`` loops require specific syntax:

```Python
for discrete_variable in list_of_values:
    some action
```

- `for` indicates that we will begin a loop.
- `discrete_variable` is a new variable we are defining, which will adopt each element of the list one by one. At every repetition of the loop, it will change its value to the new element. The technical term for these stand-in variables is a *discrete variable*.
- `in list_of_values` indicates that we want to repeat the action in the loop once per item in the list `list_of_values`.
- `:` signals the beginning of the loop.
- `some action` is to be replaced by whatever action you want to repeat. It can take multiple lines but they all have to be indented. When the code is no longer indented, the loop is over.

Here is an example:

```Python
molecules = ["H2", "H2O", "CH4"]

for mol in molecules:
  print(mol)
```

Run the code and make sure you understand each line. The most exotic feature is the discrete variable `mol`. Notice that we can use `mol` within the `for` loop for printing, even though we never defined it in the usual way (`mol = "H2"`). This is because it is defined within the opening line of the loop.

Try adding or removing elements in `molecules` and see what happens.