---
title: "Project_EDA"
author: "Niharika"
date: "February 2, 2018"
output: html_document
---



Wine Quality Analysis  by Niharika J. Shah
========================================================








# Introduction
The tidy data set on wine quality categorized from 3 to 9 is provided by Udacity. It has 4898 set of observation with 13 variables. Each variable except the varaible X which is sequence number for the dataset will be anlayzed in order to get to more about wine quality and their relationship with each other for the best quality wine.

# Univariate Plots Section



```
## 'data.frame':	4898 obs. of  13 variables:
##  $ X                   : int  1 2 3 4 5 6 7 8 9 10 ...
##  $ fixed.acidity       : num  7 6.3 8.1 7.2 7.2 8.1 6.2 7 6.3 8.1 ...
##  $ volatile.acidity    : num  0.27 0.3 0.28 0.23 0.23 0.28 0.32 0.27 0.3 0.22 ...
##  $ citric.acid         : num  0.36 0.34 0.4 0.32 0.32 0.4 0.16 0.36 0.34 0.43 ...
##  $ residual.sugar      : num  20.7 1.6 6.9 8.5 8.5 6.9 7 20.7 1.6 1.5 ...
##  $ chlorides           : num  0.045 0.049 0.05 0.058 0.058 0.05 0.045 0.045 0.049 0.044 ...
##  $ free.sulfur.dioxide : num  45 14 30 47 47 30 30 45 14 28 ...
##  $ total.sulfur.dioxide: num  170 132 97 186 186 97 136 170 132 129 ...
##  $ density             : num  1.001 0.994 0.995 0.996 0.996 ...
##  $ pH                  : num  3 3.3 3.26 3.19 3.19 3.26 3.18 3 3.3 3.22 ...
##  $ sulphates           : num  0.45 0.49 0.44 0.4 0.4 0.44 0.47 0.45 0.49 0.45 ...
##  $ alcohol             : num  8.8 9.5 10.1 9.9 9.9 10.1 9.6 8.8 9.5 11 ...
##  $ quality             : int  6 6 6 6 6 6 6 6 6 6 ...
```



```
##   X fixed.acidity volatile.acidity citric.acid residual.sugar chlorides
## 1 1           7.0             0.27        0.36           20.7     0.045
## 2 2           6.3             0.30        0.34            1.6     0.049
## 3 3           8.1             0.28        0.40            6.9     0.050
## 4 4           7.2             0.23        0.32            8.5     0.058
## 5 5           7.2             0.23        0.32            8.5     0.058
## 6 6           8.1             0.28        0.40            6.9     0.050
##   free.sulfur.dioxide total.sulfur.dioxide density   pH sulphates alcohol
## 1                  45                  170  1.0010 3.00      0.45     8.8
## 2                  14                  132  0.9940 3.30      0.49     9.5
## 3                  30                   97  0.9951 3.26      0.44    10.1
## 4                  47                  186  0.9956 3.19      0.40     9.9
## 5                  47                  186  0.9956 3.19      0.40     9.9
## 6                  30                   97  0.9951 3.26      0.44    10.1
##   quality
## 1       6
## 2       6
## 3       6
## 4       6
## 5       6
## 6       6
```


### Histograms for all variables


![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png)

### Creating two new varibles sulfurRatio and acidityRatio


