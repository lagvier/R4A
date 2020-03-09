

- Line by tester model
  ```
  library(agricolae)
  data(LxT)
  model = with(LxT, lineXtester(replication, line, tester, yield))
  ``
- Analysis of Diallel data: Griffing's and Hayman's approaches

  ![diallels](https://github.com/lagvier/R4A/blob/master/images/diallels.PNG)
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
  
  _Yijk = u + mi + fij + rk + eijk_
  ```
  install.packages("plantbreeding", repos="http://R-Forge.R-project.org")
  library(plantbreeding)
  nc1_model <- carolina1(dataframe = northcaro1, set = "set", male = "male", female = "female", 
                      progeny = "progeny", replication = "replication", yvar = "yield")
  ```
- North Carolina Design II
  _Yijk = μ + si + dj + iij + eijk_

  ```
  library(plantbreeding)
  data(northcaro2)
  nc2_model <- carolina2(dataframe = northcaro2, set = "set", male = "male", female = "female",
                        replication = "rep", yvar = "yield")
  ```
  
- North Carolina Design III



---
packages: lme4
