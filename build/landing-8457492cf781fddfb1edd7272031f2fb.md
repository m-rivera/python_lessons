# Files

## Learning outcomes

*   Read the contents of a text file.
*   Write new text files.

## Prerequisites

- [First steps](/first_steps/landing.md)
- [Variables](/variables/landing.md)
- [Control flow](/control_flow/landing.md)

## Reading files
Python has functionality to read any kind of computer file. However, making sense of a text, image, or sound file represents three very different tasks. In this lesson, we will focus on text files, since their manipulation is so common in science.

There are many different file opening methods in Python, which you may encounter especially in older programmes. Here, we will only focus on the `with open()` method, which has been recommended since Python 3.

Let's try it with an example. Download this text file ([molecule_names.txt](molecule_names.txt)) and rename it as `molecule_names.txt`. Then, copy the following example and place both the Python script containing the example (ending in `.py`) and `molecule_names.txt` in the same folder.

```Python
with open("molecule_names.txt") as file_in:
    lines_in_file = file_in.readlines()

print(lines_in_file)
```

- `with open("molecule_names.txt")` indicates that we are going to read a file called `molecule_names.txt`. This name can be replaced by any other file, but it needs to be in the same folder as your Python script to run. This restriction can be avoided by replacing the file name by a computer path indicating exactly where the file is on your computer.
- `as file_in:` assigns our file to a variable in Python: `file_in`. This variable is of a new data type called `TextIOWrapper`, which we can loosely understand as referring to the opened file. If we want to read from the file or write to it from now on, we can refer to the file as `file_in` rather than by its name (which remains just a string).
- `lines_in_file = file_in.readlines()` this is a specific way of reading text from a file. The function `file_in.readlines()` returns a list of strings, one per line of the file. However we decide to manipulate `file_in`, it needs to be done within this indentation. When the indentation ends, Python closes the file. Even if this closing is implicit, it's important to operate so that a file isn't being modified by Python and another program at the same time, yielding two conflicting versions of the file.

This final line allows us to manipulate all the information from the file, however when manipulating very large data sets, we may not want to keep all of the contents of the file in Python memory. To access files only line by line, a less intuitive but more general syntax exists. Here, we iterate over the file variable using a `for` loop, which yields each line as an individual string:

```Python
with open("molecule_names.txt") as file_in:
    for line in file_in:
        print(line)

```

Try adding more molecules to `molecule_names.txt` and ensure that they are printed by the code above.

```{admonition} Task
The following file [acetone.jdx](acetone.jdx) (data from @Linstrom1997-dp) contains the IR spectrum of acetone.

Save every line of the file as a string and append it to a list, ignoring any line that starts with `#`. Then, print the first and final lines that you saved.

```

<details><summary>Solution</summary>
Experimental text files often start with information about the instrument used to record the data (so called **metadata**). In this file, those lines all start with `#`.

```Python
data_lines = []

with open("acetone.jdx") as acetone_file:
    # loop over every line
    for line in acetone_file:
        # check that the line doesn't start with #
        if line[0] != "#":
            data_lines.append(line)

print(data_lines[0])
print(data_lines[1])
```
Usually, it takes some effort to extract exactly the data that we want from a file. Here, we wanted to remove the metadata, so we added a condition based on the `#` character. This operation is prone to error, so it's good to operate a sanity check by printing the first and final line, ensuring that we didn't accidentally remove a line we cared about.
</details>

````{admonition} Task
The data in `acetone.jdx` are organised as such:
```
wavenumber transmittance_1 transmittance_2 transmittance_3 transmittance_4 transmittance_5
wavenumber transmittance_1 transmittance_2 transmittance_3 transmittance_4 transmittance_5
...
```
where the wavenumber is in inverse centimetres and the five transmittance values are dimensionless and repeat measurements at the same wavenumber.

Generate two lists of floats:
- `wavenumbers` should contain all the wavenumbers in inverse centimetres.
- `transmittances` should contain the average of the five transmittances for each wavenumber.

Then, show the results with this block of code:

```Python
import matplotlib.pyplot as plt
plt.plot(wavenumbers, transmittances)
plt.show()
```

````