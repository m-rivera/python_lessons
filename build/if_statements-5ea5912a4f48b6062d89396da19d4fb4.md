# If statements
## Learning outcomes

*   Use comparison operators to write conditions.
*   Use "if statements" to execute code based on these conditions.

## Prerequisites

- [First steps](/first_steps/landing.md)
- [Variables](/variables/landing.md)

## Conditions
### Comparison operators
Our goal in this lesson is to learn to control whether a particular piece of code is executed by Python or is ignored, based on conditions set by us. Since these conditions are binary (execute the code or don't), they should always come down to a boolean value of `True` or `False`.

The essential way to write a condition is to place two values on either side of a *comparison operator*. For example, using the 'lesser than' comparison operator `<`:

```Python
print(1 < 3)
print(3 < 1)
```
you should see the code above output `True`, then `False`.

The common comparison operators you may encounter are the following:

| Operator | Definition | Example |
| --------- | --------- | -------|
| == | is equal to | ``a == b`` |
| != | is not equal to, &ne; | ``a != b`` |
| > | is greater than | ``a > b`` |
| < | is less than | ``a < b`` |
| >= | is greater than or equal to, &ge; | ``a >= b``|
| <= | is less than or equal to, &le; | ``a <= b`` |
| in | the object contains another object | ```a in b``` |

````{tip}
You may use `in` to check whether a value is within a list:
```Python
solvents = ["water", "ethanol", "DMSO"]
print("ethanol" in solvents)
print("methanol" in solvents)
```
You can also use it to check if a string is inside another string:
```Python
solvent = "methanol"
print("anol" in "methanol")
print("ate" in "methanol")
```
````
````{admonition} Task
In the comparisons in the code below, replace each dash with different comparison operators to get a True output.<br>
```Python
num_nitrogen = 7
num_fluorine = 9

print(num_nitrogen -- num_fluorine)
print(num_fluorine -- num_nitrogen)
print(num_fluorine -- num_nitrogen)
print(num_fluorine -- num_fluorine)
```
````
<details> <summary>Solution</summary>
Here is a set of possible solutions:

```Python
print(num_nitrogen < num_fluorine)
print(num_fluorine > num_nitrogen)
print(num_fluorine >= num_nitrogen)
print(num_fluorine == num_fluorine)
```
</details>

Although most of these comparison operators have an opposite one available, it is sometimes helpful for clarity to invert a condition. To achieve this, precede a comparison by `not`:
```Python
boiling_point = 100.0
temp = 73.3

print("Is the water boiling?", not temp < boiling_point)

```

````{admonition} Task
Read the following comparison statements and predict the output:
```Python
print("Equality")
print(3.14 == 3.15)
print(3.14 == 3.14)
print(3.0 == 3)
print("3.14" == 3.14)
print(3.14 != 3.15)
print(not 3.14 != 3.15)

print("Inequality)
print(3 < 4)
print(-3 > 3)
print(not 5 >= 5)
```

````

Comparisons, and boolean values in general, can be combined to gether to make more complicated expressions. We achieve this using *boolean opeartors*

| Operator | Definition | Example (x and y are comparisons) |
| ----- | ---- | ----- |
| and | Both instances must be True to return True, otherwise will return False. | ``x and y`` |
| or | Either instance can be True in order to return True. If both instances are False, will return False. | `` x or y `` |
| not | If the Boolean value of the instance is True, the program will return False. Essentially inverts the logic. | ``not y`` |

This allows us to make combined statements of the form:
```Python
a = 1
b = 2
c = 3
print(a < b and b <= c)
```

These combined statements can start looking quite messy, but we the help of parentheses, we can impose an order of operation and make things neater:
```Python
a = 1
b = 2
c = 3
d = 4
print((a < b or b <= c) and (b < d))
```

##
