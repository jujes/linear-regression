Paso a paso
========================================================

```r
# Estastablecemos el directorio actual desde donde empezara a trabajar.
getwd()
```

```
## [1] "/home/jujes/projects/linear-regression/uc3m"
```

```r
# Llamamos a que carguen los datos 'data-01' en 'data.01'.
data.01 <- read.delim("~/projects/linear-regression/uc3m/data/data-01.csv")
# Muestra los datos de las variables contenidas en objeto.
data.01
```

```
##    Valores.relativos..por.habitante..2008 Empleo   PIB Est.Sup
## 1                               Andalucía  0.378 18.15   0.159
## 2                                  Aragón  0.481 26.12   0.202
## 3                 Asturias, Principado de  0.410 21.92   0.219
## 4                          Balears, Illes  0.487 25.26   0.146
## 5                                Canarias  0.414 20.28   0.158
## 6                               Cantabria  0.436 22.79   0.214
## 7                         Castilla y León  0.426 22.09   0.194
## 8                    Castilla - La Mancha  0.402 19.10   0.139
## 9                                Cataluña  0.497 27.28   0.195
## 10                   Comunitat Valenciana  0.422 21.38   0.178
## 11                            Extremadura  0.361 16.06   0.137
## 12                                Galicia  0.426 20.79   0.188
## 13                   Madrid, Comunidad de  0.537 30.77   0.257
## 14                      Murcia, Región de  0.425 20.45   0.159
## 15            Navarra, Comunidad Foral de  0.530 29.46   0.236
## 16                             País Vasco  0.495 30.72   0.284
## 17                              Rioja, La  0.467 26.10   0.211
```

```r
# atribuye la trama de datos a la ruta de búsqueda R, lo que hace que sea
# fácil acceder a los nombres de variables.
attach(data.01)
# Scatterplot: crea un diagrama de dispersión de y contra x
plot(data.01)
```

![plot of chunk unnamed-chunk-1](figure/unnamed-chunk-1.png) 

```r
# Primer resumen de datos.
summary(data.01)
```

```
##      Valores.relativos..por.habitante..2008     Empleo           PIB      
##  Andalucía              : 1                 Min.   :0.361   Min.   :16.1  
##  Aragón                 : 1                 1st Qu.:0.414   1st Qu.:20.4  
##  Asturias, Principado de: 1                 Median :0.426   Median :22.1  
##  Balears, Illes         : 1                 Mean   :0.447   Mean   :23.5  
##  Canarias               : 1                 3rd Qu.:0.487   3rd Qu.:26.1  
##  Cantabria              : 1                 Max.   :0.537   Max.   :30.8  
##  (Other)                :11                                               
##     Est.Sup     
##  Min.   :0.137  
##  1st Qu.:0.159  
##  Median :0.194  
##  Mean   :0.193  
##  3rd Qu.:0.214  
##  Max.   :0.284
```

```r
# Ajustar un modelo de regresión.
linear = lm(PIB ~ Empleo)
confint(linear, level = 0.99)
```

```
##              0.5 %  99.5 %
## (Intercept) -21.44  -6.251
## Empleo       66.60 100.398
```

```r
# Muestra los datos de las variables contenidas en objeto.
linear
```

```
## 
## Call:
## lm(formula = PIB ~ Empleo)
## 
## Coefficients:
## (Intercept)       Empleo  
##       -13.8         83.5
```

```r
predict
```

```
## function (object, ...) 
## UseMethod("predict")
## <bytecode: 0x19191e8>
## <environment: namespace:stats>
```

```r
# Primer resumen de datos.
summary(linear)
```

```
## 
## Call:
## lm(formula = PIB ~ Empleo)
## 
## Residuals:
##    Min     1Q Median     3Q    Max 
## -1.559 -0.621 -0.224  0.365  3.233 
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept)   -13.85       2.58   -5.37  7.8e-05 ***
## Empleo         83.50       5.73   14.56  2.9e-10 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1 
## 
## Residual standard error: 1.17 on 15 degrees of freedom
## Multiple R-squared: 0.934,	Adjusted R-squared: 0.93 
## F-statistic:  212 on 1 and 15 DF,  p-value: 2.95e-10
```

