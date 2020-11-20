# COVID-19 vaccine tracker

Idea: [Eva Lopez](https://twitter.com/evopez)

Research, data analysis and visualization, writing: [Gianna-Carina Grün](https://twitter.com/giannagruen)

Editing: Fabian Schmidt, [Zulfikar Abbany](https://twitter.com/zulfikarabbany)

You can read the story in [English](https://p.dw.com/p/3lUln), [Deutsch](https://p.dw.com/p/3lQ2q), [Español](https://p.dw.com/p/3lVQA), [Português do Brasil](https://p.dw.com/p/3lWb1)


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
