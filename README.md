---
output:
  html_document:
    df_print: paged
knit: (function(inputFile, encoding) { rmarkdown::render(
    inputFile,
    encoding = encoding,
    output_dir = "docs",
    output_file='index.html'
  ) })
---

# Texas police agencies

This repo gets a list of police agencies for a public information request assignment.

As of this writing in January 2022, the most recent data is 2020 and is found through the FBI's [Crime Data Explorer](https://crime-data-explorer.fr.cloud.gov/pages/home).

1. Go to the [Crime Data Explorer](https://crime-data-explorer.fr.cloud.gov/pages/home)
1. Click on the [Crime data explore downloads](https://crime-data-explorer.app.cloud.gov/pages/downloads) from the menu.
1. Scroll to **Crime in the United States Annual Reports**.
1. Choose **Police Employee Data** from the dropdown, along with the year
1. Click the **Download** button

This gives you a zip file with a ton of data including folders called **Table XX State Cuts**, with XX being a number between 78 and 81.

- 78 is City Agencies
- 79 is University and College Agencies
- 80 is County Agencies
- 81 is State, Tribal, and Other Agencies

The **Texas** files were pulled from the archive and put in the `data-raw` folder. The download does include full nation files for each table that could be used instead if states other than Texas were desired.

See the following notebooks for more:

- [01-ped-2020-import](01-ped-2020-import.Rmd) | [Published notebook](https://utdata.github.io/rwd-police-agencies/01-ped-2020-import.html)
- [02-ped-2020-pir-sp22](02-ped-2020-pir-sp22.Rmd) | [Published notebook](https://utdata.github.io/rwd-police-agencies/02-ped-2020-pir-sp22.html)

Work on this project was enabled by the album [Here in the Black - Live at Hollywood Forever Cemetery](https://music.apple.com/us/album/here-in-the-black-live-at-hollywood-forever-cemetery/1080378200) by Gary Numan.

## Previous work

> The file structure of the repo was changed in January 2022 so previous work will fail but it is retained for posterity.

### Data processing

- `data/pe_1960_2018.csv` is the original file, but it is not in the repo because it is too big (192MB). It was downloaded from [FBI Crime Data Explorer](https://crime-data-explorer.fr.cloud.gov/downloads-and-docs) under Police Employee Data. The file href at the time was [this](http://s3-us-gov-west-1.amazonaws.com/cg-d4b776d0-d898-4153-90c8-8336f86bdfec/pe_1960_2018.csv).
- RStudio could not open the original file (there were errors), so I used csvkit to cut down the file to versions for Texas and Texas in 2018. See the [01-file-process.ipynb](01-file-process.ipynb) notebook, which requires Jupyter Notebooks and the python package [csvkit](https://csvkit.readthedocs.io/).
- `02-tx-2018.Rmd` is an RNotebook that explores the Texas agencies. [Published version](https://utdata.github.io/rwd-police-agencies/02-tx-2018.html).
- `02-tx-all.Rmd` starts to look at all years, but isn't really relevant at this point.
