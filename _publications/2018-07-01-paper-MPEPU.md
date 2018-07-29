---
title: "A Flexible Procedure for Mixture Proportion Estimation in Positive--Unlabeled Learning"
collection: publications
permalink: /publication/2018-07-01-paper-MPEPU
submitted: "to EJS"
---

arxiv: https://arxiv.org/abs/1801.09834

Positive--unlabeled (PU) learning considers two samples, a positive set P with observations from only
one class and an unlabeled set U with observations from two classes. The goal is to classify observations
in U. Class mixture proportion estimation (MPE) in U is a key step in PU learning. Blanchard et al.
[2010] showed that MPE in PU learning is a generalization of the problem of estimating the proportion of
true null hypotheses in multiple testing problems. Motivated by this idea, we propose reducing the problem
to one dimension via construction of a probabilistic classifier trained on the P and U data sets followed
by application of a one--dimensional mixture proportion method from the multiple testing literature to the
observation class probabilities. The flexibility of this framework lies in the freedom to choose the classifier
and the one{dimensional MPE method. We prove consistency of two mixture proportion estimators using
bounds from empirical process theory, develop tuning parameter free implementations, and demonstrate that
they have competitive performance on simulated waveform data and a protein signaling problem.


