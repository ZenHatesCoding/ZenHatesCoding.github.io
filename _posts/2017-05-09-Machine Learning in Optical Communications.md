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
# Big Picture
- from JLT - 17 (Journal of D.Zibar's ECOC 16)
- Applications:
    - NL state-space based Bayesian filtering (extended Kalman and particle filter)
        - for amplitude/phase noise, cross-pol and XPM induced prolarization scattering, PMD
        - time variying parameters estimation
    - system performance monitoring
        - NN, K means, variational Bayesian methods, independent and principal component analysis
        - signal demod, modulation format and bit rate identification
    - channel parameters estimations:
        - CD, differential group delay, Baud rate, OSNR
    - optimum classification
        - optimum symbol detection - euclidean distance metric no longer optimum
        - SVM, kernal density estimator and Gaussian mixture models
    - NL mitigation
        - factor graphs, message passing algorithm
        - include noise in DBP


## Performance Monitering
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

## Optimum Classification - Decision Boundaries        
### NL Decision Boundary Created by a ML based Classifier to Mitigate NL Phase Noise (NLPN)
- D.Wang, Beijing U of Posts and Telecomm.
- ECOC 2015
- **SVM** - NL DBound in M-ary PSK 
- numerical result
    - neglecting CD and multichannel effects
- for 8-PSK comparing with MLSE
    - Maximum transmission distance improved by 480 km
    - LPDR (launched power dynamic range) tolerance improved by 3.3 dBm 
    - 1.2 dBM for QPSK ,not significant for BPSK
- no prior information required, properties captured from training data
- multiclass classifier - only log2(M) SVMs need for M-classes problem (each SVM is a binary classifier in this paper)
- extensible to higher order QAM, performs better for higher order formats

### NL mitigation Using a ML Detector Based on K-Nearest Neighbors (KNN)
- D.Wang BUPO
- PTL 2016
- KNN - non-parameteric 
    - multiclass - comparing with SVM
    - independent of link information - comparing with expectation maximum (EM)
    - free of training process - comparing with ANN
    - based on training data only but not any parameters learned from training process 
        - can be detected directly
        - no need to finishe the training process
    - distance weighted KNN
        - inverse square of distance is set as weight coefficient
- simulation only
    - laser phase noise: random walk Wiener process
    - 25 GBaud 16QAM
    - ZDL, DML, DUL 
        - DML: 80 km SSMF + 17 DCF
        - EDFA: NF = 6dB after each span
    - Gaussian filter of 28 GHz BW to reduce ASE noise  
    - 1000 symbols for training data (2 sample/symbol at RX), KNN compute 1000x2 distances
- result: 16 QAM compared with Maximum Liklihood-post compensation (ML-PC) 
    - B2B
        - when ASE dominant, MLPC is good enough
        - IQ implance - phase differnce not 90 deg, MLPC still good, so is KNN
        - IQ + lase PN: KNN increase the linewidth tolerance by 180 kHz
    - improve the NL tolerance by 1.7, 1.0 and 0.4 dBm for ZDL, DML and DUL
        - KNN works better for non- circularly symmetric Gaussian-like noise mitigation
        - in DML, phase noise is larger than that of amplitude noise
- distortions of transmission systems:
    - ASE - linear
    - laser phase noise from tx and LO
    - NL pahse noise (NLPN) - interaction between signal and ASE via Kerr effect  
- comment: useless
  
<style>
.page-container {max-width: 1000px}
</style>
