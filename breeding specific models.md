data(datapbib)
help(datapbib)
require("lme4")
print(mod1 <- lmer(response ~ Treatment + (1|Block), data = datapbib,
contrasts = c(unordered = "contr.SAS", ordered = "contr.poly")))
print(anova(mod1))

- Line by tester model
  ```
  library(agricolae)
  data(LxT)
  model = with(LxT, lineXtester(replication, line, tester, yield))


  ```


---
packages: lme4
