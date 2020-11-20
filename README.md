# COVID-19 vaccine tracker

Idea: [Eva Lopez](https://twitter.com/evopez)

Research, data analysis and visualization, writing: [Gianna-Carina Grün](https://twitter.com/giannagruen)

Editing: Fabian Schmidt, [Zulfikar Abbany](https://twitter.com/zulfikarabbany)

You can read the story in [English](https://p.dw.com/p/3lUln), [Deutsch](https://p.dw.com/p/3lQ2q), [Español](https://p.dw.com/p/3lVQA), [Português do Brasil](https://p.dw.com/p/3lWb1), [Indonesia](https://p.dw.com/p/3lY9G)


## Data sources

This analysis is based on two different data sources that are structured differently and thus used to answer different questions as part of this analysis.

In the dataset provided by the [**WHO**](https://www.who.int/publications/m/item/draft-landscape-of-covid-19-candidate-vaccines), each row corresponds to one developer and their vaccine candidate. In this analysis, this dataset is used to 
* show how many vaccine candidates are in which phase
* classify the vaccine candidates according to their type, and subsequently also phase

In the "Clinical trials database" compiled by the [**London School of Hygiene and Tropical Medicine (LSHTM)**](https://vac-lshtm.shinyapps.io/ncov_vaccine_landscape/), each row corresponds to a registered clinical trial -- accordingly, a developer team testing their vaccine in multiple phases in parallel will see multiple entries in this dataset. In this analysis, this dataset is used to
* show trial sizes by phase by company
* provide estimates (min, max, median) of the clinical phases


## Comparisons with other vaccine trackers

Other media companies too have implemented vaccine development trackers ([NYTimes](https://www.nytimes.com/interactive/2020/science/coronavirus-vaccine-tracker.html), [Guardian](https://www.theguardian.com/world/ng-interactive/2020/nov/10/covid-vaccine-tracker-when-will-a-coronavirus-vaccine-be-ready), [Milken Institute](https://www.covid-19vaccinetracker.org/), [Zeit Online](https://www.zeit.de/wissen/gesundheit/2020-08/impfstoffentwicklung-corona-impfstoff-klinische-phasen-forschung)). 

You will see that numbers differ, based on 
* the **sources** used and 
* whether **trials or vaccine candidates** are counted and
* based on the **distinction between "in approval" and "approved"**; we chose to not show the process, but only signify a vaccine as "approved" once the major authorities have done so

<!-- 
## Definitions

### Approval

### Time ranges

Primary completion date
The date on which the last participant in a clinical study was examined or received an intervention to collect final data for the primary outcome measure. Whether the clinical study ended according to the protocol or was terminated does not affect this date. For clinical studies with more than one primary outcome measure with different completion dates, this term refers to the date on which data collection is completed for all the primary outcome measures. The "estimated" primary completion date is the date that the researchers think will be the primary completion date for the study.


### Clinical phases

  -->


## Data processing

Datasets were downloaded from the above mentioned sources. The data provided by LSHTM did not undergo any form of pre-processesing as it already came in a machine-readable format.

As the data by **WHO** is published in form of a pdf, the dowloaded file undergoes a couple of pre-processing steps before analysis can start.

First, the pdf was converted into a machine-readable format using the software Abbyy Fine Reader and subsequently cleaned manually.

The datasets consists of two parts: the first table is labelled `xx candidate vaccines in clinical evaluation` , whereas  `xx` corresponds to the number of rows in that table. It's followed by the second table `yy candidate vaccines in preclinical evaluation` that has a slightly different columns compared to the first one.

In combining both datasets, we established the one for analysis that holds the following columns

| column  |  description |
|----------------|------------------------|
| COVID-19 Vaccine developer/manufacturer  | Name of developer/manufacturer or team of developers/manufacturers, separated by  `/` |
| Vaccine platform | Type of vaccine\* |
| Preclinical| `preclinical` if True, else no value  |
| Phase 1  | if there's a trial in this phase, cell holds one or multiple trial numbers |
| Phase 1/2 | if there's a trial in this phase, cell holds one or multiple trial numbers |
| Phase 2 | if there's a trial in this phase, cell holds one or multiple trial numbers |
| Phase 3  | if there's a trial in this phase, cell holds one or multiple trial numbers |

\* For entries in the column `Vaccine platforms` we noticed different spellings of the same type, for example `Protein subunit, Protein Subunit or Protein Sub-unit` or `Non-replicating viral vector or non replicating viral vector`, which were unified to be spelled the same way before exporting the dataset for analysis.

