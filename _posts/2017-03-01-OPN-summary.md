---
layout: post
title:  "OPN summary March 2017"
date:   2017-03-01
desc: "Interesting researches reported in OPN March 17"
keywords: "III-V integration on SOI"
categories: [Optics]
tags: [ideas,optics]
icon: icon-apache
---

* Context
{: toc}



## III-V-on-Silicon Integration

- Günther Roelkens group, Ghent University

![Twoapproaches][r1]

### wafer bonding
- lithography process rather than pick-and-place process determines the alignment of the fabricated laser with the silicon waveguides.
- Fabricaing the laser:
  - etching the laser mesa, 
  - including structures for coupling the light to the silicon waveguides,
  - passivation, 
  - defining n- and p-type metal contacts.
- require sufficient coupling:
  - thickness of the bonding layer is sufficiently small and well-controlled; 
  - the layer is sufficiently transparent; 
  - applied at a temperature low enough to avoid influencing the quality of the bonded III-V semiconductor material and creating excessive strain due to differential thermal expansion between the III-V and the silicon substrate.
- popular bonding agent 
  - oxide  
    - the bonded substrates to be strictly planar, and measures to allow H2O outgassing
  - benzocyclobutene (BCB), a polymer provided by Dow Corning (USA)
    - more tolerant to non-planar substrates, and can reliably deposit bonding layers as thin as 30 nm
    - lower thermal conductivity than silica
      - however, buried oxide layer of the silicon-on-insulator (SOI) wafer, tend to dominate the thermal impedance of the actual fabricated devices. 
- Laser examples:

![Lasers][r2]

### direct epitaxiy of III-V on silicon
- cost reductions and added flexibility in device design for high-volume applications
- higher mobility of III-V materials - next generation transistors
- lattice mismatch: 4 percent with GaAs and 8 percent with InP 
  - discolations
  - can use thicker buffer layers 
    - longer growth time - costs more
    - not compatible with other devices (SOI transitors and waveguides)
  - introducing QD layers into buffer zone
    - bending the so-called threading dislocations downward, so that most of them do not reach the active layers
    - QD can also be used as gain media
    - it doesn’t solve a more subtle problem arising from a different kind of material mismatch: the effort to grow a polar material, the III-V semiconductor, on a nonpolar substrate, silicon
      - With increasing growth time, the originally separated III-V islands have to merge, and that leads to the creation of so-called anti-phase boundaries (APB), which, like dislocations, can act as nonradiative defects.
      - To get around this mismatch and suppress the APBs has, thus far, required the use of special silicon substrates not used in the CMOS industry
- The method used by authors' group
  - the III-V material is grown in small trenches defined on a standard silicon wafer, covered with a high-quality silicon oxide layer. A wet chemical etch (for example, with potassium hydroxide) exposes the (111) crystal planes of the wafer, which are very efficient in suppressing undesired APBs, - while the sidewalls of the narrow, high-aspect-ratio trenches help stop detrimental dislocations from propagating further upwards
  - all defects are confined in a layer a few tens of nanometers thick near the silicon-InP interface, with no defects found in the bulk of the material
  - To get to a laser device, a grating that will form the optical cavity can be added via **e-beam litography**.
  - **optically pumped 22 mW threshold**
  - Directly depositing a metal on top of the InP-capping layer would result in excessive losses, so facilitating current injection will require different, innovative approaches.

### Comparison of two methds
- The use of quantum dot layers allows growth of lasers with thick cladding, which facilitates straightforward electrical injection
- it does not overcome the APB problem

- The V-groove method, will face challenges in electrical injection; 
- because the III-V materials are only grown in the trenches where the silicon is exposed, the method makes it straightforward to combine these lasers with other device


[r1]: https://www.osa-opn.org/opn/media/Images/Articles/2017/1703/Features/VanThourhout-infographic.jpg?width=1200
[r2]: https://www.osa-opn.org/opn/media/Images/Articles/2017/1703/Features/VanThourhout-img2.jpg?width=1200





<style>
.page-container {max-width: 1000px}
</style>
