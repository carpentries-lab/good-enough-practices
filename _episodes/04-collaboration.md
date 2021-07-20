---
title: "Collaboration"
teaching: 0
exercises: 0
questions:
- "What do collaborators need to know to contribute to my project?"
- "How can documentation make my project more efficient?"
- "What is a (software) license and does my project need one?"
objectives:
- "Facilitate contributions from present and future collaborators."
- "Learn to treat every project as a collaborative project."
- "Describe a project in a README file."
- "Evaluate software licenses for your project."
keypoints:
- "Create an overview of your project."
- "Create a shared “to-do” list."
- "Decide on communication strategies."
- "Make the license explicit."
- "Make the project citable."
---

You may start working on projects by yourself or with a small group of
collaborators you already know, but you should design it to make it easy
for new collaborators to join. These collaborators might be new grad
students or postdocs in the lab, or they might be *you* returning to a
project that has been idle for some time. As summarized in
[[steinmacher2015](#steinmacher2015)], you want to make it easy for people to set up a local
workspace so that they *can* contribute, help them find tasks so that
they know *what* to contribute, and make the contribution process clear
so that they know *how* to contribute. You also want to make it easy for
people to give you credit for your work.

> ## Collaboration problems
>
> Discussion – what goes wrong with collaboration?
>
>> ## Solution
>>
>> *   What are we trying to do?
>> *   Whose job is it to do this thing?
> {: .solution}
{: .challenge}

### Create an overview of your project.

Have a short file in the
project's home directory that explains the purpose of the project.
This file (generally called `README`, `README.txt`, or something
similar) should contain the project's title, a brief description,
up-to-date contact information, and an example or two of how to run
various cleaning or analysis tasks. It is often the first thing
users and collaborators on your project will look at, so make it
explicit how you want people to engage with the project. If you are
looking for more contributors, make it explicit that you welcome
contributors and point them to the license (more below) and ways
they can help.

You should also create a `CONTRIBUTING` file that describes what
people need to do in order to get the project going and use or
contribute to it, i.e., dependencies that need to be installed,
tests that can be run to ensure that software has been installed
correctly, and guidelines or checklists that your project adheres
to.

### Create a shared "to-do" list.

This can be a plain text
file called something like `notes.txt` or `todo.txt`, or you can use
sites such as GitHub or Bitbucket to create a new *issue* for each
to-do item. (You can even add labels such as "low hanging fruit" to
point newcomers at issues that are good starting points.) Whatever
you choose, describe the items clearly so that they make sense to
newcomers.

### Decide on communication strategies.

Make explicit
decisions about (and publicize where appropriate) how members of the
project will communicate with each other and with externals users /
collaborators. This includes the location and technology for email
lists, chat channels, voice / video conferencing, documentation, and
meeting notes, as well as which of these channels will be public or
private.

### Make the license explicit.


> ## What is a licence?
>
> - Specifies allowable copying and reuse
> - Without a licence, people cannot legally reuse your code or data
> - Different options for different goals and funder requirements (Apache, MIT, CC, ...)
> - For example, this lesson is reusable with attribution under a Creative Commons Attribution (CC BY) 4.0 licence.
>
{: .callout}

Have a `LICENSE` file
in the project's home directory that clearly states what license(s)
apply to the project's software, data, and manuscripts. Lack of an
explicit license does not mean there isn't one; rather, it implies
the author is keeping all rights and others are not allowed to
re-use or modify the material.

We recommend Creative Commons licenses for data and text, either
CC-0[^15] (the "No Rights Reserved"
license) or CC-BY[^16] (the "Attribution"
license, which permits sharing and reuse but requires people to give
appropriate credit to the creators). For software, we recommend a
permissive open source license such as the MIT, BSD, or Apache
license [[laurent2004](#laurent2004)].


> **What Not To Do**
>
> We recommend *against* the "no commercial use" variations of the
> Creative Commons licenses because they may impede some forms of
> re-use. For example, if a researcher in a developing country is
> being paid by her government to compile a public health report,
> she will be unable to include your data if the license says
> "non-commercial". We recommend permissive software licenses rather
> than the GNU General Public License (GPL) because it is easier to
> integrate permissively-licensed software into other projects, see
> chapter three in [[laurent2004](#laurent2004)].

### Make the project citable.

by including a `CITATION`
file in the project's home directory that describes how to cite this
project as a whole, and where to find (and how to cite) any data
sets, code, figures, and other artifacts that have their own DOIs.
The example below shows the `CITATION` file for the
Ecodata Retriever[^17]; for an example of
a more detailed `CITATION` file, see the one for the
khmer[^18] project.

    Please cite this work as:

    Morris, B.D. and E.P. White. 2013. "The EcoData Retriever:
    improving access to existing ecological data." PLOS ONE 8:e65848.
    http://doi.org/doi:10.1371/journal.pone.0065848

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

