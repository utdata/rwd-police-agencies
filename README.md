# Texas police agencies

This repo gets a list of police agencies for a public information request assignment. The original list was downloaded Jan. 9, 2020 from the [FBI Crime Data Explorer](https://crime-data-explorer.fr.cloud.gov/downloads-and-docs), using the link for [Police Employee Data](http://s3-us-gov-west-1.amazonaws.com/cg-d4b776d0-d898-4153-90c8-8336f86bdfec/pe_1960_2018.csv).

## Data processing

- `data/pe_1960_2018.csv` is the original file, but it is not in the repo because it is too big (192MB). It was downloaded from [FBI Crime Data Explorer](https://crime-data-explorer.fr.cloud.gov/downloads-and-docs) under Police Employee Data. The file href at the time was [this](http://s3-us-gov-west-1.amazonaws.com/cg-d4b776d0-d898-4153-90c8-8336f86bdfec/pe_1960_2018.csv).
- RStudio could not open the original file (there were errors), so I used csvkit to cut down the file to versions for Texas and Texas in 2018. See the [01-file-process.ipynb](01-file-process.ipynb) notebook, which requires Jupyter Notebooks and the python package [csvkit](https://csvkit.readthedocs.io/).
- `02-tx-2018.Rmd` is an RNotebook that explores the Texas agencies. [Published version](https://utdata.github.io/rwd-police-agencies/02-tx-2018.html).
- `02-tx-all.Rmd` starts to look at all years, but isn't really relevant at this point.
