---
layout: post
title:  "Machine Learning in Optical Communications"
date:   2017-05-09
desc: "List of papers and brief introductions"
keywords: "optical communication, Machine learning"
categories: [Optics]
tags: [ideas,optics,ML]
icon: icon-apache
---

* Context
{: toc}
---

### ML for Optical Performance Monitoring from DD PDM-QAM Signals
- J.Wass et al DTU (D.Zibar Group)
- ECOC 2016
- supervised learning
    - SVM(formatt classifier) NN(OSNR prediction)
    - 94 % accuracy, OSNR estimation error of 0.65 dB
- experiment
- in band OSNR estimation and modulation format classification
    - up to 64 QAM using only intensity information
- avoid complete demodulation for mid-span monitoring points
- implementation:
    - matlab 2015b classfication toolbox + NN toolbox (one hidden layer of 3 neurons)
    - generate 8 features from power eyediagram
        - OSNR esitmator use 1 (minimum variance)
            - one NN trained for each combination of PS/mod format
        - MOD format classification use all
- result:
    - classifier:not good for 16 QAM and above when OSNR si below 11dB 
    - OSNR estimation: not good for OSNR above 17 dB 
    - features are hard to distinguish 
        - _should find better features_
- conclusion: achievable but definitely not good
        
###

<style>
.page-container {max-width: 1000px}
</style>
