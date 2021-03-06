#### TWO-Way ANOVA
```anova_2<- aov(value~ Rep + A +  B, data = data)```

---
#### Split-Plot analysis
```anova_sp<- aov(value~ Rep + A +Rep:A +  B  + A:B, data = data)```

---
#### Multi-Level Models

Incomplete block design
![ibd](https://github.com/lagvier/R4A/blob/master/images/ibd%20model.PNG)


- Augmented design
  ```
  install.packages("plantbreeding", repos="http://R-Forge.R-project.org")
  library(plantbreeding)
  data(augblock)
  aug_model <- aug.rcb(dataframe = augblock, genotypes = "var", block = "blk", yvar = "gw")
  ```
- Multi-year ANOVA: YEAR and REP assumed fixed

  ```model <-  lm(value ~ LINE + YEAR + REP%in%YEAR + LINE:YEAR, data = data)```

- Variance components

  ```
  model <- lme4::lmer(value ~ (1|LINE) + (1|YEAR) + (REP%in%YEAR) + (LINE:YEAR), data = data)
  summary(model)
  ```
---
#### GLM models
Generalization of linear models in which the error for the response variable is not normally distributed. The distribution can be specified with a link function.Example,

```glm_model <- glm(value ~ group, data= data, family = binomial, link = 'logit')```

---
#### Contrasts
````
print(mod1 <- lmer(response ~ Treatment + (1|Block), data = datapbib,
                  contrasts = c(unordered = "contr.SAS", ordered = "contr.poly")))
print(anova(mod1))
```

---
Packages: lme4
