# Ideation and Research Design

In the provocation phase, you already developed a specific research question, chose an archetypical research design, and set up a research compendium.

Now it is time to develop your research plan!

Remember, you can amend your research plan later.
You can even embargo your research plan and git repository for now before making it public later.
The point is to start increasing the transparency and provenance of your research project *now*, so that it *can* be made public later.

## Develop your Research Plan

It is already time to translate your specific research question and archetypical research design into a specific research plan.

### Reproduction studies

For a reproduction study, the design is to use the same data and methods to produce the same results.
Therefore, the research design will emphasize which study is to be reproduced, the motivation for reproducing it, the characteristics of the original data, the details of the original methodology, and the approach to comparing the reproduction results to the original results.

### Reanalysis studies

For a reanalysis study, the design is to repeat a prior study while modifying the methodology.
Therefore, the research design will emphasize which study is to be reanalyzed, the motivation for reanalyzing it, the characteristics of the original data, the details of the original methodology, the aspects of the methodology to be modified and rationale for doing so, and the approach to comparing the reanalysis results to the original results.

### Replication studies

For a reanalysis study, the design is to repeat the methods of a prior study with new data, in a new spatial or temporal context.
Therefore, the research design will emphasize which study is to be replicated, the motivation for replicating it, the details of the original methodology, the aspects of data/data collection and spatial or temporal context to be changed and rationale for doing so, and the approach to comparing the replication results to the original results.

### Original studies

Original studies are still based on prior literature, but entail new data collection and new methods.
Write more on archetypical original study designs here... and consider including meta-analysis as one.

## Project metadata: front matter for your study

Every journal article and book starts with front matter, and this is essentially metadata about the publication, including citation and attribution, copyright license, distribution, and more.
Open science starts with making your research project *findable*, which will require specifying standard metadata describing your research project.
Once you take the time to describe this project metadata, you will likely find that you continue to reuse the same information about your research throughout the full life cycle.
This is no coincidence, as many publishers and repositories have adopted the same DUBLIN Core standards https://www.dublincore.org/specifications/dublin-core/ for describing research artifacts.
Therefore, it is never too early to create a working draft of your project metadata in the top readme file of your research compendium.
This same information will be transferred to your analysis plans and research reports.

Some research designs may have multiple subcomponents with different spatio-temporal characteristics.
However, for this project-level metadata, simply report one all-encompassing set of spatio-temporal coverage metadata inclusive of all subcomponents and at the finest resolution.
Some research designs may be a replication study with plans to alter the prior study's spatio-temporal characteristics, in which case this project-level metadata for the research compendium should report the planned spatio-temporal coverage for the replication study.

- `Description`: a brief abstract about your research project.
- `Contributors`: names and email contact information for contributors. Note the corresponding author with an asterisk `*`. This corresponding author should be considered the `creator` of Dublin Core metadata. On GitHub, you may want to explicitly link to contributors' GitHub profiles with the `@` symbol, e.g. `@josephholler`. On OSF, you will be asked to specify contributors' permissions (administrator, read & write, or read) and whether they are a bibliographic or non-bibliographic contributor.
- `Affiliated Institutions`: List affiliations of the contributors as one would do for publications. On OSF, this field auto-populates with the registered institutions of any of the contributors as a benefit to institutional subscriptions.
- `Funding`: If applicable, include information on one or more funding sources for the research project.
  - Funder Name (for NSF project, the specific division or directorate)
  - Award Title
  - Award info URI (web address)
  - Award number
- `Date created`: date when project was started
- `Date modified`: date of most recent revision
- `Subject`: select from a controlled vocabulary
- `Tags`: select a few keywords, separated by commas. This is a feature compatible with GitHub, OSF, and Journal Articles, but is not a Dublin Core element.
- `Coverage (geographic)`: Specify the geographic extent of your study. This may be a place name and link to a feature in a gazetteer like GeoNames or OpenStreetMap, or a well known text (WKT) representation of a bounding box.
- `Coverage (temporal)`: Specify the temporal extent of your study---i.e. the range of time represented by the data observations.
- `Relation`: Identifier links to other related research elements, e.g. the OSF repository, preprints,
- `Rights`: Maintain the link to a license file and also list the license type here.
- `Resource type`: The overall research compendium is a `Collection` which will eventually include more specific subcomponents, e.g. `Preprint`, or `JournalArticle`. Dublin Core maintains a list of resource types: https://www.dublincore.org/specifications/dublin-core/resource-typelist/ as does OSF: https://help.osf.io/article/570-resource-types-in-osf
- `Resource language`: most likely `English`
- `Conforms To`: Conforms to the research compendium template for reproducible and replicable human-environment and geographical sciences at https://hegsrr.github.com/HEGSRR-Template

