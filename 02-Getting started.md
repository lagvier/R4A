#### Install Java, R and RStudio in Windows
To install the correct versions of the software, you first have check your computer/server specifications. Right click you computer icon and select properties then note the version of the operating system.

1. Download and install [Java JDK](https://www.java.com/en/download/) appropriate to your OS. Recommended version >= 8.
    - Some R packages requires uses Java for instance packages used to work on 'xls/x' files.
2. Download and install the relevant R from the [R Cran website](https://cran.r-project.org/) for windows platform*. 
    - In case you installed Java, check to ensure that R recognizes the Java in your system.```java -version```
3. Download the RStudio IDE for Desktop from the [RStudio website](https://rstudio.com/products/rstudio/)
    - Ensure that the RStudio can locate the R software installation in your computer during the installation.
    - Alternative IDE platforms: Jupyter notebook, cloud servers(kaggle, AWS)
4. R packages: core and third-party - Repos: 
    - Official R packages (Rcran): ```install.packages('packagename')```
    - GitHub: requires installation of devtools then use the command ```devtools::install_github('packagename')```
    - Other repos: r-forge,bitbucket, local hosts*, bioconductor, etc.
---    
#### Understanding RStudio platform
__Terminal__: command entered and display results. Useful for calculating and displaying small short-term expressions such as 2+2. R prompt (>) indicates position to enter commands and an indication that previous command, if applicable, has completed; Terminal - to type and run shell commands.

__Explorer__: constitutes File browser - to display and manipulate the current working directory getwd(); Plots/viewer - display graphics during analysis; packages - installing, loading and unloading packages; help - documentation on installed packages

__Environment__: consists of environment - hold details of all objects such as data, models, vectors, functions; history - log of the historical use of the R software since installation; connections - to databases and servers

__Editor__: scripts/codes to . useful for reproduceable codes

__Help__: R/package, stack overflow
