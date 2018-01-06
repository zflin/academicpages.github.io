---
title: 'R-package: Adaptive Rejection Sampling from Inverse-Gamma Distribution'
date: 2017-12-30
permalink: /posts/2017/12/arsIgamma/
tags:
  - cool posts
  - category1
  - category2
---

This is my first R-package called ``arsIgamma'', which was created for course STAT 605 (Statitical Computation). This package implements a ARS procedure for inverse-gamma distribution; it's also easy to be modified to sample from other log-concave distribution.

Inverse-gamma distribution is quite important in Bayesian Data Analysis: (1) it serves as a convenient conjugate prior; (2) it has heavier tail than Normal distribution. Adaptive Rejection Sampling is a highly efficient technique for sampling from log-concave distribution. Inverse-gamma distribution is one of log-convave distribution.

This package is implemented via Rcpp and it's super fast to do sampling.

[Download R-package `arsIgamma_1.1.tar.gz'](http://zflin.github.io/files/arsIgamma_1.1.tar.gz)

```{R}
## an example how to use the package

library(arsIgamma)

set.seed(20171230)
N = 1000
ss = 2 ## sum of square
n = 10
d2 = 1 ## square of d
Sk = exp(seq(-5, 5, length.out = 12)) ## x_0, ... x_k+1

## two parameters of inverse-gamma distribution
alpha = (n + 1/d2)/2 ## shape
beta = ss/2 ## scale

y = rpostgamma(Sk, N, ss, n, d2)

y0 = 1/rgamma(N,alpha, beta)

ks.test(y, y0)
# 	Two-sample Kolmogorov-Smirnov test
# 
# data:  y and y0
# D = 0.065, p-value = 0.02925
# alternative hypothesis: two-sided

par(mfrow=c(2,1))
hist(y, 20, xlab="1000 samples", main="arsIgamma")
hist(y0, 20, xlab="1000 samples", main="1/rgamma")
par(mfrow=c(1,1))
```

![](http://zflin.github.io/files/arsIgamma.pdf)

