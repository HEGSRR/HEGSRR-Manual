# Writing an Analysis Plan for Preregistration

Pre-analysis plan templates were designed to help researchers specify the research design decisions most susceptible to *p-hacking* in their disciplines.
It follows intuitively that the templates address research issues in biomedical research, psychology, econometrics, and other disciplines at the forefront of discovering and addressing the "replication crisis".
The templates are well suited to experimental and quasi-experimental research designs in which the researcher has significant control over sampling and observations.

However, we have not found pre-analysis plans in the human-environment and geographical sciences or related disciplines, in which many research designs integrate many different data sources with different spatio-temporal supports.
These research designs require sophisticated methods involving many researcher decisions and multiple threats to validity: therefore they require attention and detail in any analysis plan for preregistration.
At the same time, we recognize that other disciplines look to geography when it comes time to specify details about their (spatial) data sources, referring researchers to the Federal Geographic Data Committee (FGDC) or the ISO 191* series of standards for geographic metadata.
Furthermore, the highest standards for reproducible research compendia and for research data archiving require documentation with international standards.
Therefore, we have adopted the Dublin Core standard with expanded detail of the `coverage` element to describe the spatio-temporal support of the overall project; and we have adopted the International Standards Organization (ISO) 19115 standard for geographic information metadata to describe the spatio-temporal support of individual data sources.

The next sections of this chapter will guide you through the steps for preparing the analysis plan for preregistration, culminating with instructions on registering the plan on OSF.

## Study metadata

The analysis plan begins with the title and metadata for the project.
If you have completed the root `readme.md` file for your research compendium, you can probably copy that metadata directly into the top of your analysis plan.
This redundancy is necessary so that the registered plan document contains all necessary information independently from the research compendium.
This project-level metadata also provides the foundation of the analysis plan by specifying the spatio-temporal characteristics of the study, making explicit from the beginning what the target data support will be for any of the input data.
Please see instructions on this overarching metadata in **Ideation Chapter, Section X**, and see contingencies for studies with multiple sub-components and replication studies below.

### Studies with multiple spatio-temporal coverages

Some studies may contain subcomponents with different spatio-temporal characteristics, or may contain multi-level models.
In this case, you will need to enumerate different metadata values for the spatial and/or temporal characteristics that vary across subcomponents of the study.
The list of study metadata should contain the overarching metadata for the study (i.e. coverages inclusive of all subcomponents and resolutions as ranges from smallest to largest).

Below the main metadata fields, make a hierarchical list or a table of the study subcomponents and the metadata characteristics that vary across them.

For example, in a study of Social Vulnerability Indices across different spatial extents, the overarching metadata may be:
- `Spatial Coverage`: Continental United States (this spatial extent encompasses all subcomponents of the study)
- `Spatial Resolution`: Counties to EPA Regions (range from smallest resolution or enumeration units to largest)
- `Spatial Reference System`: ESRI:102003 (spatial reference system for the overarching spatial coverage)
- `Temporal Coverage`: 2017-2022 (this temporal extent encompasses all subcomponents of the study)
- `Temporal Resolution`: 5-year estimate (this example has only one resolution and therefore does not require a range)

The spatial coverage, resolution, and reference system can be shown to vary across study subcomponents by adding a statement explaining the subcomponents, followed by a hierarchical list. For example:

```md
There are three subcomponents to the studies with varying spatial coverage, resolution, and reference systems.
The subcomponents are named: Macro level, Meso level, and Micro level.

- Macro Level Analysis
  - `Spatial Coverage`: Continental United States
  - `Spatial Resolution`: EPA Regions (aggregations of states)
  - `Spatial Reference System`: ESRI:102003
- Meso Level Analysis
  - `Spatial Coverage`: EPA Region 4
  - `Spatial Resolution`: States (first admin level)
  - `Spatial Reference System`: ESRI:102003
- Micro Level Analysis
  - `Spatial Coverage`: Florida
  - `Spatial Resolution`: Counties (second admin level)
  - `Spatial Reference System`: EPSG:3086
```

A table may be used in place of a hierarchical list.
For example:

