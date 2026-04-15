# For loops
## Learning outcomes

*   Write pieces of code that run multiple times (loops).
*   End loops in a predictable way.
*   Make predictable changes to each iteration of the code.

## Prerequisites

- [First steps](/first_steps/landing.md)
- [Variables](/variables/landing.md)
- [If statements](/variables/if_statements.md)

## For loop over a list
### Basic syntax

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

````{admonition} Task
Complete the following code so that each element of the list is printed within an f-string.

```Python
atomic_masses = [1.008, 4.003, 7.0]

print("These are the first atomic masses of the periodic table:")

for -- in --:
    print(f"Mass: {--} u")

```
````

<details> <summary>Solution</summary>

```Python
atomic_masses = [1.008, 4.003, 7.0]

print("These are the first atomic masses of the periodic table:")

for atomic_mass in atomic_masses:
    print(f"Mass: {atomic_mass} u")

```
Here, `atomic_masses` is the list, so must appear after `in`. The discrete variable `atomic_mass` could be named anything, but it needs to be the same name used within the loop. Even though the discrete variable is only going to be used within this loop, it's still good practice to give it a descriptive name.
</details>

### Multi-line for loops

We can do more than just printing inside a `for` loop. All of the Python we have learned so far applies. What follows is a typical piece of Python code (a.k.a. a *programming pattern*) for generating new lists. Here, we know some pressures in mmHg and want to turn them all into bar.

```Python
# a list of known pressures in mmHg
pressures_mmHg = [2945.01, 1671.43, 908.56, 625.3]

# an empty list which we want to fill up with the unknown pressures in bar
pressures_bar = []

# loop over the pressures in mmHg
for pressure_mmHg in pressures_mmHg:
    # calculate the pressure in bar
    new_pressure_bar = pressure_mmHg / 750.06

    # as a sanity check, print the new value
    print(new_pressure_bar)

    # append the new presure to our target list
    pressures_bar.append(new_pressure_bar)

# outside of the loop, we check the result
print(pressures_bar)
```

In a final version of the code, we would remove the sanity check. Look at the output and make sure that you can match up each printed line to a print statement in the code. Note how the indented print statement is used multiple times while the unindented one happens only once.

````{admonition} Task
Write a `for` loop which prints the square of each number from 1 to 4.
````

<details> <summary>Solution</summary>

```Python
numbers = [1, 2, 3, 4]

for number in numbers:
    print(number**2)

```
Again, `number` could be named anything as long as we use that name correctly later in the `for` loop. In many cases, you will find discrete variables named `i` or `j`, inspired by indices of mathematical equations. Try to resort to this only if the meaning of the variable is so abstract that giving it a non-mathematical name would be confusing.
</details>

### For loops and if statements

We can use our knowledge from the last lesson to combine `if` and `for`. Look at this example which picks out molecular formulas containing carbon:

```Python
molecules = ["N2", "H2", "CH3OH", "H2O", "CH4"]

# loop over all molecules
for mol in molecules:
    print(f"Checking molecule: {mol}...")
    if "C" in mol:
        print(f"{mol} contains carbon!"")
    print(f"Finished checking molecule: {mol}.")

```

The most striking feature of this code is the indentation. Notice how the 

## For loops over multiple lists
### Nested loops

### The zip function

## For loops over ranges
### The range function
### The enumerate function