```
##             citric.acid residual.sugar   chlorides     density
## nobs        4898.000000    4898.000000 4898.000000 4898.000000
## NAs            0.000000       0.000000    0.000000    0.000000
## Minimum        0.000000       0.600000    0.009000    0.987110
## Maximum        1.660000      65.800000    0.346000    1.038980
## 1. Quartile    0.270000       1.700000    0.036000    0.991723
## 3. Quartile    0.390000       9.900000    0.050000    0.996100
## Mean           0.334192       6.391415    0.045772    0.994027
## Median         0.320000       5.200000    0.043000    0.993740
## Sum         1636.870000   31305.150000  224.193000 4868.746090
## SE Mean        0.001729       0.072473    0.000312    0.000043
## LCL Mean       0.330801       6.249336    0.045160    0.993944
## UCL Mean       0.337582       6.533494    0.046384    0.994111
## Variance       0.014646      25.725770    0.000477    0.000009
## Stdev          0.121020       5.072058    0.021848    0.002991
## Skewness       1.281135       1.076434    5.020254    0.977174
## Kurtosis       6.163631       3.462415   37.508493    9.777368
##                       pH   sulphates      alcohol      quality sulfurRatio
## nobs         4898.000000 4898.000000  4898.000000  4898.000000 4898.000000
## NAs             0.000000    0.000000     0.000000     0.000000    0.000000
## Minimum         2.720000    0.220000     8.000000     3.000000    0.023622
## Maximum         3.820000    1.080000    14.200000     9.000000    0.710526
## 1. Quartile     3.090000    0.410000     9.500000     5.000000    0.190935
## 3. Quartile     3.280000    0.550000    11.400000     6.000000    0.315789
## Mean            3.188267    0.489847    10.514267     5.877909    0.255577
## Median          3.180000    0.470000    10.400000     6.000000    0.253677
## Sum         15616.130000 2399.270000 51498.880000 28790.000000 1251.815926
## SE Mean         0.002158    0.001631     0.017584     0.012655    0.001343
## LCL Mean        3.184037    0.486650    10.479795     5.853101    0.252944
## UCL Mean        3.192496    0.493044    10.548739     5.902718    0.258210
## Variance        0.022801    0.013025     1.514427     0.784356    0.008836
## Stdev           0.151001    0.114126     1.230621     0.885639    0.094000
## Skewness        0.457502    0.976595     0.487044     0.155701    0.381027
## Kurtosis        0.527568    1.586208    -0.699877     0.213767    0.561985
##             acidityRatio
## nobs         4898.000000
## NAs             0.000000
## Minimum         0.011111
## Maximum         0.180328
## 1. Quartile     0.030303
## 3. Quartile     0.048479
## Mean            0.041262
## Median          0.038356
## Sum           202.100199
## SE Mean         0.000231
## LCL Mean        0.040810
## UCL Mean        0.041714
## Variance        0.000261
## Stdev           0.016141
## Skewness        1.645903
## Kurtosis        5.459204
```

### Citric Acid:

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4-1.png)

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.0000  0.2700  0.3200  0.3342  0.3900  1.6600
```

Roughly Citric Acid histogram is normally distributed I see long tail, which is\
also indicated in boxplot showing outliers. The range for 1st quartile and  3rd\
quartile is from .27 to .39 whereas max is at 1.66

### Residual Sugar:

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5-1.png)

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   0.600   1.700   5.200   6.391   9.900  65.800
```

The histogram for residual sugar has long tail which can be explained from\
boxplot that there are outliers, It will be interesting to know more about \
this variable when I will explore in bivariate plots.


### Chlorides:

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6-1.png)

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
## 0.00900 0.03600 0.04300 0.04577 0.05000 0.34600
```

Chlorides histogram looks roughly normal as well however, boxplot indicates \
that there are many outliers, also can be explained with long tail in histogram.

### Density: 

![plot of chunk unnamed-chunk-7](figure/unnamed-chunk-7-1.png)

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.9871  0.9917  0.9937  0.9940  0.9961  1.0390
```

Density histogram is looks normal and boxplot shows just three outliers.I would\
like to explore if these outliers have any corelation with other variables.


### pH Value:

![plot of chunk unnamed-chunk-8](figure/unnamed-chunk-8-1.png)

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   2.720   3.090   3.180   3.188   3.280   3.820
```

The histogram for pH value is mostly normal, with no extreme outliers on the \
far side. It would be interesting to explore acidity and pH value interaction \
as more pH value indicates more acidity in any liquid. Also, pH and alcohol \
intercation in wines.


### Sulphates:

![plot of chunk unnamed-chunk-9](figure/unnamed-chunk-9-1.png)

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.2200  0.4100  0.4700  0.4898  0.5500  1.0800
```

The histogram for sulphates is roughly normal.

### Alcohol:

![plot of chunk unnamed-chunk-10](figure/unnamed-chunk-10-1.png)

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    8.00    9.50   10.40   10.51   11.40   14.20
```

It would be interesting to know correlation between alcohol and quality, and \
how other variable correlate with alcohol as alcohol is one of the main \
variable which defines wine quality.

### Quality:

![plot of chunk unnamed-chunk-11](figure/unnamed-chunk-11-1.png)

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   3.000   5.000   6.000   5.878   6.000   9.000
```

