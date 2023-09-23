---
title: Project Organization
teaching: 15
exercises: 10
---

::::::::::::::::::::::::::::::::::::::: objectives

- Understand elements of good naming strategy
- Evaluate pros and cons of different project organizations

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How should I name my files?
- How does folder organization help me

::::::::::::::::::::::::::::::::::::::::::::::::::

Organizing the files that make up a project in a modular, logical, and consistent
directory structure will help you and others keep track of them.

:::::::::::::::::::::::::::::::::::::::  challenge

## Project organisation problems

Discuss what can go wrong with project organisation:

- Struggling to find the code that creates a particular figure
- Hating to look at or even think about your project because of how badly organised it is

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::  callout

## README files are magic

You look at a directory (or project), you read it, and it tells you what you need to know

... as long as you keep it updated!

::::::::::::::::::::::::::::::::::::::::::::::::::

## Put each project in its own directory, which is named after the project

Similar to deciding
when a chunk of code should be made a function, the ultimate goal of
dividing research into distinct projects is to help you and others
best understand your work. Some researchers create a separate
project for each manuscript they are working on, while others group
all research on a common theme, data set, or algorithm into a single
project.

As a rule of thumb, divide work into projects or modules based on the overlap
in data and code files. If two research efforts share no data or
code, they will probably be easiest to manage independently. If they
share more than half of their data and code, they are probably best
managed together, while if you are building tools that are used in
several projects, the common code should probably be in a project of
its own.

Projects do often require their own organizational model.
The below recommendations on how you can structure data,
code, analysis outputs and other files, are drawn primarily
from [[noble2009](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000424), [gentzkow2014]]. Other structures to consider are:

