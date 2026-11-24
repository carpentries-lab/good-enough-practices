---
title: What we left out
subtitle: Good practices that didn't fit in the main lesson
---

## What We Left Out

We have deliberately left many good tools and practices off our list,
including some that we use daily, because they only make sense on top of
the core practices described above, or because it takes a larger
investment before they start to pay off.

**Branches**

:   A *branch* is a "parallel universe" within a version control
repository. Developers create branches so that they can make
multiple changes to a project independently. They are central to the
way that experienced developers use systems like Git, but they add
an extra layer of complexity to version control for newcomers.
Programmers got along fine in the days of CVS and Subversion without
relying heavily on branching, and branching can be adopted without
significant disruption after people have mastered a basic
edit-commit workflow.

**Build Tools**

:   Tools like Make[^33] were originally
developed to recompile pieces of software that had fallen out of
date. They are now used to regenerate data and entire papers: when
one or more raw input files change, Make can automatically re-run
those parts of the analysis that are affected, regenerate tables and
plots, and then regenerate the human-readable PDF that depends on
them. However, newcomers can achieve the same behavior by writing
shell scripts that re-run everything; these may do unnecessary work,
but given the speed of today's machines, that is unimportant for
small projects.

**Unit Tests**

:   A *unit test* is a small test of one particular feature of a piece
of software. Projects rely on unit tests to prevent *regression*,
i.e., to ensure that a change to one part of the software doesn't
break other parts. While unit tests are essential to the health of
large libraries and programs, we have found that they usually aren't
compelling for solo exploratory work. (Note, for example, the lack
of a `test` directory in Noble's rules [[noble2009](#noble2009)].) Rather than
advocating something which people are unlikely to adopt, we have
left unit testing off this list.

**Continuous Integration**

:   Tools like Travis-CI[^34] automatically
run a set of user-defined commands whenever changes are made to a
version control repository. These commands typically execute tests
to make sure that software hasn't regressed, i.e., that things which
used to work still do. These tests can be run either before changes
are saved (in which case the changes can be rejected if something
fails) or after (in which case the project's contributors can be
notified of the breakage). CI systems are invaluable in large
projects with many contributors, but pay fewer dividends in smaller
projects where code is being written to do specific analyses.

**Profiling and Performance Tuning**

:   *Profiling* is the act of measuring where a program spends its time,
and is an essential first step in *tuning* the program (i.e., making
it run faster). Both are worth doing, but only when the program's
performance is actually a bottleneck: in our experience, most users
spend more time getting the program right in the first place.

**Coverage**

:   Every modern programming language comes with tools to report the
*coverage* of a set of test cases, i.e., the set of lines that are
and aren't actually executed when those tests are run. But as with
unit testing, this only starts to pay off once the project grows
larger, and is therefore not recommended here.

**The Semantic Web**

:   Ontologies and other formal definitions of data are useful, but in
our experience, even simplified things like Dublin
Core[^35] are rarely encountered in the wild.

**Documentation**

:   Good documentation is a key factor in software adoption, but in
practice, people won't write comprehensive documentation until they
have collaborators who will use it. They will, however, quickly see
the point of a brief explanatory comment at the start of each
script, so we have recommended that as a first step.

**A Bibliography Manager**

:   Researchers should use a reference manager of some sort, such as
Zotero[^36], and should also obtain and
use an ORCID[^37] to identify themselves
in their publications, but discussion of those is outside the scope
of this paper.

**Code Reviews and Pair Programming**

:   These practices are valuable in projects with multiple people making
large software contributions, which is not typical for the intended
audience for this paper [[petre2014](#petre2014)].

One important observation about this list is that many experienced
programmers actually do some or all of these things even for small
projects. It makes sense for them to do so because (a) they've already
paid the learning cost of the tool, so the time required to implement
for the "next" project is small, and (b) they understand that their
project will need some or all of these things as it scales, so they
might as well put it in place now.

The problem comes when those experienced developers give advice to
people who *haven't* already mastered the tools, and *don't* realize
(yet) that they will save time if and when their project grows. In that
situation, advocating unit testing with coverage checking and continuous
integration is more likely to overwhelm newcomers rather than aid them.

:::::::::::::::::::::::::::::::::::::::::  callout

## Attribution

This section is mostly material from Wilson et al.
[Good Enough Practices for Scientific Computing](https://github.com/swcarpentry/good-enough-practices-in-scientific-computing).



::::::::::::::::::::::::::::::::::::::::::::::::::