Quality is normally distributed 


### Sulfur Ratio:

![plot of chunk unnamed-chunk-12](figure/unnamed-chunk-12-1.png)

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
## 0.02362 0.19093 0.25368 0.25558 0.31579 0.71053
```

Sulfur Ratio also looks normally distributed


### Acidity Ratio:

![plot of chunk unnamed-chunk-13](figure/unnamed-chunk-13-1.png)

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
## 0.01111 0.03030 0.03836 0.04126 0.04848 0.18033
```

Acidity Ratio has long tail on right side however it is also roughly normally\
distributed.

# Univariate Analysis

### What is the structure of your dataset?

There are 4898 obs. of  13 variables in the dataset.
 X                   : num
 fixed.acidity       : num  
 volatile.acidity    : num  
 citric.acid         : num  
 residual.sugar      : num  
 chlorides           : num  
 free.sulfur.dioxide : num  
 total.sulfur.dioxide: num 
 density             : num  
 pH                  : num 
 sulphates           : num 
 alcohol             : num  
 quality             : 3,4,5,6,7,8,9 as categorical variable
 
 Most number of white wines are of quality level 6 in this dataset.
 
### What is/are the main feature(s) of interest in your dataset?

Main  feature of the datasets include how the quality and alcohol content of\
wine. I would like to see how these two varaibles correlated with other varaible.

### What other features in the dataset do you think will help support your \
investigation into your feature(s) of interest?

pH levels, residual.sugar levels, acidity levels. I would like to know if \
they have any affect on quality and alcohol.

### Did you create any new variables from existing variables in the dataset?

I created two new ratio variables for acidity and sulphur.dioxide
First variable I created is Ratio between volatile acidity and fixed acidity 
Second variable is Ratio between free.sulfur.dioxide and total.sulfur.dioxide.
After looking at their individual histogram both acidity and sulphur.dioxide \
looked similar, therefore I beleive these two ratio would give better conclusions.

Hence I decided to drop individal acidity and sulphur.dioxide variables and \
worked with ratios instead.

### Of the features you investigated, were there any unusual distributions? \
Did you perform any operations on the data to tidy, adjust, or change the form \
of the data? If so, why did you do this?

No.


# Bivariate Plots Section

### Correlation Table

<table class="table table-striped table-hover table-condensed" style="margin-left: auto; margin-right: auto;">
 <thead>
  <tr>
   <th style="text-align:left;"> corTable </th>
   <th style="text-align:left;"> citric.acid </th>
   <th style="text-align:left;"> residual.sugar </th>
   <th style="text-align:left;"> chlorides </th>
   <th style="text-align:left;"> density </th>
   <th style="text-align:left;"> pH </th>
   <th style="text-align:left;"> sulphates </th>
   <th style="text-align:left;"> alcohol </th>
   <th style="text-align:left;"> quality </th>
   <th style="text-align:left;"> sulfurRatio </th>
   <th style="text-align:left;"> acidityRatio </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> citric.acid </td>
   <td style="text-align:left;"> <span style="     color: red;">1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.09</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.11</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.15</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.16</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.06</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.08</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.01</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.02</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.25</span> </td>
  </tr>
  <tr>
   <td style="text-align:left;"> residual.sugar </td>
   <td style="text-align:left;"> <span style="     color: black;">0.09</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.09</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">0.84</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.19</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.03</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.45</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.05</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.02</span> </td>
  </tr>
  <tr>
   <td style="text-align:left;"> chlorides </td>
   <td style="text-align:left;"> <span style="     color: black;">0.11</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.09</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.26</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.09</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.02</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.36</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.21</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.03</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.04</span> </td>
  </tr>
  <tr>
   <td style="text-align:left;"> density </td>
   <td style="text-align:left;"> <span style="     color: black;">0.15</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">0.84</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.26</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.09</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.07</span> </td>
   <td style="text-align:left;"> <span style="     color: blue;">-0.78</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.31</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.07</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.08</span> </td>
  </tr>
  <tr>
   <td style="text-align:left;"> pH </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.16</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.19</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.09</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.09</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.16</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.12</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.11</span> </td>
  </tr>
  <tr>
   <td style="text-align:left;"> sulphates </td>
   <td style="text-align:left;"> <span style="     color: black;">0.06</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.03</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.02</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.07</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.16</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.02</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.05</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.02</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.03</span> </td>
  </tr>
  <tr>
   <td style="text-align:left;"> alcohol </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.08</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.45</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.36</span> </td>
   <td style="text-align:left;"> <span style="     color: blue;">-0.78</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.12</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.02</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.44</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.06</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.11</span> </td>
  </tr>
  <tr>
   <td style="text-align:left;"> quality </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.01</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.21</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.31</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.05</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.44</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.2</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.14</span> </td>
  </tr>
  <tr>
   <td style="text-align:left;"> sulfurRatio </td>
   <td style="text-align:left;"> <span style="     color: black;">0.02</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.05</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.03</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.07</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.02</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.06</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.2</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">1</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.14</span> </td>
  </tr>
  <tr>
   <td style="text-align:left;"> acidityRatio </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.25</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.02</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.04</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.08</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.11</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.03</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">0.11</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.14</span> </td>
   <td style="text-align:left;"> <span style="     color: black;">-0.14</span> </td>
   <td style="text-align:left;"> <span style="     color: red;">1</span> </td>
  </tr>
