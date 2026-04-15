# Example

In this lesson, we will illustrate the capabilities of Python by running and
editing pre-existing code.

This program:
1. Opens a `.csv` file containing UV-Vis absorption data
2. Converts its wavelength units to energy units
3. Finds all peaks in the data
4. Plots the spectrum and peaks to a scientific standard
5. Saves the figure as a `.pdf`

## Preparing your folder

The easiest way to allow Python programs to interact with files is to store the
source code in the same folder as the file. In this case, we need our `.py` file
and `.csv` files in the same place.

```{admonition} Task
Make a new folder for this lesson. Download this file: [benzene_uv-vis_nm.csv](benzene_uv-vis_nm.csv) (data from @RomandVodar1951). Save it in the folder, ensure the file is named `` and open it in a spreadsheet editor (e.g. Excel).

Also open the file in Spyder and compare it in both programs.
```

```{tip}
Comma Separated Value (`.csv`) files are often opened as spreadsheets, which
disguises the fact that they are plain text files which can be opened in Spyder,
Notepad, TextEdit, or any other such editor. Fragments of text represent values,
where lines of text correspond to rows on a spreadsheet and commas mark the
beginning of a new column.

Formatted text, or binary files, carry more information than only textual, like
typeface, images, or computer programs. This added complexity makes them harder
to use in programming.

If you are preparing a file to be read by Python, prefer plain text files and
avoid formatted ones, like `.docx` or `.xlsx`.
```

## Syntax

What now follows is a program which reads all the lines of this file which start
with a number (allowing us to skip the header). The data is stored by the
program and the last x and y data points are printed out as a health check.

```Python
"""
UV spectrum analyser

Input a spectrum in nm units and csv format.

"""

import numpy as np
import matplotlib.pyplot as plt

# parse csv data
file_name = "benzene_uv-vis_nm.csv"

wavelengths = []
absorbances = []

with open(file_name) as spec_file:
    for line in spec_file:
        # only conserve lines that start with a number
        # to skip header
        if line[0].isdigit():
            split_line = line.split(",")
            wavelengths.append(float(split_line[0]))
            absorbances.append(float(split_line[1]))

print(wavelengths[-1],absorbances[-1])
```

```{admonition} Task
Paste the code above into Spyder, save it in your working folder, and run it. Check that the output matches the
bottom line of your csv file.
```
Let's look at a few features of how Python is written, using this as an example.

- **Top to bottom**: Python code is made up of commands for the computer to
  follow. By default, they are ordered from top to bottom (the first line is
executed first, and so on). There are ways to override this rule for our
benefit, for example repeating a same line of code hundreds of times without needing to
write it repeatedly.

- **Indentation:** The space between the left of the screen and the beginning of
  Python code is called an *indent*. In Python, the indentation has a precise
meaning for the operation of the code, so it can't be changed freely to make the
program look neater. Generally, indentation is used to modify the top-to-bottom
operation of Python.

- **Colour:** Code editors highlight words using different colours to indicate
  their role in the Python language. It's as if in English, one colour was
reserved for verbs and another for nouns. Some words are invented by the
programmer, (like `file_name_`), but others are chosen from pre-existing words
with meaning (like `import` or `open`). Syntax highlighting allows you to notice
when you are choosing a word which is already reserved in Python.

- **Comments:** Programs can be hard to understand, even by experts. Therefore
  programmers leave explanatory text to help the reader understand what is going
on. These are called *comments*. Comments can be written by preceding them with
a hash symbol (`#`) or by encasing multiple lines by two sets of triple quotes
(`"""`).

- **Speech marks:** Single (`'`) or double (`"`) quotes are interchangable but don't start
  with one and end with the other.

- **Case:** Python is *case sensitive*, which means that capital and lower case
  letters are not interchangeable. Therefore, while the `print()` function is
reserved and defined in Python, `Print()` is not.

