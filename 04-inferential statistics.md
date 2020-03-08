#### Correlation analysis
Used to to test strenth and direction of relationship between two variable. Where both variables are qunatitative, a pearson correlation is used. Spearman and Kendall correlation for ordinal variables.
      - Pearson correlation: ```cor.test(data, method = "pearson")```
      - Spearman rank correlation: ```cor.test(data, method = "spearman")```
      - Kendall correlation: ```cor.test(data, method = "kendall")```

#### Chi-square Test
- To test significance in relationship between two categorical variables. It does not indicate the direction of relationship.
```chisq.test(matrixdata)```
- Fisher's exact test where atleast one cell <5 counts ```fisher.test()```

#### T-test
A statistic for testing difference between means of two categories or a mean of a category to a fixed value. The groups can either be paired or independent.
A non-paramtric equivalent of two-sample t-test is the _Mann–Whitney U-test_ also called the _Mann–Whitney–Wilcoxon test_ ```The wilcox.test()```.

```t.test(value ~ group, data = data,  alternative = "less", paired = FALSE, var.equal = FALSE, conf.level = 0.95)```
```t.test(data$value, alternative = "less", mu = 255)```

#### 1-Way ANOVA
When the group be tested has more than 2 option, then one-way ANOVA would applied with an aim of determining whether at least one category has a different mean.
The non-parametric equivalent is done using ```kruskal.test(Value ~ Group, data = data)```

```model1 <-lm(value ~ group, data = data)```

   - Diagnostics ```plot(model1)``` , ```bartlett.test(Value ~ Group, data=data)``` 
   - ANOVA outputs ```anova(model1)```   
   - Coefficients outputs ```summary(model1)```
   - Pairwise difference in ANOVA
   - Tukey HSD ```TukeyHSD(aov(value ~ group, data = data))```
   
#### Kruskal-Wallis    
   ```kruskal.test(value ~ group, data = data)```