</tbody>
</table>



We can divide wine categories into three categories: Poor (3-4), Medium(5-6), and Best(7-8-9) for further bi-variate and multi variate analysis




### Boxplot for Citric Acid for Quality Category

![plot of chunk unnamed-chunk-15](figure/unnamed-chunk-15-1.png)

```
## [1] "Mean: "
```

```
## [1] 0.33 0.34 0.33
```

Best quality wines have lowest levels of citric acid however there is no significant difference among wine categories.

### Boxplot for Residual Sugar for Quality Category

![plot of chunk unnamed-chunk-16](figure/unnamed-chunk-16-1.png)

```
## [1] "Mean: "
```

```
## [1] 7.05 6.44 5.26
```

Best quality wines have lowest level of residual sugars which can be exlplained as residual sugars turn into alcohol during fermentation process, the less the sugar, the more alcohol content. However, I see some outliers in best quality wines as well, that's explains mean and median both have significant difference.

### Boxplot for Chlorides for Quality Category

![plot of chunk unnamed-chunk-17](figure/unnamed-chunk-17-1.png)

```
## [1] "Mean: "
```

```
## [1] 0.051 0.045 0.038
```

Chloride levels are lowest in best quality wines. Mean and Median are very close for best quality wines which explains less number of outliers.

### Boxplot for Density for Quality Category

![plot of chunk unnamed-chunk-18](figure/unnamed-chunk-18-1.png)

```
## [1] "Mean: "
```

```
## [1] 0.995 0.994 0.992
```

Density is also has lowest value in best quality wine, which can be explained with alcohol content in any wine. More alcohol content results in less density. We can also see that all categories of wines have less number of outliers as for all of them mean and median both are very close.

### Boxplot for pH value for Quality Category

![plot of chunk unnamed-chunk-19](figure/unnamed-chunk-19-1.png)

```
## [1] "Mean: "
```

```
## [1] 3.170 3.189 3.215
```

pH values are highest in best quality wines hence we can say that best quality wines are less acidic than other categories.

### Boxplot for Sulphates for Quality Category

![plot of chunk unnamed-chunk-20](figure/unnamed-chunk-20-1.png)

```
## [1] "Mean: "
```

```
## [1] 0.482 0.491 0.500
```

I don't see any difference in sulphates levels among three categories. Medium and Best quality wines both have same levels, hence we can not conclude anyhting based on sulphates levels in any wine.


### Boxplot for Alcohol for Quality Category

![plot of chunk unnamed-chunk-21](figure/unnamed-chunk-21-1.png)

```
## [1] "Mean: "
```

```
## [1]  9.850 10.575 11.416
```

I can see significant difference among three catgories for alcohol content. Best quality wine certainly have more alcohol content.Additionally, there are no outliers in medium and best quality wines for alcohol content.However, poor quality wine show many outliers.


### Boxplot for Sulfur Ratio for Quality Category

