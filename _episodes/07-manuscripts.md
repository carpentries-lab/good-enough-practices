---
title: "Manuscripts"
teaching: 0
exercises: 0
questions:
- ""
- ""
- ""
objectives:
- ""
- ""
- ""
keypoints:
- ""
- ""
- ""
---

An old joke says that doing the research is the first 90% of any
project; writing up is the other 90%. While writing is rarely addressed
in discussions of scientific computing, computing has changed scientific
writing just as much as it has changed research.

Writing manuscripts is often collaborative, and so a team with
diverse backgrounds, skills, and expectations must work together.
In our experience, setting explicit expectations for writing
is essential, just like other collaborations.

> **The First Rule Is…**
>
> The workflow you choose is less important than having all authors
> agree on the workflow *before* writing starts. Make sure to also agree
> on a single method to provide feedback, be it an email thread or
> mailing list, an issue tracker, or some sort of shared online to-do list.

We suggest having a meeting (or online thread) of all authors at the
beginning of the writing process. Ask everyone how they would prefer to
write a manuscript. The agree a decision and process, and put the outcome
in writing. If co-authors are learning new tools, ask someone
familiar with those tools to support them!


### Making email-based workflows work

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
with initals and dates, and a single co-ordinator.

> **Top tips for writing manuscripts via email**
>
> 1. Give your manuscript file an informative name, and update the initials
> and date of last edit, for example `best_practices_manuscript_GW_2013-12-01`
> would be the version edited by GW on 1st December 2013.
> 2. Choose one person to co-ordinate (e.g. the first or corresponding author),
> who is responsible for merging comments and sending out updated manuscripts
> to all other co-authors.


### Good practices beyond an email-based workflow

Instead of an email-based workflow, we recommend mirroring good
practices for managing software and data to make writing scalable,
collaborative, and reproducible. As with our recommendations for version
control in general, we suggest that groups choose one of two different
approaches for managing manuscripts. The goals of both are to:

-   Ensure that text is accessible to yourself and others now and in the
    future by making a single master document that is available to all
    coauthors at all times.

-   Reduce the chances of work being lost or people overwriting each
    other's work.

-   Make it easy to track and combine contributions from multiple
    collaborators.

-   Avoid duplication and manual entry of information, particularly in
    constructing bibliographies, tables of contents, and lists.

-   Make it easy to regenerate the final published form (e.g., a PDF)
    and to tell if it is up to date.

-   Make it easy to share that final version with collaborators and to
    submit it to a journal.



### Single Master Online

Our first alternative will already be familiar to many researchers:

1.  ***Write manuscripts using online tools with rich
    formatting, change tracking, and reference
    management (6a)***, such as Google Docs.
    With the document online, everyone's changes are in one place, and
    hence don't need to be merged manually.

We realize that in many cases, even this solution is asking too much
from collaborators who see no reason to move forward from desktop GUI
tools. To satisfy them, the manuscript can be converted to a desktop
editor file format (e.g., Microsoft^^ Word `.docx` or LibreOffice
`.odt`) after major changes, then downloaded and saved in the `doc`
folder. Unfortunately, this means merging some changes and suggestions
manually, as existing tools cannot always do this automatically when
switching from a desktop file format to text and back (although
Pandoc[^27] can go a long way).


### Text-based Documents Under Version Control

The second approach treats papers exactly like software, and has been
used by researchers in mathematics, astronomy, physics, and related
disciplines for decades:

1.  ***Write the manuscript in a plain text format that
    permits version control (6b)*** such as
    LaTeX[^28] or
    Markdown[^29], and then convert them to
    other formats such as PDF as needed using scriptable tools like
    Pandoc[^30].

Using a version control system provides good support for finding and
merging differences resulting from concurrent changes. It also provides
a convenient platform for making comments and performing review.

This approach re-uses the version control tools and skills used to
manage data and software, and is a good starting point for
fully-reproducible research. However, it requires all contributors to
understand a much larger set of tools, including markdown or LaTeX,
make, BiBTeX, and Git/GitHub.

### Why Two Recommendations for Manuscripts?

We initially recommended that researchers should always using plain text
in version control to manage manuscripts. However, several members of
our community felt strongly that the learning curve associated with this
recommendation was a significant barrier to entry. For example, Stephen
Turner wrote:

> …try to explain the notion of compiling a document to an
> overworked physician you collaborate with. Oh, but before that, you
> have to explain the difference between plain text and word processing.
> And text editors. And markdown/LaTeX compilers. And BiBTeX. And Git.
> And GitHub. Etc. Meanwhile he/she is getting paged from the
> OR…
>
> …as much as we want to convince ourselves otherwise, when
> you have to collaborate with those outside the scientific computing
> bubble, the barrier to collaborating on papers in this framework is
> simply too high to overcome. Good intentions aside, it always comes
> down to "just give me a Word document with tracked changes," or
> similar.

Similarly, Arjun Raj said in a blog post[^31]:

> Google Docs excels at easy sharing, collaboration, simultaneous
> editing, commenting and reply-to-commenting. Sure, one can approximate
> these using text-based systems and version control. The question is
> why anyone would like to…
>
> The goal of reproducible research is to make sure one
> can… reproduce… computational analyses. The
> goal of version control is to track changes to source code. These are
> fundamentally distinct goals, and while there is some overlap, version
> control is merely a tool to help achieve that, and comes with so much
> overhead and baggage that it is often not worth the effort.

Collaborative editing in something like Google Docs does not have all
the benefits of text-based formats (notably, being able to store
manuscripts in the same place, and in the same way, as other materials).
However, it does meet the requirements that we initially outlined. We
still recommend *against* using desktop tools like LibreOffice and
MicrosoftWord with either email or file-sharing services like Dropbox,
as workflows based on these do not scale beyond a small number of
participants.

### Supplementary Materials

Supplementary materials often contain much of the work that went into
the project, such as tables and figures or more elaborate descriptions
of the algorithms, software, methods, and analyses. In order to make
these materials as accessible to others as possible, do not rely solely
on the PDF format, since extracting data from PDFs is notoriously hard.
Instead, we recommend separating the results that you may expect others
to reuse (e.g., data in tables, data behind figures) into separate,
text-format files in formats such as CSV, JSON, YAML, XML, or HDF5[^32].
The same holds for any commands or code you want to include as
supplementary material: use the format that most easily enables reuse
(source code files, Unix shell scripts etc).


> ## Attribution
> Content of this episode was adopted after Wilson et al.
> [Good Enough Practices for Scientific Computing](https://github.com/swcarpentry/good-enough-practices-in-scientific-computing).
{: .callout}


## I am a section

With a text.

> ## I am a yellow info
>
> And my text.
{: .callout}


~~~
I am code
~~~
{: .source}


> ## I am a problem
>
> Defined here.
>
>> ## Solution
>>
>> *   I am an answer.
>> *   So am I.
> {: .solution}
{: .challenge}



{% include links.md %}

