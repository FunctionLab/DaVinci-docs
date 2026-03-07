---
layout: page
title: Installation
description: Installation instruction
---



# Platform-specific instructions on installing DaVinci

### Linux (RHEL)
1. Install the latest version of R (>=4.0.0)
2. Install `remotes` in R.
3. Run the code below in R with `remotes` installed.
```
remotes::install_github("FunctionLab/DaVinci")
```

You may need to `yum install` the following packages depending on your setup:
- `git`
- `blas`, `lapack`, `blas-devel`, `lapack-devel`
- `cmake`
- `udunits2-devel`
- `openssl-devel`
- `gdal-devel`, `proj-devel`, `geos-dev`



### Windows
1. Install the latest version of R (>=4.0.0)
2. Install Rtools from `https://cran.r-project.org/bin/windows/Rtools/`. Be sure to select a version that matches your installed R version.
3. Create a text file named `.Renviron` under the folder `This PC/Documents/` with the following content.<br>
        ```
        PATH="${RTOOLS40_HOME}\usr\bin;${PATH}"
        ```
        <br>If Rtools installation is successful, `RTOOLS40_HOME` environment variable should have been automatically set up. The variable name may change as you install a different version of Rtools.
4. Install `remotes` in R.
5. Run the code below in R with `remotes` installed.
```
remotes::install_github("FunctionLab/DaVinci")
```



### Mac (ARM chip)
1. Install the latest version of R (>=4.0.0)
2. Install `Xcode developer tools` and `GNU Fortran compiler` following the [instructions](https://mac.r-project.org/tools/).
3. Install `remotes` in R.
4. Run the code below in R with `remotes` installed.
```
remotes::install_github("FunctionLab/DaVinci")
```


# If you want to use DaVinci without installation
You can download the the repo to your `working_directory` and use the following code block to inlcude all DaVinci functions in your working environment.
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



