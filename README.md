# Project Part 2 - basic pile-driving app

## Purpose

Demonstrate the coding skills learned in the course to develop a notebook that could be useful for engineering professionals working on pile-driving projects.

## Instructions

Your goal for Part 2 of the course project is to build a basic pile-driving app from a jupyter notebook.
In this context, "app" doesn't mean software that runs on a mobile device, it means software that someone could use to perform a particular task on a computer if they have access to your notebook and supporting Python scripts.
The notebook itself should have minimal visible code.
The majority of your code should live in one or more Python script files that are imported into the notebook.
This helps separate the inner workings of the app from the user's experience (and also helps prevent accidental changes to the code).

The app's user should be able to:

1. Choose a pile-driving log file from within the app's file directory.
2. See a plot of the pile's driving log data vs. elevation.
3. See a plot of the pile's estimated capacity vs. elevation.
4. See a short text summary of the pile's final condition, including:
   1. Pile ID
   2. Pile tip elevation
   3. Pile load capacity

The purpose of the app and instructions for using it should be clearly described in the notebook.
Any engineer who understands the basics of pile-driving and has a basic understanding of Jupyter notebooks should be able to use the notebook and understand its output.

Additionally, the supporting code should be well-documented with docstrings.
Any individual who understands Python should be able to view the supporting code and understand how each function works by reading the docstrings. 
At a minimum, docstrings should include:

1. A description of the function's purpose.
2. A list of the function's input parameters, including whether they have default values and what units the should be in.
3. A list of the function's output parameters, including what units they will be in.

### Choosing a pile-driving log file

The way a user chooses a pile-driving log file can be as simple as typing the file name into the right place in a code cell in your notebook.
Prompting the user for input or adding graphical user interface elements is not necessary.

Your assignment repository will include a small number of properly formatted pile-driving logs for you to test your notebook with.
You should assume that app users will want to add additional pile-driving logs and select them with your app.
You may assume that any pile-driving logs the user adds will follow the same format as the sample logs.

### Plot of the driving log data

The driving log data should show the blows per minute (BPM) and blows per foot (BPF) vs. pile tip *elevation*.
The elevation should be shown on the *vertical* axis
BPM and BPF can be included on a single plot or on two separate plots, but the elevations for both datasets should align visually. 
Since the elevation needs to be on the vertical axis, this means that if two plots are used, the two plots should be side-by-side.

### Plot of the pile's estimated capacity

Similar to the driving log data, the pile capacity should be plotted vs. pile tip elevation with elevation shown on the vertical axis.

The pile's capacity should be estimated using the driving log and the $S_o$ equation.
The $S_o$ equation provides a method of estimating capacity from the hammer energy and blow count. 
It is a simplification of the rational pile formula and is based on the impulse-momentum principles of the hammer/pile system.

The $S_o$ equation is:

$$ Q = \frac{a H W}{S + S_o}$$

Where:

$$S_o = \sqrt[]{\frac{a H W L}{2 A E}} $$

And:

$Q$ = Ultimate pile capacity in pounds

$H$ = Height of hammer fall in feet

$W$ = weight of hammer in pounds

$a$ = Hammer efficiency

$L$ = Total pile length in feet

$A$ = Pile cross-sectional area in square inches

$E$ = Modulus of elasticity of pile material in pounds per square inch

$S$ = Pile penetration (in feet) per blow

Use the following pile and hammer parameters for your app's calculations:

| Parameter | Value |
|----------|-----|
| $W$ | 20,000 pounds |
| $a$ | 0.4 |
| $L$ | 150 feet |
| $A$ | 477 square inches |
| $E$ | 6,000,000 psi |

### Pile summary

The text summary of the pile's final condition should include the pile ID, final tip elevation, and final load capacity.
An example is shown below (note - 1 "kip" = 1,000 pounds):

```
Pile ID: B-14
Pile tip elevation: -134 feet
Pile load capacity: 899 kips
```

## Submission

Your project will be submitted by pushing your work to GitHub (same as the homework submission procedure).
At a minimum, the submission should include:

1. Your app's notebook (one `.ipynb` file)
2. Your app's support script (one or more `.py` files)
3. At least one of the pile-driving log data files (one or more `.csv` files)


## Grading rubric

Your submission will be graded by the instructor with the following rubric:


| Category | Criteria | Points |
|----|----|----|
| Data reading | Users have a way to change which pile-driving log is being analyzed by the app. The app will work for any properly formatted pile-driving log in the directory that the sample log files are in so that if a user adds additional logs, they can be analyzed by the app |  __ / 10 |
| App instructions | The app instructions are clearly written such that an informed (i.e., familiar with pile-driving and Jupyter notebooks) user would be able to use the app. |  __ / 10  |
| Plots | Plots of BPM, BPF, and pile load capacity are generated from the log. All plots use elevation as the vertical axis. The units of data being plotted are included and correct. |  __ / 10 |
| Output |  A short summary of the pile analysis is displayed when the app is run. The output summary includes the correct units. The information in the summary is consistent with the pile log file and the plots. |  __ / 10|
| Support code |  The functions that perform the app's calculations are imported into the app from one or more supporting Python files. The functions are well documented (purpose, inputs and outputs described in a docstring). |  __ / 10 |