# Provocation

What do you have as you enter the provocation phase? Interest in a topic...

Framework for discovering and proving causal mechanisms, and extending this to consider types of research questions and motivations for extensions, reanalyses, replications, or reproductions.
Include exploratory analysis and case studies in type of research.

Reference: www.edreplication.org

## Literature review

- create bibtex file for manuscript
- beyond the manuscripts: pay attention to references to software, code, data, supplementary materials
- use reference manager to collect references for ease of bibtex generation
- take notes on search date, keywords, etc.
- include preprints
- literature reviews become more powerful with open science

## Reading a research compendium

- give idea of end goal at the beginning by reading one of our finished research compendium
- cite Nust's paper on reading a research compendium

- If you are running a study written in R using the `groundhog` package for reproducibility, you may need to run that console or enter "OK" in the console to permit groundhog to install packages for the study to run.

## Literature for reproduction, reanalysis, or replication

First, how will you choose a study?
Some criteria for choosing studies include:
- *intellectual merit* and the study's influence on a field of study
- *broader impacts* on society or the environment, e.g. through influence on policy
- *feasibility* based on availability of materials and methods
- desire to *learn* or *teach* the study and its methods
- concerns about the *validity* of a study

We argue that any reproduction, reanalysis, or replication starts with assembling and synthesizing the most complete information available about the original study design.
In order to reproduce a prior study, the reproducing researchers or students will need a comprehensive understanding of the original study.
We recommend two approaches for systematically approaching a deep reading of the original study resulting in comprehensive understanding and digital resources that link that understanding to the original manuscript and supplementary materials.
These approaches may be undertaken in parallel, and include:

1. Annotate the original manuscript and supplementary materials
2. Draw a workflow plan for the original study

### Annotation

We recommend annotating in collaborative software environments, e.g. hypothes.is or Zotero.
Choose a system of colors to represent important components of the research design, including:

- Main hypotheses or research questions
- Theoretical concepts
- Inputs of data or observations
- Processes and parameters for processes
- Computational environment
- Results, especially any result that can be checked or compared

You may also apply tags to indicate the relationship between individual hypotheses or questions and their associated processes and results and to indicate the sequence of processes in the overall research workflow.
As you approach a final draft of the workflow plan (see next subsection), we recommend assigning a unique identifier to each process and tagging the relevant sections of the original manuscript and supplementary materials with that identifier, creating a link between the original manuscript and the workflow plan.

### Workflow plan

The workflow visually illustrates the research process with three types of symbols:

- Ovals represent inputs and outputs of databases, variables, observations, etc.
- Rectangles represent processes, algorithms, models, etc.
- Arrows illustrate the sequence and flow of the research design

Early drafts of the workflow plan may be digital (e.g. on a digital whiteboard, or simply a text outline) or analog and tactile.
In methods classes, Holler has used stacks of notecards, marker pens and tape to arrange workflows on a board.
We even printed results from the paper (e.g. tables, graphs, and maps) to use as nodes of the analog board-based workflow graph.
Remote classes or research teams could do the same with images on a digital whiteboard.

We recommend drawing final draft of the workflow plan in specialized software for this task, e.g. draw.io or ____.

## Data at the provocation phase

- Avoid biasing your research plan by interacting too much with data observations
  - record / journal any empirical observations / interactions with data
  -
- view descriptive statistics and data visualization
- Save metadata

## Setting up research compendium

### what is a research compendium, and why start one so early?



### why make your research compendium in Git?

In our experience, there are at least XXX compelling reasons to use some form of git version control for your research compendium.

First, Git allows you to track, control, and revert **versions** of your own work, giving you an `undo` feature for your entire research project.
But it's more powerful than a simple `undo` feature, because Git also allows you to browse the history of versions, and visualize the changes in each version, and selectively restore elements of previous versions.
You control exactly when to `commit` new versions and describe the purpose of the new versions.
Advanced users can even experiment with `branching` multiple alternative versions of the project, e.g. to sandbox a thread of alternative changes to the project without altering the main version and then either discard failed changes or to decide when and how to integrate or `merge` the alternatives into the main project.

Second, Git allows you to manage updates to the project in a **research team**, by allowing each team member to commit changes sequentially, or by allowing team members to check out a branch of the project to work on a project subcomponent until they are ready to merging their contributions back into the main project.
If research team members work this way, the provenance of individual contributions to the team project will be recorded in git commit metadata.
If a research team uses a service like GitHub or GitLab to host the Git repository, then the research team will have access to online management and collaboration tools linked to the repository for managing, tracking, and communicating about the research project.

Third, Git and services providing servers for Git (e.g. GitHub and GitLab) make it easy to **share projects** with other researchers and with other computational environments.
The research compendium can be shared with other researchers via a URL link for `cloning` the repository to a new computer or manually downloading a compressed `zip` archive file of the whole compendium.
The compendium can also be cloned into a new computational environment, e.g. into an RStudio Server, JupyterHub Server, high performance computing (HPC) service, or Docker container.
This movement of the full research compendium between computational environments is an essential component for computationally-intensive research and for computational reproducibility.

Fourth, because Git maintains a history of commits or versions to the project, it allows the researcher to passively record the full provenance of a study's development and revision over time, including information about what changes were made, by whom, when, and for what reasons.
This adds transparency to the revision process, e.g. by making explicit how the research changed through peer review and what each member of a research team contributed.

Fifth, GitHub and GitLab can be integrated with digital archives for open science, e.g. Open Science Foundation or Figshare.
They also support web services with which researchers may publish webpages with their findings directly within their research compendium

Finally, Git is highly compatible with an open science paradigm of research in which research projects become "living papers" that may be updated over time by the original authors, editors, peer reviewers, or students.
Other researchers may easily `fork` new versions of the project for the purpose of either making and proposing changes to the original research in the form of a `pull request`, or for developing the project into a new metascience study while maintaining a formal link to the original study for the purposes of receiving updates or tracking provenance of research designs.

### Create new Git repository based on our template
  - public / private status
  - changes are tracked with commits
- Orientation to the template structure / file system
  - top-level readme
  - license
  - Markdown language
  - metadata
  - docs / reports
- committing some changes to the template
- Recommended prefixes: Or / RPl / RPr
- Choose appropriate `LICENSE` file for the work

## Conclusion

At the conclusion of the provocation phase, you have:

- Specific research question
- Connect research question to literature and to archetypical research design
- Set up template research compendium
