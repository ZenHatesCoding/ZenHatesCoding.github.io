---
layout: post
title:  "OPN summary Jan 2017"
date:   2017-01-04
desc: "Interesting researches reported in OPN Jan 17"
keywords: "Meta-Optics,On-chip OCT,Freq-comb"
categories: [Optics]
tags: [ideas,optics]
icon: icon-html
---

* Context
{: toc}



## Meta-Optics with Mie resonance
![image](http://www.osa-opn.org/opn/media/Images/Articles/2017/1701/Features/Kivshar-img2.jpg?width=1200)

- simultaneously excite strong electric and magnetic dipole and multipole modes—and, in turn, to exploit constructive or destructive interferences—allows for unusual beam-shaping and the resonant enhancement of magnetic fields in dielectric nanoparticles
- enhance nonlinear optical phenomena, control radiation angle of higher order harmonics
- advantage of dielectric metasurface comparing to plasmonics
  - lower loss
  - allowing the imprinting of different types of phase patterns by using two types of dipole resonances (or, more generally, two types of multipoles). Specifically, each dipole resonance shifts the phase of the propagating wave from 0 to π near the resonance, so that two dipoles at the same wavelength and location may cover the whole 0-to-2π phase range.
- meta material are almost homogeneous, whose feature sizes are way smaller than the wavelength, which differs it from photonic crystals.
  - application: zero reflection
  - mostly still narrow band

![image2](http://www.osa-opn.org/opn/media/Images/Articles/2017/1701/Features/Kivshar-img3.jpg?width=1200)

- Constructive interference of MD and ED -- zero backward scattering
- Desctructive interference of MD and ED -- zero forward scattering
- cancellation of the radiation patterns of ED and TD moments -- virtually nonradiating anapole mode


## Marco-Scale on-chip OCT
![image3](http://www.osa-opn.org/opn/media/Images/Homepage/Newsroom/1216/News-Dec22-icon.jpg?width=1200)

- [James Fujimoto, Massachusetts Institute of Technology](https://www.osapublishing.org/optica/abstract.cfm?uri=optica-3-12-1496)
- combining a tunable vertical cavity surface-emitting laser (__VCSEL__) with MEMS technology—thus creating an optically pumped MEMS-tunable VCSEL centered at __1310 nm__. 
- The receiver—a single-chip PIC __in-phase and quadrature receiver__—integrates waveguides, polarization splitting elements, 90-degree phase shifters and waveguide couplers, to increase the imaging range by two orders of magnitude at a given acquisition bandwidth. 
- axial resolution 15 um.


## Electron-Photon Dialogue in Si
![image4](http://www.osa-opn.org/opn/media/Images/Homepage/Newsroom/1216/News-Dec23-icon.jpg?width=1200)

- [Jason Petta, Princeton University](http://science.sciencemag.org/content/early/2016/12/21/science.aal2469)
- passing information from one QD-based quantum bit, or qubit, to another in a silicon-based quantum circuit, using photons has proved a hurdle.
  - fluctuations in the occupation of available quantum states in the semiconductor that can perturb the local electric field and get in the way of strong electron-photon coupling
- Double Quantum Dots
  -  double QD in the heterostructure that could capture individual electrons in a tightly defined potential well 
  -  The AL electrodes had another virtue: they formed an electromagnetic shield to protect the double QD-qubit, bringing about a several-orders-of-magnitude reduction in charge noise from the surrounding semiconductor.
- A tiny, half-wavelength niobium superconducting cavity to trap microwave photons.
- using current in the aluminum electrodes to tune the energy level of the electron to match that of the photon, they were able to achieve strong electron-photon coupling
- observing a key indicator of such coupling, __vacuum Rabi splitting__ (the emergence of two resolvable normal modes in the cavity transmission spectrum, separated by the vacuum Rabi frequency)

## Dual Freq-Comb spectroscopy

michelson-type|dual-comb-type
---|---
![michelson][r1]|![dualcomb][r2]


time domain|Freq domain
---|---
![time][r3]|![Freq][r4]

[r1]: http://www.osa-opn.org/opn/media/Images/Articles/2017/1701/Features/Ideguchi-side1.png?width=1200

[r2]: http://www.osa-opn.org/opn/media/Images/Articles/2017/1701/Features/Ideguchi-side2.png?width=1200

[r3]: http://www.osa-opn.org/opn/media/Images/Articles/2017/1701/Features/Ideguchi-img3.jpg?width=1200

[r4]: http://www.osa-opn.org/opn/media/Images/Articles/2017/1701/Features/Ideguchi-img3.jpg?width=1200

- An optical frequency comb is a spectrum consisting of hundreds of __thousands or millions of__ equally spaced, sharp lines—analogous to having a great many continuous-wave (CW) lasers simultaneously emitting at different, __equally__ spaced frequencies. 
- Different implementations of frequency comb
  - phase-stabilized, mode-locked ultrashort-pulse laser
  - cascaded four-wave mixing (FWM) in microcavities, to generate, through the nonlinear Kerr effect, a so-called microcomb or Kerr comb 
    - CMOS compatible
  - electro-optic modulator (EOM) comb, operates by combining intensity modulations of a single CW laser with two EOMs, inserted in branched optical paths, to generate mutually coherent dual combs. 
    - The common-mode noise cancellation guarantees a comb-resolved resolution without the need for active stabilization.	
- Practical difficulties - 2 mutually coherent freq-comb
  - real-time phase error correlation instead of phase-locking system?
  - single-laser dual-comb gernation? 
  

<style>
.page-container {max-width: 1000px}
</style>
