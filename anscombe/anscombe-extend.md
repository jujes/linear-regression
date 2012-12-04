Anscombe Extended
========================================================


```r
ansc <- read.delim("http://www.biw.kuleuven.be/vakken/statisticsbyR/SDVbyR/AnscombeExtended.txt")

names(ansc) <- c("Group", "X", "Y")

ansc
```

```
##    Group  X     Y
## 1      1  8 20.57
## 2      1 13 20.15
## 3      1  9 22.28
## 4      1 11 21.36
## 5      1 14 22.30
## 6      1  6 21.35
## 7      1  4 18.81
## 8      1 12 23.63
## 9      1  7 18.73
## 10     1  5 20.01
## 11     2 10 22.40
## 12     2  8 21.84
## 13     2 13 21.35
## 14     2  9 22.15
## 15     2 11 22.27
## 16     2 14 20.43
## 17     2  6 20.25
## 18     2  4 17.66
## 19     2 12 21.90
## 20     2  7 21.15
## 21     2  5 19.05
## 22     3 10 20.70
## 23     3  8 20.43
## 24     3 13 25.31
## 25     3  9 20.56
## 26     3 11 20.80
## 27     3 14 21.19
## 28     3  6 20.21
## 29     3  4 19.90
## 30     3 12 20.95
## 31     3  7 20.31
## 32     3  5 20.09
## 33     4 10 22.94
## 34     4  8 19.85
## 35     4 13 19.65
## 36     4  9 20.25
## 37     4 11 22.38
## 38     4 14 23.84
## 39     4  6 20.55
## 40     4  4 19.53
## 41     4 12 21.55
## 42     4  7 19.72
## 43     4  5 20.19
## 44     5  8 21.20
## 45     5  8 18.74
## 46     5  8 21.98
## 47     5  8 19.70
## 48     5  8 22.66
## 49     5  8 19.32
## 50     5  8 21.62
## 51     5  8 20.91
## 52     5  8 20.13
## 53     5  8 20.44
## 54     5 19 23.75
```

```r

ansc1 <- subset(ansc, Group == 1)
ansc2 <- subset(ansc, Group == 2)
ansc3 <- subset(ansc, Group == 3)
ansc4 <- subset(ansc, Group == 4)
ansc5 <- subset(ansc, Group == 5)

Areg1 <- lm(Y ~ X, ansc1)
Areg2 <- lm(Y ~ X, ansc2)
Areg3 <- lm(Y ~ X, ansc3)
Areg4 <- lm(Y ~ X, ansc4)
Areg5 <- lm(Y ~ X, ansc5)

ansc1reg <- lm(Y ~ X, data = ansc, subset = Group == 1)

anova(Areg1)
```

```
## Analysis of Variance Table
## 
## Response: Y
##           Df Sum Sq Mean Sq F value Pr(>F)  
## X          1   8.52    8.52    4.96  0.057 .
## Residuals  8  13.75    1.72                 
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
## X          1   8.62    8.62    5.64  0.042 *
## Residuals  9  13.75    1.53                 
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
## X          1   8.62    8.62    5.64  0.042 *
## Residuals  9  13.75    1.53                 
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
## X          1   8.62    8.62    5.64  0.042 *
## Residuals  9  13.75    1.53                 
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```r
anova(Areg5)
```

```
## Analysis of Variance Table
## 
## Response: Y
##           Df Sum Sq Mean Sq F value Pr(>F)  
## X          1   8.62    8.62    5.64  0.042 *
## Residuals  9  13.75    1.53                 
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
## -1.9158 -0.5905 -0.0714  0.9770  1.8439 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)   18.430      1.192   15.46  3.1e-07 ***
## X              0.280      0.126    2.23    0.057 .  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 1.31 on 8 degrees of freedom
## Multiple R-squared: 0.383,	Adjusted R-squared: 0.305 
## F-statistic: 4.96 on 1 and 8 DF,  p-value: 0.0566
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
## -1.920 -0.750  0.140  0.965  1.200 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)   18.430      1.124   16.39  5.2e-08 ***
## X              0.280      0.118    2.38    0.042 *  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 1.24 on 9 degrees of freedom
## Multiple R-squared: 0.385,	Adjusted R-squared: 0.317 
## F-statistic: 5.64 on 1 and 9 DF,  p-value: 0.0415
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
##  -1.16  -0.62  -0.24   0.18   3.24 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)   18.430      1.124   16.39  5.2e-08 ***
## X              0.280      0.118    2.38    0.042 *  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 1.24 on 9 degrees of freedom
## Multiple R-squared: 0.385,	Adjusted R-squared: 0.317 
## F-statistic: 5.64 on 1 and 9 DF,  p-value: 0.0415
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
## -2.420 -0.685 -0.020  0.655  1.710 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)   18.430      1.124   16.39  5.2e-08 ***
## X              0.280      0.118    2.38    0.042 *  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 1.24 on 9 degrees of freedom
## Multiple R-squared: 0.385,	Adjusted R-squared: 0.317 
## F-statistic: 5.64 on 1 and 9 DF,  p-value: 0.0415
```

```r
summary(Areg5)
```

```
## 
## Call:
## lm(formula = Y ~ X, data = ansc5)
## 
## Residuals:
##    Min     1Q Median     3Q    Max 
## -1.930 -0.755  0.000  0.740  1.990 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)   18.430      1.124   16.39  5.2e-08 ***
## X              0.280      0.118    2.38    0.042 *  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 1.24 on 9 degrees of freedom
## Multiple R-squared: 0.385,	Adjusted R-squared: 0.317 
## F-statistic: 5.64 on 1 and 9 DF,  p-value: 0.0415
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
plot(Y ~ X, ansc5)
abline(Areg1)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-15.png) 

```r

op <- par(mfrow = c(2, 3), pty = "m")

"# 2 x 3 pictures on one plot"
```

```
## [1] "# 2 x 3 pictures on one plot"
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
plot(Y ~ X, ansc5)
abline(Areg5)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-16.png) 

```r

par(op)
```

