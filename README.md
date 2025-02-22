# An Introduction to Property-Based Testing
> Created by: Zac Dodds and Ryan Soklaski

This tutorial is designed to introduce attendees to (the wonderful world of) automated testing in Python
– specifically for data science applications.

- [An Introduction to Property-Based Testing](#an-introduction-to-property-based-testing)
  - [Introduction](#introduction)
  - [Syllabus](#syllabus)
    - [Property-Based Testing 101](#property-based-testing-101)
    - [Describe your Data](#describe-your-data)
    - [Common Tests](#common-tests)
    - [Putting it into Practice](#putting-it-into-practice)
  - [Prerequisites](#prerequisites)
  - [Creating a Python Environment for this Tutorial](#creating-a-python-environment-for-this-tutorial)
  - [For Instructors](#for-instructors)

## Introduction

This tutorial is designed to promote simple but powerful methods for bolstering your software-based work/research with
property-based testing, and thereby help to close the aperture on “the things that could go wrong” because of your code.
It is structured as four blocks, each consisting of a short talk, live-coded demo, and extensive exercises for attendees:
1. Property-Based Testing 101: core concepts and the core of the Hypothesis library
2. Describe your Data: from numbers, to arrays, to recursive and more complicated things
3. Common Tests: from "does not crash" to "write+read == noop" to 'metamorphic relations'
4. Putting it into Practice: use what you've learned to find real bugs in a real project!

Each of these blocks runs for 40-60 minutes, consisting of a 5-15 minute presentation, around 5-10 minutes live-coding demo, and guided exercises.
Along with a short break in the middle, we find this pattern balances content, practice, and focus well for most classes.

[You can read through the slides here](https://docs.google.com/presentation/d/1OQLNah25gu_ElpUP0vv379dBDBZXh5LmK6fbnmMJYxM/),
as a reference for later.  Please work through the exercises for each section before reading ahead!



## Syllabus
The material will be offered as a two and a half hour session.
There will be a mixture of lectures with hands-on exercises.
The following topics will be explored:

### Property-Based Testing 101
  - In this section we will take a tour through the taxonomy of testing: encountering manual tests, parameterized tests, and property-based tests. In the meanwhile, we will be introduced to the testing library Hypothesis, which provides us with automated test-case generation and reduction.

### Describe your Data
  - It is often the case that the process of *describing our data* is by far the heaviest burden that we must bear when writing tests. This process of assessing "what variety of values should I test?", "have I thought of all the important edge-cases?", and "how much is 'enough'?" will crop up with nearly every test that we write. [Hypothesis](https://hypothesis.readthedocs.io/) is a powerful Python library that empowers us to write a _description_ (specification, to be more precise) of the data that we want to use to exercise our test.
It will then *generate* test cases that satisfy this description and will run our test on these cases.
Let's witness this in its most basic form.

### Common Tests
  - In this section, we will put Hypothesis startegies for describing data to good use and discuss some common tactics for writing effective property-based tests for our code. This will familiarize with certain patterns and properties - e.g. roundtrip pairs, equivalent functions, metamorphic relationships - to look for when crafting property-based tests for our code.

### Putting it into Practice
  - Now that we know how to write property-based tests, in this final section we will cover practical tips for using them as part of a larger project.  Test-suite design patterns, use of performance and determinism settings, reproducing test failures from a CI server, etc; they're all practical topics and typically left out of shorter introductions!


## Prerequisites

Attendees are expected to have access to a computer with with Python 3.6+ installed on it and should know how to run Jupyter notebooks.
A complete description of how to do this is detailed in [Module 1 of Python Like You Meant It](https://www.pythonlikeyoumeanit.com/module_1.html).

It is also recommended that you prepare yourself to work in your IDE of choice for Python. If you do not have an IDE that you are comfortable with yet, [Visual Studio code and PyCharm are both highly recommended](https://www.pythonlikeyoumeanit.com/Module1_GettingStartedWithPython/Getting_Started_With_IDEs_and_Notebooks.html).


## Preparing a Python Environment for this Tutorial

You will need the to install the following packages to complete this tutorial:

- numpy
- notebook
- pytest
- hypothesis

You can [create and activate a virtual environment](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/#creating-a-virtual-environment)
for the tutorial (optional but recommended), and then

```shell
> pip install notebook numpy pytest hypothesis[cli]
```

OR, to create a mini-conda environment for this tutorial, [install mini-conda](https://docs.conda.io/en/latest/miniconda.html) and then, in your terminal, execute:

```shell
> conda create -n test-tutorial python=3.8
> conda activate test-tutorial
> conda install notebook numpy pytest hypothesis[cli]
```

In this tutorial, you will be populating your own toy Python project, and will populate code under `./src/pbt_tutorial`.
Make a "dev-mode" installation of this library in your environment; navigate to the top level of this repo and run:

```shell
pip install -e .
```

This command will install `pbt_tutorial` so that any code that you add to it will immediately be reflected in your installation.
E.g. if you add to `./src/pbt_tutorial/__init__.py` the function `def my_func(): return 1`, then you will be able to import that function:

```python
>>> from pbt_tutorial import my_func
>>> my_func()
1
```

## For Instructors

The source material for this tutorial is written in [jupytext-markdown](https://jupytext.readthedocs.io/en/latest/formats.html#jupytext-markdown) in lieu of native Jupyter notebooks.
These are markdown files that can be opened as Jupyter notebooks.
These markdown notebooks contain both the exercises and solutions.
To convert these files to Jupyter notebooks to be distributed to the students, with the solutions excised, we are using the [cogbooks](https://github.com/CogWorksBWSI/Cogbooks) tool, which can be installed with: `pip install cogbooks`

