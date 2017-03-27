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
# Si Photonics
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
        - DSA: defect state absorption
    - same contact pads for both heating and photocurrent measurements
    - tunning Ring 1 to 4 sequentially to maximize the photocurrent in each ring's IRPH
    - maximum search algorithm used to account for detuning of previous tuned ring due to thermal crosstalk
    - calibration required to substract the heater current from I_total in order to obtain photocurrent
    - can be used to estimate the heater power required to tune each ring -> reduce time required
- coupling coefficients not tuned
- can be used as temperature stabilization method
- 40 degree celcius range
- IME A*STAR

### List of ideas
- **Tu2I.3** Dual-COre Polarization diverse SiPh Add/Drop switch - 400G PDM+16QAM
    - Huawei Canada
    - X output of PSR connects to Y input of PRC to self-compensate for PDL and DGD in PSR PRC and FSC(fiber spacing concentrater)
- **Tu2I.4** Full C band Nyquist-WDM interleaver
    - Monash
    - See their OE-16 paper for details
    - RAMZI, sub GHz resolution, flat top
        - _comparing to cascaded ring ?_

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


# Direct Dection
## IMDD general
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

## IMDD + SSB
### Tu2D.5 Nonlinear Equalizaer for 112-Gb SSB-PAM4 in 80 km CD uncompensated link
- Bell Labs - Noriaki Kaneda
- IMDD + SSB + PD 
    -  SSBN -> NL equalizer
- Diff-drive MZM (30 GHz) -> SSB+Carrier generation
- ADC -> Resample to 2 sps -> Clk recovery -> LMS-DD + NL eq.
    - limit nonlinear terms to self-squared terms
    - blindly adapted with no use of training symbols
        - guide the convergence - first use amplitude directed blind eq simular to CMA
        - then switch to  **LMS-DD**
            - Decision directed gradient decent algorithm with LMS error function 
    - can be implemented in Freq domain
        - scales well if disp is high and # of linear and NL terms increase 
    - an order of magnitude better in terms of BER comparing to Linear Eq only
    - 96 taps for Linear part, 48 taps 

### Tu3I.2 4x200 Gbs Twin-SSB Nyquist SCM WDM Transmission over 160 km SSMF with DD
- Peking University, Yixiao Zhu
- require OBPF(optical bandpass filter) at rx side
- require 2 x hilbert transform at tx side to achieve twin ssb (for both LSB and RSB)
- Rx side DSP
    - Resampling
    - SSBI cancellation
        - use hilbert transform to estimate ssbi then substract the estimation from the signal
        - require iterations
    - down convert to baseband 
    - RRC matched filter
    - synchornization 
    - Time-Domain equalization
        - Ts/4 spaced training sequence
        - recursive least square (RLS) algorithm
    - Downsampling to 1 sps
    - DD RLS
    - post filter + MLSD
        - 2 tap post filter
        - to compensate for the equalization-enhanced in-band noise
        

# Coherent Detection
## Probability Shaping
### M3C.1 Spectrally-Efficient Single-Carrier 400G Transmission with PS
- Yanjun Zhu -Futurewei Tech, Santa Clara, USA
- 












<style>
.page-container {max-width: 1000px}
</style>
