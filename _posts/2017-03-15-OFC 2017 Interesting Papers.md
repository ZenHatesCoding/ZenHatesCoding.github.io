---
layout: post
title:  "OFC 2017 Digest"
date:   2017-03-15
desc: "List of papers and brief introductions"
keywords: "OFC, conference digest"
categories: [Optics]
tags: [ideas,optics,conference]
icon: icon-apache
---

* Context
{: toc}

---

## Si-Ph Modulators
### Tu2H.1 High speed Silicon modulators
- Wuhan Research Institute of Post & Telecom
- EO bw over 70 GHz [1,2],sub-volt driving voltage [3] has been achieved
    - heterogeneous materials
- Silicon hard to achieve high speed modulation
    - low carrier mobility and modulation efficiency   
- 90 GBd Intensity Modulator
    - compromise between speed, IL and driving voltage
    - limited by intrinsic RC bandwidth and the modulation efficiency of the doping profile
    - interleaved PN junction 
        - improve the modulation efficiency 
        - improve the tolerance of the junction's dislocation
    - zig-zag PN junction
        - reduce capacitance of the junction
        - RC bw 50 GHz achieved
    - TWE
        - group velocity matching
    - Doping profile design
        - optimized for the IL
    - Utilizing Electrical gain peaking effects in a GSG
        - 70 Gbps MZM
    - novel substrate removed GS electrode
        - EO bw imp0roved to 55 GHz
        - trade off between EE bw and impedance matching
        - 7V Vpp
        - 15.7 dB ER
        - 9 ps on-off time
    
- 100 G CWDM4 Transmitter
    - O band
    - MZM 2.5 V Vpp
    - MUZ based on cascaded - MZI filter
    - total IL 9 dB
        - modulator on chip loss 4dB
        - MUX loss 1 dB
    - BER-free sensitivity -7.5dB -- ER 4.8 dB
    - CLR4 agreement ??
- IQ MOD 
    - 7V Vpp
    - 28 GBd QPSK 
    - 3 independent DC bias + 2 RF inputs
        - compensate for intensity imbalance
    - -> Freq comb generator

## SiPh Devices

### Tu2C.1 Reconfigurable Add-Drop Mux for MDM-WDM system
- Daoxin Dai
- MDM Mux + Rings (thermal)
- Ebeam

### Th1G.4 Automatic Tuning and Temp stabilization of High-order Si Vernier MRR filters
- Lukas
- in-resonator photoconductive heaters(IRPH)
    - n doped Si wg as PD
    - same contact pads for both heating and photocurrent measurements
    - No need for PD 
- IME A*STAR

## Packaging

### Tu3K.1 IME suspended Edge coupler
- IME
- 193 nm litho, MPW, Active process
    - 100 nm tip
    - SSC (suspended spotsize converter used) [3]
- TE -0.95 dB TM -1.3 dB
- 0.4 dB uniformity
- cleaved SMF 
- matching oil required for packaging
- future work
    - V groove + SSC for multichannel packaging

## Direct Dection

### Tu3I.3 DD solutions for 100G and beyond
- ADVA Optical Networking Germany, DTU Denmark
- IEEE 802.3bs 
    - PAM-4 + DD for 400 Gbps up to 10 km
    - single 400G channel is sufficient
    - 400 G - 8x25GBd PAM-4
    - CD -> 1272.5 to 1310.2 nm
        - 1 ps/nm.km for 1300 nm window
        - 20 ps/nm.km for 1550 nm window
    - allowed span loss **6 dB** -> amplification
    
    
- ITU-T SG15 (working)
    - DP-QPSK 100Gbps up to 250 km
- targeting at 80 km
    - CD compensating fiber/grating will introduce loss
    - DSP
        - PAM 4
            - 50 Gbps PAM-4 tolerable CD - **100 ps/nm**- 5-6 km SSMF
            - Equalize PAM-4 directly (feed forward and decision feedback equalization FFE-DFE) 
                - compensate for some CD, limited because of DD
                - 100 G 5 km
            - channel shorten filter (CSF) + MLSE
                - CSF shapes received signal to yield a remaining but pre-determined amount of ISI
                - 100 G PAM-4 80 km 
            - Precompensation  
                - 100 G 80 km 
            - SSB 
                - optical filter suppressing one side band
                - 74.67 Gb/s 20 km SSMF
            - Precompensation and SSB require DSP and 2 drive signal
                - *SSB 2 drive?* 
                    - *RF mixer*
                    - *IM + filter*
        - DMT
            - Proposed for IEEE 802.3bs 
            - 50 or 100 Gbs per wavelength
            - power fading for sub-carriers - mainly DSB
            - SSB 80 km 80 Gbps
                - +subcarrier interference cancellation
            - VSB vestigiakl side band
                - 20 GHz shift for 50 GHz channel grid multiplexer
                - part of second side band maintained
                - CD tolerance improved
                - increase channel bw
                - non-linear mixing between subcarriers ?
                    - non0linear **Volterra equalization** as a compensation algorithm [15 - ECOC2015] 
                    - 110 Gbps 100 km VSB-DMT


##











<style>
.page-container {max-width: 1000px}
</style>
