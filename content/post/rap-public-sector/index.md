---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "RAPping in the public sector"
subtitle: ""
summary: ""
toc: true
authors: []
tags: []
categories: []
date: 2021-11-10T10:57:47+13:00
lastmod: 2021-11-10T10:57:47+13:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

## The ubiquity of bad processes
Public sector, indeed even private sector, analytics are rife with silos and people-driven pipelines. Instead of building processes with minimal manual interference, pipelines are ususally a  mash of the metaphorical ductape and frenetic manual steps resulting in blood, sweat and tears for any analyst who subsequently picks up the work. 

Manual processes need to be overseen: to start, pause, stop, make changes, perform checks etc. This overload of analyst headspace can have costly outcomes due to inevitable human error. Fortunately, most of these steps can be automated allowing the analyst to dedicate their skills to using the data and providing business-relevant value. 


{{< mermaid align="left" theme="neutral" >}}
graph TD
data --> a[Put in Excel]
a --> b[Run manual calculations]
b --> c1[Excel sheet <br> with <br> manual checks]
b --> c[Copy output <br> to <br> Excel / Word]
c --> e[Review]
e --> |Changes needed| b
e  --> |Changes needed| data
{{< /mermaid >}}


## RAP to overcome bad processes
One nifty framework for moving from manual processes is RAP or reproducible analytical pipelines. Coined by the UK Government Statistical Service, [RAP](https://gss.civilservice.gov.uk/reproducible-analytical-pipelines/) brings in concepts and practices from data engineering, devops and software carpentry domains to analysts in the public sector. 

> Reproducible Analytical Pipelines (RAPs) are automated statistical and analytical processes. They incorporate elements of software engineering best practice to ensure that the pipelines are reproducible, auditable, efficient, and high quality.

These practices include: 

- Substituting manual steps with code 
- Using modern, open source programming languages 
- Converting raw data to statistical output with pipelines / workflows
- Using version control to keep records of development
- Bringing in code review practices


Despite its utility, RAP focuses primarily on converting data from a commonly-managed data store into analytical outputs (reports, tables, models etc). However, in the infrastructure-poor environments of many public sector organisations, data is often inaccessible with no automated process that transforms it from raw data to a form fit for subsequent RAPping. This means the concepts of RAP need to be brought further back into the data analysis process - into the 'data engineering domain'. 

{{< mermaid align="left" theme="neutral" >}}
graph LR
rd[Raw data source] --> lc[Local copy]
lc --> pr1[Transformation application]
pr1 --> pd[Processed data]
pd --> rep[Reports]
pd --> tab[Tables]
pd --> db[Dashboards]
{{< /mermaid >}}


## RAPping with legacy code
For any analyst who has inherited a pre-existent data processing code base replete with manual management, it's not trivial to rewrite it with RAP principles. Complicated functionality can be difficult to rewrite, and some data extraction steps are challenging. One example of a hard-to-move legacy code base has the following steps: 


{{< mermaid align="left" theme="neutral" >}}
flowchart LR
	
	subgraph EXTRACT
		direction TB
			oi[Outlook inbox] --> |Download manually|gs[Get and save data]
			gs --> |Rename file <br> change column types|rd[Raw data store]
	end
	
	subgraph TRANSFORM
		direction TB
            e[Raw data store] -->|Manual filename change| sas_read
			sas_read[Read raw data <br> into SAS format] --> |Manual filename change| sas_trans[Transform data]
			sas_trans --> data[Processed data]
	end

fa[feed A] -->|automated <br> delivery| EXTRACT --> TRANSFORM 
{{< /mermaid >}}

In the following sections, I will briefly sketch one route to RAPping this difficult process. Subsequent posts will cover more nuance in creating local versions of RAP (that include data engineering) and different strategies for making the best use of open source tools and practices. Note, much of the following content can be found in my [talk at Statistics New Zealand](https://shriv-portfolio.netlify.app/talk/rap-statsnz/). 


### Python as glue
Python is a modern, multi-paradigm, evolving, open source programming language. It is used widely across many domains - from web development to data science. Due to its breadth of use and popularity, there is an incredible ecosystem of packages. In addition, manual steps like the following can all be done using Python. 

- Changing file names in scripts to the latest data
- Getting data deliveries from Outlook inboxes
- Running scripts in order 

Python and its rich ecosystem of packages can be used be used as a glue, or interface between different programs. Packages like `exhangelib` and `saspy` can connect to APIs and programs like Outlook and SAS respectively. More on how these packages facilitate automation in the following sections. 

Another aspect of pythonic glue is `gluing` together a linear pipeline / workflow in a [Jupyter notebook](https://jupyter.org/). Cells in the notebook can be run in any order manually but using the `Run All` command sets up a linear execution - cells are run in series giving immediate linear dependency. 

{{< mermaid align="left" theme="neutral" >}}
graph TD
f[feed A] --> e[Outlook inbox]
beq --> |exchangelib| e
sc[SAS Code] --> |yaml| pws

subgraph Jupyter NOTEBOOK
	dr[Date range] --> beq[[Build email query]]
	beq --> |exchangelib <br> pandas|gsd[[Get and save data]]
	gsd --> rd[Raw data store]
	rd --> |saspy| pws[[Process with SAS]]
	pws --> pd[Processed data]
end
{{< /mermaid >}}

Jupyter notebooks also have additional features like:

- Including documentation alongside code execution - easily updated while pipeline development is still in flux
- Including checks (as tables or graphs) as part of the pipeline making the executed notebook a log of the processing run that can be saved for posterity. 
- Using Python's `try execpt` can be used to raise errors and stop execution of the pipeline to give the analyst time to correct.
- Since executed outputs are stored in memory so with a sensible structure, it can be quite easy to re-run the notebook from an intermediate point rather than run the entire process again after correcting any issues. 


## Down in the details
The following sections give a little more detail into how `exchangelib` and `saspy` help with hard to automate tasks like:

(1) automatically downloading relevant data sent by email
(2) automating SAS code that needs to be run with manual changes (e.g. new file names, data ranges etc.)


### Getting data with APIs
Using email inboxes as a primary data receiver is a common problem since public sector analysts lack the technology infrastructure to transfer data between different organisations. Email ends up being a "solution". However, using emails for frequent data feeds / frequent processing is not a sustainable process. 

Application programming interfaces (APIs) allows applications to communicate with each other. The Outlook email program has a rich API behind it called Exchange Web Services (EWS). Applications (like our RAP extract data application) can send EWS queries to push or pull data to Outlook objects like emails, contacts and calendars. The `Get and save data` functionality can now store the raw dataset as well apply any required transformations - like changing the filenames or data formats. 

{{< mermaid align="left" theme="neutral" >}}
graph TD
f[feed A] --> e[Outlook inbox]
beq --> |exchangelib| e
subgraph EXTRACT	
	d[Date range] --> beq[[Build email query]]
	beq --> |exchangelib <br> pandas|gsd[[Get and save data]]
	gsd --> rd[Raw data]
end
{{< /mermaid >}}


### Running SAS through Python with SASPy
When the SAS codebase is complex, large or both, it's convenient to instead just make it run without manual changes. Furthermore, this approach allows to incremental refactoring - allowing hard-to-convert code to remain in SAS while moving easier code to Python. 

It's worth noting that there are actually two ways of running SAS outside the SAS program: 
- With a SAS kernel in Jupyter*
- Through SASPy

[SASPy is officially supported by SAS](https://support.sas.com/en/software/saspy.html), and available as an [open source package](https://github.com/sassoftware/saspy). The library seems to be well-maintained and well-documented. 

> At its core, SASPy is capable of creating a SAS session and sending code to it for execution, as well as returning the output (logs and other output) to the controlling Python script. Yet it is also a powerful generator of SAS code, which means that it offers methods, objects, and syntax for use directly in idiomatic Python that it can then automatically convert to the appropriate SAS language statements for execution. In most cases, SAS procedures or steps are mapped directly to Python methods as a one-to-one equivalent.


### Mutating SAS code with Python
SASPy is able to generate SAS queries from Python commands. However, running existing SAS scripts with part of it needing amendment via Python needs some additional engineering. The easiest solution so far has three main steps: 

- Breaking up a SAS script into yaml chunks for "immutable" components
- "Mutable" components are created in Python
- The immutable and mutable are brought together with Python's f-strings


{{< mermaid align="left" theme="neutral" >}}
graph TD
sc[SAS Code] --> |yaml| pws
subgraph TRANSFORM
	rd[Raw data] --> |saspy| pws[[Process with SAS]]
	pws --> pd[Processed data]
end
{{< /mermaid >}}


