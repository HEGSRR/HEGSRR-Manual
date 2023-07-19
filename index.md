--- 
title: "HEGSRR Manual"
author:
  - "Peter Kedron"
  - "Joseph Holler"
date: "2023-07-19"
site: bookdown::bookdown_site
documentclass: book
bibliography: [book.bib, packages.bib]
# url: your book url like https://bookdown.org/yihui/bookdown
# cover-image: path to the social sharing image like images/cover.jpg
description: |
  This is a minimal example of using the bookdown package to write a book.
  The HTML output format for this example is bookdown::bs4_book,
  set in the _output.yml file.
link-citations: yes
github-repo: HEGSRR/HEGSRR-Manual
biblio-style: apalike
csl: chicago-fullnote-bibliography.csl
---

# Reproducible research compendia and workflows {.unnumbered}

Introduction paragraph

Other analogous reproducibility infrastructure projects include:

- TIER protocol: https://www.projecttier.org/tier-protocol/protocol-4-0/
- Social Science Reproduction Platform https://www.socialsciencereproduction.org/ and Guide for Accelerating Computational Reproducibility in the Social Sciences: https://bitss.github.io/ACRE/
- WORCS A workflow for open reproducible code in science https://cjvanlissa.github.io/worcs/


## Open science, reproducibility and replicability {.unnumbered}

Theoretical foundation for open science practices ... discovering valid and generalizable knowledge.

Open science is...

-   Mertonian norms (1942) (christensen et al pg 23)

"Replication is a methodological tool based on a reptition procedure that is invovled in establishing a fact, truth, or piece of knowledge." (Schmidt 20019)

Reproducibility is... An original study may be considered computationally reproducible if... A reproduction study...

Replicability is... A replication study...

|                |                |                      |
|----------------|----------------|----------------------|
|                | Same Procedure | Difference Procedure |
| Same Data      | Reproduction   | Renalysis            |
| Different Data | Replication    | Extension            |

: (Christensen et al pg 159)

## Pragmatic principles for designing reproducible research workflows {.unnumbered}

How did we decide how to construct the research template and workflow?

We followed these principles in making design decisions:

1.  **Efficiency** for both individual researchers and research teams
2.  **Flexibility** to accommodate many types of research
3.  **Transparency** and **provenance** at both the level of individual research artefacts and the overall research design
4.  **Compatibility** with other research standards
5.  **FAIR** data
6.  Lower **transaction costs**
7.  Ease of appropriate **citation** for research products

### Efficiency {.unnumbered}

-   Individual tasks will start to take more time, especially at first, but in the long-term, the amount of time and effort put into the research project from inception to publishing will save effort. In particular, researchers will start to reap dividends when they need to revise research, verify methodology and results for publication, or revise or correct errors early in the research workflow. Adopting reproducible research practices also reduces the transaction costs of pausing a research project (e.g. for a field season or heavy teaching semester) and restarting later.
- Reduce inefficiencies in research teams, especially teams distributed over space (in different research labs or at home and in the field) or time (e.g. shifting composition of a research team as students come and go from the program)

### Flexibility {.unnumbered}

- diversity in geography
- complexity and heterogeneity of phenomena (NASEM complexity ; precision of replication)
- not just computational geography - qualitative and mixed methods research as well
- original studies, meta-analyses, reproductions, replications
- ability to fork a reproduction into a replication

### Transparency and Provenance {.unnumbered}

- applies to individual research products, e.g. data, code, resulting figures or tables
- also applies to the overall research project in terms of research design, suggesting the need for pre-analysis registrations, tracking changes in research design

### Ethics and Privacy {.unnumbered}

- research workflow and template must account for appropriate steps to protect the privacy of human subjects and adhere to standards and  (Institutional review boards (IRB) / independent ethics committees (IEC) / etc.) reviews for responsible and ethical research.

### Compatibility {.unnumbered}

- with OSF, with journal & funding agency requirements, with standardized metadata
- facilitates convergence research if this is interoperable with other disciplines

### FAIR Data {.unnumbered}

The FAIR principles of findability, accessibility, interoperability, and reusability

- open standards (data formats)
- licensing
- metadata documented with open standards

### Transaction costs {.unnumbered}

*economic* definition of transaction costs, maximizing legibility of codified knowledge.

Maximizing efficiency and transparency of research communication and re-use / extensibility, both for other researchers and for students.

The FAIR principles of findability, accessibility, interoperability, and reusability of FAIR data contribute substantially to reducing the transaction costs for other researchers or computer algorithms to access and use the research project. However addition

- adherence to a common organizational structure/template for research compendium (think of principles for communication in education-- standardize format & structure as much as possible)
- open source software
- computational environment
- legible code
- modularity

### Citation {.unnumbered}

Once your work is easily reusable and extensible, you will want credit for it.
DOI's, Citation file in Git Repository, possibly DOI for particular artefacts if you anticipate citing them.
Cross-linking different research products so that each project becomes an living ecosystem of research components.

## Organization / Structure of this {.unnumbered}

1. Template itself and recommended content
1. Research workflow and recommended actions

We organize this manual to follow a research workflow of recommended actions, including actions interacting with, creating and editing the research compendium.

We follow the open science workflow composed of steps for:

1. Provocation
1. Ideation
1. Data observation and curation ("Knowledge Generation" in NASEM 2018)
1. Validation
1. Dissemination
1. Preservation
