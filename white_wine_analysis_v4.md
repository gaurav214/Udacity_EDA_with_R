EDA For White Wines Dataset
================
Gaurav Negi
March 22, 2018

Univariate Plots Section
------------------------

Loading the Dataset for White wines:

Removing the serial number column as its not needed and adding rating column to divide quality into 3 categories and making quality a factor variable.

Printing the dimension of the dataset

    ## [1] 4898   14

Printing structure of the dataset

    ## 'data.frame':    4898 obs. of  14 variables:
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
    ##  $ qualityf            : Ord.factor w/ 7 levels "3"<"4"<"5"<"6"<..: 4 4 4 4 4 4 4 4 4 4 ...
    ##  $ rating              : Ord.factor w/ 3 levels "Bad"<"Average"<..: 2 2 2 2 2 2 2 2 2 2 ...

Summarising the data set

    ##  fixed.acidity    volatile.acidity  citric.acid     residual.sugar  
    ##  Min.   : 3.800   Min.   :0.0800   Min.   :0.0000   Min.   : 0.600  
    ##  1st Qu.: 6.300   1st Qu.:0.2100   1st Qu.:0.2700   1st Qu.: 1.700  
    ##  Median : 6.800   Median :0.2600   Median :0.3200   Median : 5.200  
    ##  Mean   : 6.855   Mean   :0.2782   Mean   :0.3342   Mean   : 6.391  
    ##  3rd Qu.: 7.300   3rd Qu.:0.3200   3rd Qu.:0.3900   3rd Qu.: 9.900  
    ##  Max.   :14.200   Max.   :1.1000   Max.   :1.6600   Max.   :65.800  
    ##                                                                     
    ##    chlorides       free.sulfur.dioxide total.sulfur.dioxide
    ##  Min.   :0.00900   Min.   :  2.00      Min.   :  9.0       
    ##  1st Qu.:0.03600   1st Qu.: 23.00      1st Qu.:108.0       
    ##  Median :0.04300   Median : 34.00      Median :134.0       
    ##  Mean   :0.04577   Mean   : 35.31      Mean   :138.4       
    ##  3rd Qu.:0.05000   3rd Qu.: 46.00      3rd Qu.:167.0       
    ##  Max.   :0.34600   Max.   :289.00      Max.   :440.0       
    ##                                                            
    ##     density             pH          sulphates         alcohol     
    ##  Min.   :0.9871   Min.   :2.720   Min.   :0.2200   Min.   : 8.00  
    ##  1st Qu.:0.9917   1st Qu.:3.090   1st Qu.:0.4100   1st Qu.: 9.50  
    ##  Median :0.9937   Median :3.180   Median :0.4700   Median :10.40  
    ##  Mean   :0.9940   Mean   :3.188   Mean   :0.4898   Mean   :10.51  
    ##  3rd Qu.:0.9961   3rd Qu.:3.280   3rd Qu.:0.5500   3rd Qu.:11.40  
    ##  Max.   :1.0390   Max.   :3.820   Max.   :1.0800   Max.   :14.20  
    ##                                                                   
    ##     quality      qualityf       rating    
    ##  Min.   :3.000   3:  20   Bad      : 183  
    ##  1st Qu.:5.000   4: 163   Average  :3655  
    ##  Median :6.000   5:1457   Excellent:1060  
    ##  Mean   :5.878   6:2198                   
    ##  3rd Qu.:6.000   7: 880                   
    ##  Max.   :9.000   8: 175                   
    ##                  9:   5

Lets Start By plotting Uni-variate Graphs for all variables :

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-5-1.png)

Data seems to be unbalanced as most of the wines are Average and we have very less percentage of Bad Quality wines i.e. only 183 out of 4898 observations. This could be a challenge for our predictive model

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-6-1.png)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   3.800   6.300   6.800   6.855   7.300  14.200

Fixed.acidity seems to display a normal distribution with very little variation between mean and median and most of the values lieng around median(6.8).

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-7-1.png)

The Volatile acidity value seems to dispaly a postively skewed distribution with many outliers but on removing outliers and taking log transformation it becomes normally distributed

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-8-1.png)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  0.0000  0.2700  0.3200  0.3342  0.3900  1.6600

Citric acid also has almost normal distribution with many outliers. After looking at citricacid summary , there are about 19 observations where Citric.acid is not present.This is unexpected as fermentation process produces citric.acid.

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-9-1.png)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   0.600   1.700   5.200   6.391   9.900  65.800

