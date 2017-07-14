# Labs.md

## Lab 1: Getting Started

- How to start R (Rstudio)
- Discussion of the various UI elements
- Load some data
- See what the variables in the data are (brief summary?)
- How many cases in the data
- Generate frequency tables
- Generate histograms
- Generate numerical summaries (mean, median, ...)
- How to save your work as rmarkdown (maybe lab 2?)

## Lab 2: Analyzing single quantitative variable

- (President's data)
- Loading comma-separated/Excel file
- How to edit the data in R?
- Answering various "case questions" in R
- More with summary (5-num summary)
- Control histogram parameters (bins, anchor)
- Extract information, especially outliers

## Lab 3: More with plots (bargraph, boxplot, dotplot)

- Review frequency tables
- Create bargraph that includes empty categories. `ggplot(pres2, aes(gender,fill=gender)) + geom_bar() + scale_x_discrete(drop=FALSE) + scale_fill_discrete(drop=FALSE)`
- Interpreting boxplots. `ggplot(pres2, aes(party, inauguration)) + geom_boxplot()`
- Comparing dotplot and boxplot `ggplot(pres2, aes(party, inauguration)) + geom_points()`
- Inappropriateness of outlier test

## Lab 4:

- Setting value labels: `d$gender<-factor(d$gender, labels=c("Male", "Female"))`
- Computing new variables
- Subsetting the data
- 2-variable questions via boxplots
- Discussion of different kinds of variables (scalar, character, factor, ordered, logical)
- Practice reading histograms
- normal quantile plots

## Lab 5: Binomial Monte Carlo simulation

```
flipCoin = function(n = 6, p=0.5, reps = 10000) {
    heads <-
        replicate(reps,
            sum(
                sample(0:1, n, replace=TRUE, prob=c(1-p, p))
            )
        )

    hist(heads, breaks=(-1:n) + 0.5, freq=FALSE)
    curve(dnorm(x, n*p, sqrt(n*p*(1-p))), -1, n+1, add=TRUE)
}
flipCoin(n=10)
flipCoin(p=0.2)
flipCoin(reps=10000)
```

## Lab 6: Scatterplots, correlation

- making a scatterplot
- interpret a scatterplot
- calculate and interpret correlation coefficient
- regression lines
- interpret r^2
- effect of outliers on correlation and regression

## Lab 7: Residuals, regression equation

- Generating and plotting regression lines
- Assessing the model
- Using the equation to make predictions
- Interpret slope, intercept
- Generate residual plot
- (maybe add whiteside data, effect of lurking variables)

## Lab 8: Sampling distributions

- Using onlinestatbook

```
computeSampling = function(population, sampleSize, reps) {
    means = replicate(reps, mean(sample(population, sampleSize)))
    hist(means, breaks = 100, freq=FALSE)
    expMean = mean(population)
    expSd = sd(population) / sqrt(sampleSize)
    curve(dnorm(x, expMean, expSd), expMean-4*expSd, expMean+4*expSd, add=TRUE, col="red")
    cat("expected mean:", expMean, "\n")
    cat("actual mean:", mean(means), "\n")
    cat("expected stdev:", expSd, "\n")
    cat("actual stdev:", sd(means), "\n")
}
```

## Lab 9: Confidence interval for proportion, with small sample size

## Lab 10: t-tests, t-intervals

## Lab 11: Project data

