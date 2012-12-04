Anscombe UC3M
========================================================


```r
combe <- read.delim("~/projects/linear-regression/anscombe/data/combe.txt", 
    header = F)

names(combe) <- c("Group", "X", "Y")

combe
```

```
##    Group  X     Y
## 1      1 10  8.04
## 2      1  8  6.95
## 3      1 13  7.58
## 4      1  9  8.81
## 5      1 11  8.33
## 6      1 14  9.96
## 7      1  6  7.24
## 8      1  4  4.26
## 9      1 12 10.84
## 10     1  7  4.82
## 11     1  5  5.68
## 12     2 10  9.14
## 13     2  8  8.14
## 14     2 13  8.74
## 15     2  9  8.77
## 16     2 11  9.26
## 17     2 14  8.10
## 18     2  6  6.13
## 19     2  4  3.10
## 20     2 14  9.13
## 21     2  7  7.26
## 22     2  5  4.47
## 23     3 10  7.46
## 24     3  8  6.77
## 25     3 13 12.74
## 26     3  9  7.11
## 27     3 11  7.81
## 28     3 14  8.84
## 29     3  6  6.08
## 30     3  4  5.39
## 31     3 12  8.15
## 32     3  7  6.42
## 33     3  5  5.73
## 34     4  8  6.58
## 35     4  8  5.76
## 36     4  8  7.71
## 37     4  8  8.84
## 38     4  8  8.47
## 39     4  8  7.04
## 40     4  8  5.25
## 41     4 19 12.50
## 42     4  8  5.56
## 43     4  8  7.91
## 44     4  8  6.89
```

```r

ansc1 <- subset(combe, Group == 1)
ansc2 <- subset(combe, Group == 2)
ansc3 <- subset(combe, Group == 3)
ansc4 <- subset(combe, Group == 4)
ansc5 <- subset(combe, Group == 5)

Areg1 <- lm(Y ~ X, ansc1)
Areg2 <- lm(Y ~ X, ansc2)
Areg3 <- lm(Y ~ X, ansc3)
Areg4 <- lm(Y ~ X, ansc4)

ansc1reg <- lm(Y ~ X, data = combe, subset = Group == 1)
ansc1reg <- lm(Y ~ X, data = combe, subset = Group == 2)
ansc1reg <- lm(Y ~ X, data = combe, subset = Group == 3)
ansc1reg <- lm(Y ~ X, data = combe, subset = Group == 4)

anova(Areg1)
```

```
## Analysis of Variance Table
## 
## Response: Y
##           Df Sum Sq Mean Sq F value Pr(>F)   
## X          1   27.5   27.51      18 0.0022 **
## Residuals  9   13.8    1.53                  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```r
anova(Areg2)
```

```
## Analysis of Variance Table
## 
## Response: Y
##           Df Sum Sq Mean Sq F value Pr(>F)   
## X          1   28.1   28.07    17.1 0.0025 **
## Residuals  9   14.8    1.64                  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```r
anova(Areg3)
```

```
## Analysis of Variance Table
## 
## Response: Y
##           Df Sum Sq Mean Sq F value Pr(>F)   
## X          1   27.5   27.47      18 0.0022 **
## Residuals  9   13.8    1.53                  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```r
anova(Areg4)
```

```
## Analysis of Variance Table
## 
## Response: Y
##           Df Sum Sq Mean Sq F value Pr(>F)   
## X          1   27.5   27.49      18 0.0022 **
## Residuals  9   13.7    1.53                  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```r

summary(Areg1)
```

```
## 
## Call:
## lm(formula = Y ~ X, data = ansc1)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -1.9213 -0.4558 -0.0414  0.7094  1.8388 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)   
## (Intercept)    3.000      1.125    2.67   0.0257 * 
## X              0.500      0.118    4.24   0.0022 **
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 1.24 on 9 degrees of freedom
## Multiple R-squared: 0.667,	Adjusted R-squared: 0.629 
## F-statistic:   18 on 1 and 9 DF,  p-value: 0.00217
```

```r
summary(Areg2)
```

```
## 
## Call:
## lm(formula = Y ~ X, data = ansc2)
## 
## Residuals:
##    Min     1Q Median     3Q    Max 
## -1.927 -0.827  0.158  1.073  1.380 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)   
## (Intercept)    3.136      1.118    2.81   0.0205 * 
## X              0.473      0.114    4.14   0.0025 **
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 1.28 on 9 degrees of freedom
## Multiple R-squared: 0.655,	Adjusted R-squared: 0.617 
## F-statistic: 17.1 on 1 and 9 DF,  p-value: 0.00253
```

```r
summary(Areg3)
```

```
## 
## Call:
## lm(formula = Y ~ X, data = ansc3)
## 
## Residuals:
##    Min     1Q Median     3Q    Max 
## -1.159 -0.615 -0.230  0.154  3.241 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)   
## (Intercept)    3.002      1.124    2.67   0.0256 * 
## X              0.500      0.118    4.24   0.0022 **
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 1.24 on 9 degrees of freedom
## Multiple R-squared: 0.666,	Adjusted R-squared: 0.629 
## F-statistic:   18 on 1 and 9 DF,  p-value: 0.00218
```

```r
summary(Areg4)
```

```
## 
## Call:
## lm(formula = Y ~ X, data = ansc4)
## 
## Residuals:
##    Min     1Q Median     3Q    Max 
## -1.751 -0.831  0.000  0.809  1.839 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)   
## (Intercept)    3.002      1.124    2.67   0.0256 * 
## X              0.500      0.118    4.24   0.0022 **
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 1.24 on 9 degrees of freedom
## Multiple R-squared: 0.667,	Adjusted R-squared: 0.63 
## F-statistic:   18 on 1 and 9 DF,  p-value: 0.00216
```

```r

plot(Y ~ X, ansc1)
abline(Areg1)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-11.png) 

```r
plot(Y ~ X, ansc2)
abline(Areg2)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-12.png) 

```r
plot(Y ~ X, ansc3)
abline(Areg3)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-13.png) 

```r
plot(Y ~ X, ansc4)
abline(Areg4)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-14.png) 

```r

op <- par(mfrow = c(2, 2), pty = "m")

"# 2 x 2 pictures on one plot"
```

```
## [1] "# 2 x 2 pictures on one plot"
```

```r
plot(Y ~ X, ansc1)
abline(Areg1)
plot(Y ~ X, ansc2)
abline(Areg2)
plot(Y ~ X, ansc3)
abline(Areg3)
plot(Y ~ X, ansc4)
abline(Areg4)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-15.png) 

```r

par(op)
```