Residual.sugar has a positively skewed distribution with many outliers. After taking the log of residual.sugar , its showing Bimodal distribution with some very sweet wines.There is only 1 wine that is considered sweet in this dataset according to document dim(subset(ww, ww$residual.sugar &gt; 45))

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-10-1.png)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ## 0.00900 0.03600 0.04300 0.04577 0.05000 0.34600

Chlorides have a very large range i.e. 0.009 to 0.346. Thats mostly because of huge number of outliers. After removing outliers and adjusting the binwidth , it seems Chlorides have Bimodal distribution with many outliers at high range

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-11-1.png)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    2.00   23.00   34.00   35.31   46.00  289.00

I adjusted the graph for 95% of the data to remove some outliers and there seems to be multiple spikes(at 1 it looks like batman), although overall its a bimodal distribution.

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-12-1.png)

Being a superset of free.suplhor.dioxide, Its distribution is similar to that of free.sulphor.dioxide.

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-13-1.png)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  0.9871  0.9917  0.9937  0.9940  0.9961  1.0390

Density seems to have a normal distribution with tight ends, very less outliers

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-14-1.png)

pH seems to have a normal distribution and sulphates have bimodal distribution with outliers at high ranges

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-15-1.png)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    8.00    9.50   10.40   10.51   11.40   14.20

Alcohol has an abnormal distribution with about 3 peaks. The minimum alcohol content is 8% and it ranges from 8 to 14.20 %

Univariate Analysis
===================

### What is the structure of your dataset?

There are 11 variables representing physicochemical measurements and 1 variable representing the median of at least 3 evaluations of quality made by wine experts, varying from 0 (very bad) to 10 (very excellent).

### What is/are the main feature(s) of interest in your dataset?

Quality is the main feature of interest. The objective of the analysis is to determine the features that influence wine quality the most, and then building a predictive model of quality using these variables.

### What other features in the dataset do you think will help support your investigation into your feature(s) of interest?

I read that white wines are most acidic so probably acidity and residual sugar has to do with how sweat a wine is, so residual.sugar and acidity.

### Did you create any new variables from existing variables in the dataset?

I created the rating variable to categorize wines on 3 levels i.e. bad, average, and Excellent

### Of the features you investigated, were there any unusual distributions?Did you perform any operations on the data to tidy, adjust, or change the form of the data? If so, why did you do this?

The distribution of alcohol presented three unusual peaks which standed out of an otherwise normal distribution. I performed a log transformation and sqrrt transformations on some variables and adjusted their bin widths to provide better visualizations.

Bivariate Plots Section
=======================

Lets see the correlation behaviour between the features.

For better visualization I generated a correlation table in html format and added its image below :

![Correlation between all variables](C:\Users\Gaurav\Documents\R\R_Practice\R_Practice\whiteWinesCorr.png)

### Correlation matrix output shows following behaviour:

No single variable has strong corelation with quality variable, alcohol is the highest with positive 0.44 correlation.That means no single variable is influencing the quality by a significant difference, probably some combination of variables may influence the quality.On the other hand i see some variables with extremly high correlation.

Lets investigate further by plotting graph of variables with meaningful correlations:

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-17-1.png)

    ## 
    ##  Pearson's product-moment correlation
    ## 
    ## data:  ww$quality and ww$alcohol
    ## t = 33.858, df = 4896, p-value < 2.2e-16
    ## alternative hypothesis: true correlation is greater than 0
    ## 95 percent confidence interval:
    ##  0.4163317 1.0000000
    ## sample estimates:
    ##       cor 
    ## 0.4355747

There seems to be decrease in alcohol content from quality 3 to 5 and from 5 to 9 its increasing. Also the variance at highest quality wine i.e. 9 is the least. The one-tailed t test shows it has a significant difference at 95% confidence Interval

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-18-1.png)

    ## 
    ##  Pearson's product-moment correlation
    ## 
    ## data:  ww$density and ww$quality
    ## t = -22.581, df = 4896, p-value < 2.2e-16
    ## alternative hypothesis: true correlation is less than 0
    ## 95 percent confidence interval:
    ##  -1.0000000 -0.2856801
    ## sample estimates:
    ##        cor 
    ## -0.3071233

Density has a negative trend not very strong, with low variances with every quality measure. One -tailed t test, also shows significant difference at 95% confidence interval

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-19-1.png)