![plot of chunk unnamed-chunk-22](figure/unnamed-chunk-22-1.png)

```
## [1] "Mean: "
```

```
## [1] 0.232 0.262 0.278
```

Sulfur Ratio is highest in Best quality wines.


### Boxplot for Acidity Ratio for Quality Category

![plot of chunk unnamed-chunk-23](figure/unnamed-chunk-23-1.png)

```
## [1] "Mean: "
```

```
## [1] 0.045 0.039 0.040
```

Acidity Ratio doesn't give any clear picture among wine categories for better or worse wines.

### Alcohol vs. Density:

![plot of chunk unnamed-chunk-24](figure/unnamed-chunk-24-1.png)

I can see clear correlation between Alcohol and Density. As with more alcohol content in a wine density decreases, which I also observed in correlation table with high correlation coefficient -.78

### Alcohol vs. Residual Sugar


![plot of chunk unnamed-chunk-25](figure/unnamed-chunk-25-1.png)

As obsereved in correlation table with coeeficient as -.45 which is not very strong however not very weak as well. It would be interesting to see how these two variables behave in multivariate analysis with quality category.

### pH vs. Acidity Ratio

![plot of chunk unnamed-chunk-26](figure/unnamed-chunk-26-1.png)

I was looking for some correlation between pH and Acidity Ratio given pH values increases with acidity levels. However, I did not find any correlation. These two varaibles can also be explored futher based on quality category if their behaviour is different among quality category.

### pH vs. Citric Acid

![plot of chunk unnamed-chunk-27](figure/unnamed-chunk-27-1.png)

I don't see any correlation between pH and citric acid.


# Bivariate Analysis


### Talk about some of the relationships you observed in this part of the \
investigation. How did the feature(s) of interest vary with other features in \
the dataset?

* Correlation table indicates that Residual Sugar and Density are strongly \
correlated with correlation coefficient .84

* Density and Alcohol are negatively correlated with correlation \
coefficient -.78

* pH correlation with acidityRatio is low with correlaion coefficient .11

