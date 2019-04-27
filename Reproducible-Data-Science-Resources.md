What do other people recommend for reproducible data science?

### [5 Easy Steps to Make Your Data Science Project Reproducible][5easy]:
1. A Good Project Structure: Here they actually recommend [cookiecutter-data-science], which was the original basis of [cookiecutter-easydata]
2. Make Use of Virtual Environments: Done. See `make create_environment`, `make requirements`
3. Follow Best Practices while Coding: They mention pep8 and the `logging` module. We do try and make use of both, though we don't mention them specifically
4. Documentation, Documentation, Documentation: Yep. Hooks are there, though it hasn't made it to the tutorial yet. This will be part of the **Reproducible Results** section
5. Automation: They specifically mention using a `Makefile`, which we do. We also make use of a `workflow` module, thought we don't yet get into the more advanced workflow libraries

### [A Quick Guide to Organizing [Data Science] Projects (updated for 2018)][data-org-guide]

This article is based loosely on [A quick guide to organizing computational biology projects][comp-bio]. Here's how we hold up to their approach:
* "Someone unfamiliar with your project should be able to look at your computer files and understand in detail what you did and why."
* Everything you do, you will probably have to do over again.
* To this end, we use:
   * Self-documenting makefiles
   * Virtual (conda) Environments for reproducibility

* File and directory organization
   * To this end, we use a cookiecutter and a standard, Well documented filesystem layout
   * We also insist that **raw data is read-Only**: This was the reason for the `DataSource` object

* The Lab notebook
   * We recommend using Jupyter Notebooks for self-documenting code and EDA

* Carrying out a single experiment
   * Workflows
      * We use self-documenting `Makefile`s and some magic in the `workflow` module, but this article also mentions [Luigi] and [Snakemake], which are certainly worth looking at
   * Experiments
      * Our `Dataset` objects were designed to encapsulate processed data and associated metadata
      * Our `Model` object was designed to encapsulate the metadata about a single experiment 

* Handling and Preventing Errors
   * We incorporate various forms of testing (doctests, property-based tests, unit tests) into our framework out of the gate

* Command Lines versus Scripts versus Programs
   * We encourage exploratory development in notebooks, but then working code should be moved to the editable module (`src` by default). We include infrastructure to make this easy to do
* The Value of Version Control
   * We include [basic git workflows][git-workflow], and talk about using git from the beginning (**Reproducible Environments**)

### [Building a Repeatable Data Analysis Process with Jupyter Notebooks][repeatable-nb]
* Directory Structures
   * the raw/interim/processed data dir is virtually identical what we do.
* Notebook Structure
* Operationalizing & Customing This Approach
   * They also use cookiecutter

### Other Projects
[resumableds] looks to also be inspired by [cookiecutter-data-science]. Worth a look to see what they are doing.

[resumableds]: https://github.com/systemverwalter/resumableds/

[repeatable-nb]: https://pbpython.com/notebook-process.html
[comp-bio]: http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000424
[git-workflow]: https://github.com/hackalog/bus_number/wiki/Github-Workflow-Cheat-Sheet
[luigi]: https://github.com/spotify/luigi
[snakemake]: https://snakemake.readthedocs.io
[data-org-guide]: https://medium.com/outlier-bio-blog/a-quick-guide-to-organizing-data-science-projects-updated-for-2016-4cbb1e6dac71
[5easy]: https://medium.com/opex-analytics/5-easy-steps-to-make-your-data-science-project-reproducible-6254ab36c365
[cookiecutter-easydata]: https://github.com/hackalog/cookiecutter-easydata
[cookiecutter-data-science]: https://github.com/drivendata/cookiecutter-data-science