#### Data management and basic statistics
The building blocks of analytical and graphical operations.  

- Operators: assigment; comments; other operators
    - use ```<-``` to assign to values to variables. You can also use ```=``` but not recommended.
    - ```#``` is used to start a comment within a line. Unlike most programming languages, R does not have multiline comments
    - Arithmetics: ```+,-,*,/,^```
    - Logical: ```!, >,<,>=,<=,!=``` 
    
- Accessing objects on the Rstudio: the working environment

- Understanding of variable types(integer, numeric, character, etc); 
    - Data types: scalars, vectors, matrices, lists, dataframes/tables
      - ```as.vector()``` - convert to vector
      - ```matrix()``` - create matrix - one data type 
      - list: different data types
      
- Creating or reading different types of data: Importing external data
    |Data format | Description | R function |
    | ------------- |:-------------| -----|
    |RData|the R data format - created using R software| ```load()```|
    |csv |comma separated file | ```read.csv()```|
    |txt |Text in tabular format|```read.table()```|
    |xls and xlsx |Excel file formats | use excel packages eg ```readxl::read_excel()```|
    |other formats: sav, etc | SPSS, etc | use _foreign_ package |

--- 
#### Basic information on data
- Understanding the data: variable types, overview, size, data type, missing points
    - ```str(), describe(), class(), mode(), head(n=5)```

- Basic functions
  |Function| Purpose|
  | ------------- | -----|
  |```sum(x)``` |Sums the elements in x|
  |```prod(x)```| Product of the elements in x|
  |```max(x) ```|Maximum element in x|
  |```min(x)```| Minimum element in x|
  |```range(x)``` |Range (min to max) of elements in x|
  |```length(x)``` |Number of elements in x|
  |```mean(x)``` |Mean (average value) of elements in x.|
  |```median(x)``` |Median (middle value) of elements in x|
  |```var(x)``` |Variance of elements in x|
  |```sd(x)``` |Standard deviation of element in x|
  |```cor(x,y)``` |Correlation between x and y|
  |```quantile(x,p)``` |The pth quantile of x|
  |```cov(x,y)``` |Covariance between x and y |
  |```unique(x)```|the unique values of x|

- Combined basic functions
  |Function| Purpose|
  | ------------- | -----|
  |```summary(x)``` |Minimun, maximum, median, mean, quartiles 1 and 3 and number of missing values|
  |```fivenum(x)```| Minimun, maximum, quartiles 1 and 3 and median|

  _modal statistics is not available in base R_

- Plots
  |Plot function| Description|
  | ------------- | -----|
  |```boxplot(x)``` |Box and whiskers plot|
  |```pie(x)``` |Circular pie chart|
  |```hist(x)``` |Histogram of the frequencies of x|
  |```barplot(x)```| Histogram of the values of x|
  |```stripchart(x)```| Plots values of x along a line|
  |```dotchart(x)``` |Cleveland dot plot|
  |```pairs(x)```| For a matrix x, plots all bivariate pairs|
  |```plot.ts(x)```| Plot of x with respect to time (index values of the vector unless specified)|
  |```contour(x,y,z)``` |Contour plot of vectors x and y, z must be a matrix of dimension rows=x and columns=y |
  |```image(x,y,z)``` |Same as contour plot but uses colors instead of lines|
  |```persp(x,y,z)``` |3-d contour plot |
--- 
#### Data manipulations
- Data conversions and transformations, conditional transformations of specific variables
    - Creating new variables within dataframe by using arithmetic operators, logical operators and conditional operations
    
- Other data manipulations: subsetting, slicing, reshaping, merging
  ```merge()``` - merge two 
  ```rbind()``` and ```cbind()``` - append data by rows and columns respectively. rbind binds data by rows and requires same data (names and types). Utilize ```rbind.fill()``` where data fails the condition. 
  
  - ```subset()``` select specific variables and observations that have specific conditions. _Slicing_ by specifying column or row indices is also useful in subseting data. Example ```data[2:5, 2:10]``` select row 2-5 and columns 2:10 in a dataframe or matrix ```data```
  
  - ```reshape()``` or ```cast``` - changing data from wide to long formats or vice versa. ```reshape::melt()``` changes from wide to long format.
  
  - Variable tranformations: ```mutate()```. Use of ```ifelse``` conditions; working with date informats and string expressions and replacements 
  
  - iterations: ```for()``` and ```while()``` loops
  
  - ```apply()``` group of functions: ```apply(), lapply(), sapply(), mapply(), tapply()```. Other functions ```aggregate()```
  
- Writing/saving data
    - Save workspace: ```save.image()```, 
    - Save plots and images: ```save.png()```...```dev.off()```, etc
    - Save data: ```write.csv()```, ```write.table()```, use other output packages such as ```XLConnect```

---
__Packages__: ```dplyr, reshape, reshape2, plyr```