* Citric acid across quality varies and doesn't indicate any co-realtion between \
 these two variables. It stays close .32 for quality category 4,5,8 but for \
 quality category 3 and 9 it is .34 and .36 respectively. If I assume 3 as \
 worst quality and 9 as best it doesn't indicate clearly that with quality \
 it's increasing or decreasing. 
 [Many winemakers add citric acid to acidify wine to bring flavors that are too   basic.](http://www.calwineries.com/learn/wine-chemistry/wine-acids/citric-acid)/
 It is an intermediate in the TCA cycle, which provides molecular energy for \
 cellular function. However, its role in wine is far less important.
 
 * Median residual sugar is least in category 9 which is 2.2,whereas highest in \
category 5 which is 7.
[In sweet wine, the yeasts are killed before all the sugar is used, leaving residual sugars](http://www.calwineries.com/learn/wine-chemistry/sugar-in-wine) During\
fermentation process yeast consumes sugar for energy. If it consumes all of the\
sugars it falls into dry wine category. Additionally, sugar consumption by yeast also \
yeilds alcohol. Hence we can see there is negative correlation between residual\
sugar and alcohol. The less the sugar, the more alcohol content in a wine.\
However, this correlation between these is not very strong.

From above description we can say category 9 is more towards a dry wine whereas\
category 5 is a sweet wine because of highest amount of residual sugars.

* Median values for Chlorides across category from 3 to 9 are in general in \
decreasing order. This indicates that this variable needs to be explored \
more with other varaibles as well.

* Density defines, presence of water which depends on percentage of alcohol and \
sugar. Here in above boxplots density is peaks for quality category 5. However,\
it is in decreasing order from left to right indicating that from quality \
category 3 to 9 presence of water in decreasing.
Density and residual sugar are strogly correlated which can be explained here if\
we have less residual sugars, an increase in alcohol content, hence decreases\
the density of a wine.

* The higher the pH, the lower the acidity, and the lower the pH, the higher the\
acidity. Boxplots here show that pH value are higest for quality 9 which is in \
general is in increasing order from left to right.


* Sulphates don't seem to have any linear relationship amongs wine categories.

* Alcohol content in a wine found is natural result of yeast fermentation.During \
the winemaking process all sugar converts to alcohol hence, thus the higher the\
sugar in the fruit, the higher the alcohol content in a wine.Median values of \
alcohol content dips from quality 3 to 5 and then it increases from 5 to 9.
Correlation between density and alcohol is not perfectly linear however, they \
are negatively correlated strongly with correlation coefficient -.78

* Median values for sulfur ratio dips at quality category 4 and then increases \
from 5 to 8. sulfur dioxide prevents oxidization and maintains fresh taste of\
a wine. Here, we can see that it is higest in qaulity 8 wine.

* Median values for acidityRatio across quality is least in quality category 9 \
and most in quality category 4. It indicates that fixed acidity is most in category 9 whereas volatile acidity is most in category 4.

### Did you observe any interesting relationships between the other features \
(not the main feature(s) of interest)?
* I was expecting a linear realtionship between pH and acidity Ratio due to\
natural tendency of pH value and Acidity relationship. Also, similar behaviour\
expectation from citirc acid and pH value. However, that is not the case.

* There is strong negative correlation between density and alcohol which can \
be explained density decreases in presence of alcohol as given in the previous\
section.

* Strong positive correlation between alcohol and residual sugars .84 as sugars\
are converted into alcohol during wine making process. Also in more ripened \
grapes with higher sugar content are more popular to make best category wines \
now a days, which explains the correlation.

### What was the strongest relationship you found?

Positive correlation between residual sugars and alcohol content .84

# Multivariate Plots Section




![plot of chunk unnamed-chunk-28](figure/unnamed-chunk-28-1.png)

```
## 
## 	Pearson's product-moment correlation
## 
## data:  wineQualityWhitesNew$acidityRatio and wineQualityWhitesNew$chlorides
## t = 3.1223, df = 4896, p-value = 0.001805
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  0.01659216 0.07249386
## sample estimates:
##        cor 
## 0.04457791
```
 
 Chlorides are low in most best quality wines, however acidity ratio levels doesn't show any patterns with respect to chlorides for any wines.

![plot of chunk unnamed-chunk-29](figure/unnamed-chunk-29-1.png)

```
## 
## 	Pearson's product-moment correlation
## 
## data:  wineQualityWhitesNew$alcohol and wineQualityWhitesNew$density
## t = -87.255, df = 4896, p-value < 2.2e-16
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  -0.7908646 -0.7689315
## sample estimates:
##        cor 
## -0.7801376
```

Density and Alcohol show a clear pattern across all types of wines. Most best quality wines fall under low density and high alcohol content.

![plot of chunk unnamed-chunk-30](figure/unnamed-chunk-30-1.png)

```
## 
## 	Pearson's product-moment correlation
## 
## data:  wineQualityWhitesNew$acidityRatio and wineQualityWhitesNew$sulfurRatio
## t = -9.8311, df = 4896, p-value < 2.2e-16
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  -0.1664927 -0.1115633
## sample estimates:
##       cor 
## -0.139135
```

Most best quality wines fall under low acidity ratio and high sulfur ratio.However, there is a weak correlation among wine's acidity ratio and sulfur ratio.

![plot of chunk unnamed-chunk-31](figure/unnamed-chunk-31-1.png)

```
## 
## 	Pearson's product-moment correlation
## 
## data:  wineQualityWhitesNew$alcohol and wineQualityWhitesNew$residual.sugar
## t = -35.321, df = 4896, p-value < 2.2e-16
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  -0.4726723 -0.4280267
## sample estimates:
##        cor 
## -0.4506312
```

We see a clear pattern between residual sugar and alcohol content in wines as well. Most best quality wines have less residual sugar and high alcohol content.

![plot of chunk unnamed-chunk-32](figure/unnamed-chunk-32-1.png)

```
## 
## 	Pearson's product-moment correlation
## 
## data:  wineQualityWhitesNew$density and wineQualityWhitesNew$sulfurRatio
## t = -4.5947, df = 4896, p-value = 4.442e-06
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  -0.09335988 -0.03758727
## sample estimates:
##         cor 
## -0.06552475
```

Most best quality wines have low density and high sulfur ratio, however, same cannot be said about medium and poor quality wines.

![plot of chunk unnamed-chunk-33](figure/unnamed-chunk-33-1.png)

```
## 
## 	Pearson's product-moment correlation
## 
## data:  wineQualityWhitesNew$pH and wineQualityWhitesNew$citric.acid
## t = -11.614, df = 4896, p-value < 2.2e-16
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  -0.1908793 -0.1363671
## sample estimates:
##        cor 
## -0.1637482
```

I was expecting some corealtion between pH and citric acid for best quality wines. However,I did not find any correlation for different categories of wines.


![plot of chunk unnamed-chunk-34](figure/unnamed-chunk-34-1.png)

```
## 
## 	Pearson's product-moment correlation
## 
## data:  wineQualityWhitesNew$residual.sugar and wineQualityWhitesNew$density
## t = 107.87, df = 4896, p-value < 2.2e-16
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  0.8304732 0.8470698
## sample estimates:
##       cor 
## 0.8389665
```

Most best quality wines falls under low density and low residual sugar. However, for medium and poor quality wines spread is towards high density and high residual sugars.

# Multivariate Analysis

### Talk about some of the relationships you observed in this part of the \
investigation. Were there features that strengthened each other in terms of \
looking at your feature(s) of interest?

* Higher quality wines tend to have lower levels of chlorides.Acidity ratio does\
not show any strong correlation with chlorides as seen in bivariate analysis.

* Thers is clear inverse relationship exists between alcohol and density across \
quality levels. 

* The sulfurRaio stays betweeen .2 and .4 in high quality wines. High quality\
wines have lower acidityRatio, whereas low quality wines acidityRatio tends \
to vary a lot. 

* Alcohol and residual sugar have negative correlation. Alcohol content is\
higher when residual sugar is low as explained earlier sugars are consumed\
and converted in alcohol during fermentation process while making wines.


* There is a weak correlation between citric acid and pH values across wine\
qualtiy which indicates that the allowed quantities of citric acid in a \
wine doesn't affect the pH values.

### Were there any interesting or surprising interactions between features?

* The raletionship between acidityRatio and sulfurRatio for high quality wines\
where high quality wines tend to have high sulfurRatio and less acidityRatio.

* I was expecting citric acid will be correlated to pH value for different \
categories of wines however that is not the case

### OPTIONAL: Did you create any models with your dataset? Discuss the \
strengths and limitations of your model.
No
------

# Final Plots and Summary

### Plot One
![plot of chunk Plot_One](figure/Plot_One-1.png)

### Description One

This particular plot between sulfurRatio and acidityRatio got my attention. I can clearly see cluster of high quality wine for higher sulfurRatio  and less acidityRatio whereas acidityRatio varies for lower quality wines.

### Plot Two
![plot of chunk Plot_Two](figure/Plot_Two-1.png)

### Description Two

Alcohol and residual sugars are strongly correlated, hence there will be more\
alcohol content in any wine if there are less residual sugars, as in current \
times, in the wine making process wine crafter choose much riper grapes with\
more sugar content resulting in higher alcohol content. The graph also shows \
that higher quality wines tend to have less residual sugars and higher alcohol\
content.

### Plot Three
![plot of chunk Plot_Three](figure/Plot_Three-1.png)

### Description Three

It is eveident from bivaraite analysis of Quality and Alcohol content that\
higher quality wines tend to have higher alcohol content.This clearly \
indicates that higher quality wines preferred because of higher acohol \
content among their customers.

It would be nice to have customer data or sales data among different\
categories of customer to know which type of wine is preferred more among them.

------

# Reflection


1. I sturggled with colroing the high correlations values in the table.
2. GGpairs chart was not displaying very well, so I struggled if I could get just correlation table with coloring high correlated values 
3. It was difficult to interpret chart, exploring data and making a meaningful conclusion from any data while beginning of this course, that has changed over the course learning R and learning this project.
4. The boxplot in bivariate analysis gave me the clear picture about how each variable interacts with quality of a wine.Especially after displaying the median values in boxplots.
5. I liked sequence scale color brewing over other types as it clearly shows the difference sequentially among wines with repspect to quality category
6. For final plots summaries, theme panel exploration took a little to time understand.
7. I could apply machine learning techniques in future if new data is given without giving its quality variable data and predict the quality of ay wine.Also could work on models using this data for varaibles proided in this dataset.