```md
|                          | Macro Level    | Meso Level   | Micro Level    |
| :----------------------: | :------------: | :----------: | :------------: |
| Spatial Coverage         | Continental US | EPA Region 4 | Florida        |
| Spatial Resolution       | EPA Regions    | States ADM_1 | Counties ADM_2 |
| Spatial Reference System | ESRI:102003    | ESRI:102003  | EPSG:3086      |
```

### Replication studies with different spatio-temporal coverages

If the study is replication of a prior study with different spatial or temporal characteristics from the prior study, then the first block of metadata should describe the replication study spatio-temporal characteristics.
Following the replication study metadata and prior to the Study design section, add a sub-section for the original (prior) study spatio-temporal characteristics.
For example:

```md
#### Original study spatio-temporal metadata

- `Spatial Coverage`: extent of original study
- `Spatial Resolution`: resolution of original study
- `Spatial Reference System`: spatial reference system of original study
- `Temporal Coverage`: temporal extent of original study
- `Temporal Resolution`: temporal resolution of original study
```

## Study design

This section describes the archetypal study design to be used and specifies clear hypotheses or research questions.

Describe how the study relates to prior literature, e.g. is it an **original study** or a **metascience** study (one of: **meta-analysis study**, **reproduction study**, **reanalysis study**, or **replication study**)?

Also describe the original study archetype, e.g. is it **observational**, **experimental**, **quasi-experimental**, or **exploratory**?

Enumerate specific **hypotheses** to be tested or **research questions** to be investigated here, and specify the type of method, statistical test or model to be used on the hypothesis or question.
For example:

```md
> H1: Hypothesis number one

`H1` will be tested with a linear regression model.
```

If the study is a reproduction, reanalysis, replication, or meta-analysis, use prefixes to differentiate between the original study hypothesis and the meta-science hypothesis.
We recommend the following prefixes:

- `OR-H`: original hypothesis
- `MA-H`: meta-analysis hypothesis
- `RPr-H`: reproduction hypothesis
- `RA-H`: reanalysis hypothesis
- `RPl-H`: replication hypothesis

enumerate the **original study hypotheses** to be analyzed and the type of test or model to be used for the hypothesis.
These can be numbered with the prefix `OR-H` for "Original Hypothesis", e.g.

```md
> OR-H1: Median home prices of census tracts are dependent upon the distance from the central business district (CBD) in Chicago, Illinois.

OR-H1 was tested with a linear regression model having median home prices as the dependent variable and distance between the central business district and the census tract centroid as the independent variable.

> RPl-H1: The coefficient of distance from CBD in Buffalo, New York will have equivalent direction and magnitude to the coefficient of distance from the CBD in Chicago, Illinois.

RPl-H1 will be tested by substituting data for Chicago, Illinois with data for Buffalo, New York and repeating the linear regression of OR-H1.
```

The original study used a Spearman's Rho rank correlation test for OR-H1.

## Planned deviations of metascience studies

If the study is a metascience study (i.e. a reproduction, reanalysis, or replication), then most of the analysis plan has simply articulated your best understanding of the prior study.
However, to different degrees, each metascience study may intend to alter some parameters of the prior study.
These alterations should be labelled **planned deviation** and include a rationale for the deviation.
Categorize deviations **for reproduction** if the aim of the deviation is still to reproduce the original methodology and original results.
Categorize deviations as **for reanalysis** if the aim is to alter a methodological parameter of the study in order to compare results, e.g. as a test of sensitivity, uncertainty, or robustness.
Categorize deviations as **for replication** if the aim is to alter the spatial-temporal coverage of the study or to otherwise repeat the study methodology with new data/observations.

For example, a recent reproduction study of ours contained a planned deviation with no expectation of altering the data, methods, or results:

```md
**Planned deviation for reproduction**: Although the original study used SPSS and SaTScan for analysis, we will attempt to reproduce the study using R and its spatialepi and geepack packages for equivalent analysis using an open source software environment.
```

## Preregister your analysis plan on OSF

