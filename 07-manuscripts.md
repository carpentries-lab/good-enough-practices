---
title: Manuscripts
teaching: 10
exercises: 10
---

::::::::::::::::::::::::::::::::::::::: objectives

- Know how to frame writing manuscripts as a computing project
- Compare the benefits and drawbacks of 3 approaches
- Know where to start with text-based version control as a good practice for writing manuscripts

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::: questions

- How do I write a collaborative paper?

::::::::::::::::::::::::::::::::::::::::::::::::::

An old joke says that doing the research is the first 90% of any
project; writing up is the other 90%. While writing is rarely addressed
in discussions of scientific computing, computing has changed scientific
writing just as much as it has changed research.

Writing manuscripts is often collaborative, and so a team with
diverse backgrounds, skills, and expectations must work together.
In our experience, setting explicit expectations for writing
is essential, just like other collaborations.

:::::::::::::::::::::::::::::::::::::::  challenge

## Discussion (3 mins)

Whether or not you have written a scientific manuscript before,
you probably have experience of group work or writing.
Discuss on the collaborative document:

- What tools have you used before for group writing?
- What's gone wrong with group writing you've been involved with in the past?
  

::::::::::::::::::::::::::::::::::::::::::::::::::

> **The First Rule Is…**
> 
> The workflow you choose is less important than having all authors
> agree on the workflow *before* writing starts. Make sure to also agree
> on a single method to provide feedback, be it an email thread or
> mailing list, an issue tracker, or some sort of shared online to-do list.

We suggest having a meeting (or online thread) of all authors at the
beginning of the writing process. Ask everyone how they would prefer to
write a manuscript. Then agree on a decision and process, and put the outcome
in writing. If co-authors are learning new tools, ask someone
familiar with those tools to support them!

## Making email-based workflows work

A common practice in academic writing is for the lead author to email
successive versions of a manuscript to coauthors to collect feedback,
which is returned as changes to the document, comments on the document,
plain text in email, or a mix of all three. This allows co-authors to
use familiar tools, but results in a lot of files to keep track of, and
a lot of tedious manual labor to merge comments to create the next
master version.

However, if a (senior) co-author insists on using a particular format,
like word or LaTeX, or on sending comments by email or written on printouts,
in our experience it can be very difficult to convince them to change.
Two principles make an email-based workflow work: informative filenames
with date and initials, and a single lead author who co-ordinates.

> **Top tips for writing manuscripts via email**
> 
> 1. Give your manuscript file an informative name, and update the date and
>   initials of last edit, for example `best_practices_manuscript_2013-12-01_GW.doc`
>   would be the version edited by GW on 1st December 2013.
> 2. Choose one person to co-ordinate (i.e. the lead author),
>   who is responsible for merging comments and sending out updated manuscripts
>   to all other co-authors.

## Good practices beyond an email-based workflow

Instead of an email-based workflow, we recommend mirroring good
practices for managing software and data to make writing scalable,
collaborative, and reproducible. As with our recommendations for version
control in general, we suggest that groups choose one of two different
approaches for managing manuscripts. The goals of both are to:

- Ensure that text is accessible to yourself and others now and in the
  future by making a single master document that is available to all
  coauthors at all times.

- Reduce the chances of work being lost or people overwriting each
  other's work.

- Make it easy to track and combine contributions from multiple
  collaborators.

- Avoid duplication and manual entry of information, particularly in
  constructing bibliographies, tables of contents, and lists.

- Make it easy to regenerate the final published form (e.g., a PDF)
  and to tell if it is up to date.

- Make it easy to share that final version with collaborators and to
  submit it to a journal.

## Single Master Online

Our first alternative will already be familiar to many researchers:

1. ***Write manuscripts using online tools with rich
  formatting, change tracking, and reference
  management***, such as Google Docs or MS OneDrive.
  With the document online, everyone's changes are in one place, and
  hence don't need to be merged manually.

