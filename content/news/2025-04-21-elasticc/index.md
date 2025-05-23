---
title: Preparing machine learning classifiers for Rubin
date: 2025-04-21
cardimage: ml_classifiers.png
---

Given the huge amount of data expected from Rubin and the small time window available to analyse it, Machine Learning (ML) methods are the best way to go. 
<!--more-->


Fink is already classifying ZTF data using ML models with great results. While LSST is not here yet, we need to prepare for its arrival, having models ready already for the beginning of operations. Fink used a simulated dataset called ELAsTiCC, composed of more than 50 million alerts, to train ML models suitable for classifying alerts coming from LSST. These include two models adapted from ZTF (one to catch supernovae type Ia early, the other for super luminous supernovae), one general purpose light curve classifier called SuperNNova, and a deep learning multi class model designed specifically to work with LSST alerts, the CBPF alert transient search (CATS). 

<img src="images/fink-portal-cats.png" width="70%" height="700%" style="display: block; margin: auto;" />

All of them had good performances with the simulated alerts, and were able to correctly classify alerts within a few days of the detection. Furthermore, infrastructure tests showed that Fink was able to process all classifiers quickly, a strict requirement to work with LSST data.

The paper describing all results in detail can be found in [Fraga et al., 2024](https://ui.adsabs.harvard.edu/abs/2024A%26A...692A.208F/abstract).

*Text by Bernardo Fraga*