In the Open Science Foundation ecosystem of open science infrastructure, *registration* means to make and archive a permanent record of the research project at one moment in time.
When you register an analysis plan or report associated with an OSF project, a copy of the entire project is made to accompany the registration.
A *preregistration* should be a registration of the research prior to data collection and analysis.

As you are ready to preregister your plan, remember to update the `Date modified` field in your plan and on your project `readme.md` front matter.

When you are ready to register your analysis plan, log into OSF and navigate to your project.
Open the `Registrations` menu and begin a `New registration`.

OSF contains several registration templates.
To use our own template, select `Open-Ended Registration`.

Even an open-ended registration requires standard metadata.
Fortunately, OSF pulls this metadata from the umbrella project, including `title`, `description`, `contributors`, `category`, and `license`.

Curiously, this is the first opportunity to enter a `subject`, which will likely be one of:
- Social and Behavioral Sciences \ Geography \ (Geographic Information Sciences, Human Geography, Nature and Society Relations, Other Geography, Physical and Environmental Geography, Remote Sensing, Spatial Science)pro
- Social and Behavioral Sciences \ Environmental Studies \ ...

Following `Metadata`, the `Summary` should be a short description of the file you are uploading, simply to describe that it is a pre-analysis plan registration.
If you are updating a prior plan, the major updates and rationale should be noted in this summary.

Upload your pre-analysis plan `pdf` file as a supplementary file.

Finally, `Review` the registration and confirm its accuracy before moving on to `Register` the plan.
At this stage you will have the option to make the publication public immediately or enter the registration into an `embargo` with a specified end date.
The embargo option means that the registration will be locked after you `Submit` it, but it will remain private until the embargo date, after which it will be made public.

A submitted registration cannot be deleted or revoked even if it is in embargo: your only recourse for errors in the registration is to make a new registration to supersede the prior one.
All of the other admin contributors on the registration will have an option to revoke the registration in the first 48 hours after submission.

Once you have registered the pre-analysis plan, remember to copy the DOI and add the DOI link in the `Related to` section of the compendium `readme.md` file.

Note: If you need your project and the associated registration to identify specific files in your research compendium as specific types of resources, then prior to registration you can navigate to the file and edit file-level metadata. See these instructions: https://help.osf.io/article/569-add-metadata-to-an-osf-file

## Amending the analysis plan registration

Once registered, an analysis plan is locked in as a permanent record of your research plan at a particular time.
However, plans change!
*All* changes to plans between a pre-analysis registration and a post-analysis report must be documented as *unplanned deviations* so that results stemming from those changes may be interpreted appropriately.
Keeping in mind that the purpose of a preregistration is to reduce increase transparency for the purpose of reducing bias and p-hacking in the research process, a revised preregistration will only be useful if the researcher(s), based on prior observations of the data, can still specify a relatively unbiased analysis plan.
If the analysis plan is being amended on the fly based on reactions to data observations, it is better to record the amendments as *unplanned deviations* in a final report, rather than to falsely claim the changes as unbiased amendments to the analysis plan prior to the study.
*If* you need to make significant changes to an analysis plan *and* the amended plan is not already substantially biased by prior analyses and data observations, *then* it is time to amend the analysis plan and update the preregistration.

In case you need to amend the analysis plan, you may edit any section of the prior plan and add an explanation of the changes.
Be sure to update the `Date modified` field of the study metadata.

We recommend adding a second-level section titled "Rationale for analysis plan update" to the end of the analysis plan, immediately following the Integrity Statement section.
This new section should begin with a statement including the plan version and the prior registration DOI link, followed by the rationale for the update in one or more paragraphs.

Also include a paragraph discussing any change in prior observations of the data since the prior preregistration, or a statement of no change to prior observations of data.

```md
### Rationale for updated report

This is the second version of the analysis plan preregistration, superseding the first version, registered at https://doi.org/10.17605/OSF.IO/647EX on July 22, 2022.
The rationale for this update is...

Our prior observations of the data have changed/not changed.
Since the prior version, we have now...
```

## Resources

Dublin Core:
ISO 19115:
OSF Preregistration resources: https://www.cos.io/initiatives/prereg
Guide to create registrations: https://help.osf.io/article/345-create-registrations