- [The Turing Way](https://the-turing-way.netlify.app/reproducible-research/compendia.html#basic-compendium)
- [An individual researcher's template](https://github.com/HeidiSeibold/research-project-template)

> The important concepts are that is useful to organize the project in
> modules by the types of files and that consistent planning and good
> names help you effectively find and use things later. Your lab or
> organization may have a template to use.

## Put text documents associated with the project in the `doc` directory.

This includes
files for manuscripts, documentation for source code, and/or an
electronic lab notebook recording your experiments. Subdirectories
may be created for these different classes of files in large
projects.

## Put raw data and metadata in a `data` directory, and files generated during cleanup and analysis in a `results` directory

When we refer to "generated
files", this includes intermediate results, such as cleaned data sets or
simulated data, as well as final results such as figures and tables.

The `results` directory will *usually* require additional
subdirectories for all but the simplest projects. Intermediate files
such as cleaned data, statistical tables, and final
publication-ready figures or tables should be separated clearly by
file naming conventions or placed into different subdirectories;
those belonging to different papers or other publications should be
grouped together. Similarly, the `data` directory might require
subdirectories to organize raw data based on time, method of
collection, or other metadata most relevant to your analysis.

## Put project source code in the `src` directory

`src` contains all of
the code written for the project. This includes programs written in
interpreted languages such as R or Python; those written compiled
languages like Fortran, C++, or Java; as well as shell scripts,
snippets of SQL used to pull information from databases; and other
code needed to regenerate the results.

This directory may contain two conceptually distinct types of files
that should be distinguished either by clear file names or by
additional subdirectories. The first type are files or groups of
files that perform the core analysis of the research, such as data
cleaning or statistical analyses. These files can be thought of as
the "scientific guts" of the project.

The second type of file in `src` is controller or driver scripts
that contains all the analysis steps for the entire project
from start to finish, with particular parameters and data
input/output commands. A controller script for a simple project, for
example, may read a raw data table, import and apply several cleanup
and analysis functions from the other files in this directory, and
create and save a numeric result. For a small project with one main
output, a single controller script should be placed in the main
`src` directory and distinguished clearly by a name such as
"runall". The short example below is typical of
scripts of this kind; note how it uses one variable, `TEMP_DIR`, to
avoid repeating the name of a particular directory four times.

```
    TEMP_DIR = ./temp_zip_files

    echo "Packaging zip files required by analysis tool..."
    mkdir $(TEMP_DIR)
    ./src/make-zip-files.py $(TEMP_DIR) *.dat

    echo "Analyzing..."
    ./bin/sqr_mean_analyze -i $(TEMP_DIR) -b "temp"

    echo "Cleaning up..."
    rm -rf $(TEMP_DIR)
```

## Put compiled programs in the `bin` directory

`bin` contains
executable programs compiled from code in the `src` directory.
Projects that do not have any will not require `bin`.

> **Scripts vs. Programs**
> 
> We use the term "script" to mean "something that is executed
> directly as-is", and "program" to mean "something that is
> explicitly compiled before being used". The distinction is more
> one of degree than kind—libraries written in Python are actually
> compiled to bytecode as they are loaded, for example—so one other
> way to think of it is "things that are edited directly" and
> "things that are not".

> **External Scripts**
> 
> If `src` is for human-readable source code, and `bin` is for
> compiled binaries, where should projects put scripts that are
> executed directly—particularly ones that are brought in from
> outside the project? On the one hand, these are written in the
> same languages as the project-specific scripts in `src`; on the
> other, they are executable, like the programs in `bin`. The answer
> is that it doesn't matter, as long as each team's projects follow
> the same rule. As with many of our other recommendations,
> consistency and predictability are more important than
> hair-splitting.

## Name all files to reflect their content or function.

For example, use names
such as `bird_count_table.csv`, `manuscript.md`, or
`sightings_analysis.py`. Do *not* use sequential numbers (e.g.,
`result1.csv`, `result2.csv`) or a location in a final manuscript
(e.g., `fig_3_a.png`), since those numbers will almost certainly
change as the project evolves.

> File names should be:
> 
> - Machine readable
> - Human readable
> - Descriptive of their contents
> - Optional: Consistent
> - Optional: Play well with default ordering

## Example

The diagram below provides a concrete example of how a
simple project might be organized following these recommendations:

```
    .
    |-- CITATION
    |-- README
    |-- LICENSE
    |-- requirements.txt
    |-- data
    |   -- birds_count_table.csv
    |-- doc
    |   -- notebook.md
    |   -- manuscript.md
    |   -- changelog.txt
    |-- results
    |   -- summarized_results.csv
    |-- src
    |   -- sightings_analysis.py
    |   -- runall.py
```

The root directory contains a `README` file that provides an overview of
the project as a whole, a `CITATION` file that explains how to reference
it, and a `LICENSE` file that states the licensing.
The `requirements.txt` file lists the software that is required to run the data analysis.
The `data` directory
contains a single CSV file with tabular data on bird counts
(machine-readable metadata could also be included here). The `src`
directory contains `sightings_analysis.py`, a Python file containing
functions to summarize the tabular data, and a controller script
`runall.py` that loads the data table, applies functions imported from
`sightings_analysis.py`, and saves a table of summarized results in the
`results` directory.

This project doesn't have a `bin` directory, since it does not rely on
any compiled software. The `doc` directory contains two text files
written in Markdown, one containing a running lab notebook describing
various ideas for the project and how these were implemented and the
other containing a running draft of a manuscript describing the project
findings.

:::::::::::::::::::::::::::::::::::::::  challenge

## Naming and sorting (5 minutes)

Have a look at the example files from a project, similar
to the one from the previous metadata episode.

All the files have been sorted by name and
demonstrate consequences of different naming strategies.

For your information, to encode experimental details the following conventions were taken:

- phyB/phyA are sample genotypes (that is, which gene is mutated)
- sXX is the sample number
- LD/SD are different light conditions (long or short day)
- on/off are different media (on sucrose, off sucrose)
- measurement date
- other details are timepoint and raw or normalized data

```
2020-07-14_s12_phyB_on_SD_t04.raw.csv  
2020-07-14_s1_phyA_on_LD_t05.raw.csv  
2020-07-14_s2_phyB_on_SD_t11.raw.csv  
2020-08-12_s03_phyA_on_LD_t03.raw.csv  
2020-08-12_s12_phyB_on_LD_t01.raw.csv  
2020-08-13_s01_phyB_on_SD_t02.raw.csv  
2020-7-12_s2_phyB_on_SD_t01.raw.csv  
AUG-13_phyB_on_LD_s1_t11.raw.csv  
JUL-31_phyB_on_LD_s1_t03.raw.csv  
LD_phyA_off_t04_2020-08-12.norm.csv  
LD_phyA_on_t04_2020-07-14.norm.csv  
LD_phyB_off_t04_2020-08-12.norm.csv  
LD_phyB_on_t04_2020-07-14.norm.csv  
SD_phyB_off_t04_2020-08-13.norm.csv  
SD_phyB_on_t04_2020-07-12.norm.csv  
SD_phya_off_t04_2020-08-13.norm.csv  
SD_phya_ons_t04_2020-07-12.norm.csv  
ld_phyA_ons_t04_2020-08-12.norm.csv  
```

- What are the problems with having the date first?
- How do different date formats behave once sorted?
- Can you tell the importance of a leading 0 (zeros)?
- Is it equally easy to find all data from LD conditions as ON media?
- Can you spot the problem when using different cases (upper/lower)?
- Do you see benefits of keeping consistent lengths of the naming conventions?
- Do you see what happens when you mix conventions?

::::::::::::::::::::::::: solution



## Solution

 - Using dates up front makes it difficult to quickly find data for
   particular conditions or genotypes. It also masks the "logical" order of samples
   or timepoints.
 - Named months break the "expected" sorting, same as dates without leading 0
 - Without leading zeros, 's12' appear before s1 and s2
 - the first (and second) part of the name are easiest to spot
 - the last file is also from LD conditions, but appears after SD, same with 'phya' genotypes
 - the last 3 file names are easiest to read as all parts appear on top of each other
   due to the same 3 letter-length codes ons and off
 - The lack of consistency makes it very difficult to get data from related samples/conditions.

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::  callout

## Some helpful organisation tools

- Integrated Development Environments (IDEs) combine many features to write code and organise projects:
  - [PyCharm](https://www.jetbrains.com/pycharm/) for python
  - [RStudio for R](https://posit.co/products/open-source/rstudio/)
  - [VSCode](https://code.visualstudio.com) for python and other languages, etc.
- Notebooks collect data, code, results, thinking in single documents:
  - [jupyter](https://jupyter.org)
  - [R markdown](https://rmarkdown.rstudio.com)
  - [quarto](https://quarto.org), etc.
- [Cookie Cutter project templates for reproducible science](https://github.com/mkrapp/cookiecutter-reproducible-science)

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::  callout

## Attribution

This episode was adapted from and includes material from Wilson et al.
[Good Enough Practices for Scientific Computing](https://doi.org/10.1371/journal.pcbi.1005510).

Some content was adapted from [FAIR in Biological Practice episode on files and organisation](https://carpentries-incubator.github.io/fair-bio-practice/09-files-organization/index.html). That material gives a slightly different and also useful perspective.


::::::::::::::::::::::::::::::::::::::::::::::::::



[gentzkow2014]: https://web.stanford.edu/~gentzkow/research/CodeAndData.pdf


:::::::::::::::::::::::::::::::::::::::: keypoints

- A good file name suggests the file content
- Good project organization saves you time

::::::::::::::::::::::::::::::::::::::::::::::::::


