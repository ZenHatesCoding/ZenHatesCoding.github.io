---
layout: post
title:  "OPN summary Nov 2017"
date:   2017-11-01
desc: "Interesting researches reported in OPN Nov 17"
keywords: "Thermal harvesting"
categories: [Optics]
tags: [ideas,optics]
icon: icon-apache
---

* Context
{: toc}

## Heat Is the New Light
- Generally heat is inherently broadband and incoherent, but in fact thermal radiation can be not only highly coherent, but can also exceed the limits imposed by Planck's law.
### Blackbody and real material
- Planck's law:

  $$B_{\lambda}(\lambda,T) = (2hc^2/\lambda^5)(e^{hc/(\lambda kBT)}-1)^{-1}$$ 

  - thermal-emission spectrum implies the temperature
  - for real materials (not completely "black"), a factor  **spectral emissivity** $\varepsilon(\lambda,T)$which reduce the spectral radiance shall be introduced
  - the law applies only when “the linear dimension of all parts considered, as well as radii of curvature of all surfaces, … are large compared with the wavelength of the ray considered.”
    - confinement of photons -> splitted energy states that can be occupied -> modify the dinsity of optical states at a given frequency. -> resonance 
-  The spectral radiance of **thermal wire and dots** at the frequencies of their internal optical resonances can exceed the blackbody limit
- Even away from the internal resonances, an emitter’s spectral radiance can be increased by immersing it into a lossless material with a high refractive index n, which serves as a passive heat extractor,increasing the emitted energy flux by a factor of $n^2$
- Arranging emitters into ordered arrays—forming gratings, photonic crystals, metasurfaces and metamaterials—allows still **further shaping of thermal-emission spectra**
- Far-field thermal emission from nanostructured metasurfaces or metamaterials with surface areas significantly larger than the wavelength of emitted photons can no longer exceed the blackbody limit imposed by Planck’s law.
### Minding the nanoscale gap
- If a thermal emitter is brought close to an absorber, the radiative heat current between them increases beyond the blackbody limit once the emitter–absorber gap becomes much smaller than the wavelength of the dominant radiation—a regime known as near-field radiative heat transfer (NFRHT)
  - gap too narrow -> non practical
  - hard to measure a few pW heat flow and maintain/control nm size gap at the sametime
  - basic experiment configurations have been reported
    - sphere-plate
    - tip-plate
    - plate-plate
### Incandescent lamps
- Incandescent emission spectra include a significant portion of IR photons that do not contribute to visible illumination but only to heating the environment.
- The spectrum of the thermal light from an incandescent emitter is more **uniform** that that of LED
- To recycle the "wasted" IR photons
  -  surround the light bulb with spectrally selective mirrors that allow only the visible part of the thermal-emission spectrum through and that reflect the longer-wavelength, IR part back to the bulb filament
### Heat-driven photovoltaics
- using terrestrial hot objects as the sources of photons that are converted to electricity by PV cells
  - industrial furnaces used for oil refining or steel and glass making
  - absorbers heated by concentrated sunlight (solar furnaces).
- the emission spectra of terrestrial thermal sources can be tailored via optical engineering 
- IR photons can be returned to the emitter to be re-absorbed, keeping it at an elevated temperature
- challenge in experiment
  - imperfect back-mirror reflection
  - parasitic sub-bandgap absorption
  - sideway radiation loss
- Thermally excited emission from PV cells themselves can be used to generate electrical energy -> **reverse solar cell” systems, or thermoradiative (TR) cells**
  - Heating of a PV cell by a terrestrial heat source, drives the cell out of equilibrium with the environment, which boosts its emission rate.
  - creates a potential difference of opposite polarity from that of a photo-excited solar cell, which can drive electric curren
  - currently only pW level generation demonstrated experimentaly
### Radiative Cooling
-  The terrestrial emitter’s surface needs to be engineered to show high emissivity only in the atmospheric window (**8-to-13-micron**), with high reflectance outside of that window, to avoid absorption of sunlight and thermal radiation from the atmosphere
- Solar stills
  - **Temperatures below ambient levels** constitute a pre-requisite for **dew formation**
  - solar distillation:  reducing thermal emission from the solar receiver used to heat and evaporate contaminated water will increase the still’s overall efficiency
- Self-cooling clothing
  - Exploiting the frequency-selective filtering of light and heat enabled by scattering on micron-to-sub-micron-scale obstacles
    - **obstacles**
      that minimize reflection and absorption of IR photons, while remaining reflective in the UV, visible and near-IR ranges
      - fibers in woven and knitted fabrics 
      - pores in porous non-woven materia





  

<style>
.page-container {max-width: 1000px}
</style>
