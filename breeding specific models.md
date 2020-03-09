

- Line by tester model
  ```
  library(agricolae)
  data(LxT)
  model = with(LxT, lineXtester(replication, line, tester, yield))
  ``
- Analysis of Diallel data: Griffing's and Hayman's approaches
  ```
  library(DiallelAnalysisR)
  # Griffing's: Methods= c(1:4), Model= c(1,2)
  grif_model <- Griffing(y = Yield, Rep = Rep, Cross1 = Cross1, Cross2 = Cross2, 
                data = GriffingData1, Method = 1, Model = 1)
  
  # Hayman Approach
  hay_model <- Hayman(y= Yield, Rep = Rep, Cross1 = Cross1, Cross2 = Cross2, data = HaymanData)

  ````
- North Carolina Design I

  ![NC I](https://github.com/lagvier/R4A/blob/master/images/nc1.PNG)

  ```
  install.packages("plantbreeding", repos="http://R-Forge.R-project.org")
  library(plantbreeding)
  nc1_model <- carolina1(dataframe = northcaro1, set = "set", male = "male", female = "female", 
                      progeny = "progeny", replication = "replication", yvar = "yield")
  ```

---
packages: lme4
