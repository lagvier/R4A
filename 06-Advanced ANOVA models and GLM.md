#### TWO-Way ANOVA

---
#### Multi-Level Models

Incomplete block design
![ibd](https://github.com/lagvier/R4A/blob/master/images/ibd%20model.PNG)

- Multi-year ANOVA: YEAR and REP FIXED effects

  ```model <-  lm(value ~ LINE + YEAR + REP%in%YEAR + LINE:YEAR, data = data)```

- Variance components

  ```
  model <- lme4::lmer(value ~ (1|LINE) + (1|YEAR) + (REP%in%YEAR) + (LINE:YEAR), data = data)
  summary(model)
  ```
---
#### GLM models
```glm_model <- glm(value ~ group, data = 'binomial', link = 'logit')```

---
#### Contrasts
````
print(mod1 <- lmer(response ~ Treatment + (1|Block), data = datapbib,
                  contrasts = c(unordered = "contr.SAS", ordered = "contr.poly")))
print(anova(mod1))
```

---
Packages: lme4
