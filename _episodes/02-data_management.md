---
title: "Data Management"
teaching: 0
exercises: 0
questions:
- "What is data management?"  
- "How should I back up my data?"  
- "What data should I back up?"  
- "How should I name my data?"  
- "How do I share my data?"  
- "How do I uniquely and persistently identify my data?"  

objectives:  
- "Identify problems with data management practices"  
- "Understand what raw data is"  
- "Understand what is backing up data and why it is important to back up in more than one location"  
- "Be able to decide on appropiate file names and identifiers"  
- "Be able to create analysis ready datasets"  
- "Understand the importance of documenting your process"  
- "Understand what a DOI is and its usefulness"  

keypoints:  
- "Raw data is the data as originally generated. It should be kept read-only"  
- "Raw data has to be backed up in more than one location"  
- "Create the data you wished you have received"  
- "Keeping track of your actions is a key part of data management"  
- "The Digital object identifiers (DOIs) is a unique identifier that permanently identifies data and makes it findable"  
- "Finding a repository tailored to your data is key to making it finable and accessible by the broader community"  

---

![Figure 1. Four stages of data loss](../fig/ew-data-loss.png)
Source: PHD Comics. ["Four stages of data loss"](http://phdcomics.com/comics/archive.php/images/archive.php?comicid=382) 

> ## Data management problems (2+2 minutes)  
> In your opinion, what can go wrong with data management? Write down 2 issues in the collaborative document.  
>   
> > ## Solution  
> > * Data loss  
> > * Data corruption  
> > * Confusion: what does this data mean? where does it come from? what is its purpose?   
> > * Versioning issues: Which version of the analysis script was used for the manuscript?   
> >   
> {: .solution}  
{: .challenge}  

## Data management  
Data within a project may need to exist in various forms, ranging from what first arrives to what is actually used for the primary analyses.  
Data management is the process of storing, documenting, organising, and sharing the data created and collected during a project.  
Our recommendations have two main themes. One is to work towards ready-to-analyze data incrementally, documenting both the intermediate data and the process. We also describe the key features of "tidy data", which can be a powerful accelerator for analysis [[wickham2014](#wickham2014), [hart2016](#hart2016)].

### Save the raw data  
> ## Backing up your data (2+2 minutes)  
>  
> Which of the following do you believe are good ways and bad ways of backing up your data?  
> * Commercial cloud service  
> * In-house cloud service  
> * USB pen-drive  
> * External hard-drive  
> * My laptop  
> * My workstation's hard-disk  
> * Network drive  
> 
> > ## Solution  
> > Commercial cloud service: it depends. Where are the servers located? How secure is it? How reliable is it?  
> > In-house cloud service: this is a good way to back up your data (usually). You have local support. It is probably compliant with funders and data security guidelines.  
> > USB pen drive: definitely not! pen-drives are prone to dying (and your data with it). It also raises data security issues.  
> > External hard-drive: see above.  
> > My laptop: it is good as a temporal storage solution for your active data. However, you should back it up appropiately.  
> > My workstation's hard-disk: it is good as a temporal storage solution for your active data. However, you should back it up appropiately.  
> > Network drive: this is a good way to back up your data (usually). You have local support. It is probably compliant with funders and data security guidelines.  
> {: .solution}  
{: .challenge}  
  
Where possible, save data as originally generated (i.e. by an
instrument or from a survey). It is tempting to overwrite raw data
files with cleaned-up versions, but faithful retention is essential
for re-running analyses from start to finish; for recovery from
analytical mishaps; and for experimenting without fear. Consider
changing file permissions to read-only or using spreadsheet
protection features, so it is harder to damage raw data by accident
or to hand edit it in a moment of weakness.

Some data will be impractical to manage in this way. For example,
you should avoid making local copies of large, stable databases. In
that case, record the exact procedure used to obtain the raw data,
as well as any other pertinent information, such as an official
version number or the date of download.

**Ensure that raw data is backed up in more than one location.**  
> ## Discussion (2 minutes)  
> How do you back-up your data? Enter your answers in the collaborative document.  
{: .challenge}  
  
If external hard drives
are used, store them off-site of the original location. Universities
often have their own data storage solutions, so it is worthwhile to
consult with your local Information Technology (IT) group or
library. Alternatively cloud computing resources, like
Amazon Simple Storage Service (Amazon
S3)[^4], Google Cloud
Storage[^5] or
https://azure.microsoft.com/en-us/services/storage/ are
reasonably priced and reliable. For large data sets, where storage
and transfer can be expensive and time-consuming, you may need to
use incremental backup or specialized storage systems, and people in
your local IT group or library can often provide advice and
assistance on options at your university or organization as well.

### Create the data you wish to see in the world  
> ## Discussion (2 minutes)  
> Which file formats do you store your data in? Enter your answers in the collaborative document.  
{: .challenge}  
  
*Filenames*: Store especially useful metadata as part of the
filename itself, while keeping the filename regular enough for easy
pattern matching. For example, a filename like
`2016-05-alaska-b.csv` makes it easy for both people and programs to
select by year or by location.

*Variable names*: Replace inscrutable variable names and artificial
data codes with self-explaining alternatives, e.g., rename variables
called `name1` and `name2` to `personal_name` and `family_name`,
recode the treatment variable from `1` vs. `2` to `untreated` vs.
`treated`, and replace artificial codes for missing data, such as
"-99", with `NA`, a code used in most programming languages to
indicate that data is "Not Available" [[white2013](#white2013)].

*File formats*: Convert data from closed, proprietary formats to
open, non-proprietary formats that ensure machine readability across
time and computing setups [[UIllinois](#UIllinois)]. Good options include CSV for
tabular data, JSON, YAML, or XML for non-tabular data such as
graphs[^6], and HDF5 for certain kinds of structured data.

Create the dataset you *wish* you had received. The goal here is to improve machine and
human readability, but *not* to do vigorous data filtering or add
external information. Machine readability allows automatic
processing using computer programs, which is important when others
want to reuse your data. Specific examples of non-destructive
transformations that we recommend at the beginning of analysis:

### Create analysis-friendly data  
> ## Discussion (2 minutes)  
> Which of the table layouts is analysis friendly? Discuss. Enter your answers in the collaborative document.  
> ![Figure 2. Tidy data](../fig/wilson-tidy-data.png)  
{: .challenge}  
  
Analysis can be much easier
if you are working with so-called "tidy" data [[wickham2014](#wickham2014)]. Two key
principles are:

*Make each column a variable*: Don't cram two variables into one,
e.g., "male\_treated" should be split into separate variables for
sex and treatment status. Store units in their own variable or in
metadata, e.g., "3.4" instead of "3.4kg".

*Make each row an observation*: Data often comes in a wide format,
because that facilitated data entry or human inspection. Imagine one
row per field site and then columns for measurements made at each of
several time points. Be prepared to gather such columns into a
variable of measurements, plus a new variable for time point.
Figure 2 presents an example of such a transformation.


### Record all the steps used to process data

Data manipulation is as
integral to your analysis as statistical modeling and inference. If
you do not document this step thoroughly, it is impossible for you,
or anyone else, to repeat the analysis.

The best way to do this is to write scripts for *every* stage of
data processing. This might feel frustratingly slow, but you will
get faster with practice. The immediate payoff will be the ease with
which you can re-do data preparation when new data arrives. You can
also re-use data preparation steps in the future for related
projects. For very large data sets, data preparation may also
include writing and saving scripts to obtain the data or subsets of
the data from remote storage.

Some data cleaning tools, such as
OpenRefine[^7], provide a graphical user
interface, but also automatically keep track of each step in the
process. When tools like these or scripting is not feasible, it's
important to clearly document every manual action (what menu was
used, what column was copied and pasted, what link was clicked,
etc.). Often you can at least capture *what* action was taken, if
not the complete *why*. For example, choosing a region of interest
in an image is inherently interactive, but you can save the region
chosen as a set of boundary coordinates.

> ## How, when and why do you document?  
> As much as possible, always and to help you future self.  
{: .callout}   

### Anticipate the need to use multiple tables, and use a unique identifier for every record

Raw data, even if tidy,
is not necessarily complete. For example, the primary data table
might hold the heart rate for individual subjects at rest and after
a physical challenge, identified via a subject ID. Demographic
variables, such as subject age and sex, are stored in a second table
and will need to be brought in via merging or lookup. This will go
more smoothly if subject ID is represented in a common format in
both tables, e.g., always as "14025" versus "14,025" in one table
and "014025" in another. It is generally wise to give each record or
unit a unique, persistent key and to use the same names and codes
when variables in two datasets refer to the same thing.

### Submit data to a reputable DOI-issuing repository so that others can access and cite it.  
> ## Sharing your data with the world (2+2 minutes)  
>  
> Which of the following places would be good places to share your data?  
> * Personal/lab web-site  
> * Github  
> * General repo (i.e.: Zenodo, Data Dryad, etc.)  
> * Community specific repo (i.e.: ArrayExpress, SRA, EGA, PRIDE, etc.)  
>   
> > ## Solution  
> > Personal/lab web-site: this is not the best place to store your data long-term. Can you think of why?  
> > Github: in itself it is not proper for sharing your data as it can be modified. However, a snapshot of a Github repository can be stored in Zenodo and be issued a DOI.   
> > General repo (i.e.: Zenodo, Data Dryad, etc.): good option to deposit data that does not fit in a specific repository.  
> > Community specific repo (i.e.: ArrayExpress, SRA, EGA, PRIDE, etc.): best option to share your data.  
> >  
> {: .solution}  
{: .challenge}  

Your data is as much a
product of your research as the papers you write, and just as likely
to be useful to others (if not more so). Sites such as
Figshare[^8],
Dryad[^9], and
Zenodo[^10] allow others to find your
work, use it, and cite it; we discuss licensing in
Section [sec:collaboration] below. Follow your research community's
standards for how to provide metadata. Note that there are two types
of metadata: metadata about the dataset as a whole and metadata
about the content within the dataset. If the audience is humans,
write the metadata (the README file) for humans. If the audience
includes automatic metadata harvesters, fill out the formal metadata
and write a good README file for the humans [[wickes2015](#wickes2015)].

> ## What is a DOI?  
> - A digital object identifier is a persistent identifier or handle used to identify objects uniquely.  
> - Data with a persistent doi can be found even when your lab website dies  
> - doi-issuing repositories include: zenodo, figshare, dryad  
>  
{: .callout}  

> ## Places to share Data, with DOIs
>
> - UoE DataShare (https://datashare.is.ed.ac.uk/) local open-access repository
> - UoE DataVault (https://datavault.ed.ac.uk) local long-term retention.
> - Dataverse (http://thedata.org): A repository for research data that takes care of long-term preservation and good archival practices, while researchers can share, keep control of, and get recognition for their data.
> - FigShare (http://figshare.com): A repository where users can make all of their research outputs available in a citable, shareable, and discoverable manner.
> - Zenodo (http://zenodo.org): A repository service that enables researchers, scientists, projects, and institutions to share and showcase multidisciplinary research results (data and publications)
> - Dryad (http://datadryad.org): A repository that aims to make data archiving as simple and as rewarding as possible through a suite of services not necessarily provided by publishers or institutional websites.
>
{: .callout}

### Summary

Taken in order, the recommendations above will produce intermediate data
files with increasing levels of cleanliness and task-specificity. An
alternative approach to data management would be to fold all data
management tasks into a monolithic procedure for data analysis, so that
intermediate data products are created "on the fly" and stored only in
memory, not saved as distinct files.

While the latter approach may be appropriate for projects in which very
little data cleaning or processing is needed, we recommend the explicit
creation and retention of intermediate products. Saving intermediate
files makes it easy to re-run *parts* of a data analysis pipeline, which
in turn makes it less onerous to revisit and improve specific data
processing tasks. Breaking a lengthy workflow into pieces makes it
easier to understand, share, describe, and modify. This is particularly
true when working with large data sets, where storage and transfer of
the entire data set is not trivial or inexpensive.


> ## Attribution
> Content of this episode was adopted after Wilson et al.
> [Good Enough Practices for Scientific Computing](https://github.com/swcarpentry/good-enough-practices-in-scientific-computing).
{: .callout}


{% include links.md %}