We realize that in many cases, even this solution is asking too much
from collaborators who see no reason to move forward from desktop GUI
tools. To satisfy them, the manuscript can be converted to a desktop
editor file format (e.g., Microsoft Word `.docx` or LibreOffice
`.odt`) after major changes, then downloaded and saved in the `doc`
folder. Unfortunately, this means merging some changes and suggestions
manually, as existing tools cannot always do this automatically when
switching from a desktop file format to text and back (although
[Pandoc](https://pandoc.org/) can go a long way).

## Text-based Documents Under Version Control

The second approach treats papers exactly like software, and has been
used by researchers in mathematics, astronomy, physics, and related
disciplines for decades:

1. ***Write the manuscript in a plain text format that
  permits version control*** such as
  [LaTeX](https://www.latex-project.org/) or
  [Markdown](https://daringfireball.net/projects/markdown/), and then convert them to
  other formats such as PDF as needed using scriptable tools like
  [Pandoc](https://pandoc.org/).

Using a version control system provides good support for finding and
merging differences resulting from concurrent changes. It also provides
a convenient platform for making comments and performing review.

This approach re-uses the version control tools and skills used to
manage data and software, and is a good starting point for
fully-reproducible research. However, it requires all contributors to
understand a much larger set of tools, including [markdown](https://www.markdownguide.org) or LaTeX,
make, BiBTeX, and Git/GitHub.

It is even possible using this approach to combine manuscripts and data analysis,
e.g. through [Rmarkdown](https://rmarkdown.rstudio.com/).

> **Top tips for writing manuscripts via text-based version control**
> 
> 1. Project organization is crucial here, structure your folder thoughtfully.
> 2. Make a project/manuscript README file, including the agreed workflow.
> 3. Separate sentences by linebreaks in your plain-text document, to make comparisons and merging easier.

## Benefits and drawbacks of each approach

| Things to consider                           | Email based workflow | Single master online | Text-based under version control | 
| -------------------------------------------- | -------------------- | -------------------- | -------------------------------- |
| Previous user experience/comfort             | High                 | Medium               | Low                              | 
| Visible tracking of changes                  | Low                  | Variable             | High                             | 
| Institutional support                        | Low                  | High                 | Low                              | 
| Ease of merging changes and suggestions      | Low                  | Medium               | High                             | 
| Distributed control                          | Low                  | High                 | High                             | 
| Ease of formatting changes for re-submission | Low                  | Low                  | High                             | 

While we feel that text-based version control is a superior method,
the barriers to entry may be too high for many users.
The single master online approach is a good compromise.
If your institution has invested in an environment (Google Docs / MS Office),
users can stay within their familiar desktop GUI applications while still
taking advantage of automatic file versioning and shared editing.

:::::::::::::::::::::::::::::::::::::::  challenge

## Discussion: Approaching your next manuscript (7 mins)

In groups, discuss:

- What's the next manuscript you'll work on, and who with?
- Which approaches will you use to collaborate on this next manuscript?
  

::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::::  callout

## Getting started writing text-based version control

[Version Control with Git](https://swcarpentry.github.io/git-novice/) Carpentries lesson introduces text-based version control, that you could use for a collaborative manuscript.

[Manubot](https://manubot.org) is an open-source system for writing scholarly manuscripts via GitHub, with tutorials.


::::::::::::::::::::::::::::::::::::::::::::::::::

## Supplementary Materials

Supplementary materials often contain much of the work that went into
the project, such as tables and figures or more elaborate descriptions
of the algorithms, software, methods, and analyses. In order to make
these materials as accessible to others as possible, do not rely solely
on the PDF format, since extracting data from PDFs is notoriously hard.
For the same reason, Excel is not a suitable file format for table data
that others may want to re-analyze. It is acceptable for summary statistics
tables so long as the underlying data is also available in a text file format such as CSV.

We recommend separating the results that you may expect others
to reuse (e.g., data in tables, data behind figures) into separate,
text-format files in formats such as CSV, JSON, YAML, XML, or HDF5.
The same holds for any commands or code you want to include as
supplementary material: use the format that most easily enables reuse
(source code files, Unix shell scripts etc).

:::::::::::::::::::::::::::::::::::::::::  callout

## Attribution

This episode was adapted from and includes material from Wilson et al.
[Good Enough Practices for Scientific Computing](https://github.com/swcarpentry/good-enough-practices-in-scientific-computing).


::::::::::::::::::::::::::::::::::::::::::::::::::



:::::::::::::::::::::::::::::::::::::::: keypoints

- Have all authors agree on a workflow before the writing starts
- Email-based workflows work better with informative filenames and clear co-ordination
- Text-based documents with version control scale better, if co-authors are familiar with the tools
- Single Master Online approaches can be an effective compromise

::::::::::::::::::::::::::::::::::::::::::::::::::


