# Texas police agencies

This repo gets a list of police agencies for a public information request assignment. The original list was downloaded Jan. 9, 2020 from the [FBI Crime Data Explorer](https://crime-data-explorer.fr.cloud.gov/downloads-and-docs), using the [Public Employee Data](http://s3-us-gov-west-1.amazonaws.com/cg-d4b776d0-d898-4153-90c8-8336f86bdfec/pe_1960_2018.csv).

## Dat processing

- `data/pe_1960_2018.csv` is the original file, but it is not in the repo because it is too big. It was downloaded from [FBI Crime Data Explorer](https://crime-data-explorer.fr.cloud.gov/downloads-and-docs) under Police Employee Data. The file ref at the time was [this](http://s3-us-gov-west-1.amazonaws.com/cg-d4b776d0-d898-4153-90c8-8336f86bdfec/pe_1960_2018.csv)
- RStudio could not open the original file, so I had to cut it down using csvkit. See the [01-file-process.ipynb](01-file-process.ipynb) notebook, which requires Jupyter Notebooks and the python package [csvkit](https://csvkit.readthedocs.io/).
- `02-texas.Rmd` is an RNotebook that explores the Texas agencies