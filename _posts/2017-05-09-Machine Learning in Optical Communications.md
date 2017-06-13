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


# Implementing ML (ANN) 
## ONN
### Deep learning with coherent nanophotonic circuits
- MIT Yichen Shen, Marin Soljačić
- Nature Photonics  2017
- General
    - input signal, parallel pulses
    - training done off-line (using CPU), a novel way of implementing forward propagation
    - ALso enables a new training method: instead of backpropagation, using 2 forward propagations to estimate the gradients
    - resetting parameters (trainning) consumes power, **the selling point** is: except for the power consumed by thermal heater, Ideally forward propagation should be passive - new phase shifting materials required
    - **OPSIS foundary**
    - limits:
        - #MZI not enough - one path only achieve U x Sigma, cannot do full SVD
            - the chip was designed for quantum optics
            - iteration required
        - activation func simulated using CPU - not applying real saturable absorber
        - space required is way larger than electric circuits
        - Sigma achieved using attenuators - IL large - scalability may be limited
        - mentioned in their paper:
            - thermal crosstalk between phase shifters in interferometers, 
            - optical coupling drift
            - the finite precision with which an optical phase canbe set (16 bits)
            - photodetection noise and 
            - finite photodetection dynamic range (30 dB)
- Dealing with Matrix Multiplication
    - SVD: M = U x Sigma x V*; U, V are unitary
    - Using cascaded MZI to achieve U,V
        - 56 MZI used
        - thermal tuning required
            - internal phase - splitting ratio
            - external phase - output phase relation
            - ~10 mW per phase modulator
        - MZI: 
            - 0.5[ [ exp(i*phi)(exp(i*theta-1), iexp(i*phi)(exp(i*theta)+1) ];
                 [ i(1+exp(i*theta)), 1-exp(i*theta) ] ] 
                 is unitary
            - has 2 parameters: theta and phi
            - Unitary Matrix (2x2)
                -[ [ a,b]; [-exp(i*theta)b*,  exp(i*theta)*a*]]
                - |a|^2 + |b|^2 = 1, a, b \in Complex
                - requires 4 parameters: phase of a and b, theta, ratio of |a| and |b|
            - More then 1 MZI is required to achieve a unitary matrix
            - rank N unitary matrix can be decomposed into sets of SU(2) rotations - [__Reck propsal__][r1]
    - Sigma
        - attenuator
            - each output connected to an MZI
            - using MZI to rotate the light to untracked mode
            - Sigma_ii = sin(theta/2)





[r1]:(https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.73.58)

<style>
.page-container {max-width: 1000px}
</style>
