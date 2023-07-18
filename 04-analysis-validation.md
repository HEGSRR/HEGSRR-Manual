# Analysis and Validation

## Changes to the pre-analysis plan registration

Researchers will likely encounter the need to deviate from the registered pre-analysis plan.

- save a version of the text file used to write and register the pre-analysis plan
- major changes to the plan may require updating that document, rendering a new PDF and updating the registration on OSF.

QUESTION: when is a change to the registered pre-analysis plan big enough to require an update on OSF?
- if an uncertainty or ambiguity and contingencies for that were already articulated in the pre-analysis plan, there is no need to update the plan.
- if alterations to the pre-analysis plan may ultimately impact the interpretation of claims made by the research, the changes should be registered on OSF.

- in parallel, all changes (minor and major) should be identified with bold text or subheadings in the narrative of the analytical plan as research progresses. Our suggested labels for changes include:
  -
- update the preanalysis plan

## Coding and Code style

R should follow Tidyverse style: https://style.tidyverse.org/ and there are two great addins:
- stylr formats your code for you https://styler.r-lib.org/
- lintr checks your code formatting: https://github.com/jimhester/lintr

Python should follow PEP 8 Style: https://www.python.org/dev/peps/pep-0008/

## Intermediary outputs

It is possible, but unwise, to encode the entire workflow in a computational notebook without saving intermediary results.
When should intermediary results be saved, how, and why?
There are at least five major situations in which saving data results is paramount for increasing the reproducibility of your study:

1. Immediately following code to download or create data that can be redistributed, the data should be saved in the `raw\public` folder.
2. As soon as confidential, proprietary, or very large data sources has been processed enough to redistribute, the data should be saved to the `derived\public` folder.
3. After very computationally intensive processes, results should be saved to the `derived\public` folder.
4. If any external software or process is used to manipulate the data, then the data should be saved to the `derived\public` folder just **prior** to the external process *and* just **after** the external process. Any process outside of the main computational notebook should be documented in notebook narrative and/or separate `procedure` `code` or `protocol` files.
5. If any randomization or stochastic model is applied in the analysis, the results of the random aspect of the analysis should be saved to the `derived\public` folder.

The computational notebook should include code both to save and to (re)load intermediary data files, and the recommended practice is to:
1. save in formats with open standards without encoding the data object name
2. read in with functions that assign a data object name

Recommended open standard file types include `.csv`, `.json` and `.gpkg`.
For example, while working in R, it is best to use the  `.RDS` file type to store individual data objects without the data object name rather than relying on `.RData` files potentially encompassing multiple data objects and encoding their names.
Saving data files agnostic to the object name in R or Python adds clarity to the provenance of data as it is manipulated by the research workflow and allows researchers to modify the code and compare results of replications or reanalyses.

Researchers can encode data saving and loading procedures in separate code blocks and modify the code chunk options for optimal reproducibiliy.
For example, it is not necessary to query an API every time a computational notebook is run: the code chunk for an API query can be set to `eval = FALSE` while the code chunk to load the resulting data can be set to `eval = TRUE`.

See RMarkdown code chunk options: https://rpubs.com/Lingling912/870659 and Jupyter code block options

## Function parameters

While it may be convenient to use the default parameters for functions while coding the script for a research project, this practice makes it more difficult for other researchers to understand the code and may be vulnerable to changes in the required packages over time.
If a parameter is important, best practice is to include it in the function call.
As an example, functions for classifying continuous data for the purpose of choropleth mapping may contain a default number of classes, but it is helpful to choose and declare that default explicitly in the research code rather than requiring others to look up function defaults.
The result of declaring parameters will be more intentional research design and more legible code.

## Store publication-ready outputs in the results directory

Store publication-ready final research outputs, e.g. figures, tables, or other media for publications and presentations in the `results` directory.

Although these types of results will ideally be embedded as outputs in computational notebooks, most researchers will also find it convenient to share and repurpose individual figures and tables for blogs, web designs, presentations, and more.
Therefore, it makes sense to add a final block of code to computational studies to output important results to separate files.
As you do so, complete the `results_metadata.csv` file indexing each results file, including the fields:

- `path`: the path from results folder, e.g., `figures`, `other`, or `tables`
- `name`: the file name
- `description`: very brief description or figure title

Wise researchers may even edit this `results_metadata.csv` file in their computational notebook!
