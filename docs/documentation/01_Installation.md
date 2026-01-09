---
layout: page
title: Installation
description: Installation instruction
---

# Install DaVinci

To install the R package from GitHub, you just need to run through the following code block in R.

```
remotes::install_github("FunctionLab/DaVinci")
```

### If the installation is not successful
You can download the the repo to `working_directory` and use the following code block to inlcude all DaVinci functions in your working environment.
 ```
 library(Rcpp)
 library(mclust)
 
 script.path <- "working_directory/R/"
 script.list <- list.files(script.path)
 script.list <- setdiff(script.list, c("DAVINCHI.R", "import.R", "RcppExports.R"))
 script.list <- paste0(script.path, script.list)
 sapply(script.list, source)
 
 sourceCpp("working_directory/src/util.cpp")
 
 ```


# Platform-specific instructions on installing R

### Linux
1. Install the latest version of R (>=4.0.0)
2. Install `remotes` in R.
3. Install `DaVinci` from `GitHub`.


### Windows
1. Install the latest version of R (>=4.0.0)
2. Install Rtools from `https://cran.r-project.org/bin/windows/Rtools/`. Be sure to select a version that matches your installed R version.
3. Create a text file named `.Renviron` under the folder `This PC/Documents/` with the following content.<br>
        ```
        PATH="${RTOOLS40_HOME}\usr\bin;${PATH}"
        ```
        <br>If Rtools installation is successful, `RTOOLS40_HOME` environment variable should have been automatically set up. The variable name may change as you install a different version of Rtools.
3. Install `remotes` in R.
4. Install `DaVinci` from `GitHub`.



### Mac (ARM chip)
To be updated.