The variance is very high for all quality measures, and the correlation is also low for residual.sugar

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-20-1.png)

There is a negative i.e With increase in alcohol, density is decreasing with a strong correlation of -0.78. Its expected as density of alcohol tends to be lower than water

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-21-1.png)

As expected strong negative trend , as we know strong acids have lower pH.

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-22-1.png)

After plotting for 99% of data, we can see a very strong positive trend line. There is increase in residual sugar with small amount of density. Probably due to influence of alcohol with density also. Will Investigate in multivariate section.

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-23-1.png)

    ## 
    ##  Pearson's product-moment correlation
    ## 
    ## data:  ww$total.sulfur.dioxide and ww$free.sulfur.dioxide
    ## t = 54.645, df = 4896, p-value < 2.2e-16
    ## alternative hypothesis: true correlation is greater than 0
    ## 95 percent confidence interval:
    ##  0.6006859 1.0000000
    ## sample estimates:
    ##      cor 
    ## 0.615501

There is a positive trend with high correlation of 0.65. As the concentration of total.sulphor.dioxide increases the points are becoming more scattered that is increasing variance.

Bivariate Analysis:
===================

### Talk about some of the relationships you observed in this part of the investigation.

### How did the feature(s) of interest vary with other features in the dataset?

No single variable has a strong correlation with quality, the highest correlation with feature of interest i.e quality is with alcohol (0.44) and with density (-0.31).

### Did you observe any interesting relationships between the other features (not the main feature(s) of interest)?

The most interesting relationship i found is with density and residual.sugar and alcohol. After googling, I found that in the fermentation process yeast breaks down sugar into alcohol i.e the more sugar lesser alcohol or vice-versa.

pH and acidity also have strong correlation which is to be expected as the higher acids have lower pH

### What was the strongest relationship you found?

Positive relationship : residual.sugar ~ density &lt;- 0.84 Negative relationship : alcohol~density &lt;- -0.78

Multivariate Plots Section
==========================

![](white_wine_analysis_v4_files/figure-markdown_github/unnamed-chunk-24-1.png)

Multivariate Analysis'
======================

There is no clear influence on quality in case of (Fixed.acidity Vs pH) and (freeSO2 Vs TotalSO2). But for density Vs residual.sugar , higher quality wines seems to have low density and high sugar, I guess sweet wines are considered high quality. and if we keep sugar constant , higher density wines have bad quality.

Final Plots and Summary
=======================

### Plot One

![](white_wine_analysis_v4_files/figure-markdown_github/Plot_One-1.png)

Alcohol has played a role in determining wine quality. Experts prefer higher alcohol concentration in wines.

### Plot Two

![](white_wine_analysis_v4_files/figure-markdown_github/Plot_Two-1.png)

Density seems to be normal for bad to average wines but as the wine quality increases , a bimodal nature seeems to be emerging out, this is probably due some outliers or lurking variables as mentioned in document not all variables are present in the dataset. There is one Wine with highest density in dataset that also has highest residual.sugar and fairely average concentration of alcohol compared to other wines in dataset which was unexpected as both alcohol and residual.sugar are negatively correlated.

### Plot Three:

![](white_wine_analysis_v4_files/figure-markdown_github/Plot_Three-1.png)

It is clear from the plot that: at same level of residual.sugar, better wines have lower density and bad wines have tends to have high density.

Reflection'
===========

Our Dataset has 4898 observations, in which quality is out Dependent variable, our objective was to determine variables which influence the dependent variable using exploratory data analysis. I started my Exploratory Data Analysis by first exploring each variable i.e. Univariate Analysis, from which I explored many questions and observations and was able to answer some of them in initial phase. Then to answer futher and explore more questions I started exploring the influence of multiple independent variables togther on our dependent variable i.e. Quality.Due to the unbalanced data I was not able to create a meningful model which can predict the quality of wine given the other variables with less margin of error.Still I got many things from this analysis which are as follows:

1.  Better wines tends to have high concentration of alcohol.
2.  Good wines tends to have lower density, thats probably because of alcohol as alcohol decreases density.

Limitations of current analysis is that the provided dataset consist of samples from specific region i.e. from Portuguese and the dataset does not contains some of the crucial variables such as grapes or age of wine etc. IF we can get a bigger dataset from different regions of the world , I would like to construct a mathematical model to calculate the accuracy of quality.The best suited model for this case would be multinomial logistic regression , I tried using it on this case but did not found any meaningful observations.