The project metadata has excluded just a few Dublin Core elements:
- `Title` is implied by the first-level header of the Markdown document.
- `Creator` is implied by the contributor noted as the corresponding author and by the history of Git commits.
- `Publisher` will likely include multiple entities as the repository linked to services like GitHub, GitLab, OSF, Figshare, or other digital Git repositories or archives. Publisher will be implied by the service on which the service is hosted.
- `Format` is excluded because the research compendium *collection* contains digital files of many different formats.

The metadata also includes a few elements beyond the 15 core elements:
- `Coverage` is explicitly subdivided into geographic and temporal coverages.
- `Funding` is added for compatibility with OSF and to fulfill requirements of funding agencies.
- `Affiliated Institutions` is added for compatibility with OSF and would normally be included with

## Create an OSF project

The Open Science Foundation (OSF, at https://osf.io) is a digital archive for open science digital artifacts.
We recommend creating an umbrella OSF project mapping directly to your Git research compendium.

First, create new project.
Make the project settings of `title` and `description` identical to the information in your compendium `readme.md` file.
The best `category` value for a complete research compendium is `project`.
The other project categories are more suitable for specific project components, should you need to register those separately.

Second, add additional `contributors`, unless you are developing the project as a solo researcher.
For each contributor, choose their level of permissions (administer, read and write, or just read) and check the `bibliographic contributor` if they are to be included in citations to this work.

Third, the project `License` can be set on the project home page (click the project title at top-left) under the Description.
Use the `Add a license` link to choose a license.
Stodden (XXXX) suggests the BSD 3-Clause "New"/"Revised" License for computational open science research.
If you do not choose a license or if you choose "No license", then full copyright protections are implied and it will be impossible for other researchers to re-use the project content.

Fourth, complete additional `metadata`.
The `description` field points to the same data as the project settings `description` and the `contributors` data points to the same data as the `contributors` menu.
The `affiliated institutions` are controlled by OSF institutional subscriptions, and the `date created` and `date modified` are automatically generated.

This leaves three `metadata` fields to manage:
- `Resource information`: The `Resource type` should be set to `Collection` for a research compendium composed of multiple resource types and data formats.
`Resource language` should likely be `English`, unless you have translated the compendium template.
Other project subcomponents could be registered separately with more specific `resource type` classifications.
- `Funding/support information`: The funding fields match information in your compendium `readme.md` file.
- `Tags`: match information in your compendium `readme.md` file.

Fifth, connect your OSF project to your GitHub repository.
- Add-ons -> GitHub
- Files -> add repository???
As you continue to work on your git repository and push changes to GitHub, your OSF project will automatically stay up-to-date with all of the changes.
Further on in the research life cycle you will create OSF registrations, which will archive a static version of your compendium at the time of registration.

Finally, projects have a `Make Public` option, which OSF warns you not to use until you are ready for the contents to be truly public.
When you *are* ready for the project to be public, you can also generate a `DOI` for inclusion in your project `Citation`.
Additionally, you can type `bibtex` into the `get more citations` dropdown to copy BibTex citation data for your OSF project.
Once your project is public with a DOI, you may crosslink this information from the GitHub repository:
- Return to the compendium `readme.md` and add the OSF project DOI to the `Related to:` section.
- Update the `CITATION.cff` file to cite your OSF Project with DOI.

## Data in the ideation phase

At this phase of research, we should avoid directly observing study data to the greatest extent that this can be avoided.
The pre-analysis plan will require you to disclose any experience or engagement you have had with the data because of the potential biases this engagement introduces into the research process.
Therefore, our larger discussion about data management with open science research compendiums is in the next chapter on Observation.
At this stage, we should be more concerned about researching potential secondary data sources and inventing the structure and observation design for primary data to be collected.
As such, we are more concerned at this phase about *metadata* about the data we are to acquire, create, and analyze, than we are about the data themselves.
It is recommended to save information about your data into the `data/metadata` folder, to start populating the `data/data_metadata.csv` tabular index to the data directories with a row for each data sources and associated metadata files, and possibly to write preliminary code for accessing data with specialized packages or application programming interfaces (APIs), including using APIs to query and save metadata.

The `data_metadata.csv` file may contain information about data files that do not yet exist
At this phase of research, you may not know specific paths and names for the files you will create.
However, you will want to keep track of the different `layers` you intend to create or acquire and their associated metadata files.
Therefore, you may create temporary working names for the `name` column, keep an accurate list of metadata files in the `metadata` column, n

The `data_metadata.csv` file is a tabular index of each data file in your project, including the fields:

- `path`: the path to the data folder, likely one of: `raw\private`, `raw\public`, `derived\private` or `derived\public`
- `name`: the file name, including extension. You may refer to individual tables of relational databases (e.g. geopackages) by appending `|` and the layer name, e.g. the `my_layer` table of `my_geopackage.gpkg` could be noted with this name: `my_geopackage.gpkg|my_layer`
- `metadata`: list of metadata files for this data source, stored in the `data\metadata` folder. These may include ISO-191** or FGDC standard `XML` files, data dictionaries, licenses or attributions, user guides, webpage printouts, etc. Separate multiple files with semicolons: `;`.
- `description`: *very* brief description of the dataset. If the data is **simulated**,  **randomized**, or represents only a limited **sample** of the full research dataset, you should note those limitations here.

In many cases you may document metadata about data sources that will not be directly included in the repository because they are either too large, they are proprietary, or they contain confidential information.
The  `data_metadata.csv` file should proscribe the location of these types of data as `raw\private` for data sources that need to be downloaded and/or acquired with permission and/or funding or as `derived\private` for large or confidential files that will be created with computational code or scripts.

Researchers are **strongly encouraged** to include additional metadata in the `metadata` folder.
Further information about the procedures used to create or acquire data to be stored in `private` directories should be maintained in the [procedure_metadata.csv](../procedure/procedure_metadata.csv).

Ideally, metadata should be documented to FGDC or ISO standards and saved in `xml`, `json`, or `yaml` format. Some tools for reading and writing metadata include:

- USGS Metadata Wizard 2.0: https://www.usgs.gov/software/metadata-wizard-20
- MDEditor: https://www.mdeditor.org/
- GeoNetwork: https://geonetwork-opensource.org/
- R geometa: https://cran.r-project.org/web/packages/geometa
- Python pygeometa: https://pypi.org/project/pygeometa/

Social science metadata may follow the Data Documentation Initiative (DDI) Codebook: https://www.projecttier.org/tier-protocol/protocol-4-0/root/data/originaldata/metadata/metadataguide/ and Project TIER provides good advice about data metadata: https://www.projecttier.org/tier-protocol/protocol-4-0/root/data/originaldata/metadata/.

## Writing

- Write in plain text or code
- new sentence on each line
- stored in Git repository with version control
- options:
  - non-computational (markdown or latex only)
  - Rmarkdown computational notebook
  - Jupyter Python

We need to move toward having the pre-analysis plan, code, outputs, everything in the same R markdown file or Jupyter notebook.
For Markdown, use knitr to generate the report https://yihui.org/knitr/
For Jupyter, use stitch https://pystitch.github.io/

When knitr or stitch is run, the report can be saved to the reports folder.
At that time, the researcher should commit a Version of the Git repository, and then continue revising the main notebook / rmarkdown.
This will reduce redundancies while recording provenance of the data, research plan, and code.

## Citing

- Use BibTex for managing citations for integration with Rmarkdown and LaTeX
- Necessary to cite not only literature, but also software and data
- Important to give credit to researchers who developed the software packages and/or data you are using by citing their preferred reference
- GitHub repositories may have .cff files or other information with preferred citations
- Citations to other versions of the paper and work (e.g. preprint, compendium, data, code)
- citation package in R https://ropensci.org/blog/2021/11/16/how-to-cite-r-and-r-packages/
- Guide to intergating Zotero and RMarkdown: https://christopherjunk.netlify.app/blog/2019/02/25/zotero-rmarkdown/
- The `worcs` package in r supports distinguishing "essential" references from "non-essential" references, so that a full reference list can be rendered in a preprint while a limited reference list can be rendered in a journal article with limitations on the number of references or words. See https://cjvanlissa.github.io/worcs/articles/citation.html

## Procedures

Save all methods and procedures and supporting documents in the `procedures` directory.

Catalog all procedures in an *ordered* table documenting any code or other research procedure/protocol documents. Provide a brief description of the purpose of each procedure and piece of code.

Catalog the files in `procedure_metadata.csv`

See the example table below, and modify the table to suit your research design.

- `path`: the path to the file or directory, usually one of `code` for software code and scripts, `environment` for the hardware/software computational environment, or `protocol` for non-code protocols like
- `name`: the file name, including extension
- `purpose`: *very* brief description of the purpose of the file

The *sequence* of procedures to be followed is implied by the *order* in the table and should be explicit in the pre-analysis plan and post-analysis report.

path | name | purpose |
-- | -- | -- |
code | script1.R | download and preprocess data |
protocol | survey_irb.pdf | Institutional review board protocol for survey sampling and instrument |
protocol | mapworkshop.pdf | participatory mapping workshop protocol |
code | script2.R | run analysis |
code | script3.R | generate visualizations for results |

### Environment

Store detailed information about the hardware and software environment requirements for procedures and code here.
You may also document a recipe or container of the computational environment here.

This directory is specifically for hardware and software environments.
Contextual factors or confounds of human subjects research or field research should be communicated in protocol documents and stored in the `protocols` subdirectory.

It is imperative to track the versions of software, software packages, and their dependencies for a research project.
Package versions change frequently, and may even change while you are working on your project.
We highly recommend keeping one main list of all software packages and versions required for a project and using this list to install and load the packages in code and to document metadata about the computational environment.
Many guides to reproducible computational research suggest writing code in a series of scripts, with one script for each phase of the research workflow.
If you are taking this approach, take caution not to load different sets of packages in different scripts without maintaining one comprehensive list of all required packages.

If you are using R, we suggest that you also make use of our template Rmarkdown code in `01-R-markdown.Rmd`.
The code in the computational environment section creates a list of packages to load in a data object named `packages`.
The `groundhog` package is then used to manage loading the version of R and packages and their dependencies as they were on a specific date, set as `groundhog.day`.
Please keep track of the packages you are using, and instead of using `library()` to load them, use `groundhog` instead.
Once the packages are loaded, the code uses the `sessionInfo()` function to query computational environment information, and saves this information in the `environment` directory in an `r-environment.txt` text file.
For more useful environment information, install the `devtools` package and replace `sessionInfo()` with `devtools::session_info()`.

If you are using Python, you likely have your own system for installing packages, e.g. `pip` or `conda`, prior to writing code.
Packages are then loaded and aliased as needed with the `import` statement.
Regardless of the system that you have used for installing packages, information about required packages must be recorded in the `environment` directory.
Depending on the package management tool used, this information may be recorded in an `environment.yml`, `requirements.txt`, or `Pipfile` with `Pipfile.lock`, file(s).
Additionally, researchers using Python should include instructions on recovering the computational environment in the `environment` directory's `README.md` file.

For a sense of how critical it is to record the computational environment, read ahead to the reproduction chapter.

### Code

Store computational code-based research procedures in the `code` subdirectory.
Examples include R scripts, Rmarkdown notebooks, Python scripts, Jupyter notebooks, KNIME workflows, executable graphical models (e.g. for QGIS or GRASS), batch processing scripts, macros, parameter files, and so on.

### Protocols

Store any non-computational protocols and research procedures in the `protocols` subdirectory.
Examples include Institutional Review Board (IRB) protocols for human subjects research, survey forms or instruments, protocols for field data collection, or protocols for systematic reviews or qualitative coding.

- store IRB protocol and any forms or instruments in procedures / protocols
- the research compendium is part of the data management plan
- read ahead to dissemination phase for considering privacy and data management

## Pilot studies

Some research designs will benefit from a pilot study, which will use a limited set of observations to test and revise (the) data collection instrument(s) or test the methodology on a limited set of data.
Pilot studies should be specified in the analysis plan methodology and disclosed in the *Prior observations* section of the plan.
The data observations and findings from a pilot study are not be included in the complete study and will not be disseminated or archived.
Therefore, pilot study data and materials may be saved in the `data/scratch` directory for temporary use.

## Conclusion

At this phase of the open science research cycle, you have...

... developed your archetypical research design into a specific registered research plan.  
... developed your research compendium.  
... connected your research registration on OSF to a GitHub.  
