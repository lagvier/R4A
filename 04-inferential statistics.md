#### T-test
A statistic for testing difference between means of two categories or a mean of a category to a fixed value. The groups can either be paired or independent.
A non-paramtric equivalent of t-test ```The wilcox.test()```.

```t.test(value ~ group, data = data,  alternative = "less", paired = FALSE, var.equal = FALSE, conf.level = 0.95)```
```t.test(data$value, alternative = "less", mu = 255)```

#### 1-Way ANOVA
When the group be tested has more than 2 option, then one-way ANOVA would applied with an aim of determining whether at least one category has a different mean.

```model1 <-lm(value ~ group, data = data)```

   - Diagnostics ```plot(model1)```    
   - ANOVA outputs ```anova(model1)```   
   - Coefficients outputs ```summary(model1)```
   - Pairwise difference in ANOVA
   - Tukey HSD ```TukeyHSD(aov(value ~ group, data = data))```
   
#### Kruskal-Wallis    
   ```kruskal.test(value ~ group, data = data)```
